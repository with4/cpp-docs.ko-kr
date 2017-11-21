---
title: "컴파일러 오류 C3668 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3668
dev_langs: C++
helpviewer_keywords: C3668
ms.assetid: 53a96698-bde4-4447-95b5-b5108291f60c
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5db5144aac56112522f7ac707bd1b5f252929dc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3668"></a>컴파일러 오류 C3668
'method': 재정의 지정자 'override' 메서드는 기본 클래스 메서드를 재정의 하지 않았습니다  
  
 존재 하지 않는 함수를 재정의 하려고 하는 함수입니다.  
  
 자세한 내용은 참조 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3668 오류가 발생 합니다.  
  
```  
// C3668.cpp  
// compile with: /c  
__interface I {  
   void f(int);   // virtual by default  
};  
  
class J {  
public:  
   void g(int);  
   virtual void h(int);  
};  
  
struct R : I,J {  
   virtual void f() override {}   // C3668  
   virtual void f(int) override {}   // OK  
  
   virtual void g(int) override {}   // C3668  
   virtual void h(int) override {}   // OK  
};  
```