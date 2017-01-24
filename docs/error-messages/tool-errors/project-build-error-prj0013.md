---
title: "프로젝트 빌드 오류 PRJ0013 | Microsoft Docs"
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
  - "PRJ0013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0013"
ms.assetid: 95e7bafd-63c8-4b2d-b778-f19cdf9ba36c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 오류 PRJ0013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시스템 리소스가 심각하게 부족할 수 있습니다.빌드를 시작하는 데 필요한 파이프를 만들 수 없습니다.  
  
 이 오류는 시스템 리소스가 부족함을 나타냅니다.  이 오류를 해결하려면 다른 프로세스\/응용 프로그램의 시스템 리소스 사용을 줄입니다.  
  
 보안 수준이 파이프를 만드는 데 충분하지 않은 경우에도 이 오류가 발생할 수 있습니다\([CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx) 참조\).