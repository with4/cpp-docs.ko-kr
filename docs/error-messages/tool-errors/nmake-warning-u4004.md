---
title: "NMAKE 경고 U4004 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U4004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4004"
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE 경고 U4004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'targetname' 대상에 대한 규칙이 너무 많습니다.  
  
 단일 콜론\(**:**\)을 구분 기호로 사용하여 둘 이상의 설명 블록을 대상에 지정했습니다.  NMAKE는 첫째 설명 블록에 있는 명령을 실행하고 나머지 블록을 무시했습니다.  
  
 여러 종속성에 동일한 대상을 지정하려면 각 종속성 줄에 이중 콜론\(`::`\)을 구분 기호로 사용합니다.