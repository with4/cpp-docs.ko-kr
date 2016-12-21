---
title: "컴파일러 오류 C2812 | Microsoft Docs"
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
  - "C2812"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2812"
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2812
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/clr:pure 및 \/clr:safe를 지정하면 \#import를 사용할 수 없습니다.  
  
 [\#import 지시문](../../preprocessor/hash-import-directive-cpp.md)은 **\/clr:pure** 및 **\/clr:safe**와 함께 사용할 수 없습니다. `#import`에는 네이티브 컴파일러 지원 라이브러리를 사용해야 하기 때문입니다.  
  
## 예제  
 다음 샘플에서는 C2812 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```