---
title: "컴파일러 오류 C2245 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2245
dev_langs: C++
helpviewer_keywords: C2245
ms.assetid: 08aaeadf-10ec-485a-b2a6-6e775289082b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc7a27aba6326fddea9684562fbab7f824f6f628
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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