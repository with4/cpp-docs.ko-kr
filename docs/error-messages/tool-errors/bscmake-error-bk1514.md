---
title: "BSCMAKE 오류 BK1514 | Microsoft Docs"
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
  - "BK1514"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1514"
ms.assetid: 7c7e2504-a490-44ab-bb1f-47385ee2f4b0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE 오류 BK1514
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 .SBR 파일이 잘렸습니다. filename에서 찾을 수 없습니다.  
  
 업데이트하기 위해 지정한 모든 .sbr 파일이 원래 찾아보기 정보 파일\(.bsc\)의 일부가 아닙니다.  이 오류를 발생시킨 .sbr 파일의 이름을 보려면 앞에 오는 [BK4502](../../error-messages/tool-errors/bscmake-warning-bk4502.md) 경고를 읽으십시오.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  .sbr 또는 .bsc에 지정한 파일 이름이 잘못되었습니다.  
  
2.  손상된 .bsc 파일을 BSCMAKE에서 다시 빌드해야 합니다.