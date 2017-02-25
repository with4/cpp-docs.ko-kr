---
title: "링커 도구 오류 LNK1264 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1264"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1264"
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 링커 도구 오류 LNK1264
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/LTCG:PGINSTRUMENT가 지정되었지만 코드를 생성하지 않아도 됩니다. 계측하지 못했습니다.  
  
 **\/LTCG:PGINSTRUMENT**가 지정되었지만 [\/GL](../../build/reference/gl-whole-program-optimization.md)로 컴파일한 .obj 파일이 없습니다.  계측을 발생시킬 수 없으며 링크하지 못했습니다.  계측을 발생시키려면 **\/GL**로 컴파일한 .obj 파일이 명령줄에 하나 이상 있어야 합니다.  
  
 PGO\(프로필 기반 최적화\)는 64비트 컴파일러에서만 사용할 수 있습니다.