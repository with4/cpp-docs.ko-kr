---
title: "컴파일러 경고 (수준 1) C4733 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4733"
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인라인 asm이 'FS:0'에 할당되었습니다. 처리기가 안전한 처리기로 등록되지 않았습니다.  
  
 새로운 식 처리기를 추가하기 위해 FS:0의 값을 수정하는 함수가 안전한 예외에는 작동하지 않습니다. 이는 처리기가 올바른 예외 처리기로 등록되지 않았기 때문입니다. 자세한 내용은 [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)를 참조하십시오.  
  
 이 경고를 해결하려면 FS:0 정의를 제거하거나, 이 경고를 해제하고 [.SAFESEH](../../assembler/masm/dot-safeseh.md)를 사용하여 안전한 예외 처리기를 지정하십시오.  
  
 다음 샘플에서는 C4733 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4733.cpp  
// compile with: /W1 /c  
// processor: x86  
#include "stdlib.h"  
#include "stdio.h"  
void my_handler()  
{  
   printf("Hello from my_handler\n");  
   exit(1);  
}  
  
int main()  
{  
   _asm {  
      push    my_handler  
      mov     eax, DWORD PTR fs:0  
      push    eax  
      mov     DWORD PTR fs:0, esp   // C4733  
   }  
  
   *(int*)0 = 0;  
}  
```