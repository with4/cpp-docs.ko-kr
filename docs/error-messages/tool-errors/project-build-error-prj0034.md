---
title: "프로젝트 빌드 오류 PRJ0034 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0034"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0034"
ms.assetid: 1da4a55b-231b-4476-8545-6997628fbc00
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 프로젝트 빌드 오류 PRJ0034
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로젝트 수준의 사용자 지정 빌드 단계의 '추가 종속성' 속성에 'macro'\('macro\_expansion'\(으\)로 확인됨\)이\(가\) 들어 있습니다.  
  
 매크로 확인 문제 때문에 프로젝트의 사용자 지정 빌드 단계의 추가 종속성에 오류가 있습니다.  이 오류는 파일 경로에 사용할 수 없는 문자 또는 문자 조합이 포함되어 경로가 잘못 지정되었음을 의미할 수도 있습니다.  
  
 이 오류를 해결하려면 매크로를 수정하거나 경로 지정을 수정합니다.  확인된 경로는 프로젝트 디렉터리로부터의 절대 경로입니다.