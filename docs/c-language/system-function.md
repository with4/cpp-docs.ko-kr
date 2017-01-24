---
title: "시스템 함수 | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "시스템 함수"
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 시스템 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 4.10.4.5 system** 함수에 의한 문자열의 실행 모드 및 내용  
  
 **시스템** 함수는 명령줄이 아닌 C 프로그램 내에서 내부 운영 체제 명령 또는 .EXE, .COM\(Windows NT에서는 .CMD\) 또는 .BAT 파일을 실행합니다.  
  
 시스템 함수는 명령 해석기를 찾습니다. 일반적으로 명령 해석기는 Windows NT 운영 체제에서 CMD.EXE, Windows에서는 COMMAND.COM을 찾습니다.   그런 다음 시스템 함수는 인수 문자열을 명령 해석기에 전달합니다.  
  
 자세한 내용은 [system, \_wsystem](../c-runtime-library/reference/system-wsystem.md)을 참조하십시오.  
  
## 참고 항목  
 [라이브러리 함수](../c-language/library-functions.md)