---
title: "심각한 오류 C1305 | Microsoft Docs"
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
  - "C1305"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1305"
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1305
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pgd\_file' 프로필 데이터베이스는 다른 아키텍처용입니다.  
  
 다른 플랫폼에 대한 \/LTCG:PGINSTRUMENT 작업으로 생성된 .pgd 파일을 [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)에 전달했습니다.  [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md) 는 x86 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 플랫폼에 사용할 수 있습니다.  그러나 한 플랫폼에 대한 \/LTCG:PGINSTRUMENT 작업으로 생성된 .pgd 파일을 다른 플랫폼에 대한 \/LTCG:PGOPTIMIZE에 입력으로 사용할 수 없습니다.  
  
 이 오류를 해결하려면 \/LTCG:PGINSTRUMENT로 생성된 .pgd 파일을 동일한 플랫폼에서만 \/LTCG:PGOPTIMIZE에 전달해야 합니다.