---
title: ".DOSSEG | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".DOSSEG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".DOSSEG directive"
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .DOSSEG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

세그먼트 세그먼트 MS\-DOS 규칙에 따라 정렬: 코드 먼저 않은 DGROUP에서 다음 세그먼트와 다음 세그먼트 DGROUP에서.  
  
## 구문  
  
```  
  
.DOSSEG  
  
```  
  
## 설명  
 이 순서에 있는 DGROUP 세그먼트에 따라: 세그먼트에 BSS 또는 스택, BSS 세그먼트가 및 스택 세그먼트입니다.  독립 실행형 프로그램을 MASM에서 CodeView 지원 되도록 하는 데 주로 사용 합니다.  다른 이름으로 동일한  [DOSSEG](../../assembler/masm/dosseg.md).  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)