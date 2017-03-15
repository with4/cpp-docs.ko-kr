---
title: "프로젝트 빌드 오류 PRJ0035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0035"
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 프로젝트 빌드 오류 PRJ0035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

XML 파일 'file'에 사용자의 ANSI 코드 페이지로 변환할 수 없는 유니코드 내용이 들어 있습니다.  
  
 ***파일의 유니코드 내용***  
  
 ***file*** 은\(는\) 웹 배포 도구의 명령 줄로 만들어지는 XML 파일입니다.  
  
 프로젝트 시스템이 웹 배포 속성 페이지의 일부 속성에서 ANSI로 제대로 변환할 수 없는 유니코드 문자를 찾았습니다.  
  
 이 오류의 해결책은 ANSI를 사용하도록 속성의 내용을 업데이트하거나 시스템에 코드 페이지를 설치하고 해당 코드 페이지를 시스템 기본값으로 설정하는 것입니다.