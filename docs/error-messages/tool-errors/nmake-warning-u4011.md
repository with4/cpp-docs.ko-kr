---
title: "NMAKE 경고 U4011 | Microsoft Docs"
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
  - "U4011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U4011"
ms.assetid: e8244514-eba6-4285-8853-7baeefdcd8a4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NMAKE 경고 U4011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'target': 모든 종속 파일을 사용할 수 없습니다. 대상이 빌드되지 않았습니다.  
  
 지정한 대상의 종속 파일이 없거나 변경되었으며 종속 파일을 업데이트하기 위한 명령이 0이 아닌 종료 코드를 반환했습니다.  \/K 옵션을 사용하면 NMAKE는 빌드의 관련되지 않은 부분을 계속 처리하고 NMAKE 세션이 끝나면 종료 코드 1을 발생시킵니다.  
  
 작성 또는 업데이트하지 못한 각 종속 파일에 대해 이 경고는 [U4010](../../error-messages/tool-errors/nmake-warning-u4010.md) 경고 다음에 발생합니다.