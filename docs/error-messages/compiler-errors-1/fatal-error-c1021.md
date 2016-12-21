---
title: "심각한 오류 C1021 | Microsoft Docs"
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
  - "C1021"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1021"
ms.assetid: e23171f4-ca6b-40c0-a913-a2edc6fa3766
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1021
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'string' 전처리기 명령이 잘못되었습니다.  
  
 `string`은 유효하지 않은 [전처리기 지시문](../../preprocessor/preprocessor-directives.md)입니다. 오류를 해결하려면 `string`에 대해 올바른 전처리기 이름을 사용합니다.  
  
 다음 샘플에서는 C1021을 생성합니다.  
  
```  
// C1021.cpp #BadPreProcName    // C1021 delete line  
```