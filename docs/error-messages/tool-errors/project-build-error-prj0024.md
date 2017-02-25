---
title: "프로젝트 빌드 오류 PRJ0024 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0024"
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 프로젝트 빌드 오류 PRJ0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'path' 유니코드 경로를 사용자의 ANSI 코드 페이지로 변환할 수 없습니다.  
  
 ***path*** 는 경로 문자열의 원본 유니코드 버전입니다.  현재 시스템 코드 페이지의 ANSI로 바로 변환할 수 없는 유니코드 경로가 있을 때 이 오류가 발생할 수 있습니다.  
  
 사용자 컴퓨터에 없는 코드 페이지를 사용하는 시스템에서 개발된 프로젝트로 작업하는 경우 이 오류가 발생할 수 있습니다.  
  
 이 오류의 해결책은 ANSI 텍스트를 사용하도록 경로를 업데이트하거나 시스템에 코드 페이지를 설치하고 해당 코드 페이지를 시스템 기본값으로 설정하는 것입니다.