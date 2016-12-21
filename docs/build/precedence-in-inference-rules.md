---
title: "유추 규칙의 우선 순위 | Microsoft Docs"
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
  - "우선 순위, 유추 규칙"
  - "규칙, 유추"
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 유추 규칙의 우선 순위
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

유추 규칙이 여러 개 정의되어 있는 경우 NMAKE는 우선 순위가 최상위인 정의를 사용합니다.  다음 목록은 우선 순위를 최상위에서 최하위 순으로 나타냅니다.  
  
1.  메이크파일에 정의된 유추 규칙, 뒤에 오는 정의가 우선합니다.  
  
2.  Tools.ini에 정의된 유추 규칙, 뒤에 오는 정의가 우선합니다.  
  
3.  미리 정의된 유추 규칙  
  
## 참고 항목  
 [유추 규칙](../build/inference-rules.md)