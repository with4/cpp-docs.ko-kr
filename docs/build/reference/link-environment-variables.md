---
title: "LINK 환경 변수 | Microsoft Docs"
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
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "환경 변수[C++], LINK"
  - "LIB 환경 변수"
  - "LINK 도구[C++], 환경 변수"
  - "변수, 환경"
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LINK 환경 변수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK 도구는 다음과 같은 환경 변수를 사용합니다.  
  
-   LINK 및 \_LINK\_\(정의된 경우\).  LINK 도구는 처리 전에 LINK 환경 변수에서 정의된 옵션 및 인수를 명령줄 인수 앞에 추가하고 \_LINK\_ 환경 변수에서 정의된 옵션 및 인수를 명령줄 인수 뒤에 추가합니다.  
  
-   LIB\(정의된 경우\).  LINK 도구는 개체, 라이브러리 또는 [\/base](../../build/reference/base-base-address.md) 옵션이나 명령줄에서 지정된 기타 파일을 검색할 때 LIB 경로를 사용합니다.  또한 LIB 경로를 사용하여 개체에 명명된 .pdb 파일을 찾습니다.  LIB 변수에는 하나 이상의 경로 사양이 세미콜론으로 구분되어 포함될 수 있습니다.  한 경로는 Visual C\+\+ 설치의 \\lib 하위 디렉터리를 가리켜야 합니다.  
  
-   PATH\(도구가 CVTRES를 실행해야 하고 LINK 자체와 동일한 디렉터리에서 파일을 찾을 수 없는 경우\).  LINK가 .res 파일을 연결하려면 CVTRES가 필요합니다. PATH는 Visual C\+\+ 설치의 \\bin 하위 디렉터리를 가리켜야 합니다.  
  
-   TMP\(OMF 또는 .res 파일을 연결할 때 디렉터리 지정\)  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)