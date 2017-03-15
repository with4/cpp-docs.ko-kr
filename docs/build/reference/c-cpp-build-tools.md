---
title: "C/C++ 빌드 도구 | Microsoft Docs"
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
  - "c.build"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드[C++], C/C++ 도구"
  - "도구[C++], 빌드"
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 빌드 도구
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 빌드 출력을 보고 조작하는 데 사용하는 다음과 같은 명령줄 도구를 제공합니다.  
  
-   [BSCMAKE.EXE](../../build/reference/bscmake-reference.md)는 프로그램의 기호\(클래스, 함수, 데이터, 매크로 및 형식\)에 대한 정보가 들어 있는 찾아보기 정보 파일\(.bsc\)을 빌드합니다.  개발 환경 내의 찾아보기 창에서 이 정보를 볼 수 있습니다. .bsc 파일은 개발 환경에서 빌드할 수도 있습니다.  
  
-   [LIB.EXE](../../build/reference/lib-reference.md)는 COFF\(Common Object File Format\) 개체 파일 라이브러리를 만들고 관리하는 데 사용됩니다.  또한 내보내기 파일을 만들고 내보낸 정의를 참조하는 라이브러리를 가져오는 데 사용될 수 있습니다.  
  
-   [EDITBIN.EXE](../../build/reference/editbin-reference.md)는 COFF 이진 파일을 수정하는 데 사용됩니다.  
  
-   [DUMPBIN.EXE](../../build/reference/dumpbin-reference.md)는 COFF 이진 파일에 대한 정보\(기호 테이블 등\)를 표시합니다.  
  
-   [NMAKE](../../build/nmake-reference.md)는 메이크파일을 읽고 실행합니다.  
  
-   오류 조회 유틸리티인 [ERRLOOK](../../build/reference/value-edit-control.md)은 입력된 값을 바탕으로 시스템 오류 메시지나 모듈 오류 메시지를 검색합니다.  
  
## 참고 항목  
 [C\/C\+\+ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [데코레이팅된 이름](../../build/reference/decorated-names.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)