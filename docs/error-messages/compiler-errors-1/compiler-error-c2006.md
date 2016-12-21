---
title: "컴파일러 오류 C2006 | Microsoft Docs"
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
  - "C2006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2006"
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'directive' : 파일 이름이 와야 하는데 'token'이\(가\) 있습니다.  
  
 [\#include](../../preprocessor/hash-include-directive-c-cpp.md) 또는 [\#import](../../preprocessor/hash-import-directive-cpp.md)와 같은 지시문에는 파일 이름이 필요합니다.  이 오류를 해결하려면 *token*이 유효한 파일 이름이어야 하며,  파일 이름을 큰따옴표나 꺾쇠 괄호로 묶어야 합니다.  
  
 다음 샘플에서는 C2006 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```