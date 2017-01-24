---
title: "컴파일러 오류 C2537 | Microsoft Docs"
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
  - "C2537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2537"
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier': 링크 사양이 올바르지 않습니다.  
  
 가능한 원인  
  
1.  링크 지정자가 지원되지 않습니다.  "C" 링크 지정자만 지원됩니다.  
  
2.  오버로드된 함수 집합에서 둘 이상의 함수에 대해 "C" 링크가 지정되었습니다.  이것은 허용되지 않습니다.  
  
 다음 샘플에서는 C2537 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```