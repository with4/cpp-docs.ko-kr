---
title: "NMAKE 경고 U4010 | Microsoft Docs"
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
  - "U4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4010"
ms.assetid: 99d8eb9a-ae31-40d1-b8c5-8c66732127d3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 경고 U4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'target': 빌드하지 못했습니다. \/K를 지정하고 계속합니다.  
  
 지정한 대상에 대한 명령 블록의 명령이 0이 아닌 종료 코드를 반환했습니다.  \/K 옵션을 사용하면 NMAKE는 빌드의 관련되지 않은 부분을 계속 처리하고 NMAKE 세션이 끝나면 종료 코드 1을 발생시킵니다.  
  
 지정한 대상 자체가 다른 대상에 종속될 경우 NMAKE는 이 경고 다음에 [U4011](../../error-messages/tool-errors/nmake-warning-u4011.md) 경고를 발생시킵니다.