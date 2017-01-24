---
title: "링커 도구 오류 LNK1158 | Microsoft Docs"
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
  - "LNK1158"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1158"
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1158
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename'을\(를\) 실행할 수 없습니다.  
  
 [LINK](../../build/reference/linker-command-line-syntax.md)에 의해 호출된 지정된 실행 파일이 LINK를 포함하는 디렉터리 또는 PATH 환경 변수에 지정한 디렉터리에 없습니다.  
  
 예를 들어, 32비트 운영 체제를 사용하는 컴퓨터에서 [\/LTCG](../../build/reference/ltcg-link-time-code-generation.md) 링커 옵션에 PGOPTIMIZE 매개 변수를 사용하려고 하면 이 오류가 발생합니다.