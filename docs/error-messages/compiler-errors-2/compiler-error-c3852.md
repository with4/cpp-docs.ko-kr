---
title: 컴파일러 오류 C3852 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3852
dev_langs:
- C++
helpviewer_keywords:
- C3852
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 439e6518c1e1f94918671f2e710ccf1a86621f16
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3852"></a>컴파일러 오류 C3852
'type' 형식이 있는 ' member': 집합체 초기화에서이 멤버를 초기화할 수 없습니다  
  
 집합체 초기화의 일부로 집합체 초기화에서 기본 초기화를 받을 수 없는 데이터 멤버에 게 기본 초기화를 할당 하려고 했습니다.  
  
 다음 샘플에서는 c3852:  
  
```  
// C3852.cpp  
struct S  
{  
   short s;  
};  
  
struct S1  
{  
   int i;  
   const S s;  
};  
  
struct S2  
{  
   int i;  
   char & rc;  
};  
  
int main()  
{  
   S1 s1 = { 1 };   // C3852 const member   
   // try the following line instead  
   // S1 s1 = { 1, 2 };  
  
   S2 s2 = { 2 };   // C3852 reference member  
   // try the following line instead  
   // char c = 'a';  
   S2 s2 = { 2, c };  
}  
```