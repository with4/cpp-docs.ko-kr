---
title: "프로젝트 빌드 오류 PRJ0050 | Microsoft Docs"
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
  - "PRJ0050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0050"
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 오류 PRJ0050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

출력을 등록하지 못했습니다.레지스트리를 수정할 수 있는 권한이 있는지 확인하십시오.  
  
 Visual C\+\+ 빌드 시스템에서 빌드 출력\(.dll 또는 .exe\)을 등록할 수 없습니다.  레지스트리를 수정하려면 관리자로 로그온해야 합니다.  
  
 .dll을 빌드하는 경우 regsvr32.exe를 사용하여 .dll을 수동으로 등록해 볼 수 있습니다. 이렇게 하면 빌드가 실패한 이유를 설명하는 정보가 표시됩니다.  
  
 .dll을 빌드하지 않는 경우에는 오류를 발생시킨 명령에 대한 빌드 로그를 검토하십시오.