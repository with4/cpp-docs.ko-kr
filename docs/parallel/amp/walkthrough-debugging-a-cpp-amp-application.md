---
title: '연습: c + + AMP 응용 프로그램을 디버깅 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1bf80276b5434804651bcc4507397e9479f6e494
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463094"
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>연습: C++ AMP 응용 프로그램 디버깅
이 항목에는 처리 GPU (그래픽 장치)를 활용 하기 위해 c + + Accelerated Massive Parallelism (c + + AMP)를 사용 하는 응용 프로그램을 디버깅 하는 방법을 보여 줍니다. 큰 정수 배열의을 요약 하는 병렬 감소 프로그램을 사용 합니다. 이 연습에서는 다음 작업을 수행합니다.  
  
-   GPU 디버거를 시작 합니다.  
  
-   GPU 스레드 창에 GPU 스레드를 검사합니다.  
  
-   병렬 스택 창의 사용 하 여 동시에 여러 GPU 스레드의 호출 스택을 것을 볼 수 있습니다.  
  
-   병렬 조사식 창을 사용 하 여 동시에 여러 스레드에 대해 단일 식의 값을 검사 합니다.  
  
-   플래그 설정, 재개, 중지 및 GPU 스레드를 그룹화 합니다.  
  
-   코드에서 특정 위치에 조각의 모든 스레드를 실행 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습 시작 하기 전에:  
  
-   읽기 [c + + AMP 개요](../../parallel/amp/cpp-amp-overview.md)합니다.  
  
-   확인 해당 줄 번호는 텍스트 편집기에 표시 됩니다. 자세한 내용은 참조 [하는 방법: 편집기에서 줄 번호 표시](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor)합니다.  
  
-   실행 되 고 있는지 확인 [!INCLUDE[win8](../../build/reference/includes/win8_md.md)] 또는 [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] 소프트웨어 에뮬레이터에서 디버깅을 지원할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### <a name="to-create-the-sample-project"></a>샘플 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  아래 **설치 됨** 템플릿 창에서 선택 **Visual c + +** 합니다.  
  
4.  선택 **Win32 콘솔 응용 프로그램**, 형식 `AMPMapReduce` 에 **이름** 상자를 선택한 후는 **확인** 단추입니다.  
  
5.  **다음** 단추를 선택합니다.  
  
6.  지우기는 **미리 컴파일된 헤더** 확인란을 선택한 후는 **마침** 단추입니다.  
  
7.  **솔루션 탐색기**, stdafx.h, targetver.h, 및 stdafx.cpp 프로젝트에서 삭제 합니다.  
  
