---
title: "컴파일러 오류 C2794 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2794
dev_langs:
- C++
helpviewer_keywords:
- C2794
ms.assetid: d508191c-9044-4c6a-9119-4bca668c0b93
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5b25829804bf8cb375507550f339022d09951d35
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2794"></a>컴파일러 오류 C2794
'function': 클래스는 직접 또는 간접 기본 클래스의 'class'의 구성원이 아닙니다  
  
 사용 하려는 [super](../../cpp/super.md) 존재 하지 않는 멤버 함수를 호출 합니다.  
  
 다음 샘플에서는 C2794  
  
```  
// C2794.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::f();  // C2794  
   }  
};  
```
