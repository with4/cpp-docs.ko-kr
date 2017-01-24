---
title: "컴파일러 오류 C3619 | Microsoft Docs"
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
  - "C3619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3619"
ms.assetid: 76ae80d0-9fbe-4297-a1ef-b1503377fdcf
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되는 형식 또는 WinRT 형식 내에 템플릿을 선언할 수 없습니다.  
  
 관리되는 클래스나 WinRT 클래스 또는 인터페이스에서 클래스 템플릿을 사용할 수 없습니다.  
  
 C3619 오류는 **\/clr:oldSyntax**를 사용해서만 도달할 수 있습니다.  
  
 다음 샘플에서는 C3619 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3619.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class X {  
   template<typename T> class Y {   // C3619  
   };  
};  
```