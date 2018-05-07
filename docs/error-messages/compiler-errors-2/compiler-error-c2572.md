---
title: 컴파일러 오류 C2572 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2572
dev_langs:
- C++
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f2211137361d9de86397c333e51abf0a903ff67
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2572"></a>컴파일러 오류 C2572
'class::member': 기본 매개 변수 재정의: 매개 변수 param  
  
 기본 매개 변수를 재정의할 수 없습니다. 필요 하면 다른 값의 기본 매개 변수는 매개 변수에 대 한 왼쪽을 정의 하지 않아야 합니다.  
  
 다음 샘플에서는 C2572 오류가 생성 됩니다.  
  
```  
// C2572.cpp  
// compile with: /c  
void f(int i = 1);   // function declaration  
  
// function definition  
void f(int i = 1) {}   // C2572  
  
// try the following line instead  
// void f(int i) {}  
```