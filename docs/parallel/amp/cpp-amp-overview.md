---
title: "C++ AMP 개요 | Microsoft Docs"
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
  - "C + + Accelerated Massive Parallelism, 요구 사항"
  - "C + + Accelerated Massive Parallelism, 아키텍처"
  - "C++ AMP"
  - "C + + Accelerated Massive Parallelism, 개요"
  - "C++ Accelerated Massive Parallelism"
ms.assetid: 9e593b06-6e3c-43e9-8bae-6d89efdd39fc
caps.latest.revision: 60
caps.handback.revision: 60
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ AMP 개요
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

C + + Accelerated Massive Parallelism (c + + AMP)은 개별 그래픽 카드에는 처리 GPU (그래픽 장치)와 같은 데이터 병렬 하드웨어 기능을 활용 하 여 c + + 코드의 실행을 가속화 합니다. C + + AMP를 사용 하 여 유형이 다른 하드웨어에서 병렬 처리를 사용 하 여 실행 과정을 가속화할 수 수 있도록 다차원 데이터 알고리즘을 코딩할 수 있습니다. 다차원 배열, 인덱싱, 메모리 전송, 바둑판식으로 배열 및 수치 연산 함수 라이브러리는 c + + AMP 프로그래밍 모델에 포함 되어 있습니다. 성능을 향상 시킬 수 있도록 CPU에서 GPU를 역방향으로 데이터는 이동 하는 방법을 제어 하려면 c + + AMP 언어 확장을 사용할 수 있습니다.  
  
## <a name="system-requirements"></a>시스템 요구 사항  
  
- [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../../parallel/amp/includes/winsvr08_r2_md.md)] 또는 [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)]  
  
-   DirectX 11 기능 수준 11.0 또는 이후 하드웨어  
  
-   소프트웨어 에뮬레이터에서 디버깅을 위해 [!INCLUDE[win8](../../build/includes/win8_md.md)] 또는 [!INCLUDE[winserver8](../../build/includes/winserver8_md.md)] 가 필요 합니다. 하드웨어에서 디버깅하는 경우에는 사용 중인 그래픽 카드의 드라이버를 설치해야 합니다. 자세한 내용은 참조 [GPU 코드 디버깅](../Topic/Debugging%20GPU%20Code.md)합니다.  
  
## <a name="introduction"></a>소개  
 다음 두 예제는 c + + AMP의 주요 구성 요소를 보여 줍니다. 두 1 차원 배열의 해당 요소를 추가 한다고 가정 합니다. 예를 들어 수 추가 하려는 `{1, 2, 3, 4, 5}` 및 `{6, 7, 8, 9, 10}` 얻으려고 `{7, 9, 11, 13, 15}`합니다. C + + AMP를 사용 하지 않고 숫자를 추가 하 고 결과 표시 하는 다음 코드를 작성할 수 있습니다.  
  
```cpp  
  
#include <iostream>  
  
void StandardMethod() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5];  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        sumCPP[idx] = aCPP[idx] + bCPP[idx];  
    }  
  
    for (int idx = 0; idx < 5; idx++)  
    {  
        std::cout << sumCPP[idx] << "\n";  
    }  
}  
  
```  
  
 코드의 중요 한 부분은 다음과 같습니다.  
  
-   데이터: 데이터 배열이 세 구성 됩니다. 모두 동일한 차수 (1) 및 길이 (5) 되어 있습니다.  
  
-   반복: 첫 번째 `for` 루프는 배열에 있는 요소를 반복 하는 것에 대 한 메커니즘을 제공 합니다. 첫 번째에 포함 된 합계를 계산 하는 데 실행 하려는 코드 `for` 블록입니다.  
  
-   인덱스:는 `idx` 변수 배열의 개별 요소에 액세스 합니다.  
  
 C + + AMP를 사용 하 여 다음 코드는을 대신 작성할 수 있습니다.  
  
