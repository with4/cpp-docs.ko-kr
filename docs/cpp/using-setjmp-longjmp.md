---
title: "setjmp/longjmp 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "longjmp"
  - "setjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 예외 처리, setjmp/longjmp 함수"
  - "C++ 프로그램의 longjmp 함수"
  - "setjmp 함수"
  - "setjmp 함수, C++ 프로그램"
  - "SETJMP.H"
  - "SETJMPEX.H"
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# setjmp/longjmp 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[setjmp](../c-runtime-library/reference/setjmp.md) 및 [longjmp](../c-runtime-library/reference/longjmp.md)를 함께 사용하면 비로컬 `goto`를 실행할 수 있습니다.  setjmp와 longjmp는 표준 호출이나 반환 규칙을 사용하지 않고 전에 호출된 루틴에서 오류 처리 또는 복구 코드에 실행 제어를 전달하는 데 주로 사용됩니다.  
  
> [!CAUTION]
>  그러나 `setjmp` 및 `longjmp`는 C\+\+ 개체 의미 체계를 지원하지 않으며 지역 변수의 최적화를 막아 성능을 저하시킬 수 있으므로 C\+\+ 프로그램에서는 사용하지 않는 것이 좋습니다.  대신 `try`\/`catch` 구문을 사용하십시오.  
  
 C\+\+ 프로그램에서 `setjmp`\/`longjmp`를 사용하려면 함수와 C\+\+ 예외 처리 간에 올바른 상호 작용이 이루어지도록 SETJMP.H나 SETJMPEX.H를 포함해야 합니다.  [\/EH](../build/reference/eh-exception-handling-model.md)를 사용하여 컴파일할 경우 스택 해제 중에 로컬 개체의 소멸자가 호출됩니다.  **\/EHs**를 사용하여 컴파일할 경우 함수 중 하나가 [nothrow](../cpp/nothrow-cpp.md)를 사용하는 함수를 호출하고 `nothrow`를 사용하는 함수가 `longjmp`를 호출하면 최적화 프로그램에 따라 소멸자가 해제될 수 있습니다.  
  
 이식 가능한 코드에서 `longjmp`를 호출하는 비로컬 `goto`가 실행되면 프레임 기반 개체가 제대로 삭제되지 않을 수도 있습니다.  
  
## 참고 항목  
 [\(구조적\) C 및 C\+\+ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)