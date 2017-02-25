---
title: "Naked 함수에 대한 규칙 및 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "naked 함수"
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Naked 함수에 대한 규칙 및 제한
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 naked 함수에는 다음과 같은 규칙과 제한이 적용됩니다.  
  
-   `return` 문이 허용되지 않습니다.  
  
-   구조적 예외 처리 및 C\+\+ 예외 처리 구문은 스택 프레임에서 해제되어야 하기 때문에 허용되지 않습니다.  
  
-   같은 이유로, 모든 형태의 `setjmp`가 금지됩니다.  
  
-   `_alloca` 함수의 사용이 금지됩니다.  
  
-   프롤로그 시퀀스 전에 지역 변수에 대한 초기화 코드가 나타나지 않도록 하기 위해 초기화된 지역 변수가 함수 범위에서 허용되지 않습니다.  특히 C\+\+ 개체의 선언이 함수 범위에서 허용되지 않습니다.  그러나 중첩된 범위에서 초기화된 데이터가 있을 수 있습니다.  
  
-   프레임 포인터 최적화\(\/Oy 컴파일러 옵션\)는 권장되지 않지만 naked 함수에 대해 자동으로 무시됩니다.  
  
-   C\+\+ 클래스 개체를 함수 어휘 범위에서 선언할 수 없습니다.  그러나 중첩된 블록에서 개체를 선언할 수 있습니다.  
  
-   `naked` 키워드는 [\/clr](../build/reference/clr-common-language-runtime-compilation.md)을 사용하여 컴파일할 때 무시됩니다.  
  
-   [\_\_fastcall](../cpp/fastcall.md) naked 함수의 경우, C\/C\+\+ 코드에 레지스터 인수 중 하나에 대한 참조가 있을 때마다 프롤로그 코드에서 해당 레지스터의 값을 해당 변수의 스택 위치에 저장해야 합니다.  예를 들면 다음과 같습니다.  
  
```  
// nkdfastcl.cpp  
// compile with: /c  
// processor: x86  
__declspec(naked) int __fastcall  power(int i, int j) {  
   // calculates i^j, assumes that j >= 0  
  
   // prolog  
   __asm {  
      push ebp  
      mov ebp, esp  
      sub esp, __LOCAL_SIZE  
     // store ECX and EDX into stack locations allocated for i and j  
     mov i, ecx  
     mov j, edx  
   }  
  
   {  
      int k = 1;   // return value  
      while (j-- > 0)   
         k *= i;  
      __asm {   
         mov eax, k   
      };  
   }  
  
   // epilog  
   __asm {  
      mov esp, ebp  
      pop ebp  
      ret  
   }  
}  
```  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [Naked 함수 호출](../cpp/naked-function-calls.md)