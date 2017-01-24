---
title: "NMAKE 심각한 오류 U1100 | Microsoft Docs"
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
  - "U1100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1100"
ms.assetid: c71910a7-c581-4d9c-a38c-d2d557d56289
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 심각한 오류 U1100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'macroname' 매크로는 'rule' 일괄 처리 규칙의 컨텍스트에서 잘못되었습니다.  
  
 NMAKE는 배치 모드 규칙의 명령 블록이 $\<가 아닌 특수한 파일 매크로를 직접적 또는 간접적으로 참조할 때 이 오류를 생성합니다.  
  
 배치 모드 규칙에는 $\< 매크로만 사용할 수 있습니다.