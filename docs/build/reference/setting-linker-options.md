---
title: "링커 옵션 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파일[C++], LINK"
  - "입력 파일[C++]"
  - "입력 파일[C++], 링커"
  - "링커[C++], 스위치"
  - "링커[C++], 옵션 설정 방법"
  - "개체/라이브러리 모듈"
ms.assetid: e08fb487-0f2e-4f24-87db-232dbc8bd2e2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 옵션 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

링커 옵션은 개발 환경 내부 또는 외부에서 설정할 수 있습니다.  각 링커 옵션 항목에서는 개발 환경에서 해당 링커 옵션을 설정하는 방법에 대해 설명합니다.  전체 목록은 [링커 옵션](../../build/reference/linker-options.md)을 참조하십시오.  
  
 개발 환경 외부에서 LINK를 실행하면 다음 방법으로 입력을 지정할 수 있습니다.  
  
-   [명령줄](../../build/reference/linker-command-line-syntax.md) 사용  
  
-   [LINK 명령 파일](../../build/reference/link-command-files.md) 사용  
  
-   [LINK 환경 변수](../../build/reference/link-environment-variables.md) 사용  
  
 LINK를 실행하면 LINK 환경 변수에 지정된 옵션이 먼저 처리된 다음 명령줄과 명령 파일에 지정된 옵션이 순서대로 처리됩니다.  서로 다른 인수를 사용하여 동일한 옵션을 반복하는 경우에는 마지막으로 처리된 옵션이 가장 우선합니다.  
  
 옵션은 전체 빌드에 적용되지만 특정 입력 파일에는 옵션이 적용되지 않을 수도 있습니다.  
  
## 참고 항목  
 [C\/C\+\+ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [링커 옵션](../../build/reference/linker-options.md)