---
title: "컴파일러 오류 C3734 | Microsoft Docs"
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
  - "C3734"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3734"
ms.assetid: 4e2afdcc-7da9-45a1-9c96-85f25e2986e8
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3734
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': 관리되는 클래스 또는 WinRT 클래스에는 coclass를 사용할 수 없습니다.  
  
 [coclass](../../windows/coclass.md) 특성은 관리되는 클래스 또는 WinRT 클래스에서 사용할 수 없습니다.  
  
 다음 샘플에서는 C3734를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3734.cpp  
// compile with: /clr /c  
[module(name="x")];  
  
[coclass]  
ref class CMyClass {   // C3734 remove the ref keyword to resolve  
};  
```  
  
 다음 샘플에서는 C3734를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3734_b.cpp  
// compile with: /clr:oldSyntax /c  
[module(name="x")];  
  
[coclass]  
__gc class CMyClass {   // C3734 remove the __gc keyword to resolve  
};  
```