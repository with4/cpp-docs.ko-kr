---
title: "의사 대상 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메이크파일, 의사 대상"
  - "NMAKE 프로그램, 의사 대상"
  - "NMAKE 프로그램, 대상"
  - "의사 대상 및 NMAKE"
  - "타임스탬프, 메이크파일 의사 대상"
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 의사 대상
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

의사 대상은 종속 줄에 파일 이름 대신 사용하는 레이블입니다.  의사 대상은 존재하지 않는 파일로 해석되므로 오래된 것입니다.  NMAKE는 의사 대상의 타임스탬프가 모든 종속 파일의 타임스탬프 중 가장 최근이라고 가정합니다.  종속 파일이 없는 경우 타임스탬프를 현재 시간으로 가정합니다.  의사 대상이 대상으로 사용된 경우 의사 대상의 명령은 항상 실행됩니다.  또, 종속 파일로 사용된 의사 대상도 다른 종속 줄에 대상으로 나타나야 합니다.  그러나 해당 종속 줄에는 명령 블록이 없어도 됩니다.  
  
 의사 대상 이름은 대상에 대한 파일 이름 구문 규칙을 따릅니다.  그러나 이름에 확장명이 없는 경우\(즉 마침표가 포함되지 않은 경우\) 의사 대상 이름은 파일 이름에 대한 8자 제한을 초과하여 256자까지 사용할 수 있습니다.  
  
## 참고 항목  
 [대상](../build/targets.md)