```cpp  
  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
const int size = 5;  
  
void CppAmpMethod() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[size];  
  
    // Create C++ AMP objects.  
    array_view<const int, 1> a(size, aCPP);  
    array_view<const int, 1> b(size, bCPP);  
    array_view<int, 1> sum(size, sumCPP);  
    sum.discard_data();  
  
    parallel_for_each(   
        // Define the compute domain, which is the set of threads that are created.  
        sum.extent,   
        // Define the code to run on each thread on the accelerator.  
 [=](index<1> idx) restrict(amp)  
    {  
        sum[idx] = a[idx] + b[idx];  
    }  
    );  
  
    // Print the results. The expected output is "7, 9, 11, 13, 15".  
    for (int i = 0; i < size; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
 동일한 기본 요소는 있지만 c + + AMP 구문이 사용 됩니다.  
  
-   데이터: c + + 배열 구성에 사용 하 세 c + + AMP [array_view](../../parallel/amp/reference/array-view-class.md) 개체입니다. 생성 하는 4 개의 값을 제공한는 `array_view` 개체: 데이터 값, 순위, 요소 형식 및 길이 `array_view` 각 차원에는 개체입니다. 순위 및 형식을 형식 매개 변수로 전달 됩니다. 데이터 및 길이 생성자 매개 변수로 전달 됩니다. 이 예제에서는 생성자에 전달 되는 c + + 배열은 1 차원입니다. 순위 및 길이 사용 하 여 구성에 있는 데이터의 직사각형 세이프는 `array_view` 개체 및 데이터 값 배열을 채우는 데 사용 됩니다. 런타임 라이브러리도 포함 되어는 [array 클래스](../../parallel/amp/reference/array-class.md), 있으며 그와 비슷한 인터페이스는 `array_view` 클래스 및이 문서의 뒷부분에서 설명 합니다.  
  
-   반복:는 [parallel_for_each 함수 (c + + AMP)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) 데이터 요소를 반복 하는 메커니즘을 제공 하거나 *도메인 계산*합니다. 이 예제에서는 하 여 계산 도메인을 지정 `sum.extent`합니다. 람다 식에 포함 된 실행 하려는 코드 또는 *커널 함수가*합니다.  `restrict(amp)` c + + AMP를 통해 가속할 수 있는 c + + 언어의 하위 집합만 사용 됨을 나타냅니다.  
  
-   인덱스:는 [index 클래스](../../parallel/amp/reference/index-class.md) 변수인 `idx`, 의 순위와 일치 하도록 하나의 순위를 사용 하 여 선언 되는 `array_view` 개체입니다. 인덱스를 사용 하 여의 개별 요소를 액세스할 수는 `array_view` 개체입니다.  
  
## <a name="shaping-and-indexing-data-index-and-extent"></a>데이터 셰이핑 및 인덱싱: 인덱스 및 범위  
 데이터 값을 정의 하 고 커널 코드를 실행 하기 전에 데이터의 형태를 선언 해야 합니다. 모든 데이터가 다음과 같이 정의 됩니다 (사각형), 배열 및 모든 순위 (차원의 수)을 배열을 정의할 수 있습니다. 데이터에는 큐브의 차원에 임의의 크기 일 수 있습니다.  
  
### <a name="index-class"></a>index 클래스  
  [index 클래스](../../parallel/amp/reference/index-class.md) 의 위치를 지정 된 `array` 또는 `array_view` 개체를 개체 하나에 각 차원에서 원점 으로부터의 오프셋을 캡슐화 하 여. 배열 내의 위치에 액세스할 때 전달는 `index` 개체 인덱싱 연산자를 `[]`, 정수 인덱스의 목록 대신 합니다. 사용 하 여 각 차원에 있는 요소를 액세스할 수는 [배열:: operator () 연산자](../Topic/array::operator\(\)%20Operator.md) 또는 [array_view::operator() 연산자](../Topic/array_view::operator\(\)%20Operator.md)합니다.  
  
 다음 예제에서는 1 차원에서 세 번째 요소를 지정 하는 1 차원 인덱스 `array_view` 개체입니다. 인덱스를 사용 하 여를 세 번째 요소를 인쇄는 `array_view` 개체입니다. 출력은 3입니다.  
  
```cpp  
 
int aCPP[] = {1, 2, 3, 4, 5};  
array_view<int, 1> a(5, aCPP);

index<1> idx(2);

std::cout <<a[idx] <<"\n";    
// Output: 3  
 
```  
  
 다음 예제에서는 요소를 지정 하는 2 차원 인덱스를 행 = 1, 열 = 2는 2 차원에서 `array_view` 개체입니다. 첫 번째 매개 변수는 `index` 생성자는 w 구성 요소 이며 두 번째 매개 변수는 열 구성 요소입니다. 출력은 6입니다.  
  
```cpp  
 
int aCPP[] = {1, 2, 3,  
    4, 5, 6};  
