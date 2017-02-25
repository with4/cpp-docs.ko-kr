---
title: "&lt;mutex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<mutex>"
dev_langs: 
  - "C++"
ms.assetid: efb60c89-687a-4e38-8fe4-694e11c4e8a3
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# &lt;mutex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

표준 헤더 \<mutex\>를 포함하려면 클래스`mutex`, `recursive_mutex`, `timed_mutex`, `recursive_timed_mutex`, 템플릿 `lock_guard` 및 `unique_lock`과 상호 배제 코드 영역을 정의하는 지원 형식 및 함수를 정의합니다.  
  
> [!WARNING]
>  Visual Studio 2015의 STL 동기화 형식은 Windows 동기화 기본 형식을 따르고 더 이상 ConcRT를 사용하지 않습니다\(대상 플랫폼이 Windows XP인 경우 제외\).  \<mutex\>에 정의된 형식은 모든 ConcRT 형식 및 함수와 함께 사용하면 안 됩니다.  
  
## 구문  
  
```cpp  
#include <mutex>  
```  
  
## 설명  
  
> [!NOTE]
>  이 헤더는 **\/clr** 또는 **\/clr:pure**를 사용하여 컴파일된 코드에서 차단됩니다.  
  
 클래스는 `mutex` 및 `recursive_mutex`는 *뮤텍스 형식*입니다.  뮤텍스 형식에는 예외를 throw하지 않는 기본 생성자와 소멸자가 있습니다.  이러한 개체에는 여러 스레드가 동일한 개체를 잠그려고 할 때 상호 배제하는 메서드가 있습니다.  특히, 뮤텍스 형식에는 `lock`, `try_lock` 및 `unlock` 메서드가 포함되어 있습니다.  
  
-   스레드가 뮤텍스의 소유권을 가져올 때까지 `lock` 메서드가 호출 스레드를 차단합니다.  반환 값은 무시됩니다.  
  
-   `try_lock` 메서드는 차단하지 않고 뮤텍스에 대한 소유권을 가져오려고 시도합니다.  메서드가 소유권을 가져오면 반환 값이 `bool`로 변환되어 `true`가 되지만 그렇지 않은 경우에는 `false`입니다.  
  
-   `unlock` 메서드는 호출 스레드에서 뮤텍스의 소유권을 해제합니다.  
  
 뮤텍스 형식을 형식 인수로 사용하여 템플릿 `lock_guard` 및 `unique_lock`을 인스턴스화할 수 있습니다.  템플릿 [condition\_variable\_any](../standard-library/condition-variable-any-class.md)에서 이러한 형식의 개체를 멤버 대기 함수에 대한 `Lock` 인수로 사용할 수 있습니다.  
  
 *시간이 지정된 뮤텍스 형식*은 뮤텍스 형식에 대한 요구 사항을 충족합니다.  또한 `try_lock_for` 및 `try_lock_until` 메서드가 있습니다. 이러한 메서드는 인수 하나를 사용하여 호출할 수 있어야 하고 `bool`로 변환할 수 있는 형식을 반환해야 합니다.  시간이 지정된 뮤텍스 형식은 추가 인수 모두에 기본값이 있는 경우 이러한 인수를 사용하여 함수를 정의할 수 있습니다.  
  
-   `try_lock_for` 메서드는 하나의 인수 즉, `Rel_time`을 사용하여 호출할 수 있어야 합니다. 이 인수의 형식은 [chrono::duration](../standard-library/duration-class.md)의 인스턴스화입니다.  이 메서드에서 뮤텍스의 소유권을 가져오려고 시도하지만 성공 여부에 관계없이 `Rel_time`으로 지정한 시간 이내에 반환합니다.  메서드가 소유권을 가져오면 반환 값이 `true`로 변환되지만 그렇지 않은 경우 반환 값은 `false`로 변환됩니다.  
  
-   `try_lock_until` 메서드는 하나의 인수 즉, `Abs_time` 사용하여 호출할 수 있어야 합니다. 이 인수의 형식은 [chrono::time\_point](../standard-library/time-point-class.md)의 인스턴스화입니다.  이 메서드에서 뮤텍스의 소유권을 가져오려고 시도하지만 성공 여부에 관계없이 `Abs_time`으로 지정한 시간 이내에 반환합니다.  메서드가 소유권을 가져오면 반환 값이 `true`로 변환되지만 그렇지 않은 경우 반환 값은 `false`로 변환됩니다.  
  
 뮤텍스 형식은 *잠금 가능 형식*이라고도 합니다.  멤버 함수 `try_lock`을 제공하지 않는 경우 *기본 잠금 가능 형식*입니다.  시간이 지정된 뮤텍스 형식은 *시간이 지정된 잠금 가능 형식*이라고도 합니다.  
  
