---
title: "컴파일러 오류 C2912 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2912
dev_langs:
- C++
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88533f00ebf926823d6493aa1027013638694a43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2912"></a>컴파일러 오류 C2912
명시적 특수화 'declaration'이 함수 템플릿의 특수화가 아닙니다.  
  
 비템플릿 함수를 특수화할 수 없습니다.  
  
 다음 샘플에서는 C2912 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2912.cpp  
// compile with: /c  
void f(char);  
template<> void f(char);   // C2912  
template<class T> void f(T);   // OK  
```  
  
 이 오류는 Visual Studio .NET 2003에서 수행된 컴파일러 규칙 작업의 결과로 발생합니다. 모든 명시적 특수화의 경우 기본 템플릿의 매개 변수와 일치하도록 명시적 특수화의 매개 변수를 선택해야 합니다.  
  
```  
// C2912b.cpp  
class CF {  
public:  
   template <class A> CF(const A& a) {}   // primary template  
  
   // attempted explicit specialization  
   template <> CF(const char* p) {}   // C2912  
  
   // try the following line instead  
   // template <> CF(const char& p) {}  
};  
```