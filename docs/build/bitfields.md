---
title: "비트 필드 | Microsoft Docs"
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
  - "비트 필드"
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 비트 필드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

구조체 비트 필드는 64비트로 제한되어 있으며 그 형식은 signed int, unsigned int, int64 또는 unsigned int64가 될 수 있습니다.  형식 경계에 걸쳐 있는 비트 필드는 비트를 생략하고 비트 필드를 다음 형식 맞춤에 정렬합니다.  예를 들어, 정수 비트 필드는 32비트 경계를 넘어설 수 없습니다.  
  
## 참고 항목  
 [형식 및 저장소](../build/types-and-storage.md)