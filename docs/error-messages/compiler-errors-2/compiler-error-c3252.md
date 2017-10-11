---
title: "컴파일러 오류 C3252 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3252
dev_langs:
- C++
helpviewer_keywords:
- C3252
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2123ad376530868afa1bacc987341905617e766b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3252"></a>컴파일러 오류 C3252
'method': 관리되는 형식 또는 WinRT 형식에서 가상 메서드의 접근성을 줄일 수 없습니다.  
  
 기본 클래스에서 가상 메서드를 구현하거나 인터페이스에서 메서드를 구현하는 클래스는 해당 메서드에 대한 액세스를 줄일 수 없습니다.  
  
 인터페이스의 모든 메서드는 공용입니다.  
  
 다음 샘플에서는 C3252 오류가 발생하는 경우 및 이를 해결 방법을 보여 줍니다.  
  
```  
// C3252.cpp  
// compile with: /clr /c  
ref class A {  
public:  
   virtual void f1() {}  
};  
  
ref class B : public A {  
// To fix, uncomment the following line:   
// public:      
   virtual void f1() override sealed {}   // C3252, make this method public  
};  
```