8.  AMPMapReduce.cpp 열고 해당 내용을 다음 코드로 바꿉니다.  
  
 ```cpp  
    // AMPMapReduce.cpp defines the entry point for the program.  
    // The program performs a parallel-sum reduction that computes the sum of an array of integers.   
  
    #include <stdio.h>  
    #include <tchar.h>  
    #include <amp.h>  
  
    const int BLOCK_DIM = 32;  
  
    using namespace concurrency;  
  
    void sum_kernel_tiled(tiled_index<BLOCK_DIM> t_idx, array<int, 1> &A, int stride_size) restrict(amp)  
    {  
        tile_static int localA[BLOCK_DIM];  
  
        index<1> globalIdx = t_idx.global * stride_size;  
        index<1> localIdx = t_idx.local;  
  
        localA[localIdx[0]] =  A[globalIdx];  
  
        t_idx.barrier.wait();  
  
        // Aggregate all elements in one tile into the first element.  
        for (int i = BLOCK_DIM / 2; i > 0; i /= 2)   
        {  
            if (localIdx[0] < i)   
            {  
  
                localA[localIdx[0]] += localA[localIdx[0] + i];  
            }  
  
            t_idx.barrier.wait();  
        }  
  
        if (localIdx[0] == 0)  
        {  
            A[globalIdx] = localA[0];  
        }  
    }  
  
    int size_after_padding(int n)  
    {  
        // The extent might have to be slightly bigger than num_stride to   
        // be evenly divisible by BLOCK_DIM. You can do this by padding with zeros.  
        // The calculation to do this is BLOCK_DIM * ceil(n / BLOCK_DIM)  
        return ((n - 1) / BLOCK_DIM + 1) * BLOCK_DIM;  
    }  
  
    int reduction_sum_gpu_kernel(array<int, 1> input)   
    {  
        int len = input.extent[0];  
  
        //Tree-based reduction control that uses the CPU.  
        for (int stride_size = 1; stride_size < len; stride_size *= BLOCK_DIM)   
        {  
            // Number of useful values in the array, given the current  
            // stride size.  
            int num_strides = len / stride_size;    
  
            extent<1> e(size_after_padding(num_strides));  
  
            // The sum kernel that uses the GPU.  
            parallel_for_each(extent<1>(e).tile<BLOCK_DIM>(), [&input, stride_size] (tiled_index<BLOCK_DIM> idx) restrict(amp)  
            {  
                sum_kernel_tiled(idx, input, stride_size);  
            });  
        }  
  
        array_view<int, 1> output = input.section(extent<1>(1));  
        return output[0];  
    }  
  
    int cpu_sum(const std::vector<int> &arr) {  
        int sum = 0;  
        for (size_t i = 0; i < arr.size(); i++) {  
            sum += arr[i];  
        }  
        return sum;  
    }  
  
    std::vector<int> rand_vector(unsigned int size) {  
        srand(2011);  
  
        std::vector<int> vec(size);  
        for (size_t i = 0; i < size; i++) {  
            vec[i] = rand();  
        }  
        return vec;  
    }  
  
    array<int, 1> vector_to_array(const std::vector<int> &vec) {  
        array<int, 1> arr(vec.size());  
        copy(vec.begin(), vec.end(), arr);  
        return arr;  
    }  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
        std::vector<int> vec = rand_vector(10000);  
        array<int, 1> arr = vector_to_array(vec);  
  
        int expected = cpu_sum(vec);  
        int actual = reduction_sum_gpu_kernel(arr);  
  
        bool passed = (expected == actual);  
        if (!passed) {  
            printf("Actual (GPU): %d, Expected (CPU): %d", actual, expected);  
        }  
        printf("sum: %s\n", passed  "Passed!" : "Failed!");   
  
        getchar();  
  
        return 0;  
    }  
  
 ```  
  
9. 메뉴 모음에서 **파일**, **모두 저장**을 차례로 선택합니다.  
  
10. **솔루션 탐색기**, 바로 가기 메뉴를 열고 **AMPMapReduce**를 선택한 후 **속성**합니다.  
  
11. 에 **속성 페이지** 대화 상자의 **구성 속성**, 선택 **C/c + +**, **미리 컴파일된 헤더**합니다.  
  
12. 에 대 한는 **미리 컴파일된 헤더** 속성을 선택 **미리 컴파일된 헤더 사용 안 함**를 선택한 후는 **확인** 단추입니다.  
  
13. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
## <a name="debugging-the-cpu-code"></a>CPU 코드 디버깅  
 이 절차에서는이 응용 프로그램의 CPU 코드 정확한 지 확인 하는 로컬 Windows 디버거를 사용 합니다. 특히 흥미로운이 응용 프로그램의 CPU 코드 세그먼트는는 `for` 루프는 `reduction_sum_gpu_kernel` 함수입니다. GPU에서 실행 되는 트리 기반 병렬 감소를 제어 합니다.  
  
### <a name="to-debug-the-cpu-code"></a>CPU 코드를 디버깅 하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **AMPMapReduce**를 선택한 후 **속성**합니다.  
  
2.  에 **속성 페이지** 대화 상자의 **구성 속성**, 선택 **디버깅**합니다. 확인 **로컬 Windows 디버거** 에서 선택한는 **실행할 디버거** 목록입니다.  
  
3.  코드 편집기로 반환 합니다.  
  
4.  (약 줄 67 선 70) 다음 그림에 표시 된 코드의 줄에 중단점을 설정 합니다.  
  
     ![CPU 중단점](../../parallel/amp/media/campcpubreakpoints.png "campcpubreakpoints")  
CPU 중단점  
  
5.  메뉴 모음에서 **디버그**, **디버깅 시작**을 차례로 선택합니다.  
  
