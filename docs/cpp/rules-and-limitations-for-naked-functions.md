---
title: "규칙 및 Naked 함수에 대 한 제한 사항 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: naked functions [C++]
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 827585c5c6695b30c090c95d8c135a4a40b301c1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="rules-and-limitations-for-naked-functions"></a>Naked 함수의 규칙 및 제한
## <a name="microsoft-specific"></a>Microsoft 전용  
 naked 함수에는 다음과 같은 규칙과 제한이 적용됩니다.  
  
-   `return` 문이 허용되지 않습니다.  
  
-   구조적 예외 처리 및 C++ 예외 처리 구문은 스택 프레임에서 해제되어야 하기 때문에 허용되지 않습니다.  
  
-   같은 이유로, 모든 형태의 `setjmp`가 금지됩니다.  
  
-   `_alloca` 함수의 사용이 금지됩니다.  
  
-   프롤로그 시퀀스 전에 지역 변수에 대한 초기화 코드가 나타나지 않도록 하기 위해 초기화된 지역 변수가 함수 범위에서 허용되지 않습니다. 특히 C++ 개체의 선언이 함수 범위에서 허용되지 않습니다. 그러나 중첩된 범위에서 초기화된 데이터가 있을 수 있습니다.  
  
-   프레임 포인터 최적화(/Oy 컴파일러 옵션)는 권장되지 않지만 naked 함수에 대해 자동으로 무시됩니다.  
  
-   C++ 클래스 개체를 함수 어휘 범위에서 선언할 수 없습니다. 그러나 중첩된 블록에서 개체를 선언할 수 있습니다.  
  
-   `naked` 키워드는로 컴파일할 때 무시 됩니다 [/clr](../build/reference/clr-common-language-runtime-compilation.md)합니다.  
  
-   에 대 한 [__fastcall](../cpp/fastcall.md) naked 함수, C/c + + 코드에 레지스터 인수 중 하나에 대 한 참조가 있을 때마다 프롤로그 코드 해당 변수의 스택 위치에 레지스터의 값을를 저장 해야 합니다. 예:  
  
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
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [Naked 함수 호출](../cpp/naked-function-calls.md)