---
title: 컴파일러 오류 C2111 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2111
dev_langs:
- C++
helpviewer_keywords:
- C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2be4ec3f1637a7397c349323a162a3439f85dcd5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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