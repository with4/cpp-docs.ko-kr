---
title: 컴파일러 오류 C2293 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2293
dev_langs:
- C++
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6b3f395199a1621d507683aa6c79b1212888145
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2293"></a>컴파일러 오류 C2293
'identifier': 멤버 변수를 __based 지정자로 사용할 수 없습니다.  
  
 `__based` 한정자에 대한 지정자는 비멤버 포인터여야 합니다.  
  
 다음 샘플에서는 C2293을 생성합니다.  
  
```  
// C2293.cpp  
// compile with: /c  
class A {  
   static int *i;  
   void __based(i) *bp;   // C2293  
   void *bp2;   // OK  
};  
```