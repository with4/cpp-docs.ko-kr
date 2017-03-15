---
title: "링커 도구 오류 LNK1140 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1140"
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 링커 도구 오류 LNK1140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램 데이터베이스에 대한 모듈이 너무 많습니다. \/PDB:NONE으로 링크합니다.  
  
 프로젝트에 있는 모듈이 4096개를 넘습니다.  
  
### 문제를 해결하려면 다음과 같은 해결책을 사용해 보십시오.  
  
1.  [\/PDB:NONE](../../build/reference/pdb-use-program-database.md)을 사용하여 다시 링크합니다.  
  
2.  정보를 디버깅하지 않은 상태로 일부 모듈을 컴파일합니다.  
  
3.  모듈 개수를 줄입니다.