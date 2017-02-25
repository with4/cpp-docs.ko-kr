---
title: "NMAKE 심각한 오류 U1064 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1064"
ms.assetid: 7141e66e-cde6-4173-84df-a391f3ebcdd1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# NMAKE 심각한 오류 U1064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MAKEFILE을 찾을 수 없고 대상이 지정되지 않았습니다.  
  
 NMAKE 명령줄은 메이크파일이나 대상을 지정하지 않았으며 현재 디렉터리에 이름이 MAKEFILE인 파일이 없습니다.  
  
 NMAKE에는 메이크파일이나 명령줄 대상\(또는 모두\)이 필요합니다.  NMAKE에서 메이크파일을 사용하려면 \/F 옵션을 지정하거나 현재 디렉터리에 이름이 MAKEFILE인 파일을 배치해야 합니다.  메이크파일이 제공되지 않는 경우 NMAKE는 유추 규칙을 사용하여 명령줄 대상을 만들 수 있습니다.