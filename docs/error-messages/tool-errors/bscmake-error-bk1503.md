---
title: "BSCMAKE 오류 BK1503 | Microsoft Docs"
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
  - "BK1503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1503"
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE 오류 BK1503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 파일에 쓸 수 없습니다. \[: reason\]  
  
 BSCMAKE는 컴파일하는 동안 생성된 .sbr 파일을 하나의 브라우저 데이터베이스로 결합합니다.  이 오류는 결과 브라우저 데이터베이스가 64MB를 초과하거나 입력 파일\(.sbr\)의 개수가 4092를 초과하는 경우에 발생합니다.  
  
 4092개 이상의 .sbr 파일 때문에 이 문제가 발생한 경우에는 입력 파일 개수를 줄여야 합니다.  Visual Studio 내에서 전체 프로젝트에 대해 [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)를 이용하여 개수를 줄인 다음 파일별로 파일을 다시 검사합니다.  
  
 64MB 이상의 .bsc 파일 때문에 이 문제가 발생한 경우에는 입력 파일로 사용되는 .sbr 파일 개수를 줄이면 결과 .bsc 파일의 크기가 줄어듭니다.  또한 \/Em\(매크로 확장 기호 제외\), \/El\(지역 변수 제외\) 및 \/Es\(시스템 파일 제외\)를 사용하면 찾아보기 정보의 용량을 줄일 수 있습니다.  
  
## 참고 항목  
 [BSCMAKE 옵션](../../build/reference/bscmake-options.md)