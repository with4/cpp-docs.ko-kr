---
title: "심각한 오류 C1033 | Microsoft Docs"
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
  - "C1033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1033"
ms.assetid: 09976c03-8450-4cf7-8b43-1b91c2c2b9f9
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pdb 프로그램 데이터베이스를 열 수 없습니다.  
  
 이 오류는 디스크 문제로 인해 발생할 수 있습니다.  
  
 Visual C\+\+ .NET 2002에서 파일 이름 또는 파일 이름의 디렉터리 경로에 MBCS 문자가 포함된 경우에 사용자 로캘을 올바르게 설정해야 합니다.  시스템 로캘 설정이 충분하지 않은 경우에는 MBCS 문자를 처리하도록 사용자 로캘을 설정해야 합니다.  
  
 더 많은 정보를 위해 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;246007](http://support.microsoft.com/default.aspx?scid=kb;en-us;246007)을 참조하십시오.