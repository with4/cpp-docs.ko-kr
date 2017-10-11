---
title: "컴파일러 오류 C2088 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2088
dev_langs:
- C++
helpviewer_keywords:
- C2088
ms.assetid: b93f7094-185b-423d-8bb9-507cd757dbf5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a8c99d25995baf6285fe77761c7a054a0512bdfc
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2088"></a>컴파일러 오류 C2088
'operator': ' s-k '에 대 한 잘못 되었습니다.  
  
 구조체 또는 공용 구조체에 대 한 연산자를 정의 하지 않았습니다. 이 오류 C 코드에 대해서만 유효합니다.  
  
 다음 샘플에서는 세 번 C2088를 생성합니다.  
  
```  
// C2088.c  
struct S {  
   int m_i;   
} s;  
  
int main() {  
   int i = s * 1;   // C2088  
   struct S s2 = +s;   // C2088  
   s++;   // C2088  
}  
```
