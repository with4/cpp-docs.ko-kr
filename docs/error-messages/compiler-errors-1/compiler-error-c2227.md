---
title: 컴파일러 오류 C2227 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2227
dev_langs:
- C++
helpviewer_keywords:
- C2227
ms.assetid: d470e8b8-7e15-468b-84fa-37d1a0132271
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6a23d055dec45693f292978039c5c5108e34e7a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169090"
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