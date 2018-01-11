---
title: "컴파일러 오류 C2990 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2990
dev_langs: C++
helpviewer_keywords: C2990
ms.assetid: 674e9f6a-6743-4af0-a7ed-cbe11103a2f8
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94b40071e08dd22c5382e310d27c125f76e1bd6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2990"></a>컴파일러 오류 C2990
'class': 비 클래스 형식으로 이미 클래스 형식으로 선언  
  
 비 제네릭 또는 템플릿 클래스는 제네릭 또는 템플릿 클래스를 재정의합니다. 헤더 파일의 충돌을 확인 합니다.  
  
 다음 샘플에서는 C2990 오류가 생성 됩니다.  
  
```  
// C2990.cpp  
// compile with: /c  
template <class T>  
class C{};  
class C{};   // C2990  
```  
  
 C2990은 제네릭을 사용 하는 경우에 발생할 수 있습니다.  
  
```  
// C2990b.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct GC;  
  
ref struct GC {};   // C2990  
```  
  
 Visual c + + 2005; C2990 Visual c + + 컴파일러의 주요 변경 내용으로 인해 발생할 수 있습니다. 컴파일러는 이제 여러 선언이 동일한 형식에 대 한 템플릿 사양 동일할 필요 합니다.  
  
 다음 샘플에서는 C2990 오류가 생성 됩니다.  
  
```  
// C2990c.cpp  
// compile with: /c  
template<class T>  
class A;  
  
template<class T>  
struct A2 {  
   friend class A;   // C2990  
};  
  
// OK  
template<class T>  
struct B {  
   template<class T>  
   friend class A;  
};  
```