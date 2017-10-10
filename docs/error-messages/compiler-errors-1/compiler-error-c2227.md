---
title: "컴파일러 오류 C2227 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2227
dev_langs:
- C++
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 57ace27f349eeb32fac0b916979c30cf2bce01c1
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2227"></a>컴파일러 오류 C2227
'->member' 왼쪽은 클래스/구조체/공용 구조체/제네릭 형식을 가리켜야 합니다.  
  
 `->` 왼쪽의 피연산자가 클래스, 구조체 또는 공용 구조체에 대한 포인터가 아닙니다.  
  
 다음 샘플에서는 C2227을 생성합니다.  
  
```  
// C2227.cpp  
int *pInt;  
struct S {  
public:  
    int member;  
} s, *pS = &s;  
  
int main() {  
   pInt->member = 0;   // C2227 pInt points to an int  
   pS->member = 0;   // OK  
}  
```
