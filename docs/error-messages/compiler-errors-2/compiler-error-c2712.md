---
title: "컴파일러 오류 C2712 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2712"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2712"
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 컴파일러 오류 C2712
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체 해제 기능이 사용되는 함수에서는 \_\_try를 사용할 수 없습니다.  
  
 [\/EHsc](../../build/reference/eh-exception-handling-model.md)를 사용하고 구조적 예외 처리를 포함하는 함수에 해제\(소멸\)가 필요한 개체도 있는 경우 C2712 오류가 발생할 수 있습니다.  
  
 가능한 해결 방법:  
  
-   SEH가 필요한 코드를 다른 함수로 이동합니다.  
  
-   SEH를 사용하는 함수를 다시 작성하여 소멸자가 있는 지역 변수 및 매개 변수를 사용하지 않도록 합니다.  생성자 또는 소멸자에 SEH를 사용하지 않습니다.  
  
-   \/EHsc 없이 컴파일합니다.  
  
 [\_\_event](../../cpp/event.md) 키워드를 사용하여 선언된 메서드를 호출하는 경우에도 C2712 오류가 발생할 수 있습니다.  다중 스레드 환경에서 이벤트를 사용할 수 있으므로 컴파일러는 기본 이벤트 개체의 조작을 차단하는 코드를 생성한 다음 생성된 코드를 SEH [try\-finally 문](../../cpp/try-finally-statement.md)으로 묶습니다.  따라서 이벤트 메서드를 호출하고 해당 형식에 소멸자가 포함된 인수를 값으로 전달하는 경우 C2712 오류가 발생합니다.  이 경우 한 가지 해결 방법은 인수를 상수 참조로 전달하는 것입니다.  
  
## 예제  
 **\/clr:pure**를 사용하여 컴파일하고 `__try` 블록에서 포인터\-함수의 정적 배열을 선언하는 경우에도 C2712 오류가 발생할 수 있습니다.  정적 멤버는 컴파일러가 **\/clr:pure** 아래에서 동적 초기화를 사용하도록 요구하며, 이는 C\+\+ 예외 처리를 암시합니다.  그러나 C\+\+ 예외 처리는 `__try` 블록에서 허용되지 않습니다.  
  
 다음 샘플에서는 C2712 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2712.cpp  
// compile with: /clr:pure /c  
struct S1 {  
   static int smf();  
   void fnc();  
};  
  
void S1::fnc() {  
   __try {  
      static int (*array_1[])() = {smf,};   // C2712  
  
      // OK  
      static int (*array_2[2])();  
      array_2[0] = smf;  
    }  
    __except(0) {}  
}  
```