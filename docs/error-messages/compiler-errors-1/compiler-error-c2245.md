---
title: 컴파일러 오류 C2245 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2245
dev_langs:
- C++
helpviewer_keywords:
- C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c9328c65ce722ea8b1668235810102204ac5512
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170962"
---
# <a name="compiler-error-c2245"></a>컴파일러 오류 C2245
존재하지 않는 멤버 함수 'function'을 Friend로 지정했습니다. 멤버 함수 서명이 오버로드와 일치하지 않습니다.  
  
 컴파일러에서 Friend로 지정된 함수를 찾을 수 없습니다.  
  
 다음 샘플에서는 C2245를 생성합니다.  
  
```  
// C2245.cpp  
// compile with: /c  
class B {  
   void f(int i);  
};  
  
class A {  
   int m_i;  
   friend void B::f(char);   // C2245  
   // try the following line instead  
   // friend void B::f(int);  
};  
  
void B::f(int i) {  
   A a;  
   a.m_i = 0;  
}  
```