6.  에 **지역** 창에 대 한 값을 관찰 `stride_size` 70 줄에서 중단점에 도달할 때까지 합니다.  
  
7.  메뉴 모음에서 **디버그**, **디버깅 중지**를 차례로 선택합니다.  
  
## <a name="debugging-the-gpu-code"></a>GPU 코드 디버그  
 이 섹션에서는 포함 된 코드의 GPU 코드를 디버깅 하는 방법을 보여 줍니다.에 `sum_kernel_tiled` 함수입니다. GPU 코드 각 "블록"에 대 한 정수의 합을 병렬로 계산 합니다.  
  
### <a name="to-debug-the-gpu-code"></a>GPU 코드를 디버깅 하려면  
  
1.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **AMPMapReduce**를 선택한 후 **속성**합니다.  
  
2.  에 **속성 페이지** 대화 상자의 **구성 속성**, 선택 **디버깅**합니다.  
  
3.  에 **실행할 디버거** 목록에서 **로컬 Windows 디버거**합니다.  
  
4.  에 **디버거 형식** 나열 되어 있는지 확인 합니다. **자동** 을 선택 합니다.

    **자동** 기본값입니다. Windows 10 이전 **GPU 전용** 대신 필요한 값은 **자동**합니다.
  
5.  **확인** 단추를 선택합니다.  
  
6.  다음 그림에 나와 있는 것 처럼 30, 줄에 중단점을 설정 합니다.  
  
     ![GPU 중단점](../../parallel/amp/media/campgpubreakpoints.png "campgpubreakpoints")  
GPU 중단점  
  
7.  메뉴 모음에서 **디버그**, **디버깅 시작**을 차례로 선택합니다. CPU 코드 67 및 70 줄에 중단점 GPU CPU에서 실행 되므로 해당 코드 줄을 디버깅 하는 동안 실행 되지 않습니다.  
  
### <a name="to-use-the-gpu-threads-window"></a>GPU 스레드 창 사용 하려면  
  
1.  GPU 스레드 창 메뉴 모음에서 열려면 선택 **디버그**, **Windows**, **GPU 스레드**합니다.  
  
     표시 되는 GPU 스레드 창에 있는 GPU 스레드 상태를 검사할 수 있습니다.  
  
2.  Visual Studio의 맨 아래에 GPU 스레드 창을 고정 합니다. 선택 된 **스레드 스위치 확장** 타일 및 스레드 텍스트 상자를 표시 하려면 단추입니다. 다음 그림에 나와 있는 것 처럼 GPU 스레드 창 총 활성 및 차단 된 GPU 스레드 수를 보여 줍니다.  
  
     ![4 개의 활성 스레드가 있는 GPU 스레드 창](../../parallel/amp/media/campc.png "campc")  
