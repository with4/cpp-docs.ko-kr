---
title: "링커 도구 오류 LNK2023 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2023"
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 오류 LNK2023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\<dll 또는 entry point\> 진입점이 잘못되었습니다.  
  
 링커가 잘못된 버전의 msobj90.dll을 로드하고 있습니다.  경로에 있는 link.exe와 msobj90.dll의 버전은 동일해야 합니다.  
  
 msobj90.dll의 종속성이 없을 수 있습니다.  msobj90.dll의 종속성 목록은 다음과 같습니다.  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 컴퓨터에 msobj90.dll의 최신 버전이 아닌 다른 복사본이 있는지 확인하십시오.