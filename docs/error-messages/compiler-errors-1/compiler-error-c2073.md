---
title: "컴파일러 오류 C2073 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2073
dev_langs:
- C++
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2503073e960f93cbede95bf54d2d4d1bd079c185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2073"></a>컴파일러 오류 C2073
'identifier': 부분적으로 초기화 된 배열의 요소에는 기본 생성자가 있어야 합니다.  
  
 사용자 정의 형식 또는 상수 배열에 너무 적은 이니셜라이저 지정 했습니다. 명시적 이니셜라이저가 및 해당 생성자가 배열 멤버에 대 한 지정 하지 않은 경우 기본 생성자를 제공 합니다.  
  
 다음 샘플에서는 C2073 오류가 생성 됩니다.  
  
```  
// C2073.cpp  
class A {  
public:  
   A( int );   // constructor for ints only  
};  
A a[3] = { A(1), A(2) };   // C2073, no default constructor  
```  
  
```  
// C2073b.cpp  
// compile with: /c  
class B {  
public:  
   B();   // default constructor declared  
   B( int );  
};  
B b[3] = { B(1), B(2) };   // OK  
```