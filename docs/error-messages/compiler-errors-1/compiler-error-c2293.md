---
title: "컴파일러 오류 C2293 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2293
dev_langs:
- C++
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0b57daead4d355c81d0d411e37665e453d8f76c1
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
