---
title: "컴파일러 오류 C3655 | Microsoft Docs"
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
  - "C3655"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3655"
ms.assetid: 724919ab-2915-4b61-8794-44648e162d62
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3655
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수가 이미 명시적으로 재정의되었습니다.  
  
 함수는 한 번만 명시적으로 재정의할 수 있습니다.  자세한 내용은 [명시적으로 재정의](../../windows/explicit-overrides-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3655 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3655.cpp  
// compile with: /clr /c  
public ref struct B {  
   virtual void f();  
   virtual void g();  
};  
  
public ref struct D : B {  
   virtual void f() new sealed = B::f;  
   virtual void g() new sealed = B::f;   // C3655  
   // try the following line instead  
   // virtual void g() new sealed = B::g;  
};  
```