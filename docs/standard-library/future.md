---
title: "&lt;future&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<future>"
dev_langs: 
  - "C++"
ms.assetid: 2f5830fc-455d-44f9-9e3d-94ea051596a2
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;future&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 헤더를 \<향후\> 에 템플릿 클래스와 가능한 별도의 스레드에서 함수를 간단히 실행하는 템플릿들과 결과 검색을 정의하려면 추가하세요.  그 결과는 해당 함수에 의해 반환 되는 값 이나 함수에 의해 생성되지만 함수에서 잡히지 않는 예외입니다.  
  
 이 헤더는 다른 ConcRT 메커니즘과 함께 사용할 수 있도록 동시성 런타임 \(ConcRT\)을 사용 합니다.  ConcRT에 대한 자세한 내용은 [동시성 런타임](../parallel/concrt/concurrency-runtime.md)를 참조하십시오.  
  
## 구문  
  
```cpp  
#include <future>  
```  
  
## 설명  
  
> [!NOTE]
>  여기 **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일된 코드에서는 이 헤더가 차단 됩니다.  
  
 한 *비동기 공급자* 는 함수 호출의 결과를 저장합니다.  한 *비동기 개체 반환* 은 함수 호출의 결과를 검색하는 데 사용됩니다.  한 *연관된 비동기 상태* 는 비동기 공급자와 하나 또는 그 이상의 비동기 반환 개체 간의 통신을 제공 합니다.  
  
 프로그램에서는 비동기 상태 개체와 연결된 것은 직접 만들지 않습니다.  그 프로그램은 필요할 때마다 비동기 공급자를 생성합니다. 그리고 연관된 비동기 상태를 공유하는 비동기 반환 개체를 생성합니다.  비동기 공급자 및 비동기 반환 개체가 공유된 연관 비동기 상태 개체를 관리 합니다.  관련된 비동기 상태를 참조 하는 마지막 개체를 해제 하는 경우 관련된 비동기 상태를 유지하는 개체가 소멸 됩니다.  
  
 연관 비동기 상태가 없는 비동기 공급자 또는 비동기 반환 개체는 *empty*입니다.  
  
 연결된 비동기 상태는 해당 비동기 공급자가 반환 값을 저장했거나 예외를 저장한 경우에만 *준비*입니다.  
  
 템플릿 함수 `async` 및 템플릿 클래스 `promise` 및 `packaged_task` 는 비동기 공급자입니다.  템플릿 클래스 `future` 및 `shared_future` 는 비동기 반환 개체에 대해 설명 합니다.  
  
 각각의 템플릿 클래스 `promise`, `future`, 및 `shared_future` 는 `void` 형식에 대한 특수화와 참조에 의해 값을 저장하고 검색하는 부분 특수화를 가지고 있습니다.  이러한 특수화들은 반환 값을 저장하고 검색하는 함수의 서명과 의미체계만의 기본 템플릿과 다릅니다.  
  
 템플릿 클래스 `future` 와 `shared_future` 는 이전 버전과의 호환성을 위해 유지한 경우 외에는 소멸자에서 절대 블록되지 않습니다:: 다른 모든 미래와는 달리, `future` 또는 마지막 `shared_future`은 `std::async`와 시작된 작업에 연결되어 있습니다. 즉, 이 스레드가 아직 `.get()` 또는 `.wait()` 을 호출하지 않은 경우 이것은 블록되고 작업은 계속 작업중에 있습니다.  다음과 같은 유용성 참고는 초안 표전에서 `std::async` 의 설명에 추가되어 왔습니다: "\[참고: std::async에서 가져온 future이 외부 지역으로 이동 하는 경우 future에 사용된 다른 코드들은 future의 소멸자가 준비되기 위한 공유 상태를 위해 블록할 것이라는 것을 주의해야 합니다. \-참고 끝\]" 다른 모든 경우에 `future` 와 `shared_future` 소멸자는 요구되었고 차단하지 않는 것을 보장합니다.  
  
## 멤버  
  
### 클래스  
  
|Name|설명|  
|----------|--------|  
|[future 클래스](../standard-library/future-class.md)|비동기 반환 개체에 대해 설명합니다.|  
|[future\_error 클래스](../standard-library/future-error-class.md)|형식들의 메서드에 의해 throw될 수 있는 예외 개체를 설명합니다. 그 형식은 `future` 개체를 관리합니다.|  
|[packaged\_task 클래스](../standard-library/packaged-task-class.md)|비동기 공급자가 래퍼 호출이고 호출 서명은 `Ty(ArgTypes...)`이라는 것을 설명합니다.  그것의 관련된 비동기 상태는 잠재적인 결과 뿐만 아니라 호출할 수 개체의 복사본을 보유합니다.|  
|[promise 클래스](../standard-library/promise-class.md)|비동기 공급자를 설명합니다.|  
|[shared\_future 클래스](../standard-library/shared-future-class.md)|비동기 반환 개체에 대해 설명합니다.  이 `future` 개체와 달리, 비동기 공급자는 여러 개의 `shared_future` 개체와 연관될 수 있습니다.|  
  
### 구조체  
  
|Name|설명|  
|----------|--------|  
|[is\_error\_code\_enum 구조체](../standard-library/is-error-code-enum-structure.md)|이 `future_errc` 를 가리키는 특수화는 `error_code`저장에 적합합니다.|  
|[uses\_allocator 구조체](../standard-library/uses-allocator-structure.md)|특수화는 항상 적용됩니다.|  
  
### 함수  
  
|Name|설명|  
|----------|--------|  
|[async 함수](../Topic/async%20Function.md)|비동기 공급자를 나타냅니다.|  
|[future\_category 함수](../Topic/future_category%20Function.md)|해당 `error_category` 개체에 대한 참조를 반환합니다. 이 개체는 `future` 개체와 관련된 오류의 특징입니다.|  
|[make\_error\_code 함수](../Topic/make_error_code%20Function.md)|한 `error_code` 를 생성하세요. 그것은 `error_category` 개체를 가지고 있고 그 개체는 `future` 오류의 특징입니다.|  
|[make\_error\_condition 함수](../Topic/make_error_condition%20Function.md)|한 `error_condition` 를 생성하세요. 그것은 `error_category` 개체를 가지고 있고 그 개체는 `future` 오류의 특징입니다.|  
|[swap 함수\(\<future\>\)](../Topic/swap%20Function%20\(%3Cfuture%3E\).md)|다른 개체와 한 `promise` 개체의 관련된 비동기 상태를 교환합니다.|  
  
### 열거형  
  
|Name|설명|  
|----------|--------|  
|[future\_errc 열거형](../Topic/future_errc%20Enumeration.md)|에러에 대한 기호화된 이름을 제공합니다. 그것은 `future_error` 클래스에 의하여 보고됩니다.|  
|[future\_status 열거형](../Topic/future_status%20Enumeration.md)|일정 시간의 대기 함수가 반환할 수 있기 때문에 기호 이름을 제공 합니다.|  
|[launch 열거형](../Topic/launch%20Enumeration.md)|템플릿 함수 `async`에 대한 가능한 모드를 설명하는 비트 마스크 형식을 나타냅니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)