array_view<int, 2> a(2, 3, aCPP);

index<2> idx(1, 2);

std::cout <<a[idx] <<"\n";  
// Output: 6  
 
```  
  
 다음 예제에서는 요소를 지정 하는 3 차원 인덱스를 깊이 = 0 이면 행 = 1, 열 = 3에는 3 차원 `array_view` 개체입니다. 눈에 띌 첫 번째 매개 변수는 깊이 구성 요소, 두 번째 매개 변수 행 구성 요소가 세 번째 매개 변수 열 구성 요소입니다. 출력은 8입니다.  
  
```cpp  
 
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
 
array_view<int, 3> a(2, 3, 4, aCPP);

// Specifies the element at 3, 1, 0.  
index<3> idx(0, 1, 3);

std::cout <<a[idx] <<"\n";  
 
// Output: 8  
 
```  
  
### <a name="extent-class"></a>extent 클래스  
  [extent 클래스](../../parallel/amp/reference/extent-class-cpp-amp.md) 각 차원에 있는 데이터의 길이 지정 된 `array` 또는 `array_view` 개체입니다. 익스텐트를 만들고 사용 하 여 만들 수는 `array` 또는 `array_view` 개체입니다. 기존 범위를 검색할 수도 있습니다 `array` 또는 `array_view` 개체입니다. 다음 예제에서는 출력의 각 차원에 있는 익스텐트의의 길이 `array_view` 개체입니다.  
  
```cpp  
 
int aCPP[] = {  
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12,   
    1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12};  
// There are 3 rows and 4 columns, and the depth is two.  
array_view<int, 3> a(2, 3, 4, aCPP);

std::cout <<"The number of columns is " <<a.extent[2] <<"\n";  
std::cout <<"The number of rows is " <<a.extent[1] <<"\n";  
std::cout <<"The depth is " <<a.extent[0]<<"\n";  
std::cout <<"Length in most significant dimension is " <<a.extent[0] <<"\n";  
 
```  
  
 다음 예제에서는 `array_view` 사용 하 여 앞의 예에서 하지만이 예제에서 개체와 같은 개체 크기는 `extent` 에 명시적 매개 변수를 사용 하는 대신 개체는 `array_view` 생성자입니다.  
  
```cpp  
 
int aCPP[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24};  
extent<3> e(2, 3, 4);

array_view<int, 3> a(e, aCPP);

std::cout <<"The number of columns is " <<a.extent[2] <<"\n";  
std::cout <<"The number of rows is " <<a.extent[1] <<"\n";  
std::cout <<"The depth is " <<a.extent[0] <<"\n";  
 
```  
  
## <a name="moving-data-to-the-accelerator-array-and-arrayview"></a>액셀러레이터로 데이터 이동: array 및 array_view  
 액셀러레이터로 데이터를 이동 하는 데 사용 되는 두 개의 데이터 컨테이너는 런타임 라이브러리에 정의 됩니다. 이들은 [array 클래스](../../parallel/amp/reference/array-class.md) 및 [array_view 클래스](../../parallel/amp/reference/array-view-class.md)합니다.  `array` 클래스는 개체를 생성할 때 데이터의 전체 복사본을 만드는 컨테이너 클래스입니다.  `array_view` 커널 함수에서 데이터에 액세스할 때 데이터를 복사 하는 래퍼 클래스입니다. 데이터 소스 장치에서 필요한 경우 데이터는 다시 복사 됩니다.  
  
### <a name="array-class"></a>array 클래스  
 경우는 `array` 개체가 만들어지면 데이터의 전체 복사본을이 데이터 집합에 대 한 포인터를 포함 하는 생성자를 사용 하는 경우는 엑셀 러 레이 터에 만들어집니다. 커널 함수는 가속기에서 복사본을 수정 합니다. 커널 함수 실행이 완료 되 면 원본 데이터 구조에 다시 데이터를 복사 해야 합니다. 다음 예제에서는 10 벡터의 각 요소를 곱합니다. 커널 함수가 완료 되 면 [벡터 변환 연산자]-brokenlink-(... /Topic/array::operator%20std::vector%3Cvalue_type%3E%20Operator.md)is 벡터 개체에 다시 데이터를 복사 하는 데 사용 합니다.  
  
```cpp  
 
std::vector<int> data(5);

for (int count = 0; count <5; count++)   
{  
    data[count] = count;  
}  
 
