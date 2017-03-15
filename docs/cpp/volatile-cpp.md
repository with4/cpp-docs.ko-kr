---
title: "volatile (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "volatile_cpp"
  - "volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "인터럽트 처리기 및 volatile 키워드"
  - "개체[C++], volatile"
  - "volatile 키워드[C++]"
  - "volatile 개체"
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
caps.latest.revision: 43
caps.handback.revision: 43
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# volatile (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

형식 한정자는 하드웨어 프로그램에서 개체를 수정할 수 있는 개체를 선언 하는 데 사용할 수 있는 것입니다.  
  
## 구문  
  
```  
  
volatile declarator ;  
```  
  
## 설명  
 다음 [\/휘발성](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 스위치를 어떻게 컴파일러가 이 키워드를 해석하는지 수정하기 위해 사용할 수 있습니다.  
  
 Visual Studio는 `volatile` 키워드를 대상 아키텍처에 따라 다르게 해석합니다.  ARM의 경우, 만약 **\/volatile** 컴파일러 옵션이 지정되지 않은 경우, 컴파일러는 **\/volatile:iso** 가 지정된 것처럼 수행됩니다.  ARM과 다른 구조에서, **\/volatile** 컴파일러 옵션이 지정되지 않은 경우, 컴파일러는 **\/volatile:ms** 이 지정된 것처럼 수행합니다; 따라서, ARM 이외의 다른 아키텍처에 대해 우리는 강력하게 **\/volatile:iso** 를 지정하도록 권장하고, 스레드 간에 공유되는 메모리를 처리 할 때 컴파일러 내장 및 명시적 동기화 기본 형식을 사용하는 것을 권장합니다.  
  
 `volatile` 한정자를 사용하여 인터럽트 처리기와 같은 비동기 프로세스에 의해 사용되는 메모리 위치에 액세스 할 수 있습니다.  
  
 `volatile` 가 [\_\_restrict](../cpp/extension-restrict.md) 키워드를 가진 변수에 사용될 경우, `volatile` 은 우선적으로 적용됩니다.  
  
 `struct` 멤버가 `volatile`로 표시되면 전체 구조체에 `volatile`이 전파됩니다.  구조체에 하나의 명령을 사용하여 현재 아키텍처에 복사할 수 있는 길이가 없는 경우 해당 구조체에서 `volatile`이 완전히 손실될 수 있습니다.  
  
 `volatile` 키워드는 다음 조건 중 하나가 참일 경우 키워드 필드에 영향을 미치지 않습니다.  
  
-   Volatile 필드의 길이는 현재 아키텍처에서 하나의 명령을 사용하여 복사될 수 있는 최대 크기를 초과 합니다.  
  
-   다음 `struct`을 포함하는 가장 바깥쪽 길이 ㅡ혹은 가능한 중첩의 멤버인 경우 `struct`ㅡ현재 아키텍처에서 하나의 명령을 사용하여 복사할 수 있는 최대 크기를 초과 합니다.  
  
 프로세서 메모리에 캐시할 수 없는 액세스 순서는 변경 되지 않습니다, 하지만 `volatile` 처럼 캐시할 수 없는 변수로 표시 되어야 합니다. 액세스 하려면 컴파일러는 메모리 순서가 변경 되지 않습니다.  
  
 `volatile`로 선언된 개체는 해당 값이 언제든지 변경될 수 있기 때문에 특정 최적화에서 사용되지 않습니다.  시스템은 이전 명령에 동일한 개체에서 값을 요청 하는 경우라도 요청이 오면 휘발성 개체의 현재 값을 항상 읽습니다.  또한 개체의 값이 할당에서 즉시 기록됩니다.  
  
## ISO 규격  
 [C\# 휘발성](../Topic/volatile%20\(C%23%20Reference\).md) 키워드와 익숙하거나, 또는 `volatile` 동작을 Visual C\+\+ 이전 버전에서 익숙하다면, C\+\+ 11 ISO 표준 `volatile` 키워드가 다르고 [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 옵션이 지정될 때 Visual Studio에서 지원된다는 것을 알아야 합니다. \(ARM에 대해, 기본적으로 지정됩니다\).  C\+\+ 11 ISO 표준 코드에서`volatile` 키워드는 하드웨어 엑세스를 위해서만 사용됩니다; 스레드 간 통신을 위해 사용 하지 마십시오.  스레드 간 통신에서, [std::atomic\<T\>](../standard-library/atomic.md) 과같은 메커니즘을 [C\+\+ 표준 템플릿 라이브러리](../standard-library/cpp-standard-library-reference.md) 로부터 사용하십시오.  
  
## ISO 규격의 끝  
  
## Microsoft 전용  
 **\/volatile:ms** 컴파일러 옵션이 사용될 때 ㅡ기본적으로 ARM 이외의 아키텍처를 대상으로 할 때ㅡ컴파일러는 다른 전역 개체에 대한 참조 순서를 유지하는 데 추가적으로 휘발성 개체 참조 중의 순서를 유지하는 데 추가 코드를 생성 합니다.  특히 다음과 같습니다.  
  
-   휘발성 개체 쓰기\(휘발성 쓰기라고도 알려진\)는 Release 의미 체계를 가지며; 즉, 명령 시퀀스에서 휘발성 개체의 쓰기 전에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 휘발성 쓰기 전에 발생합니다.  
  
-   휘발성 개체 읽기\(휘발성 읽기라고도 알려진\)는 Acquire 의미 체계를 가지며;즉, 명령 시퀀스에서 휘발성 메모리의 읽기 다음에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 휘발성 읽기 다음에 발생합니다.  
  
 이것은 휘발성 개체를 다중 스레드 응용 프로그램에서 메모리 잠금 및 해제에 사용할 수 있도록 합니다.  
  
> [!NOTE]
>  **\/volatile:ms** 컴파일러 옵션이 사용 될 때 제공된 향상된 보증에 의존 할 때, 코드는 이식 가능 하지 않습니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)