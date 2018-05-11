---
title: 컴파일러 경고 (수준 1) C4733 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4733
dev_langs:
- C++
helpviewer_keywords:
- C4733
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 59d702867fb4950b97ee2d2c6249c26229aac975
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4733"></a>컴파일러 경고(수준 1) C4733
인라인 asm 'fs: 0'에 할당: 처리기 안전한 처리기로 등록 되지 않았습니다  
  
 새 예외 핸들러를 추가 하려면 fs: 0에 있는 값을 수정 하는 함수가 안전한 예외에는 작동 하지 않을 수 있습니다 (참조 [/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)).  
  
 이 경고를 해결 하려면 하거나 fs: 0 정의 제거 하거나이 경고 끈 사용 [합니다. SAFESEH](../../assembler/masm/dot-safeseh.md) 안전한 예외 처리기를 지정할 수 있습니다.  
  
 다음 샘플에서는 C4733 오류가 생성 됩니다.  
  
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