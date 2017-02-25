---
title: "NMAKE 심각한 오류 U1056 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1056"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1056"
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE 심각한 오류 U1056
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령 처리기를 찾을 수 없습니다.  
  
 **COMSPEC** 또는 **PATH** 환경 변수에서 지정한 경로에 명령 처리기가 없습니다.  
  
 NMAKE는 명령을 실행할 때 COMMAND.COM 또는 CMD.EXE를 명령 처리기로 사용합니다.  먼저 **COMSPEC**에 설정된 경로에서 명령 처리기를 찾습니다.  **COMSPEC**에 없으면 NMAKE는 **PATH**에 지정된 디렉터리를 검색합니다.