array<int, 1> a(5, data.begin(), data.end());

 
parallel_for_each(
    a.extent, 
 [=, &a](index<1> idx) restrict(amp)  
 {  
    a[idx] = a[idx]* 10;  
 });

 
data = a;  
for (int i = 0; i <5; i++)   
{  
    std::cout <<data[i] <<"\n";  
}  
 
```  
  
### <a name="arrayview-class"></a>array_view 클래스  
  `array_view` 와 거의 동일한 멤버에는 `array` 하지만 기본 동작은 같지 않습니다. 에 전달 된 데이터는 `array_view` 과 마찬가지로 생성자는 GPU에서 복제 되지 않습니다는 `array` 생성자입니다. 대신 커널 함수를 실행할 때 액셀러레이터로 데이터 복사 됩니다. 따라서 두 개 만들면 `array_view` 동일한 데이터를 사용 하는 개체 모두 `array_view` 개체가 동일한 메모리 공간을 참조 합니다. 이렇게 하면 모든 다중 스레드 액세스를 동기화 해야 합니다. 사용 하 여의 주요 장점은 `array_view` 클래스는 필요한 경우에 데이터를 이동 합니다.  
  
### <a name="comparison-of-array-and-arrayview"></a>array와 array_view 비교  
 다음 표에서 유사성을 요약 하 고 차이 `array` 및 `array_view` 클래스입니다.  
  
|설명|array 클래스|array_view 클래스|  
|-----------------|-----------------|-----------------------|  
|순위를 확인 하는 경우|컴파일 시.|컴파일 시.|  
|익스텐트를 확인 하는 경우|런타임 시.|런타임 시.|  
|모양|사각형입니다.|사각형입니다.|  
|데이터 저장소|데이터 컨테이너가입니다.|데이터 래퍼입니다.|  
|복사|정의에서 명시적이 고 전체 복사본입니다.|커널 함수에 액세스할 때 암시적 복사본입니다.|  
|데이터 검색|배열 데이터를 복사 하 여 CPU 스레드에서 개체에 백업 합니다.|대 한 직접 액세스는 `array_view` 개체는 [array_view:: synchronize 메서드](../Topic/array_view::synchronize%20Method.md) 계속 원래 컨테이너의 데이터에 액세스 합니다.|  
  
### <a name="shared-memory-with-array-and-arrayview"></a>Array와 array_view를 사용 하 여 공유 메모리  
 공유 메모리는 CPU와 액셀러레이터에서 액세스할 수 있는 메모리입니다. 공유 메모리 사용을 제거 또는 CPU와 가속기 간에 데이터를 복사 하는 오버 헤드를 크게 줄여 줍니다. 메모리는 공유 되지만 CPU에서 가속기를 둘 다에서 동시에 액세스할 수 없습니다 및 정의 되지 않은 동작이 하면 됩니다.  
  
 `array` 관련된 가속기가 지 원하는 경우 공유 메모리의 사용에 대해 세부적으로 제어를 지정 하려면 개체를 사용할 수 있습니다. 엑셀 러 레이 터의 의해 결정 됩니다 가속기 공유 메모리를 지원 하는지 여부를 [supports_cpu_shared_memory](../Topic/accelerator::supports_cpu_shared_memory%20Data%20Member.md) 반환 하는 속성을 `true` 공유 메모리 지원 되는 경우. 공유 메모리 지원 되 면 기본 [access_type 열거형](../Topic/access_type%20Enumeration.md) 액셀러레이터의 할당에 의해 결정 됩니다 메모리는 `default_cpu_access_type` 속성. 기본적으로 `array` 및 `array_view` 개체는 동일한 걸릴 `access_type` 연결 된 주 `accelerator`합니다.  
  
 설정 하 여는 [array:: cpu_access_type 데이터 멤버](../Topic/array::cpu_access_type%20Data%20Member.md) 속성은 `array` 하면 명시적으로 연습 세부적으로 제어할 수 방법을 공유 메모리를 통해 사용 해당 계산 커널 메모리 액세스 패턴을 기반으로 하드웨어의 성능 특성에 대 한 응용 프로그램을 최적화할 수 있도록 합니다.  `array_view` 동일한 반영 `cpu_access_type` 으로 `array` ; 연결 또는 데이터 원본 없이 array_view 생성 되 면 해당 `access_type` 는 먼저 저장소를 할당 하는 환경을 반영 합니다. 즉, 처음 액세스 하는 호스트 (CPU), 동작 하 고 CPU 데이터 원본 및 공유를 통해 생성 된 경우에 따라는 `access_type` 의 `accelerator_view` ;에 캡처로 연결 하 여 첫 번째 경우 액세스 하는 반면는 `accelerator_view`, 것 처럼 동작을 통해 생성 된 다음는 `array` 그에 만든 `accelerator_view` 하 고 공유는 `array`의 `access_type`합니다.  
  
 다음 코드 예제는 기본 액셀러레이터를 공유 메모리 지원를 cpu_access_type 다른 구성이 포함 된 다양 한 배열을 만듭니다 하는지 여부를 확인 하는 방법을 보여 줍니다.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
  
using namespace Concurrency;  
  
int main()  
{  
  accelerator acc = accelerator(accelerator::default_accelerator);  
  
  // Early out if the default accelerator doesn’t support shared memory.  
  if (!acc.supports_cpu_shared_memory)  
  {  
    std::cout << "The default accelerator does not support shared memory" << std::endl;  
    return 1;  
  }  
  
  // Override the default CPU access type.  
  acc.default_cpu_access_type = access_type_read_write  
  
  // Create an accelerator_view from the default accelerator. The  
  // accelerator_view inherits its default_cpu_access_type from acc.  
  accelerator_view acc_v = acc.default_view;  
  
  // Create an extent object to size the arrays.  
  extent<1> ex(10);  
  
  // Input array that can be written on the CPU.  
  array<int, 1> arr_w(ex, acc_v, access_type_write);  
  
  // Output array that can be read on the CPU.  
  array<int, 1> arr_r(ex, acc_v, access_type_read);  
  
  // Read-write array that can be both written to and read from on the CPU.  
  array<int, 1> arr_rw(ex, acc_v, access_type_read_write);  
}  
  
```  
  
