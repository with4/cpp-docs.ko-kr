---
title: "컴파일러 오류 C2876 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2876
dev_langs:
- C++
helpviewer_keywords:
- C2876
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 84b5609dab6e8f12c5545c2e5c8d64a173cd41ec
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2876"></a>컴파일러 오류 C2876
'class::symbol': 액세스할 수 있는 일부 오버 로드  
  
 모든 오버 로드 된 형태의 기본 클래스의 함수가 파생된 클래스에 액세스할 수 있어야 합니다.  
  
 다음 샘플에서는 C2876 오류가 생성 됩니다.  
  
```  
// C2876.cpp  
// compile with: /c  
class A {  
public:     
   double a(double);  
private:  
   int a(int);  
};  
  
class B : public A {  
   using A::a;   // C2876 one overload is private in base class  
};  
```
