---
title: "링커 도구 오류 LNK1277 | Microsoft Docs"
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
  - "LNK1277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1277"
ms.assetid: afca3de0-50cc-4140-af7a-13493a170835
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pgd \(filename\)에서 개체 레코드를 찾을 수 없습니다.  
  
 [\/LTCG:PGOPTIMZE](../../build/reference/ltcg-link-time-code-generation.md)를 사용할 때 .lib, def 또는 .obj 입력 파일 중 하나의 경로가 \/LTCG:PGINSTRUMENT를 사용하는 동안 이들 파일이 발견된 경로와 다릅니다.  \/LTCG:PGINSTRUMENT 이후에 LIB 환경 변수를 변경했기 때문일 수 있습니다.  입력 파일의 전체 경로가 .pgd 파일에 저장됩니다.  
  
 \/LTCG:PGOPTIMIZE를 사용하려면 입력 항목이 \/LTCG:PGINSTRUMENT 단계와 동일해야 합니다.  
  
 이 경고를 해결하려면 다음 중 하나를 수행하십시오.  
  
-   \/LTCG:PGINSTRUMENT를 실행하고 모든 테스트 실행을 다시 수행한 다음 \/LTCG:PGOPTIMIZE를 실행합니다.  
  
-   \/LTCG:PGINSTRUMENT를 실행할 때의 상태로 LIB 환경 변수를 변경합니다.  
  
 LNK1277 오류를 해결하기 위해 \/LTCG:PGUPDATE는 사용하지 않는 것이 좋습니다.