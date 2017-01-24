---
title: "연습: C++ AMP 응용 프로그램 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디버깅, C++ Accelerated Massive Parallelism"
  - "C++ AMP, 디버깅"
  - "C++ Accelerated Massive Parallelism, 디버깅"
  - "디버깅, C++ AMP"
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
caps.latest.revision: 35
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: C++ AMP 응용 프로그램 디버깅
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 C\+\+ Accelerated Massive Parallelism \(C\+\+ AMP\)를 사용하여 그래픽 처리 장치\(GPU\)를 활용하는 응용 프로그램을 디버깅 하는 방법을 보여 줍니다.  다양한 정수를 더하는 동시 감소 프로그램을 사용합니다.  이 연습에서는 다음 작업을 수행합니다.  
  
-   GPU 디버거 시작  
  
-   GPU 스레드 창의 검사 GPU 스레드.  
  
-   병렬 스택 창을 사용하여 동시에 여러 개의 GPU 스레드의 호출 스택을 볼 수 있습니다.  
  
-   병렬 조사식 창을 사용하여 동시에 여러 스레드에서 하나의 식의 값을 검사 합니다.  
  
-   플래그, 고정, 재개, 및 GPU 스레드를 그룹화.  
  
-   코드에서 특정 위치에 타일의 모든 스레드를 실행 합니다.  
  
## 사전 요구 사항  
 이 연습을 시작하기 전에:  
  
-   [C\+\+ AMP 개요](../../parallel/amp/cpp-amp-overview.md)를 읽는 경우  
  
-   줄 번호는 텍스트 편집기에 표시 되는지 확인합니다.  자세한 내용은 [방법: 편집기에서 줄 번호 표시](../Topic/How%20to:%20Display%20Line%20Numbers%20in%20the%20Editor.md)을 참조하십시오.  
  
-   [!INCLUDE[win8](../../build/includes/win8_md.md)] 또는 [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] 가 소프트웨어 에뮬레이터에서 디버깅을 지원 하도록 실행하는지 확인 하십시오.  
  
 [!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]  
  
### 샘플 프로젝트를 만들려면  
  
1.  Visual Studio를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
3.  여기 **설치된** 템플릿 창에서, **Visual C\+\+** 을 선택합니다.  
  
4.  **Win32 콘솔 응용 프로그램**을 선택하고, `AMPMapReduce` 를 **이름** 에 입력 한 다음, **확인** 단추를 선택합니다.  
  
5.  **다음** 단추를 선택합니다.  
  
6.  **미리 컴파일된 헤더** 확인란을 지우고, **완료** 단추를 선택합니다.  
  
7.  **솔루션 탐색기**에서, stdafx.h, targetver.h, stdafx.cpp를 프로젝트에서 삭제 합니다.  
  
