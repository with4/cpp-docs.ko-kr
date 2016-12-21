---
title: "링커 도구 오류 LNK1200 | Microsoft Docs"
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
  - "LNK1200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1200"
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 프로그램 데이터베이스를 읽는 동안 오류가 발생했습니다.  
  
 PDB\(프로그램 데이터베이스\)가 읽지 못했습니다.  
  
 이 오류는 파일이 손상된 경우에 발생할 수 있습니다.  
  
 `filename`이 개체 파일의 PDB인 경우 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)를 사용하여 개체 파일을 다시 컴파일하십시오.  
  
 `filename`이 기본 출력 파일의 PDB이며 증분 링크 중에 이 오류가 발생하면 PDB를 삭제하고 다시 링크하십시오.