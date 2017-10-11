---
title: "컴파일러 오류 C2572 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2572
dev_langs:
- C++
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a0825883dae30dcee267f09322467590a6a405cd
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

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
