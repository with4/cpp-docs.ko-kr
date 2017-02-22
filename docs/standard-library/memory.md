---
title: "&lt;memory&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::<memory>"
  - "std.<memory>"
  - "<memory>"
  - "std::<memory>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "memory 헤더"
ms.assetid: ef8e38da-7c9d-4037-9ad1-20c99febf5dc
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# &lt;memory&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개체를 할당하고 해제하는 데 도움이 되는 클래스, 연산자 및 몇 가지 템플릿을 정의합니다.  
  
## 구문  
  
```  
  
#include <memory>  
  
```  
  
## 멤버  
  
### Functions  
  
|||  
|-|-|  
|[addressof](../Topic/addressof.md)|개체의 실제 주소를 가져옵니다.|  
|[맞춤](../Topic/align.md)|제공된 정렬 및 시작 주소를 기준으로 지정된 크기 범위에 포인터를 반환합니다.|  
|[allocate\_shared](../Topic/allocate_shared.md)|지정된 할당자를 사용하여 지정된 형식에 대해 할당되고 작성된 개체에 대한 `shared_ptr`을 만듭니다.|  
|[checked\_uninitialized\_copy](../misc/checked-uninitialized-copy.md)|`uninitialized_copy`과 동일하지만 출력 반복기로 확인된 반복기 사용을 적용합니다.|  
|[checked\_uninitialized\_fill\_n](../misc/checked-uninitialized-fill-n.md)|`uninitialized_fill_n`과 동일하지만 출력 반복기로 확인된 반복기 사용을 적용합니다.|  
|[const\_pointer\_cast](../Topic/const_pointer_cast.md)|`shared_ptr`로 const\_cast를 수행합니다.|  
|[declare\_no\_pointers](../Topic/declare_no_pointers.md)|지정된 주소에서 시작하고 표시된 블록 크기 내에 속하는 문자는 추적 가능한 포인터를 포함하지 않음을 가비지 수집기에 알립니다.|  
|[declare\_reachable](../Topic/declare_reachable.md)|지정된 주소가 할당된 저장소 대한 것이며 접근할 수 있음을 가비지 수집에 알립니다.|  
|[default\_delete](../Topic/default_delete.md)|`operator new`를 사용하여 할당된 개체를 삭제합니다.  `unique_ptr`에 사용하는 데 적합합니다.|  
|[dynamic\_pointer\_cast](../Topic/dynamic_pointer_cast.md)|`shared_ptr`로 dynamic\_cast를 수행합니다.|  
|[get\_deleter](../Topic/get_deleter%20Function.md)|`shared_ptr`에서 Deleter 가져오기|  
|[get\_pointer\_safety](../Topic/get_pointer_safety.md)|모든 가비지 수집기에서 간주된 포인터 안전 형식을 반환합니다.|  
|[get\_temporary\_buffer](../Topic/get_temporary_buffer.md)|지정된 수의 요소를 초과하지 않는 요소의 시퀀스를 위한 임시 저장소를 할당합니다.|  
|[make\_shared](../Topic/make_shared%20\(%3Cmemory%3E\).md)|기본 할당자를 사용하여 하나 이상의 인수에서 작성된 할당된 개체를 가리키는 `shared_ptr`를 만들고 반환합니다.|  
|[make\_unique](../Topic/make_unique.md)|하나 이상의 인수에서 작성된 할당된 개체를 가리키는 [unique\_ptr](../standard-library/unique-ptr-class.md)을 만들고 반환합니다.|  
|[owner\_less](../Topic/owner_less.md)|공유된 포인터와 약한 포인트에 대한 소유권 기반의 혼합된 비교를 허용합니다.|  
|[pointer\_safety](../Topic/pointer_safety%20Enumeration.md)|`get_pointer_safety`에 대한 모든 가능한 반환 값의 열거형입니다.|  
|[return\_temporary\_buffer](../Topic/return_temporary_buffer.md)|`get_temporary_buffer` 템플릿 함수를 사용하여 할당된 임시 메모리를 취소합니다.|  
|[static\_pointer\_cast](../Topic/static_pointer_cast.md)|`shared_ptr`에 대한 정적 캐스팅입니다.|  
|[스왑](../Topic/swap%20\(C++%20Standard%20Library\).md)|두 `shared_ptr` 또는 `weak_ptr` 개체를 바꿉니다.|  
|[unchecked\_uninitialized\_copy](../misc/unchecked-uninitialized-copy.md)|`uninitialized_copy`와 동일하지만 \_SECURE\_SCL\=1이 정의된 경우 선택하지 않은 반복기를 출력 반복기로 사용하도록 허용합니다.|  
|[unchecked\_uninitialized\_fill\_n](../misc/unchecked-uninitialized-fill-n.md)|`uninitialized_fill_n`와 동일하지만 \_SECURE\_SCL\=1이 정의된 경우 선택하지 않은 반복기를 출력 반복기로 사용하도록 허용합니다.|  
|[undeclare\_no\_pointers](../Topic/undeclare_no_pointers.md)|기본 주소 포인터와 블록 크기로 정의된 메모리 블록에 있는 문자는 이제 추적이 가능한 포인터를 포함할 수 있음을 가비지 수집기에 알립니다.|  
|[undeclare\_reachable](../Topic/undeclare_reachable.md)|지정된 메모리 위치에 접근할 수 없음을 `garbage_collector`에 알립니다.|  
|[uninitialized\_copy](../Topic/uninitialized_copy.md)|지정된 입력 범위에서 초기화되지 않은 대상 범위로 개체를 복사합니다.|  
|[uninitialized\_copy\_n](../Topic/uninitialized_copy_n.md)|입력 반복기에서 지정된 수의 요소의 복사본을 만듭니다.  복사본은 정방향 반복기에 배치됩니다.|  
|[uninitialized\_fill](../Topic/uninitialized_fill.md)|지정된 값의 개체를 초기화되지 않은 대상 범위로 복사합니다.|  
|[uninitialized\_fill\_n](../Topic/uninitialized_fill_n.md)|지정된 값의 개체를 초기화되지 않은 대상 범위의 지정된 수의 요소로 복사합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cmemory%3E\).md)|지정된 클래스의 할당자 개체가 다른지 테스트합니다.|  
|[연산자\=\=](../Topic/operator==%20\(%3Cmemory%3E\).md)|지정된 클래스의 할당자 개체가 같은지 테스트합니다.|  
|[operator \>\=](../Topic/operator%3E=%20\(%3Cmemory%3E\).md)|하나의 할당자 개체에 대한 테스트는 지정된 클래스의 두 번째 할당자 개체보다 크거나 같습니다.|  
|[operator \<](../Topic/operator%3C%20\(%3Cmemory%3E\).md)|하나의 개체에 대한 테스트는 지정된 클래스의 두 번째 개체보다 적습니다.|  
|[operator \<\=](../Topic/operator%3C=%20\(%3Cmemory%3E\).md)|하나의 개체에 대한 테스트는 지정된 클래스의 두 번째 개체보다 적거나 같습니다.|  
|[operator \>](../Topic/operator%3E%20\(%3Cmemory%3E\).md)|하나의 개체에 대한 테스트는 지정된 클래스의 두 번째 개체보다 큽니다.|  
|[연산자 \<\<](../Topic/operator%3C%3C%20\(%3Cmemory%3E\).md)|`shared_ptr` inserter.|  
  
