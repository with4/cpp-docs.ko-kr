---
title: "심각한 오류 C1104 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1104"
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

libid를 가져오는 동안 심각한 오류가 발생했습니다. 'message'  
  
 컴파일러가 형식 라이브러리를 가져오는 동안 문제를 발견했습니다.  예를 들어 libid를 사용하여 형식 라이브러리를 지정하고 `no_registry`도 지정할 수는 없습니다.  
  
 자세한 내용은 [\#import 지시문](../../preprocessor/hash-import-directive-cpp.md)을 참조하세요.  
  
 다음 샘플에서는 C1104를 생성합니다.  
  
```  
// C1104.cpp #import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104  
```