8.  AMPMapReduce.cpp를 열고 내용을 다음 코드로 바꿉니다.  
  
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
        printf("sum: %s\n", passed ? "Passed!" : "Failed!");   
  
        getchar();  
  
        return 0;  
    }  
  
    ```  
  
9. 메뉴 모음에서 **파일**, **모두 저장**을 차례로 선택합니다.  
  
10. **솔루션 탐색기**에서, **AMPMapReduce**의 바로 가기 메뉴를 열고, **속성**을 선택합니다.  
  
11. **속성 페이지** 대화 상자에서, **구성 속성**아래서, **C\/C\+\+**, **미리 컴파일된 헤더**를 선택합니다.  
  
12. **미리 컴파일된 헤더** 속성에, **미리 컴파일된 헤더 사용 안 함**을 선택한 후, **확인** 단추를 선택합니다.  
  
13. 메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
## CPU 코드 디버깅  
 이 절차에서는, 이 응용 프로그램의 CPU 코드가 정확한 지 확인 하려면 로컬 Windows 디버거를 사용합니다.  특히 흥미 있는 응용 프로그램에서 CPU 코드 세그먼트는 `for` 루프를 `reduction_sum_gpu_kernel` 함수입니다.  GPU에서 실행 되는 트리 기반 병렬 감소를 제어 합니다.  
  
### CPU 코드를 디버깅 방법  
  
1.  **솔루션 탐색기**에서, **AMPMapReduce**의 바로 가기 메뉴를 열고, **속성**을 선택합니다.  
  
2.  **속성 페이지** 대화 상자에서, **구성 속성** 아래에서, **디버깅**을 선택합니다.  **로컬 Windows 디버거** 가 **실행할 디버거** 목록에서 선택합니다.  
  
3.  코드 편집기로 반환 합니다.  
  
4.  다음 그림에 표시된 코드의 줄 \(약 67줄 70줄\) 에 중단점을 설정 합니다.  
  
     ![CPU 중단점](../../parallel/amp/media/campcpubreakpoints.png "CampCpuBreakpoints")  
CPU 중단점  
  
5.  메뉴 모음에서 **디버그**, **디버깅 시작**을 차례로 선택합니다.  
  
6.  **로컬** 창에서, 70줄에 있는 중단점에 도달할 때까지 `stride_size` 의 값을 관찰합니다.  
  
7.  메뉴 모음에서 **디버그**, **디버깅 중지**를 차례로 선택합니다.  
  
## GPU 코드 디버깅  
 이 섹션에서는 GPU 코드를 포함하는 코드를 디버깅 하는 방법을 보여 줍니다. 이 코드는 `sum_kernel_tiled` 함수에 있습니다.  GPU 코드는 병렬로 각 "블록"에 대한 정수의 합을 계산합니다.  
  
### GPU 코드를 디버깅 하는 방법  
  
1.  **솔루션 탐색기**에서, **AMPMapReduce**의 바로 가기 메뉴를 열고, **속성**을 선택합니다.  
  
2.  **속성 페이지** 대화 상자에서, **구성 속성** 아래에서, **디버깅**을 선택합니다.  
  
3.  **실행할 디버거** 목록에서 **로컬 Windows 디버거**를 선택합니다.  
  
4.  **디버거 형식** 목록에서 **GPU 전용**을 선택합니다.  
  
5.  **확인** 단추를 선택합니다.  
  
6.  다음 그림에서와 같이 30줄에 중단점을 설정 합니다.  
  
     ![GPU 중단점](../../parallel/amp/media/campgpubreakpoints.png "CampGpuBreakpoints")  
GPU 중단점  
  
7.  메뉴 모음에서 **디버그**, **디버깅 시작**을 차례로 선택합니다.  코드가 CPU에서 실행 되지 않기 때문에 GPU 디버깅을 하는 동안 CPU 코드 67\-70 줄에 중단점이 실행 되지 않습니다.  
  
### GPU 스레드 창 사용하는 방법  
  
1.  GPU 스레드 창을 열고, 메뉴 모음에서, **디버그**, **Windows**, **GPU 스레드**를 선택합니다.  
  
     나타나는 GPU 스레드 창에서 GPU 스레드 상태를 검사할 수 있습니다.  
  
2.  Visual Studio 아래쪽에 GPU 스레드 창을 고정합니다.  타일 및 스레드 텍스트 상자를 표시하기 위해 **스레드 전환 확장** 을 선택합니다.  다음 그림과 같이, GPU 스레드 창은 활성화 된 총 수 및 차단된 GPU 스레드를 보여줍니다.  
  
     ![4개의 활성 스레드가 있는 GPU 스레드 창](../../parallel/amp/media/campc.png "CampC")  
GPU 스레드 창  
  
     이 계산에 할당된 313 타일입니다.  각 타일은 32 스레드를 포함합니다.  로컬 GPU 디버깅이 소프트웨어 에뮬레이터에서 발생하기 때문에, GPU 스레드 네 개가 있습니다.  4개 스레드는 동시에 지침을 실행 한 다음 함께 다음 명령으로 이동합니다.  
  
     GPU 스레드 창에서, 4개의 GPU 스레드 활성화 및 [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md)문 \(21줄에서 정의 하는 문 \(`t_idx.barrier.wait();`\)\) 에서 차단된 28개의 GPU 스레드가 있습니다.  모든 32개의 GPU 스레드는 첫 번째 타일인 `tile[0]`에 속합니다.  화살표가 현재 스레드에 포함된 행을 가리킵니다.  다른 스레드로 전환하려면, 다음 방법 중 하나를 사용 합니다.  
  
    -   GPU 스레드 창에서 스레드에 대한 행의 바로 가기 메뉴에서, 바로 가기 메뉴를 열고 **스레드 전환**을 선택합니다.  둘 이상의 스레드를 나타내는 행인 경우, 첫 번째 스레드가 스레드 좌표에 따라 전환 됩니다.  
  
    -   스레드의 타일 및 스레드 값을 해당 텍스트 상자에 입력한 다음 **전환 스레드** 단추를 선택합니다.  
  
     호출 스택 창에서 현재 GPU 스레드의 호출 스택을 표시합니다.  
  
### 병렬 스택 창을 사용하는 방법  
  
1.  병렬 스택 창의 메뉴 모음을 열기 위해, 메뉴 바에서, **디버깅**, **Windows**, **병렬 스택**을 선택합니다.  
  
     병렬 스택 창을 동시에 여러 개의 GPU 스레드의 스택 프레임을 검사하여 사용할 수 있습니다.  
  
2.  Visual Studio 아래쪽에 병렬 스택 창을 고정합니다.  
  
3.  왼쪽 맨 위의 목록에서 **스레드**가 선택되어 있는지 확인합니다.  다음 그림에서, 병렬 스택 창은 GPU 스레드 창에서 보았던 GPU 스레드의 호출 스택을 중심 보기를 보여 줍니다.  
  
     ![4개의 활성 스레드가 있는 병렬 스택 창](../../parallel/amp/media/campd.png "CampD")  
병렬 스택 창  
  
     `_kernel_stub` 의 32개의 스레드는 `parallel_for_each` 함수 호출에 있는 람다문으로, 병렬 감소가 발생하는 `sum_kernel_tiled` 함수로 보냅니다. 32개의 스레드 중 28개는 [tile\_barrier::wait](../Topic/tile_barrier::wait%20Method.md) 문을 진행해왔고 30줄에 있는 `sum_kernel_tiled` 함수에서 활성 상태로 유지되는 4개의 다른 스레드가 있는 22줄에 차단된 상태로 남아있습니다.  
  
     병렬 스택 창의 rich DataTip에서 GPU 스레드 창에서 사용할 수 있는 GPU 스레드의 속성을 검사할 수 있습니다.  이것을 하기 위해, **sum\_kernel\_tiled**의 스택 프레임에 마우스 포인터를 놓습니다.  다음 그림에서는 DataTip을 보여 줍니다.  
  
     ![병렬 스택용 DataTip 창](../../parallel/amp/media/campe.png "CampE")  
DataTip GPU 스레드  
  
     병렬 작업 창에 대한 자세한 내용은 다음을 참조하십시오. [병렬 스택 창 사용](../Topic/Using%20the%20Parallel%20Stacks%20Window.md).  
  
### 병렬 조사식 창을 사용하는 방법  
  
1.  병렬 조사식 창을 열기 위해, 메뉴 바에서, **디버깅**, **Windows**, **병렬 감시**, **병렬 조사식 1**을 선택합니다.  
  
     여러 스레드에서 식의 값을 검사 하기 위해 병렬 조사식 창을 사용할 수 있습니다.  
  
2.  Visual Studio 아래쪽에 병렬 조사식 1 창을 고정합니다.  병렬 조사식의 창의 표에 32개의 행이 있습니다.  GPU 스레드 창과 병렬 스택 창 모두에서 나타나는 GPU 스레드에 해당 합니다.  이제, 모든 32개의 GPU 스레드를 검사하고 싶은 값을 갖고 있는 표현식을 입력할 수 있습니다.  
  
3.  **조사식 추가** 열 머리글을 선택하고, `localIdx`를 입력하고, Enter 키를 선택 합니다.  
  
4.  **조사식 추가** 열 머리글을 다시 선택하고, `globalIdx`를 입력한 다음, Enter 키를 선택 합니다.  
  
5.  **조사식 추가** 열 머리글을 다시 선택하고, `localA[localIdx[0]]`를 입력한 다음, Enter 키를 선택 합니다.  
  
     해당 열 머리글을 선택하여 지정된 식으로 정렬할 수 있습니다.  
  
     **localA\[localIdx \[0\]** 열 머리글을 선택하여 열을 정렬합니다.  다음 그림은 **\[\[0\]localIdx\]localA**에 의해 정렬된 결과를 보여줍니다.  
  
     ![정렬된 결과가 포함된 병렬 조사식 창](../../parallel/amp/media/campf.png "CampF")  
 정렬 결과  
  
     병렬 조사식 창에서 Excel 단추를 선택하고 **Excel에서 열기**를 선택하여 내용을 내보낼 수 있습니다.  개발 컴퓨터에 Excel이 설치된 경우, 내용이 포함된 Excel 워크시트가 열립니다.  
  
6.  병렬 조사식 창의 오른쪽 위 모서리에서, 부울 식을 사용하여 콘텐츠를 필터링 하는 데 사용할 수 있는 필터 컨트롤이 있습니다.  필터 컨트롤 텍스트 상자에 `localA[localIdx[0]] > 20000` 를 입력하고 Enter 키를 선택합니다.  
  
     창은 이제 `localA[localIdx[0]]` 값이 20000 보다 큰 스레드만 포함합니다.  콘텐츠는 이전에 수행한 정렬 작업인 `localA[localIdx[0]]` 행에 의해 정렬 됩니다.  
  
## GPU 스레드 플래그 지정  
 GPU 스레드 창, 병렬 조사식 창, 또는 병렬 스택 창의 DataTip에서 플래그를 지정하여 GPU의 특정 스레드를 표시할 수 있습니다.  GPU 스레드 창의 한 행에 둘 이상의 스레드가 있는 경우, 이 행에 포함된 모든 스레드 플래그를 지정 합니다.  
  
### GPU 스레드에 플래그를 지정하는 방법  
  
1.  병렬 조사식 1 창에서 **\[스레드\]** 열 머리글을 선택하여 타일 인덱스와 스레드 인덱스에 의해 정렬 시킵니다.  
  
2.  메뉴 바에서, \(AMPMapReduce.cpp 32 줄에 정의된\) 다음 장벽에 진행 중에 활성화 된 네 개의 스레드를 야기하기 때문에 **디버깅**, **계속**을 선택합니다.  
  
3.  이제 활성화 된 네 개의 스레드를 포함 하는 행의 왼쪽에 플래그 기호를 선택 합니다.  
  
     다음 그림에서는 스레드 GPU 스레드 창에서 4개의 활성된 플래그가 지정된 스레드를 보여줍니다.  
  
     ![플래그 지정된 스레드가 있는 GPU 스레드 창](../../parallel/amp/media/campg.png "CampG")  
GPU 스레드 창의 활성 스레드  
  
     병렬 조사식 창과 병렬 스택 창의 DataTip은 모두 플래그가 지정된 스레드를 나타냅니다.  
  
4.  플래그를 지정 하는 4개의 스레드를 중점적으로 원하는 경우, GPU 스레드, 병렬 조사식, 및 병렬 스택 창에서, 플래그가 지정 된 스레드만 표시 하도록 선택할 수 있습니다.  
  
     플래그가 지정된 표시 단추를 아무 창 또는 **디버그 위치** 도구 모음을 선택합니다.  다음 그림은 **디버그 위치** 도구 모음에서 플래그가 지정된 표시 단추를 보여줍니다.  
  
     ![플래그 설정된 항목만 표시 아이콘이 있는 디버그 위치 도구 모음](../../parallel/amp/media/camph.png "CampH")  
플래그가 지정된 항목만 단추를 표시하기  
  
     이제 GPU 스레드, 병렬 조사식, 및 병렬 스택 창을 플래그가 지정된 스레드만 표시합니다.  
  
## GPU 스레드 중지 및 재개  
 GPU 스레드 창 또는 병렬 조사식 창 둘 중 하나에서 GPU 스레드를 고정 \(중단\) 및 재개 \(resume\) 할 수 있습니다.  동일한 방법으로 CPU 스레드를 중지하고 재개할 수 있습니다; 자세한 내용은 다음을 참조 하십시오. [방법: 스레드 창 사용](../Topic/How%20to:%20Use%20the%20Threads%20Window.md).  
  
### GPU 스레드를 중지하거나 재개하는 방법  
  
1.  **플래그가 지정된 것만 표시** 버튼을 선택하여 모든 스레드를 표시 합니다.  
  
2.  메뉴 바에서, **디버그**, **계속**을 선택합니다.  
  
3.  활성화된 행에 대한 바로 가기 메뉴를 열고 **중지**를 선택합니다.  
  
     GPU 스레드 창의 다음 그림에서는 모든 4개의 스레드가 고정된 것을 보여줍니다.  
  
     ![고정된 스레드를 표시하는 GPU 스레드 창](../../parallel/amp/media/campk.png "CampK")  
GPU 스레드 창에 고정된 스레드  
  
     마찬가지로, 모든 4개의 스레드가 고정된 병렬 조사식 창을 표시 합니다.  
  
4.  메뉴 바에서, **디버깅**, **계속** 을 선택하여 다음 네 개의 GPU 스레드를 22줄의 장애물을 지나서 진행하고 30줄의 중단점을 연결할 수 있도록 합니다.  GPU 스레드 창은 고정 및 활성 상태로 유지된 이전에 고정 된 4개의 스레드를 표시합니다.  
  
5.  메뉴 바에서, **디버그**, **계속**을 선택합니다.  
  
6.  병렬 조사식 창에서, 개인 또는 다중 GPU 스레드를 재개 할 수 있습니다.  
  
### GPU 스레드를 그룹화하는 방법  
  
1.  **GPU 스레드** 창에서 스레드 중 하나에 대한 바로 가기 메뉴에서, **Group By**, **주소**를 선택합니다.  
  
     GPU 스레드 창에 있는 스레드는 주소에 의해 그룹화 됩니다.  주소는 각 스레드 그룹이 위치한 분해의 명령에 해당합니다. 24 스레드는 [tile\_barrier::wait 메서드](../Topic/tile_barrier::wait%20Method.md) 가 실행되는 22줄에 있습니다. 12 스레드는 32줄의 장애물에 대한 명령입니다.  스레드 중 4개가 플래그가 지정 됩니다.  8 스레드는 30줄에 있는 중단점입니다.  4개의 이러한 스레드 고정 됩니다.  다음 그림에서는 GPU 스레드 창에서 그룹화된 스레드를 보여 줍니다.  
  
     ![주소로 그룹화된 스레드가 있는 GPU 스레드 창](../../parallel/amp/media/campl.png "CampL")  
GPU 스레드 창에 그룹화 된 스레드  
  
2.  **Group By** 연산자를 병렬 조사식 창의 데이터 그리드의 바로 가기 메뉴를 열고, **Group By**를 선택한 다음, 스레드를 그룹화 할 방법에 대해 해당하는 메뉴 항목을 선택하면서 수행할 수 있습니다.  
  
## 코드의 특정 위치에 모든 스레드를 실행합니다.  
 **현재 타일 커서까지 실행**을 사용하면서 커서를 포함하는 줄에 주어진 일에 있는 모든 스레드를 실행합니다.  
  
### 커서에서 표시한 위치에 모든 스레드를 실행 하는 방법  
  
1.  고정된 스레드에 대한 바로 가기 메뉴에서, **재개**를 선택합니다.  
  
2.  코드 편집기에서, 30줄에 커서를 놓습니다.  
  
3.  코드 편집기의 바로 가기 메뉴에서, **커서에 현재 타일 실행**을 선택합니다.  
  
     21줄에 있는 장애물에 이전에 차단된 24개의 스레드이 32줄로 진행 되었습니다.  이것은 **GPU 스레드** 창에서 보여집니다.  
  
## 참고 항목  
 [C\+\+ AMP 개요](../../parallel/amp/cpp-amp-overview.md)   
 [GPU 코드 디버깅](../Topic/Debugging%20GPU%20Code.md)   
 [방법: GPU 스레드 창 사용](../Topic/How%20to:%20Use%20the%20GPU%20Threads%20Window.md)   
 [방법: 병렬 조사식 창 사용](../Topic/How%20to:%20Use%20the%20Parallel%20Watch%20Window.md)   
 [동시성 시각화 도우미로 C\+\+ AMP 코드 분석하기](http://go.microsoft.com/fwlink/?LinkID=253987&clcid=0x409)