## <a name="executing-code-over-data-parallelforeach"></a>데이터에 대해 코드 실행: parallel_for_each  
  [parallel_for_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) 데이터에 대해 가속기에서 실행 해야 하는 코드를 정의 하는 함수는 `array` 또는 `array_view` 개체입니다. 이 항목의 소개에서 다음 코드를 살펴보세요.  
  
```cpp  
  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
void AddArrays() {  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5] = {0, 0, 0, 0, 0};  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
  
    parallel_for_each(  
        sum.extent,   
 [=](index<1> idx) restrict(amp)  
        {  
            sum[idx] = a[idx] + b[idx];  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
  `parallel_for_each` 메서드는 두 개의 인수, 계산 도메인 및 람다 식입니다.  
  
  *도메인 계산* 는 `extent` 개체 또는 `tiled_extent` 를 병렬 실행을 위해 만드는 스레드 집합을 정의 하는 개체입니다. 계산 도메인에 있는 각 요소에 대 한 하나의 스레드가 생성 됩니다. 이 경우에 `extent` 개체는 1 차원 고 다섯 개의 요소를 갖습니다. 따라서 5 개의 스레드 시작 됩니다.  
  
  *람다 식을* 각 스레드에서 실행 하는 코드를 정의 합니다. 캡처 절 `[=]`, 람다 식의 본문이 캡처된 모든 변수에 경우에 값별로 액세스 하도록 지정 `a`, `b`, 및 `sum`합니다. 이 예제에서는 매개 변수 목록 만듭니다 1 차원 `index` 라는 변수 `idx`합니다. 값은 `idx[0]` 는 첫 번째 스레드가에 0이 고 각 후속 스레드에서 1 씩 증가 합니다.  `restrict(amp)` c + + AMP를 통해 가속할 수 있는 c + + 언어의 하위 집합만 사용 됨을 나타냅니다.  Restrict 한정자가 있는 함수에 대 한 제한 사항에 설명 된 [제한 (c + + AMP)](../../cpp/restrict-cpp-amp.md)합니다. 자세한 내용은 참조, [람다 식 구문](../../cpp/lambda-expression-syntax.md)합니다.  
  
 람다 식을 실행 하는 코드를 포함할 수 또는 별도 커널 함수를 호출할 수 있습니다. 커널 함수를 포함 해야는 `restrict(amp)` 한정자입니다. 다음 예제에서는 이전 예제와 동일 하지만 별도 커널 함수를 호출 합니다.  
  
```cpp  
  
