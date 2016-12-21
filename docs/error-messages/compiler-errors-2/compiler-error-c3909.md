---
title: "컴파일러 오류 C3909 | Microsoft Docs"
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
  - "C3909"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3909"
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3909
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

WinRT 또는 관리되는 이벤트는 WinRT 또는 관리되는 형식에서만 선언할 수 있습니다.  
  
 Windows 런타임 이벤트 또는 관리되는 이벤트가 네이티브 형식으로 선언되었습니다.  이 오류를 해결하려면 Windows 런타임 형식 또는 관리되는 형식으로 이벤트를 선언합니다.  
  
 자세한 내용은 [event](../../windows/event-cpp-component-extensions.md)를 참조하세요.  
  
 다음 샘플에서는 C3909를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```