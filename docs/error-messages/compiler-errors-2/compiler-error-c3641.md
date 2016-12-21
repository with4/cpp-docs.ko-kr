---
title: "컴파일러 오류 C3641 | Microsoft Docs"
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
  - "C3641"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3641"
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3641
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : \/clr:pure 또는 \/clr:safe로 컴파일한 함수에 대한 호출 규칙 'calling\_convention'이\(가\) 잘못되었습니다.  
  
 [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md)에는 [\_\_clrcall](../../cpp/clrcall.md) 호출 규칙만 사용할 수 있습니다.  
  
 다음 샘플에서는 C3641 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```