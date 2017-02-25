---
title: "유추된 종속 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "종속 파일, 유추 상태"
  - "NMAKE의 유추된 종속 파일"
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 유추된 종속 파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

유추된 종속 파일은 유추 규칙에서 파생되며 명시적 종속 파일 전에 계산됩니다.  유추된 종속 파일이 대상에 대하여 오래된 경우 NMAKE는 종속 줄에 대한 명령 블록을 호출합니다.  유추된 종속 파일이 없거나 자신의 종속 파일에 대하여 오래된 경우 NMAKE는 먼저 유추된 종속 파일을 업데이트합니다.  유추된 종속 파일에 대한 자세한 내용은 [유추 규칙](../build/inference-rules.md)을 참조하십시오.  
  
## 참고 항목  
 [종속 파일](../build/dependents.md)