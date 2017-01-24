---
title: "컴파일러 오류 C3140 | Microsoft Docs"
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
  - "C3140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3140"
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

같은 컴파일 단위에 여러 개의 'module' 특성을 사용할 수 없습니다.  
  
 [module](../../windows/module-cpp.md) 특성은 프로젝트당 한 번만 정의할 수 있습니다.  
  
 다음 샘플에서는 C3140 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3140.cpp  
// compile with: /c  
[emitidl];  
[module(name = "MyLibrary")];  
[module(name = "MyLibrary2")];   // C3140  
```