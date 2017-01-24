---
title: "프로젝트 빌드 오류 PRJ0009 | Microsoft Docs"
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
  - "PRJ0009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0009"
ms.assetid: 89291778-cda4-495d-983f-ddcc06dfc98b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로젝트 빌드 오류 PRJ0009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

빌드 로그를 열 수 없습니다.  
  
 **파일이 열려 있거나 쓰기 금지되어 있는지 확인하십시오.**  
  
 **빌드 로깅** 속성을 **예**로 설정하고 빌드 또는 재빌드를 수행한 후 Visual C\+\+에서 빌드 로그를 단독 모드로 열 수 없습니다.  
  
 **도구** 메뉴에서 **옵션** 명령을 클릭하여 **옵션** 대화 상자를 연 다음 **프로젝트** 폴더의 **VC\+\+ 빌드**를 선택하여 **빌드 로깅** 설정을 확인합니다.  빌드 파일은 BuildLog.htm이라고 하며 중간 디렉터리 $\(IntDir\)에 저장됩니다.  
  
 이 오류의 가능한 이유는 다음과 같습니다.  
  
-   두 가지 Visual C\+\+ 프로세스를 실행하고 있으며 같은 프로젝트의 동일한 구성을 동시에 빌드하려고 했습니다.  
  
-   파일을 잠그는 프로세스에 따라 빌드 로그 파일을 열었습니다.  
  
-   사용자에게 파일을 만들 수 있는 권한이 없습니다.  
  
-   현재 사용자에게 BuildLog.htm 파일에 대한 쓰기 권한이 없습니다.