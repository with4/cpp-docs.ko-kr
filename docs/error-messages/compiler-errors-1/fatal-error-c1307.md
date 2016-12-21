---
title: "심각한 오류 C1307 | Microsoft Docs"
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
  - "C1307"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1307"
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1307
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로필 데이터가 수집된 이후 프로그램이 편집되었습니다.  
  
 [\/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)를 사용할 때 \/LTCG:PGINSTRUMENT 이후 다시 컴파일된 입력 모듈을 링커가 발견했습니다. 이 모듈은 기존 프로필 데이터가 더는 관련되지 않은 지점까지 변경되었습니다.  예를 들어, 다시 컴파일된 모듈에서 호출 그래프가 변경된 경우 컴파일러에서 C1307이 발생합니다.  
  
 이 오류를 해결하려면 \/LTCG:PGINSTRUMENT를 실행하고 모든 테스트 실행을 다시 수행한 다음 \/LTCG:PGOPTIMIZE를 실행해야 합니다.  \/LTCG:PGINSTRUMENT를 실행하고 모든 테스트 실행을 다시 수행할 수 없는 경우 \/LTCG:PGOPTIMIZE 대신 \/LTCG:PGUPDATE를 사용하여 최적화된 이미지를 만듭니다.