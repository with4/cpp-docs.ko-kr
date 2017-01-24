---
title: "컴파일러 오류 C3389 | Microsoft Docs"
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
  - "C3389"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3389"
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3389
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/clr:pure 또는 \/clr:safe를 지정하면 \_\_declspec\(keyword\)를 사용할 수 없습니다.  
  
 [\_\_declspec](../../cpp/declspec.md) 한정자는 프로세스 상태별로 사용됩니다.  [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md)는 [appdomain](../../cpp/appdomain.md) 상태별로 적용됩니다.  따라서 `keyword` **\_\_declspec** 한정자를 사용하여 변수를 선언하고 **\/clr:pure**를 사용하여 컴파일할 수 없습니다.  
  
 다음 샘플에서는 C3389 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```