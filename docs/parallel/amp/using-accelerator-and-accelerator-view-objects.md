---
title: "accelerator 및 accelerator_view 개체 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 18f0dc66-8236-4420-9f46-1a14f2c3fba1
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# accelerator 및 accelerator_view 개체 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용할 수는 [엑셀 러 레이 터](../../parallel/amp/reference/accelerator-class.md) 및 [accelerator_view](../../parallel/amp/reference/accelerator-view-class.md) 지정 장치 또는 에뮬레이터에서 c + + AMP 코드를 실행 하는 클래스입니다. 여러 장치 또는 에뮬레이터 메모리 양, 공유 메모리 지원, 디버깅 지원 또는 이중 정밀도 지원 하 여 다른 시스템에 있을 수 있습니다. C + + Accelerated Massive Parallelism (c + + AMP)는 사용할 수 있는 액셀러레이터를 검사, 기본으로 설정 하 고, parallel_for_each를 여러 번 호출에 대 한 여러 텍스처가 액셀러레이터 보기를 지정 하 고 특수 디버깅 작업을 수행 하는 데 사용할 수 있는 Api를 제공 합니다.  
  
## <a name="using-the-default-accelerator"></a>기본 액셀러레이터를 사용 하 여  
 C + + AMP 런타임이 특정 하나를 선택 하는 코드를 작성 하지 않는 경우 기본 엑셀 러 레이 터를 선택 합니다. 런타임에서 기본 액셀러레이터를 다음과 같이 선택합니다.  
  
1.  앱 디버그 모드에서 실행 중이면 바로 연결 하는 디버깅 지원 합니다.  
  
2.  그렇지 않은 경우 설정 된 경우 CPPAMP_DEFAULT_ACCELERATOR 환경 변수로 지정 된 엑셀 러 레이 터입니다.  
  
3.  그렇지 않으면 에뮬레이트되지 않은 장치입니다.  
  
4.  그렇지 않으면 사용 가능한 메모리를 거둘 수 있는 장치.  
  
5.  그렇지 않으면 디스플레이에 연결 되어 있지 않은 장치입니다.  
  
 또한 런타임에서 지정 된 `access_type` 의 `access_type_auto` 기본 엑셀 러 레이 터에 대 한 합니다. 즉, 기본 엑셀 러 레이 터 (대역폭 및 대기 시간)의 성능 특성 전용된 (비공유) 메모리와 동일한 것으로 알려진 경우 요소 및 지원 되는 경우 공유 메모리를 사용 합니다.  
  
 기본 액셀러레이터를 구성 하 고 해당 속성을 검사 하 여 기본 액셀러레이터의 속성을 확인할 수 있습니다. 다음 코드 예제에서는 인쇄 경로 엑셀 러 레이 터 메모리 양, 공유 메모리 지원, 이중 정밀도 지원 및 기본 액셀러레이터의 제한 된 범위의 배정밀 지원 합니다.  
  
```cpp  
 
void default_properties() {  
    accelerator default_acc;  
    std::wcout <<default_acc.device_path <<"\n";  
    std::wcout <<default_acc.dedicated_memory <<"\n";  
    std::wcout <<(accs[i].supports_cpu_shared_memory    
 "CPU shared memory: true" : "CPU shared memory: false") <<"\n";  
    std::wcout <<(accs[i].supports_double_precision    
 "double precision: true" : "double precision: false") <<"\n";  
    std::wcout <<(accs[i].supports_limited_double_precision    
 "limited double precision: true" : "limited double precision: false") <<"\n";  
}  
 
```  
  
### <a name="cppampdefaultaccelerator-environment-variable"></a>CPPAMP_DEFAULT_ACCELERATOR 환경 변수  
 지정 하는 CPPAMP_DEFAULT_ACCELERATOR 환경 변수를 설정할 수는 `accelerator::device_path` 는 기본 액셀러레이터의 합니다. 경로 하드웨어에 따라 다릅니다. 다음 코드는 `accelerator::get_all` 함수를 사용할 수 있는 액셀러레이터의 목록을 검색 한 다음 경로 각 엑셀 러 레이 터의 특성을 표시 합니다.  
  
```cpp  
 
void list_all_accelerators()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
for (int i = 0; i <accs.size();

i++) {  
    std::wcout <<accs[i].device_path <<"\n";  
    std::wcout <<accs[i].dedicated_memory <<"\n";  
    std::wcout <<(accs[i].supports_cpu_shared_memory    
 "CPU shared memory: true" : "CPU shared memory: false") <<"\n";  
    std::wcout <<(accs[i].supports_double_precision    
 "double precision: true" : "double precision: false") <<"\n";  
    std::wcout <<(accs[i].supports_limited_double_precision    
 "limited double precision: true" : "limited double precision: false") <<"\n";  
 }  
}  
 
```  
  
