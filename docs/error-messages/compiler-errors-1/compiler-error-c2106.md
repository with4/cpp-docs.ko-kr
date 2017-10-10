---
title: "컴파일러 오류 C2106 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2106
dev_langs:
- C++
helpviewer_keywords:
- C2106
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 36196b87acfd2cd7aa064c414b2e9d0f4a2f7ead
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2106"></a>컴파일러 오류 C2106
'operator': 왼쪽된 피연산자는 l-value 이어야 합니다  
  
 연산자 왼쪽 피연산자로 l 값 있어야 합니다.  
  
 다음 샘플에서는 C2106 오류가 생성 됩니다.  
  
```  
// C2106.cpp  
int main() {  
   int a;  
   1 = a;   // C2106  
   a = 1;   // OK  
}  
```
