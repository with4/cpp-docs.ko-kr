---
title: "컴파일러 옵션 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러"
  - "컴파일러 옵션, C++"
  - "IPF Visual C++ 컴파일러"
  - "Itanium Visual C++ 컴파일러"
  - "x64 Visual C++ 컴파일러"
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# 컴파일러 옵션
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cl.exe는 Microsoft C 및 C\+\+ 컴파일러 및 링커를 제어하는 도구입니다. cl.exe는 Microsoft Visual Studio를 지원하는 운영 체제에서만 실행할 수 있습니다.  
  
> [!NOTE]
>  이 도구는 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 시작할 수 있습니다.  시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
 컴파일러는 COFF\(Common Object File Format\) 개체 파일\(.obj\)을 생성합니다.  링커는 실행 파일\(.exe\)이나 DLL\(동적 연결 라이브러리\)를 생성합니다.  
  
 모든 컴파일러 옵션은 대\/소문자를 구분합니다.  
  
 링크하지 않고 컴파일하려면 [\/c](../../build/reference/c-compile-without-linking.md)를 사용하십시오.  
  
## 옵션 찾기  
 특정 컴파일러 옵션을 찾으려면 다음 목록 중 하나를 참조하십시오.  
  
-   [컴파일러 옵션 사전순 목록](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)  
  
## 옵션 지정  
 통합 개발 환경에서 각 컴파일러 옵션을 설정하는 방법은 각 컴파일러 옵션 단원에서 설명합니다.  개발 환경 밖에서 옵션을 지정하는 방법을 알아보려면 다음을 참조하십시오.  
  
-   [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL 명령 파일](../../build/reference/cl-command-files.md)  
  
-   [CL 환경 변수](../../build/reference/cl-environment-variables.md)  
  
## 관련 빌드 도구  
 출력 파일을 빌드하려면 [NMAKE](../../build/nmake-reference.md)를 사용합니다.  
  
 클래스 검색을 지원하려면 [BSCMAKE](../../build/reference/bscmake-reference.md)를 사용합니다.  
  
 [링커 옵션](../../build/reference/linker-options.md)도 프로그램 빌드 방법에 영향을 줍니다.  
  
## 참고 항목  
 [C\/C\+\+ 빌드 참조](../../build/reference/c-cpp-building-reference.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일 속도 향상](../../build/reference/fast-compilation.md)   
 [CL에서의 링커 호출](../../build/reference/cl-invokes-the-linker.md)