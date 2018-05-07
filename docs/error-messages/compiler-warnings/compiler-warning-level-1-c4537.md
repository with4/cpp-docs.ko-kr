---
title: 컴파일러 경고 (수준 1) C4537 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4537
dev_langs:
- C++
helpviewer_keywords:
- C4537
ms.assetid: 9454493c-d419-475e-8f35-9c00233c9329
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c3762d79d5c6937eb23428fe00b86b1489ea869a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4537"></a>컴파일러 경고(수준 1) C4537
'object': 'operator' 비 UDT 형식에 적용  
  
 대 한 참조는 개체 (사용자 정의 형식) 필요한 위치 전달 되었습니다. 참조는 개체는 있지만 인라인 어셈블러 코드로 위해 그 차이 만들 수 없습니다. 컴파일러에서는 코드 처럼 ***개체*** 인스턴스.  
  
 다음 샘플에서는 C4537 오류가 생성 됩니다.  
  
```  
// C4537.cpp  
// compile with: /W1 /c  
// processor: x86  
struct S {  
   int member;  
};  
  
void f1(S &s) {  
   __asm mov eax, s.member;   // C4537  
   // try the following code instead  
   // or, make the declaration "void f1(S s)"  
   /*  
   mov eax, s  
   mov eax, [eax]s.member  
   */  
}  
```