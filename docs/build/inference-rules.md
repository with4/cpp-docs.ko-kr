---
title: "유추 규칙 | Microsoft Docs"
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
  - "NMAKE의 유추 규칙"
  - "NMAKE 프로그램, 유추 규칙"
  - "규칙, 유추"
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 유추 규칙
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

유추 규칙은 대상을 업데이트하고 대상에 대한 종속 파일을 유추하는 명령을 제공합니다.  유추 규칙에 포함된 확장명은 기본 이름이 같은 단일 대상 및 종속 파일과 일치합니다.  유추 규칙은 사용자가 정의하거나 미리 정의된 규칙입니다. 미리 정의된 규칙은 다시 정의할 수 있습니다.  
  
 오래된 종속 줄에 명령이 없고 종속 파일의 확장명이 [.SUFFIXES](../build/dot-directives.md)에 포함된 경우 NMAKE는 확장명이 대상 및 현재 디렉터리나 지정된 디렉터리의 기존 파일과 일치하는 규칙을 사용합니다.  기존 파일과 일치하는 규칙이 하나 이상인 경우 **.SUFFIXES** 목록은 사용할 규칙을 지정하며 목록의 우선 순위는 왼쪽이 가장 높고 오른쪽이 가장 낮습니다.  종속 파일이 없고 다른 설명 블록에 대상으로 나열되어 있지 않은 경우 유추 규칙은 기본 이름이 같은 다른 파일로부터 누락된 종속 파일을 만듭니다.  설명 블록의 대상에 종속 파일이나 명령이 없는 경우 유추 규칙이 대상을 업데이트할 수 있습니다.  유추 규칙은 설명 블록이 없는 경우에도 명령줄 대상을 빌드할 수 있습니다.  명시적 종속 파일이 지정된 경우 NMAKE가 유추된 종속 파일에 대한 규칙을 호출할 수도 있습니다.  
  
## 추가 정보  
 [규칙 정의](../build/defining-a-rule.md)  
  
 [일괄 처리 모드 규칙](../build/batch-mode-rules.md)  
  
 [미리 정의된 규칙](../build/predefined-rules.md)  
  
 [유추된 종속 파일과 규칙](../build/inferred-dependents-and-rules.md)  
  
 [유추 규칙의 우선 순위](../build/precedence-in-inference-rules.md)  
  
## 참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)