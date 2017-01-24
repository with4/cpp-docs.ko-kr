---
title: "링커 도구 경고 LNK4022 | Microsoft Docs"
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
  - "LNK4022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4022"
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 경고 LNK4022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' 기호에만 일치하는 것을 찾을 수 없습니다.  
  
 LINK 또는 LIB는 지정된 데코레이팅되지 않은 기호에 일치하는 것을 여러 개 찾았는데 모호성을 해결하지 못했습니다.  따라서 출력 파일\(.exe, .dll, .exp 또는 .lib\)이 생성되지 않았습니다.  이 경고 다음에는 각 중복 기호에 대한 하나의 경고 [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md)가 오며 마지막으로 심각한 오류인 [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md)가 옵니다.  
  
 이 경고를 방지하려면 기호를 데코레이팅된 형식으로 지정하십시오.  개체에 대해 [DUMPBIN](../../build/reference/dumpbin-options.md)을 실행하여 데코레이팅된 이름을 확인하십시오.