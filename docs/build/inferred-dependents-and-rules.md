---
title: "유추된 종속 파일과 규칙 | Microsoft Docs"
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
  - "종속 파일, 유추 상태"
  - "NMAKE의 유추된 종속 파일"
  - "NMAKE의 유추 규칙"
  - "규칙, 유추 상태"
ms.assetid: 9381e74a-53d9-445c-836d-0ff7ef6112d9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 유추된 종속 파일과 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

적용할 수 있는 유추 규칙이 있는 경우 NMAKE는 대상에 대한 유추된 종속 파일을 가정합니다.  다음과 같은 경우 규칙이 적용됩니다.  
  
-   *toext*가 대상의 확장명과 일치하는 경우  
  
-   *fromext*가 대상과 기본 이름이 같고 현재 디렉터리나 지정된 디렉터리에 있는 파일의 확장명과 일치하는 경우  
  
-   *fromext*가 [.SUFFIXES](../build/dot-directives.md)에 있고 일치하는 규칙의 다른 *fromext*에는 상위 **.SUFFIXES** 우선 순위가 없는 경우  
  
-   **.SUFFIXES** 우선 순위가 상위인 명시적 종속 파일이 없는 경우  
  
 유추된 종속 파일을 사용하면 예상치 못한 부수적 효과가 발생할 수 있습니다.  대상의 설명 블록에 명령이 포함되어 있는 경우 NMAKE는 규칙에 포함된 명령 대신 설명 블록의 명령을 실행합니다.  
  
## 참고 항목  
 [유추 규칙](../build/inference-rules.md)