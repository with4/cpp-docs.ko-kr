---
title: "컴파일러 오류 C3860 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3860
dev_langs:
- C++
helpviewer_keywords:
- C3860
ms.assetid: 1fb5110d-594e-4f1c-8773-888233af1313
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7229392e763450e658fc26762751c732bf743bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3860"></a>컴파일러 오류 C3860
형식 인수 목록에 클래스 형식 이름 다음의 형식 매개 변수 목록에 사용 된 순서 매개 변수를 나열 해야 합니다.  
  
 제네릭 또는 템플릿 인수 목록 형식이 잘못 되었습니다.  
  
 다음 샘플에서는 C3860 오류가 생성 됩니다.  
  
```  
// C3860.cpp  
// compile with: /LD  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T1, T2>::f() {}   // C3860  
```  
  
 해결 방법:  
  
```  
// C3860b.cpp  
// compile with: /c  
template <class T1, class T2>  
struct A {  
   void f();  
};  
  
template <class T2, class T1>  
void A<T2, T1>::f() {}  
```  
  
 C3860은 제네릭을 사용 하는 경우에 발생할 수 있습니다.  
  
```  
// C3860c.cpp  
// compile with: /clr  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,T>::f() {}   // C3860  
```  
  
 해결 방법:  
  
```  
// C3860d.cpp  
// compile with: /clr /c  
generic<class T,class U>  
ref struct GC {  
   void f();  
};  
  
generic<class T, class U>  
void GC<T,U>::f() {}  
```