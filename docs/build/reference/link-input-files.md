---
title: "LINK 입력 파일 | Microsoft Docs"
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
  - "링커 파일에 대한 명령 입력[C++]"
  - "파일[C++], LINK"
  - "가져오기 라이브러리[C++], 링커 파일"
  - "입력 파일[C++], LINK"
  - "LINK 도구[C++], 입력 파일"
  - "링커[C++], 입력 파일"
  - "모듈 정의 파일"
  - "모듈 정의 파일, 링커 파일"
  - "리소스[C++], 링커 파일"
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LINK 입력 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

개체, 가져오기 및 표준 라이브러리, 리소스, 모듈 정의, 명령 입력이 포함된 파일은 사용자가 링커에 제공합니다.  LINK에서는 파일 확장명을 통해 파일의 내용을 가정하지 않으며,  대신 각 입력 파일을 검사하여 해당 파일의 형식을 결정합니다.  
  
 명령줄의 개체 파일은 각 파일이 명령줄에 사용된 순서에 따라 처리됩니다.  라이브러리도 명령줄 순서에 따라 검색되지만 이 경우 주의해야 할 사항이 있습니다. 확인되지 않은 기호를 라이브러리에서 개체 파일로 가져오는 경우 이 기호를 해당 라이브러리에서 먼저 검색한 다음 명령줄과 [\/DEFAULTLIB\(기본 라이브러리 지정\)](../../build/reference/defaultlib-specify-default-library.md) 지시문의 순서에 따라 다음 라이브러리에서 검색하고 마지막으로 명령줄의 시작 부분에 있는 모든 라이브러리에서 검색합니다.  
  
> [!NOTE]
>  LINK는 지시 파일과 순서 파일에서 세미콜론이나 기타 문자를 더 이상 주석의 시작으로 사용하지 않습니다.  세미콜론은 모듈 정의 파일\(.def\)에서만 주석의 시작으로 인식됩니다.  
  
 LINK에서는 다음 형식의 입력 파일을 사용합니다.  
  
-   [.obj 파일](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [.netmodule files](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [.lib 파일](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [.exp 파일](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [.def 파일](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [.pdb 파일](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [.res 파일](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [.exe 파일](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [.txt 파일](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [.ilk 파일](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)