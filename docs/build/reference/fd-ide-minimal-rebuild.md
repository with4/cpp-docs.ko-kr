---
title: "/FD(IDE 최소 재빌드) | Microsoft Docs"
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
  - "/FD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FD 컴파일러 옵션[C++]"
  - "FD 컴파일러 옵션[C++]"
  - "-FD 컴파일러 옵션[C++]"
ms.assetid: 7ef21b8c-a448-4bb4-9585-a2a870028e17
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FD(IDE 최소 재빌드)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/Gm\(최소 다시 빌드 사용\)](../../build/reference/gm-enable-minimal-rebuild.md)도 같이 선택하지 않은 경우에만 **\/FD**는 C\+\+ 프로젝트의 **속성 페이지** 대화 상자에 있는 [명령줄](../../ide/command-line-property-pages.md) 속성 페이지를 제외하고 사용자에게 노출되지 않습니다.  **\/FD** 옵션은 개발 환경에서만 적용됩니다.  **\/FD**는 **cl \/?**의 출력에 영향을 주지 않습니다.  
  
 개발 환경에서 **\/Gm**을 사용하지 않으면 **\/FD**가 사용됩니다.  **\/FD**를 사용하면 .idb 파일에 충분한 종속성 정보가 포함됩니다.  **\/FD**는 개발 환경에서만 사용되며, 명령줄이나 빌드 스크립트에서 사용해서는 안 됩니다.  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)