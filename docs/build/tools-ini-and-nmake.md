---
title: "Tools.ini와 NMAKE | Microsoft Docs"
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
  - "NMAKE 프로그램, 파일 읽기"
  - "Tools.ini 및 NMake"
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Tools.ini와 NMAKE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\/R를 사용하지 않은 경우 NMAKE는 Tools.ini를 읽은 후 메이크파일을 읽습니다.  NMAKE는 먼저 현재 디렉터리에서 Tools.ini를 찾은 다음 INIT 환경 변수로 지정한 디렉터리에서 찾습니다.  초기화 파일의 NMAKE 설정 섹션은 `[NMAKE]`로 시작하며 모든 메이크파일 정보가 포함될 수 있습니다.  주석은 숫자 기호\(\#\)로 시작하는 별도의 줄에 지정합니다.  
  
## 참고 항목  
 [NMAKE 실행](../build/running-nmake.md)