### 클래스  
  
|이름|설명|  
|--------|--------|  
|[lock\_guard 클래스](../standard-library/lock-guard-class.md)|소멸자가 `mutex`의 잠금을 해제하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.|  
|[mutex 클래스\(STL\)](../standard-library/mutex-class-stl.md)|뮤텍스 형식을 나타냅니다.  이 형식의 개체를 사용하면 프로그램 내에서 상호 배제를 강제로 수행할 수 있습니다.|  
|[recursive\_mutex 클래스](../standard-library/recursive-mutex-class.md)|뮤텍스 형식을 나타냅니다.  `mutex` 클래스와 달리 이미 잠겨 있는 개체에 대한 잠금 메서드 호출 동작이 잘 정의되어 있습니다.|  
|[recursive\_timed\_mutex 클래스](../standard-library/recursive-timed-mutex-class.md)|시간이 지정된 뮤텍스 형식을 나타냅니다.  이러한 형식의 개체를 사용하면 프로그램 내에서 시간이 제한된 차단이 있는 상호 배제를 강제로 수행할 수 있습니다.  `timed_mutex` 형식의 개체와 달리 `recursive_timed_mutex` 개체에 대한 잠금 메서드 호출의 효과가 잘 정의되어 있습니다.|  
|[timed\_mutex 클래스](../standard-library/timed-mutex-class.md)|시간이 지정된 뮤텍스 형식을 나타냅니다.  이러한 형식의 개체를 사용하면 프로그램 내에서 시간이 제한된 차단이 있는 상호 배제를 강제로 수행할 수 있습니다.|  
|[unique\_lock 클래스](../standard-library/unique-lock-class.md)|`mutex`의 잠금 및 잠금 해제를 관리하는 개체를 만들기 위해 인스턴스화할 수 있는 템플릿을 나타냅니다.|  
  
### 함수  
  
|이름|설명|  
|--------|--------|  
|[call\_once 함수](../Topic/call_once%20Function.md)|지정된 호출 가능 개체를 실행 중 정확하게 한 번 호출할 수 있는 메커니즘을 제공합니다.|  
|[lock 함수](../Topic/lock%20Function.md)|교착 상태가 발생하지 않고 모든 인수를 잠그려고 시도합니다.|  
  
### Structs  
  
|이름|설명|  
|--------|--------|  
|[adopt\_lock\_t 구조체](../standard-library/adopt-lock-t-structure.md)|`adopt_lock`을 정의하는 데 사용되는 형식을 나타냅니다.|  
|[defer\_lock\_t 구조체](../standard-library/defer-lock-t-structure.md)|`unique_lock`의 오버로드된 생성자 중 하나를 선택하는 데 사용되는 `defer_lock` 개체를 정의하는 형식을 나타냅니다.|  
|[once\_flag 구조체](../standard-library/once-flag-structure.md)|실행 스레드가 여러 개 있는 경우에도 초기화 코드를 한 번만 호출하기 위해 템플릿 함수 `call_once`와 함께 사용되는 `struct` 나타냅니다.|  
|[try\_to\_lock\_t 구조체](../standard-library/try-to-lock-t-structure.md)|`try_to_lock` 개체를 정의하고 `unique_lock`의 오버로드된 생성자 중 하나를 선택하는 데 사용되는 `struct`를 나타냅니다.|  
  
### 변수  
  
|이름|설명|  
|--------|--------|  
|[adopt\_lock 변수](../Topic/adopt_lock%20Variable.md)|생성자에게 전달 중인 뮤텍스 개체가 잠겨 있음을 나타내기 위해 `lock_guard` 및 `unique_lock`의 생성자에 전달할 수 있는 개체를 나타냅니다.|  
|[defer\_lock 변수](../Topic/defer_lock%20Variable.md)|생성자가 전달 중인 뮤텍스 개체를 잠그면 안 됨을 나타내기 위해 `unique_lock`의 생성자에 전달할 수 있는 개체를 나타냅니다.|  
|[try\_to\_lock 변수](../Topic/try_to_lock%20Variable.md)|생성자가 차단 없이 전달 중인 `mutex`의 잠금을 해제하려고 하면 안 됨을 나타내기 위해 `unique_lock`의 생성자에 전달할 수 있는 개체를 나타냅니다.|  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)