## <a name="selecting-an-accelerator"></a>액셀러레이터 키를 선택합니다.  
 액셀러레이터 키를 선택 하려면 사용 된 `accelerator::get_all` 해당 속성을 기반으로 하는 메서드를 사용할 수 있는 액셀러레이터의 목록을 검색 한 다음 하나를 선택 합니다. 이 예제에는 가장 많은 메모리를 가진 가속기를 선택 하는 방법을 보여 줍니다.  
  
```cpp  
 
void pick_with_most_memory()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
accelerator acc_chosen = accs[0];  
    for (int i = 0; i <accs.size();

i++) {  
    if (accs[i].dedicated_memory> acc_chosen.dedicated_memory) {  
    acc_chosen = accs[i];  
 }  
 }  
 
    std::wcout <<"The accelerator with the most memory is "    
 <<acc_chosen.device_path <<"\n"  
 <<acc_chosen.dedicated_memory <<".\n";  
}  
 
```  
  
> [!NOTE]
>  반환 되는 액셀러레이터 키 중 하나 `accelerator::get_all` CPU 엑셀 러 레이 터는 합니다. CPU 액셀러레이터에 코드를 실행할 수 없습니다. CPU 액셀러레이터를 필터링 하려면 값을 비교는 [device_path](../Topic/accelerator::device_path%20Data%20Member.md) 속성에서 반환 되는 엑셀 러 레이 터의 `accelerator::get_all` 값으로는 [accelerator:: cpu_accelerator](../Topic/accelerator::cpu_accelerator%20Data%20Member.md)합니다. 자세한 내용은이 문서의 "특별 한 Accelerator" 섹션을 참조 합니다.  
  
## <a name="shared-memory"></a>공유 메모리  
 공유 메모리는 CPU와 액셀러레이터에서 액세스할 수 있는 메모리입니다. 공유 메모리 사용을 제거 또는 CPU와 가속기 간에 데이터를 복사 하는 오버 헤드를 크게 줄여 줍니다. 메모리는 공유 되지만 CPU에서 가속기를 둘 다에서 동시에 액세스할 수 없습니다 및 정의 되지 않은 동작이 하면 됩니다. 액셀러레이터 키 속성 [supports_cpu_shared_memory](../Topic/accelerator::supports_cpu_shared_memory%20Data%20Member.md) 반환 `true` 가속기 공유 메모리를 지 원하는 경우 및 [default_cpu_access_type](../Topic/accelerator::default_cpu_access_type%20Data%20Member.md) 속성 기본값을 가져옵니다 [access_type](../Topic/access_type%20Enumeration.md) 에 할당 된 메모리에 대 한는 `accelerator`-예를 들어 `array`과 연결 된는 `accelerator`, 또는 `array_view` 에서 액세스 되는 개체는 `accelerator`합니다.  
  
 C + + AMP 런타임 최상의 기본값을 자동으로 선택 `access_type` 각 `accelerator`, 하지만 CPU, 또는 둘 다에서 작성 하는 CPU에서 읽을 때 공유 메모리의 성능 특성 (대역폭 및 대기 시간)의 전용된 (비공유) 가속기 메모리 보다 성능은 낮을 수 있습니다. 공유 메모리와 CPU에서 읽고 쓰기 위해 전용된 된 메모리를 수행 하는 경우 런타임에서 기본적으로 `access_type_read_write`고, 그렇지 않으면 런타임이 선택할 보다 보수적 기본 `access_type`, 응용 프로그램에서 해당 계산 커널 메모리 액세스 패턴 다른 경우 재정의 허용 하 고 `access_type`합니다.  
  
 다음 코드 예제에서는 여부 확인 하는 기본 액셀러레이터 공유 메모리를 지원 하 고 다음 해당 기본 액세스 형식을 재정의 만듭니다는 `accelerator_view` 에서.  
  
```cpp  
#include <amp.h>  
#include <iostream>  
  
using namespace Concurrency;  
  
int main()  
{  
  accelerator acc = accelerator(accelerator::default_accelerator);  
  
  // Early out if the default accelerator doesn’t support shared memory.  
  if(!acc.supports_cpu_shared_memory)  
  {  
    std::cout << "The default accelerator does not support shared memory" << std::endl;  
    return 1;  
  }  
  
  // Override the default CPU access type.  
  acc.set_default_cpu_access_type(access_type_read_write);  
  
  // Create an accelerator_view from the default accelerator. The  
  // accelerator_view reflects the default_cpu_access_type of the  
  // accelerator it’s associated with.  
  accelerator_view acc_v = acc.default_view;  
}  
  
```  
  
  `accelerator_view` 항상 반영 된 `default_cpu_access_type` 의 `accelerator` 를 재정의 하거나 변경 하지 인터페이스를 제공 하 고 연결 된 해당 `access_type`합니다.  
  
