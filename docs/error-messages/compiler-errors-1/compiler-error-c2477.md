---
title: "컴파일러 오류 C2477 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2477
dev_langs:
- C++
helpviewer_keywords:
- C2477
ms.assetid: 60bc324b-6605-4833-8099-a291efc712e7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 72b83b09ec97a2e7e68b2ee28429eeb31567178c
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2477"></a>컴파일러 오류 C2477
'member': 파생된 클래스를 통해 정적 데이터 멤버를 초기화할 수 없습니다  
  
 템플릿 클래스의 정적 데이터 멤버를 잘못 초기화 되었습니다. ISO c + + 표준을 따르려면 버전 Visual Studio.NET 2003 이전 Visual c + + 컴파일러의 주요 변경 내용입니다.  
  
 다음 샘플에서는 C2477 오류가 생성 됩니다.  
  
```  
// C2477.cpp  
// compile with: /Za /c  
template <class T>  
struct S {  
   static int n;  
};  
  
struct X {};  
struct A: S<X> {};  
  
int A::n = 0;   // C2477  
  
template<>  
int S<X>::n = 0;  
```