GPU 스레드 창  
  
     이 계산을 위해 할당 된 313 타일 있습니다. 각 타일에는 스레드 32 개 포함 되어 있습니다. 소프트웨어 에뮬레이터에서 앱 발생 로컬 GPU 디버깅을 하기 때문에 4 개의 활성 GPU 스레드가 있습니다. 4 개 스레드 지침을 동시에 실행 한 다음 함께 다음 명령 합니다.  
  
     GPU 스레드 창에 있는 4 개의 GPU 스레드 활성화 되 고 28 GPU 스레드에서 차단 된 [tile_barrier:: wait](reference/tile-barrier-class.md#wait) 21 줄에 대 한에 정의 된 설명 (`t_idx.barrier.wait();`). 첫 번째 타일에 속한 모든 GPU 스레드 32 개 `tile[0]`합니다. 화살표는 현재 스레드를 포함 하는 행을 가리킵니다. 다른 스레드를 전환 하려면 다음 방법 중 하나를 사용 합니다.  

  
    -   GPU 스레드 창에서 전환할 스레드에 대 한 행의 바로 가기 메뉴를 열고 **스레드 전환**합니다. 행이 둘 이상의 스레드를 나타내는 경우에 스레드 좌표에 따라 첫 번째 스레드로 전환 됩니다.  
  
    -   해당 텍스트 상자에는 스레드의 타일 및 스레드 값을 입력 한 다음 선택에서 **스위치 스레드** 단추입니다.  
  
     호출 스택 창에는 현재 GPU 스레드의 호출 스택이 표시 됩니다.  
  
### <a name="to-use-the-parallel-stacks-window"></a>병렬 스택 창을 사용 하 여  
  
1.  병렬 스택 창의 메뉴 모음에서 열려면 선택 **디버그**, **Windows**, **병렬 스택**합니다.  
  
     동시에 여러 개의 GPU 스레드 스택 프레임을 검사 하는 병렬 스택 창의 사용할 수 있습니다.  
  
2.  병렬 스택 창의 Visual Studio의 아래쪽에 도킹 합니다.  
  
3.  다음 사항을 확인 **스레드** 왼쪽 위 모서리에 있는 목록에서 선택 합니다. 다음 그림에서는 병렬 스택 창의 GPU 스레드 창에서 표시 하는 GPU 스레드의 호출 스택 포커스가 있는 보기를 표시 합니다.  
  
     ![4 개의 활성 스레드가 있는 병렬 스택 창](../../parallel/amp/media/campd.png "campd")  
병렬 스택 창  
  
     오류가 발생 했습니다. 스레드 32 개 `_kernel_stub` 람다 문에 `parallel_for_each` 함수 호출 후는 `sum_kernel_tiled` 함수, 병렬 감소 발생 합니다. 28 32 스레드 상태까지 진행는 [tile_barrier:: wait](reference/tile-barrier-class.md#wait) 문을 다른 4 개의 스레드에서 활성 상태로 유지 하는 반면 22, 줄에서 차단 된 상태로 유지 하 고는 `sum_kernel_tiled` 30 선에서 함수입니다.  

  
     병렬 스택 창의 풍부한 DataTip에서 GPU 스레드 창에서 사용할 수 있는 GPU 스레드 속성을 검사할 수 있습니다. 이 위해의 스택 프레임에 마우스 포인터를 놓으면 **sum_kernel_tiled**합니다. 다음 그림에서는 DataTip을 보여 줍니다.  
  
     ![병렬 스택 창에 대 한 DataTip](../../parallel/amp/media/campe.png "campe")  
GPU 스레드 DataTip  
  
     병렬 스택 창에 대 한 자세한 내용은 참조 [병렬 스택 창을 사용 하 여](/visualstudio/debugger/using-the-parallel-stacks-window)합니다.  
  
### <a name="to-use-the-parallel-watch-window"></a>병렬 조사식 창을 사용 하 여  
  
1.  병렬 조사식 창, 메뉴 모음에서 열려면 선택 **디버그**, **Windows**, **병렬 조사식**, **병렬 조사식 1**합니다.  
  
     병렬 조사식 창을 사용 하 여 여러 스레드에서 식의 값을 검사할 수 있습니다.  
  
2.  병렬 조사식 1 창이 Visual Studio 아래쪽에 도킹 합니다. 병렬 조사식 창의 테이블에 32 행이 있습니다. 각 GPU 스레드 창과 병렬 스택 창에 표시 된 GPU 스레드에 해당 합니다. 이제 식 모든 GPU 스레드 32 개에서 검사 하려는 경우 해당 값을 입력할 수 있습니다.  
  
3.  선택 된 **조사식 추가** 열 머리글을 입력 `localIdx`, Enter 키를 선택 합니다.  
  
4.  선택 된 **조사식 추가** 다시 열 머리글을 입력 `globalIdx`, Enter 키를 선택 합니다.  
  
5.  선택 된 **조사식 추가** 다시 열 머리글을 입력 `localA[localIdx[0]]`, Enter 키를 선택 합니다.  
  
     해당 열 머리글을 선택 하 여 지정 된 식을 사용 하 여 정렬할 수 있습니다.  
  
     선택 된 **localA [localIdx [0]]** 열을 정렬 하려면 열 머리글입니다. 다음 그림에서 정렬 결과 보여 줍니다. **localA [localIdx [0]]** 합니다.  
  
     ![정렬 된 결과가 포함 된 병렬 조사식 창](../../parallel/amp/media/campf.png "campf")  
 정렬 결과  
  
     Excel 단추를 선택 하면 선택 하 여 병렬 조사식 창에서 콘텐츠를 Excel로 내보낼 수 있습니다 **Excel에서 열기**합니다. 개발 컴퓨터에 Excel이 설치를 사용 하도록 설정한 경우이 콘텐츠를 포함 하는 Excel 워크시트를 엽니다.  
  
6.  병렬 조사식 창의 오른쪽 위 모서리에 부울 식을 사용 하 여 콘텐츠를 필터링 하는 데 사용할 수 있는 필터 컨트롤이 있습니다. Enter `localA[localIdx[0]] > 20000` 필터 컨트롤 텍스트에서 상자에 한 다음 Enter 키를 선택 합니다.  
  
     창에는 이제만 스레드에는 `localA[localIdx[0]]` 값 20000 보다 큽니다. 콘텐츠 여전히 기준으로 정렬는 `localA[localIdx[0]]` 열은 이전에 수행한 정렬 동작입니다.  
  
## <a name="flagging-gpu-threads"></a>GPU 스레드를 플래그 지정  
 GPU 스레드 창, 병렬 조사식 창 또는 병렬 스택 창의 DataTip에서 플래그를 지정 하 여 특정 GPU 스레드를 표시할 수 있습니다. GPU 스레드 창에 행에 둘 이상의 스레드가 있으면 행에 포함 된 모든 스레드 플래그 지정 해당 행에 플래그를 지정 합니다.  
  
### <a name="to-flag-gpu-threads"></a>GPU 스레드 플래그를 설정 하려면  
  
1.  선택 된 **[스레드]** 타일 인덱스와 스레드 인덱스 별로 정렬 하려면 병렬 조사식 1 창에 열 머리글입니다.  
  
2.  메뉴 모음에서 **디버그**, **계속**, (32 AMPMapReduce.cpp의 줄에서 정의 됨) 다음 장벽에 진행률을 활성 상태 였던 때문에 4 개 스레드입니다.  
  
3.  이제 활성화 된 4 개의 스레드를 포함 하는 행의 왼쪽에 있는 플래그 기호를 선택 합니다.  
  
     다음 그림은 GPU 스레드 창에 4 개의 활성 플래그가 지정 된 스레드를 보여 줍니다.  
  
     ![플래그가 지정 된 스레드가 있는 GPU 스레드 창](../../parallel/amp/media/campg.png "campg")  
GPU 스레드 창의 활성 스레드  
  
     병렬 조사식 창 및 병렬 스택 창의 두 DataTip 플래그가 지정 된 스레드를 나타냅니다.  
  
4.  플래그를 지정 하는 4 개의 스레드에 집중 하려면 GPU 스레드, 병렬 조사식 및 병렬 스택 창의 플래그가 지정 된 스레드만 표시할 수 있습니다.  
  
     선택 하 고 스레드만 표시 단추에 windows 하거나는 **디버그 위치** 도구 모음입니다. 다음 그림과 스레드만 표시 단추에는 **디버그 위치** 도구 모음입니다.  
  
     ![디버그 위치 도구 모음 지정 된 스레드만 표시 아이콘으로](../../parallel/amp/media/camph.png "camph")  
플래그가 지정된 항목만 표시 단추  
  
     이제 GPU 스레드, 병렬 조사식 및 병렬 스택 창에 플래그가 지정 된 스레드만 표시 됩니다.  
  
## <a name="freezing-and-thawing-gpu-threads"></a>GPU 스레드 중지 및 재개  
 고정할 수 있습니다 (일시 중단) 하거나 재개 (다시 시작) GPU 스레드 GPU 스레드 창 또는 병렬 조사식 창에서. 고정 하 고 동일한 방식으로; CPU 스레드 재개 자세한 내용은 참조 [하는 방법: 스레드 창 사용](/visualstudio/debugger/how-to-use-the-threads-window)합니다.  
  
### <a name="to-freeze-and-thaw-gpu-threads"></a>중지 및 재개 GPU 스레드  
  
1.  선택 된 **스레드만 표시** 모든 스레드를 표시 하려면 단추입니다.  
  
2.  메뉴 모음에서 **디버그**, **계속**합니다.  
  
3.  현재 행에 대 한 바로 가기 메뉴를 열고 **고정**합니다.  
  
     GPU 스레드 창의 다음 그림에서는 모든 4 개의 스레드 고정  
  
     ![고정 된 스레드를 표시 하는 GPU 스레드 창](../../parallel/amp/media/campk.png "campk")  
GPU 스레드 창에 고정된 스레드  
  
     마찬가지로, 모든 4 개의 스레드 고정 병렬 조사식 창에 표시 합니다.  
  
4.  메뉴 모음에서 **디버그**, **계속** 다음 네 개의 GPU 스레드 22 선에서 장벽을 지난 진행 하 고 30 줄에서 중단점에 도달할 수 있도록 합니다. GPU 스레드 창 고정 및 활성 상태로 된 4 개의 이전에 고정 된 스레드를 계속 표시 됩니다.  
  
5.  메뉴 모음에서 **디버그**, **계속**합니다.  
  
6.  병렬 조사식 창에서 개인 또는 여러 개의 GPU 스레드 재개 수도 있습니다.  
  
### <a name="to-group-gpu-threads"></a>GPU 스레드를 그룹화 하려면  
  
1.  스레드 중 하나에 대 한 바로 가기 메뉴는 **GPU 스레드** 창 선택 **Group By**, **주소**합니다.  
  
     GPU 스레드 창에서 스레드 주소로 그룹화 됩니다. 주소에서 디스어셈블리 각 스레드 그룹이 위치한 명령에 해당 합니다. 22 줄 24 스레드는 여기서는 [tile_barrier:: wait 메서드](reference/tile-barrier-class.md#wait) 실행 됩니다. 12 스레드는 32 선에서 장벽에 대 한 지침입니다. 이러한 스레드 중 4 개 플래그가 지정 됩니다. 8 개 스레드는 30 줄에 중단점입니다. 이러한 스레드 중 4 개 고정 됩니다. 다음 그림은 GPU 스레드 창에 그룹화 된 스레드를 보여 줍니다.  

  
     ![주소로 그룹화 된 스레드가 있는 GPU 스레드 창](../../parallel/amp/media/campl.png "campl")  
GPU 스레드 창에 그룹화 된 스레드  
  
2.  수행할 수도 있습니다는 **Group By** 병렬 조사식 창 데이터 표에 대 한 바로 가기 메뉴를 열고 작업 선택 **Group By**, 다음 용도에 해당 하는 메뉴 항목을 선택 하 고 스레드를 그룹화 합니다.  
  
## <a name="running-all-threads-to-a-specific-location-in-code"></a>코드의 특정 위치에 실행 하는 모든 스레드  
 특정된 타일에서 사용 하 여 커서를 포함 하는 줄 모든 스레드를 실행 하면 **현재 타일 커서까지 실행**합니다.  
  
### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>커서에 의해 표시 된 위치까지 모든 스레드를 실행 하려면  
  
1.  고정 된 스레드에 대 한 바로 가기 메뉴에서 선택 **재개**합니다.  
  
2.  코드 편집기에서 30 줄에 커서를 놓습니다.  
  
3.  코드 편집기에 대 한 바로 가기 메뉴에서 선택 **실행 현재 Tile을 커서까지**합니다.  
  
     줄 21 장벽에 이전에 차단 된 스레드 24 개가 32 줄으로 진행 되었습니다. 에 나타내지는 **GPU 스레드** 창.  
  
## <a name="see-also"></a>참고 항목  
 [C + + AMP 개요](../../parallel/amp/cpp-amp-overview.md)   
 [GPU 코드 디버그](/visualstudio/debugger/debugging-gpu-code)   
 [방법: GPU 스레드 창 사용](/visualstudio/debugger/how-to-use-the-gpu-threads-window)   
 [방법: 병렬 조사식 창 사용](/visualstudio/debugger/how-to-use-the-parallel-watch-window)   
 [동시성 시각화 도우미를 사용 하 여 c + + AMP 코드 분석](http://go.microsoft.com/fwlink/p/?linkid=253987&clcid=0x409)