### 클래스  
  
|||  
|-|-|  
|[할당자](../standard-library/allocator-class.md)|템플릿 클래스는 저장소 할당 및 **형식** 형식의 개체에 대한 배열 해제를 관리하는 개체를 설명합니다.|  
|[allocator\_traits](../standard-library/allocator-traits-class.md)|할당자를 사용할 수 있는 컨테이너에 필요한 모든 정보를 확인하는 개체에 대해 설명합니다.|  
|[auto\_ptr](../standard-library/auto-ptr-class.md)|템플릿 클래스는 바깥쪽 auto\_ptr이 소멸될 때 포인터가 가리키는 개체가 삭제되도록 하는 **형식 \*** 형식의 할당된 개체에 포인터를 저장하는 개체를 설명합니다.|  
|[bad\_weak\_ptr](../standard-library/bad-weak-ptr-class.md)|불량 weak\_ptr 예외를 보고합니다.|  
|[enabled\_shared\_from\_this](../standard-library/enable-shared-from-this-class.md)|`shared_ptr`을 생성할 수 있습니다.|  
|[pointer\_traits](../standard-library/pointer-traits-struct.md)|포인터 형식 `allocator_traits`를 사용하여 할당자를 설명하기 위해 템플릿 클래스 `Ptr`의 개체에 필요한 정보를 제공합니다.|  
|[raw\_storage\_iterator](../standard-library/raw-storage-iterator-class.md)|초기화되지 않은 메모리에 결과를 저장하는 알고리즘을 사용할 수 있도록 제공되는 어댑터 클래스입니다.|  
|[shared\_ptr](../standard-library/shared-ptr-class.md)|동적으로 할당된 개체 주위에 참조 횟수가 계산되는 스마트 포인터를 래핑합니다.|  
|[unique\_ptr](../standard-library/unique-ptr-class.md)|소유한 개체에 대한 포인터를 저장합니다.  다른 `unique_ptr`이 아닌 곳에서 포인터를 소유하고 있습니다.  `unique_ptr`은 소유자가 소멸될 때 소멸됩니다.|  
|[weak\_ptr](../standard-library/weak-ptr-class.md)|약하게 링크된 포인터를 래핑합니다.|  
  
### 특수화  
  
|||  
|-|-|  
|[할당자\<void\>](../standard-library/allocator-void-class.md)|형식 void에 대한 템플릿 클래스 할당자의 특수화로, 이 특수화된 컨텍스트에서 맞는 멤버 형식만 정의합니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)