---
title: "Compiler Error C3252 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3252"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3252"
ms.assetid: aa9ad096-e9ac-41c7-8ad9-b966751c7c75
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3252
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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