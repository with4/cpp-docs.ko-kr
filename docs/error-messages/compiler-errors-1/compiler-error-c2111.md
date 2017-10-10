---
title: "컴파일러 오류 C2111 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2111
dev_langs:
- C++
helpviewer_keywords:
- C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 02c2783f156fbdd0c805c0dff71e53a681dc3327
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2111"></a>컴파일러 오류 C2111
'+': 포인터 더하기에는 정수 계열 피연산자가 있어야 합니다.  
  
 더하기( `+` ) 연산자를 사용하여 포인터에 정수 계열이 아닌 값을 추가하려고 했습니다.  
  
 다음 샘플에서는 C2111을 생성합니다.  
  
```  
// C2111.cpp  
int main() {  
   int *a = 0, *pa = 0, b = 0;  
   double d = 0.00;  
  
   a = pa + d;   // C2111  
   a = pa + b;   // OK  
}  
```
