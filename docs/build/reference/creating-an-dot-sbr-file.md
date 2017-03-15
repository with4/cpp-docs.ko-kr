---
title: ".Sbr 파일 만들기 | Microsoft Docs"
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
  - ".sbr 파일"
  - "BSCMAKE, 입력 파일"
  - "찾아보기 정보의 로컬 기호"
  - "SBR 파일"
  - "소스 브라우저 파일"
  - "기호"
ms.assetid: bdb4b93c-a88a-441a-84fd-01087d03be25
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .Sbr 파일 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

BSCMAKE의 입력 파일은 .sbr 파일입니다.  컴파일러는 컴파일하는 각 개체 파일\(.obj\)에 대해 .sbr 파일을 만듭니다.  찾아보기 정보 파일을 빌드하거나 업데이트하는 경우 프로젝트의 모든 .sbr 파일이 디스크에 있어야 합니다.  
  
 가능한 모든 정보를 포함하여 .sbr 파일을 만들려면 [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)를 지정합니다.  
  
 로컬 기호를 포함하지 않는 .sbr 파일을 만들려면 [\/Fr](../../build/reference/fr-fr-create-dot-sbr-file.md)를 지정합니다.  .sbr 파일에 로컬 기호가 있는 경우 BSCMAKE의 [\/El 옵션](../../build/reference/bscmake-options.md)을 사용하여 .bsc 파일에서 로컬 기호를 생략할 수 있습니다`.`  
  
 전체 컴파일을 수행하지 않고 .sbr 파일을 만들 수 있습니다.  예를 들어 컴파일러에 \/Zs 옵션을 지정하여 구문 검사를 수행하고 \/FR 또는 \/Fr를 지정하면 전체 컴파일과 마찬가지로 .sbr 파일을 만들 수 있습니다.  
  
 .sbr 파일을 처음 패킹하여 참조되지 않은 정의를 제거하면 빌드 과정을 더 효율적으로 진행할 수 있습니다.  컴파일러는 .sbr 파일을 자동으로 패킹합니다.  
  
## 참고 항목  
 [.Bsc 파일 빌드](../../build/reference/building-a-dot-bsc-file.md)