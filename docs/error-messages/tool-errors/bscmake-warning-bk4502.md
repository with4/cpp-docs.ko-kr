---
title: "BSCMAKE 경고 BK4502 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK4502"
  - "BK1513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1513"
  - "BK4502"
ms.assetid: ee412ec8-df03-4cdb-91ee-5d609ded8691
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# BSCMAKE 경고 BK4502
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.SBR 파일 'filename'\(filename이\(가\) 아님\)이\(가\) 잘렸습니다.  
  
 업데이트하는 동안 원래 .bsc 파일의 일부가 아닌 길이가 0인 .sbr 파일을 지정했습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  지정한 파일 이름이 잘못되었습니다.  
  
2.  파일이 삭제되었습니다 \(오류 [BK1513](../../error-messages/tool-errors/bscmake-error-bk1513.md) 발생\).  
  
3.  파일이 손상되었습니다. BSCMAKE에서 전체를 빌드해야 합니다.