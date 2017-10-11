---
title: "컴파일러 오류 C3253 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3253
dev_langs:
- C++
helpviewer_keywords:
- C3253
ms.assetid: da40be26-0f78-4730-8727-ad11cddf8869
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5eae8e6bae423cb24e2a364ef59309d4110ccc49
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3253"></a>컴파일러 오류 C3253
'function': 명시적 재정의에 오류  
  
 명시적 재정의 잘못 지정 되었습니다. 예를 들어 순수으로 지정 하는 재정의 대 한 구현을 지정할 수 없습니다. 자세한 내용은 참조 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3253 오류가 생성 됩니다.  
  
```  
// C3253.cpp  
// compile with: /clr  
public interface struct I {  
   void a();  
   void b();  
   void c();  
};  
  
public ref struct R : I {  
   virtual void a() = 0, I::a {}   // C3253  
   virtual void b() = I::a {}   // OK  
   virtual void c() = 0;   // OK  
};  
```
