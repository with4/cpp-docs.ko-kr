---
title: "프로젝트 빌드 오류 PRJ0036 | Microsoft Docs"
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
  - "PRJ0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0036"
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 오류 PRJ0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

웹 배포 도구의 '추가 파일' 속성에 잘못된 항목이 들어 있습니다.  
  
 매크로 확인 문제 때문에 웹 배포 속성 페이지의 추가 파일 속성에 오류가 있습니다.  이 오류는 파일 경로에 사용할 수 없는 문자 또는 문자 조합이 포함되어 경로가 잘못 지정되었음을 의미할 수도 있습니다.  
  
 이 오류를 해결하려면 매크로를 수정하거나 경로 지정을 수정합니다.  확인된 경로는 프로젝트 디렉터리로부터의 절대 경로입니다.  
  
 이 오류는 참조된 파일 중 하나가 존재하지 않음을 의미할 수도 있습니다.