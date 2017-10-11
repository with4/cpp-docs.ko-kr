---
title: volatile (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- volatile_cpp
dev_langs:
- C++
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
caps.latest.revision: 43
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1bbbceaa8f170ad8c75173d60d38e5dd3df1fbdd
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="volatile-c"></a>volatile (C++)
하드웨어에 의해 프로그램에서 수정할 수 있는 개체를 선언하는 데 사용할 수 있는 형식 한정자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
volatile declarator ;  
```  
  
## <a name="remarks"></a>설명  
 사용할 수는 [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 스위치 컴파일러가이 키워드를 해석 하는 방법을 수정할 수 있습니다.  
  
 Visual Studio는 대상 아키텍처에 따라 `volatile` 키워드를 다르게 해석합니다. Arm, 없는 경우 **/volatile** 컴파일러 옵션을 지정한 경우 컴파일러는 수행 처럼 **/volatile:iso** 지정 되었습니다. 되지 않은 경우 ARM 이외의 아키텍처 **/volatile** 컴파일러 옵션을 지정한 경우 컴파일러는 수행 처럼 **/volatile:ms** 에 지정 했습니다; 따라서 아키텍처에 대 한 강력한 म ARM 이외의 지정 하는 권장 되는 **/volatile:iso**, 고 스레드 간에 공유 되는 메모리를 처리할 때 컴파일러 내장 형식 및 명시적 동기화 기본 형식을 사용 합니다.  
  
 `volatile` 한정자를 사용하여 인터럽트 처리기와 같은 비동기 프로세스에 의해 사용되는 메모리 위치에 액세스할 수 있습니다.  
  
 때 `volatile` 역시 하는 변수에서 사용 되는 [__restrict](../cpp/extension-restrict.md) 키워드를 `volatile` 우선적으로 적용 합니다.  
  
 `struct` 멤버가 `volatile`로 표시되면 전체 구조체에 `volatile`이 전파됩니다. 구조체에 하나의 명령을 사용하여 현재 아키텍처에 복사할 수 있는 길이가 없는 경우 해당 구조체에서 `volatile`이 완전히 손실될 수 있습니다.  
  
 다음 조건 중 하나가 true일 경우 `volatile` 키워드는 필드에 영향을 주지 않습니다.  
  
-   volatile 필드의 길이가 현재 아키텍처에서 하나의 명령을 사용하여 복사할 수 있는 최대 크기를 초과합니다.  
  
-   `struct`을 포함하는 가장 바깥쪽 길이 또는 중첩된 `struct` 멤버인 경우 현재 아키텍처에서 하나의 명령을 사용하여 복사할 수 있는 최대 크기를 초과합니다.  
  
 프로세서에서 캐시할 수 없는 메모리의 액세스 순서를 변경하지 않지만 컴파일러에서 메모리 액세스 순서를 변경하지 않도록 캐시할 수 없는 변수를 `volatile`로 표시해야 합니다.  
  
 로 선언 된 개체 `volatile` 해당 값은 언제 든 지 변경 될 수 있으므로 특정 최적화에 사용 되지 않습니다.  시스템이 항상 읽습니다 volatile 개체의 현재 값 요청 될 때 이전 지시문 동일한 개체에서 값을 요청 하는 경우에 합니다.  또한 개체의 값은 할당에 바로 기록 됩니다.  
  
## <a name="iso-compliant"></a>ISO 규격  
 C# volatile 키워드에 잘 알고 있거나의 동작에 익숙한 경우 `volatile` 이전 버전의 Visual c + +에서는 기억해 야 하는 C + + 11 ISO 표준 `volatile` 키워드는 서로 다른 되 고 Visual Studio에서 지원 때는 [/ /volatile: iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션을 지정 합니다. ARM의 경우 기본적으로 지정됩니다. C++ 11 ISO 표준 코드의 `volatile` 키워드는 하드웨어 액세스를 위해서만 사용되며 스레드 간 통신에는 사용되지 않습니다. 스레드 간 통신에 대 한 메커니즘을와 같은 사용 [std::atomic\<T >](../standard-library/atomic.md) 에서 [c + + 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)합니다.  
  
## <a name="end-of-iso-compliant"></a>ISO 규격의 끝  
  
## <a name="microsoft-specific"></a>Microsoft 전용  
 경우는 **/volatile:ms** 컴파일러 옵션을 사용-기본적으로 ARM 이외의 아키텍처가 대상인 경우-컴파일러 유지 관리 외에 volatile 개체에 대 한 참조 순서를 유지 하기 위해 추가 코드를 생성 합니다. 다른 전역 개체에 대 한 참조 순서를 지정 합니다. 특히 다음과 같습니다.  
  
-   volatile 개체 쓰기(volatile 쓰기)는 Release 의미 체계를 사용합니다. 즉 명령 시퀀스에서 volatile 개체에 쓰기 전에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 volatile 쓰기 전에 발생합니다.  
  
-   volatile 개체 읽기(volatile 읽기)는 Acquire 의미 체계를 사용합니다. 즉 명령 시퀀스에서 volatile 메모리 읽기 다음에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 volatile 읽기 다음에 발생합니다.  
  
 따라서 일시적 개체를 메모리 잠금 및 다중 스레드 응용 프로그램의 버전에 대해 사용할 수 있습니다.  
  
> [!NOTE]
>  의존 때 제공 된 향상된 된 보증은 **/volatile:ms** 컴파일러 옵션을 사용 하면 코드 이식 가능 하지 않습니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)
