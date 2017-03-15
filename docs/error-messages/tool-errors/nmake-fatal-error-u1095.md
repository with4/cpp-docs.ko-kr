---
title: "NMAKE 심각한 오류 U1095 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1095"
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE 심각한 오류 U1095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'commandline' 확장 명령줄이 너무 깁니다.  
  
 매크로 확장 이후 지정한 명령줄이 운영 체제의 명령줄 길이 제한을 초과했습니다.  
  
 MS\-DOS는 명령줄에 128문자까지 허용합니다.  
  
 파일에서 명령줄 입력을 받아 들일 수 있는 프로그램용 명령의 경우 해당 명령을 변경하여 디스크에 있는 파일이나 인라인 파일에서 입력을 제공하십시오.  예를 들어, LINK와 LIB는 지시 파일로부터 입력을 받습니다.