#include <amp.h>  
#include <iostream>  
using namespace concurrency;  
  
void AddElements(index<1> idx, array_view<int, 1> sum, array_view<int, 1> a, array_view<int, 1> b) restrict(amp)  
{  
    sum[idx] = a[idx] + b[idx];  
}  
  
void AddArraysWithFunction() {  
  
    int aCPP[] = {1, 2, 3, 4, 5};  
    int bCPP[] = {6, 7, 8, 9, 10};  
    int sumCPP[5] = {0, 0, 0, 0, 0};  
  
    array_view<int, 1> a(5, aCPP);  
    array_view<int, 1> b(5, bCPP);  
    array_view<int, 1> sum(5, sumCPP);  
  
    parallel_for_each(  
        sum.extent,   
 [=](index<1> idx) restrict(amp)  
        {  
            AddElements(idx, sum, a, b);  
        }  
    );  
  
    for (int i = 0; i < 5; i++) {  
        std::cout << sum[i] << "\n";  
    }  
}  
  
```  
  
## <a name="accelerating-code-tiles-and-barriers"></a>가속 코드: 타일 및 장벽  
 바둑판식 배열을 사용 하 여 추가 가속을 얻을 수 있습니다. 사각형 하위 집합에 스레드가 나누어 바둑판식 배열 또는 *타일*합니다. 데이터 집합 및 코딩 하는 알고리즘에 따라 적절 한 타일 크기를 결정 합니다. 에 액세스할 수 있는 각 스레드에 대해는 *글로벌* 전체를 기준으로 데이터 요소의 위치 `array` 또는 `array_view` 에 대 한 액세스는 *로컬* 타일에 상대적인 위치입니다. 로컬 인덱스 값을 사용 하 여 로컬 전역에서 인덱스 값을 변환 하는 코드를 작성 하지 않아도 되므로 코드를 단순화 합니다. 바둑판식 배열을 사용 하려면 호출는 [extent:: tile 메서드](../Topic/extent::tile%20Method.md) 계산 도메인에서 `parallel_for_each` 메서드를 사용 하 여 한 [tiled_index](../../parallel/amp/reference/tiled-index-class.md) 람다 식에는 개체입니다.  
  
 일반적인 응용 프로그램에서 하 고 어떤 식으로든에서 연관 되어 있는 타일의 요소를 코드에 액세스 하 고 타일 간에 값 한 추적 합니다. 사용 된 [tile_static 키워드](../../cpp/tile-static-keyword.md) 키워드 및 [tile_barrier:: wait 메서드](../Topic/tile_barrier::wait%20Method.md) 이를 위해. 있는 변수는 `tile_static` 키워드는 전체 타일 간에 범위가 및 각 타일에 대해 변수 인스턴스가 만들어집니다. 변수에 대 한 타일 스레드 액세스 동기화를 처리 해야 합니다.  [tile_barrier:: wait 메서드](../Topic/tile_barrier::wait%20Method.md) 타일의 모든 스레드 호출에 도달할 때까지 현재 스레드 실행을 중지 `tile_barrier::wait`합니다. 사용 하 여 타일 간에 값을 누적 되므로 `tile_static` 변수입니다. 그런 다음 모든 값에 액세스 해야 하는 모든 계산을 완료할 수 있습니다.  
  
 다음 다이어그램 타일에 있는 데이터를 샘플링 하는 2 차원 배열을 나타냅니다.  
  
 ![바둑판식 범위의 인덱스 값](../../parallel/amp/media/camptiledgridexample.png "CampTiledGridExample")  
  
 다음 코드 예제에서는 위의 다이어그램에서 샘플링 데이터를 사용합니다. 코드에 타일에 있는 값의 평균으로 타일에서 각 값을으로 바뀝니다.  
  
```cpp  
 
// Sample data:  
int sampledata[] = {  
    2, 2, 9, 7, 1, 4,  
    4, 4, 8, 8, 3, 4,  
    1, 5, 1, 2, 5, 2,  
    6, 8, 3, 2, 7, 2};  
 
// The tiles:  
// 2 2    9 7    1 4  
// 4 4    8 8    3 4  
//  
// 1 5    1 2    5 2  
// 6 8    3 2    7 2  
 
// Averages:  
int averagedata[] = {   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
};  
 
array_view<int, 2> sample(4, 6, sampledata);

