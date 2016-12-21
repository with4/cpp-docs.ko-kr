---
title: "프로젝트 빌드 오류 PRJ0025 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0025"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0025"
ms.assetid: 57725c78-bc63-44f3-9667-2969b2d7c41d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 오류 PRJ0025
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file' 배치 파일에 사용자의 ANSI 코드 페이지로 변환할 수 없는 유니코드 내용이 있습니다.  
  
 ***파일의 유니코드 내용***  
  
 프로젝트 시스템이 사용자 지정 빌드 규칙이나 빌드 이벤트에서 사용자의 현재 ANSI 코드 페이지로 제대로 변환할 수 없는 유니코드 내용을 발견했습니다.  
  
 이 오류를 해결하려면 ANSI를 사용하도록 빌드 규칙이나 빌드 이벤트의 내용을 업데이트하거나, 시스템에 코드 페이지를 설치하고 해당 코드 페이지를 시스템 기본값으로 설정하는 것입니다.  
  
 사용자 지정 빌드 단계와 빌드 이벤트에 대한 자세한 내용은 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../../ide/understanding-custom-build-steps-and-build-events.md)를 참조하십시오.