---
title: 컴파일러 경고 (수준 4) C4913 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4913
dev_langs:
- C++
helpviewer_keywords:
- C4913
ms.assetid: b94aa52e-6029-4170-9134-017714931546
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbac505559f07e2c58b76970ba33b11a109d90b7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4913"></a>컴파일러 경고(수준 4) C4913
**사용자 정의 이항 연산자 ','가 존재하지만 오버로드가 모든 피연산자를 변환하지 못했습니다. 기본 내장 이항 연산자 ','를 사용합니다.**  
  
 오버로드된 쉼표 연산자도 있는 프로그램에서 기본 제공 쉼표 연산자에 대한 호출이 발생하고 예상했던 변환이 발생하지 않았습니다.  
  
 다음 코드 샘플에서는 C4913을 생성합니다.  
  
```  
// C4913.cpp  
// compile with: /W4  
struct A  
{  
};  
  
struct S  
{  
};  
  
struct B  
{  
   // B() { }  
   // B(S &s) { s; }  
};  
  
B operator , (A a, B b)     
{  
   a;  
   return b;  
}  
  
int main()  
{  
   A a;  
   B b;  
   S s;  
  
   a, b;   // OK calls user defined operator  
   a, s;   // C4913 uses builtin comma operator  
           // uncomment the conversion code in B to resolve.  
}  
```