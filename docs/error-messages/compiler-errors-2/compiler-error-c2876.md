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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 428b93ebd4f4a855824d950d920143ee2d171ee7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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