array_view<int, 2> average(4, 6, averagedata);

 
parallel_for_each(*// Create threads for sample.extent and divide the extent into 2 x 2 tiles.  
    sample.extent.tile<2,2>(), 
 [=](tiled_index<2,2> idx) restrict(amp)  
 { *// Create a 2 x 2 array to hold the values in this tile.  
    tile_static int nums[2][2]; *// Copy the values for the tile into the 2 x 2 array.  
    nums[idx.local[1]][idx.local[0]] = sample[idx.global]; *// When all the threads have executed and the 2 x 2 array is complete, find the average.  
    idx.barrier.wait();
int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1]; *// Copy the average into the array_view.  
    average[idx.global] = sum / 4;  
 });

 
for (int i = 0; i <4; i++) {  
    for (int j = 0; j <6; j++) {  
    std::cout <<average(i,j) <<" ";  
 }  
    std::cout <<"\n";  
}  
 
// Output:  
// 3 3 8 8 3 3  
// 3 3 8 8 3 3  
// 5 5 2 2 4 4  
// 5 5 2 2 4 4  
 
```  
  
## <a name="math-libraries"></a>수학 라이브러리  
 C + + AMP에는 두 개의 수학 라이브러리 포함 됩니다. 이중 정밀도 라이브러리에는 [concurrency:: precise_math 네임 스페이스](../../parallel/amp/reference/concurrency-precise-math-namespace.md) 배정밀 함수에 대 한 지원을 제공 합니다. 또한 하드웨어에 이중 정밀도 지원은 여전히 필요 하지만 단 정밀도 함수에 대 한 지원을 제공 합니다. 준수는 [C99 사양의 (ISO/IEC 9899)](http://go.microsoft.com/fwlink/LinkId=225887)합니다. 액셀러레이터 키 배정밀도 전체를 지원 해야 합니다. 값을 확인 하는 작업을 수행 하는지 여부를 확인할 수는 [accelerator:: supports_double_precision 데이터 멤버](../Topic/accelerator::supports_double_precision%20Data%20Member.md)합니다. 빠른 수학 라이브러리에는 [concurrency:: fast_math 네임 스페이스](../../parallel/amp/reference/concurrency-fast-math-namespace.md), 다른 일련의 수치 연산 함수를 포함 합니다. 이러한 함수에만 지원 `float` 피연산자를 더 신속 하 게 실행 되지만 이중 정밀도 수치 연산 라이브러리에 있는 것으로 충분 하지는 않습니다. 함수는 \< amp_math.h > 헤더 파일에 포함 되 고 선언 된 모든 `restrict(amp)`합니다. 에 포함 된 함수는 \< cmath> 헤더 파일 둘 다로 가져온는 `fast_math` 및 `precise_math` 네임 스페이스입니다.  `restrict` 키워드는 구분 하는 데는 \< cmath> 버전 및 c + + AMP 버전입니다. 다음 코드는 계산 도메인에 있는 각 값의 빠른 메서드를 사용 하는 상용 로그를 계산 합니다.  
  
```cpp  
  
#include <amp.h>  
#include <amp_math.h>  
#include <iostream>  
using namespace concurrency;  
  
void MathExample() {  
  
    double numbers[] = { 1.0, 10.0, 60.0, 100.0, 600.0, 1000.0 };  
    array_view<double, 1> logs(6, numbers);  
  
    parallel_for_each(  
        logs.extent,  
 [=] (index<1> idx) restrict(amp) {  
            logs[idx] = concurrency::fast_math::log10(logs[idx]);  
        }  
    );  
  
    for (int i = 0; i < 6; i++) {  
        std::cout << logs[i] << "\n";  
    }  
}  
  