## <a name="changing-the-default-accelerator"></a>기본 액셀러레이터를 변경합니다.  
 호출 하 여 기본 액셀러레이터를 변경할 수는 `accelerator::set_default` 메서드. 앱 당 실행 하 고 변경 해야 모든 코드는 GPU에서 실행 되기 전에 한 번만 기본 액셀러레이터를 변경할 수 있습니다. 액셀러레이터 키를 변경 하는 모든 이후의 함수 호출 반환 `false`합니다. 에 대 한 호출에서 서로 다른 액셀러레이터를 사용 하려면 `parallel_for_each`, 이 문서의 "여러 Accelerator를 사용 하 여" 섹션을 참조 합니다. 다음 코드 예제에서는 에뮬레이션 되지 않았습니다, 표시 되는 연결 되지 않은 및 이중 정밀도 지원 되는 기본 액셀러레이터를 설정 합니다.  
  
```cpp  
 
    bool pick_accelerator()  
{  
    std::vector<accelerator> accs = accelerator::get_all();
accelerator chosen_one;  
 
    auto result = 
    std::find_if(accs.begin(), accs.end(), [] (const accelerator& acc)  
 {  
    return !acc.is_emulated&& 
    acc.supports_double_precision&& 
 !acc.has_display;  
 });

 
    if (result != accs.end())  
    chosen_one = *(result);

 
    std::wcout <<chosen_one.description <<std::endl;  
 
    bool success = accelerator::set_default(chosen_one.device_path);

    return success;  
}  
 
```  
  
## <a name="using-multiple-accelerators"></a>여러 액셀러레이터 키를 사용 하 여  
 응용 프로그램에서 여러 액셀러레이터 키를 사용 하는 방법은 두 가지가 있습니다.  
  
-   전달할 수 `accelerator_view` 개체에 대 한 호출에는 [parallel_for_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md) 메서드.  
  
-   생성할 수는 `array` 특정을 사용 하 여 `accelerator_view` 개체입니다. C + AMP 런타임이 선택 해 서는 `accelerator_view` 개체에서 캡처된 `array` 람다 식에는 개체입니다.  
  
## <a name="special-accelerators"></a>특별 한 액셀러레이터 키  
 세 가지 특별 한 가속기의 장치 경로 속성으로 사용할 수는 `accelerator` 클래스:  
  
- [accelerator:: direct3d_ref 데이터 멤버](../Topic/accelerator::direct3d_ref%20Data%20Member.md): 단일 스레드는이 액셀러레이터를 사용 하 여 소프트웨어 CPU에는 일반 그래픽 카드를 에뮬레이션 합니다. 디버깅을 기본적으로 사용 하지만 하드웨어 액셀러레이터 보다 느린 있기 때문에 프로덕션 환경에서 유용 하지 않습니다. 또한 DirectX SDK 및 Windows SDK에만 사용할 수 및 고객의 컴퓨터에 설치할 수 없는 가능성이 있습니다. 자세한 내용은 참조 [GPU 코드 디버깅](../Topic/Debugging%20GPU%20Code.md)합니다.  
  
- [accelerator:: direct3d_warp 데이터 멤버](../Topic/accelerator::direct3d_warp%20Data%20Member.md):이 엑셀 러 레이이 터 (SSE)를 사용 하는 다중 코어 Cpu에서 c + + AMP 실행에 대 한 대체 (fallback) 솔루션을 제공 합니다.  
  
- [accelerator:: cpu_accelerator 데이터 멤버](../Topic/accelerator::cpu_accelerator%20Data%20Member.md): 배열 준비를 설정 하기 위한이 액셀러레이터를 사용할 수 있습니다. 이 c + + AMP 코드를 실행할 수 없습니다. 자세한 내용은 참조는 [c + + amp에서 준비 배열](http://go.microsoft.com/fwlink/p/LinkId=248485) Parallel Programming in Native Code 블로그의에 게시 합니다.  
  
## <a name="interoperability"></a>상호 운용성  
 C + + AMP 런타임 간의 상호 운용성 지원에서 `accelerator_view` 클래스와는 Direct3D [ID3D11Device 인터페이스](http://go.microsoft.com/fwlink/p/LinkId=248488)합니다.  [create_accelerator_view](../Topic/create_accelerator_view%20Function.md) 메서드는 `IUnknown` 인터페이스와 반환 된 `accelerator_view` 개체입니다.  [get_device](http://msdn.microsoft.com/ko-kr/8194125e-8396-4d62-aa8a-65831dea8439) 메서드는 `accelerator_view` 개체를 반환 된 `IUknown` 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + AMP (c + + Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [GPU 코드 디버깅](../Topic/Debugging%20GPU%20Code.md)   
 [accelerator_view 클래스](../../parallel/amp/reference/accelerator-view-class.md)
