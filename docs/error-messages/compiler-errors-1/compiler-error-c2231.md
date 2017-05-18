---
title: "컴파일러 오류 C2231 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2231
dev_langs:
- C++
helpviewer_keywords:
- C2231
ms.assetid: 677c5c66-d30f-4c3b-bbb9-760858d56477
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 223af570c50bd4918e9b136c30e9e97971739752
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-error-c2231"></a>컴파일러 오류 C2231
'.': 왼쪽 피연산자를 가리킵니다 s-k '를 사용 하 여 '->'  
  
 멤버 선택 연산 (.)의 왼쪽에 있는 피연산자는 클래스, 구조체 또는 공용 구조체 대신 포인터입니다.  
  
 다음 샘플에서는 C2231을 생성합니다.  
  
```  
// C2231.c  
struct S {  
   int member;  
} s, *ps = &s;  
int main() {  
   ps.member = 0;   // C2231  
  
   // OK  
   ps->member = 0;   // crash  
   s.member = 0;  
}  
```