```  
  
## <a name="graphics-library"></a>그래픽 라이브러리  
 C + + AMP 가속된 그래픽 프로그래밍에 대 한 설계 된 그래픽 라이브러리가 포함 되어 있습니다. 이 라이브러리는 기본 그래픽 기능을 지 원하는 장치에만 사용 됩니다. 메서드는에 [concurrency:: graphics 네임 스페이스](../../parallel/amp/reference/concurrency-graphics-namespace.md) \< amp_graphics.h > 헤더 파일에 포함 되어 있습니다. 그래픽 라이브러리의 주요 구성 요소에는  
  
- [texture 클래스](../../parallel/amp/reference/texture-class.md): 텍스처를 만드는 파일 또는 메모리에서 질감 클래스를 사용할 수 있습니다. 데이터를 포함 하 고 컨테이너의 템플릿 라이브러리 STL (표준) 할당 및 복사본 생성에 대해과 유사 하기 때문에 배열과 유사한 하는 질감입니다. 자세한 내용은 참조 [STL 컨테이너](../../standard-library/stl-containers.md)합니다. 에 대 한 템플릿 매개 변수는 `texture` 클래스는 요소 형식 및 순위입니다. 순위는 1, 2 또는 3 수 있습니다. 요소 형식은이 문서의 뒷부분에서 설명 하는 short 벡터 형식 중 하나일 수 있습니다.  
  
- [writeonly_texture_view 클래스](../../parallel/amp/reference/writeonly-texture-view-class.md): 모든 질감에 대 한 쓰기 전용 액세스를 제공 합니다.  
  
- [Short 벡터 라이브러리](http://msdn.microsoft.com/ko-kr/4c4f5bed-c396-493b-a238-c347563f645f): 2, 3 및 4에 따라 길이의 short 벡터 형식 집합을 정의 `int`, `uint`, `float`, `double`, [norm](../../parallel/amp/reference/norm-class.md), 또는 [unorm](../../parallel/amp/reference/unorm-class.md)합니다.  
  
## <a name="includewin8appnamelongtokenwin8appnamelongmdmd-apps"></a>[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 응용 프로그램  
 다른 c + + 라이브러리와 마찬가지로 c + + AMP를 사용할 수 있습니다 프로그램 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 앱입니다. 이러한 문서는 c + +, C#, Visual Basic 또는 JavaScript를 사용 하 여 만든 응용 프로그램에서 c + + AMP 코드를 포함 하는 방법을 설명 합니다.  
  
- [C + + AMP를 사용 하 여 Windows 스토어 앱에서](../../parallel/amp/using-cpp-amp-in-windows-store-apps.md)  
  
- [연습: c + + 및 JavaScript에서 호출 기본적인 Windows 런타임 구성 요소 만들기](http://go.microsoft.com/fwlink/p/LinkId=249077)  
  
- [Bing 지도 여정 최적화 프로그램에서 JavaScript 및 c + +는 Window 스토어 앱](http://go.microsoft.com/fwlink/p/LinkId=249078)  
  
- [C# Windows 런타임 사용에서 c + + AMP를 사용 하는 방법](http://go.microsoft.com/fwlink/p/LinkId=249080)  
  
- [C#에서 c + + AMP를 사용 하는 방법](http://go.microsoft.com/fwlink/p/LinkId=249081)  
  
- [관리 코드에서 네이티브 함수 호출](../../dotnet/calling-native-functions-from-managed-code.md)  
  
## <a name="c-amp-and-concurrency-visualizer"></a>C++ AMP 및 동시성 시각화 도우미  
 동시성 시각화 도우미에는 c + + AMP 코드의 성능 분석에 대 한 지원이 포함 됩니다. 이러한 문서는 이러한 기능을 설명합니다.  
  
- [GPU 작업 그래프](../Topic/GPU%20Activity%20Graph.md)  
  
- [GPU 작업 (페이징)](../Topic/GPU%20Activity%20\(Paging\).md)  
  
- [GPU 작업 (이 프로세스)](../Topic/GPU%20Activity%20\(This%20Process\).md)  
  
- [GPU 작업 (다른 프로세스)](../Topic/GPU%20Activity%20\(Other%20Processes\).md)  
  
- [채널 (스레드 뷰)](../Topic/Channels%20\(Threads%20View\).md)  
  
- [동시성 시각화 도우미를 사용 하 여 c + + AMP 코드 분석](http://go.microsoft.com/fwlink/LinkID=253987&clcid=0x409)  
  
## <a name="performance-recommendations"></a>성능 권장 사항  
 모듈러스 및 부호 없는 정수의 나누기는 모듈러스 및 부호 있는 정수 나누기 보다 성능이 크게 향상 합니다. 가능한 경우 부호 없는 정수를 사용 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + AMP (c + + Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [람다 식 구문](../../cpp/lambda-expression-syntax.md)   
 [참조 (c + + AMP)](../../parallel/amp/reference/reference-cpp-amp.md)   
 [네이티브 코드 블로그의 병렬 프로그래밍](http://go.microsoft.com/fwlink/p/LinkId=238472)
