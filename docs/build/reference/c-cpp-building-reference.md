---
title: "C/C++ 빌드 참조 | Microsoft Docs"
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
  - "빌드[C++], 추가 정보"
  - "cl.exe 컴파일러[C++], 프로그램 빌드"
  - "소스 코드 컴파일[C++], 추가 정보"
  - "링커[C++], 빌드 참조"
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 빌드 참조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에서는 두 가지 방법을 사용하여 C\/C\+\+ 프로그램을 빌드할 수 있습니다.  가장 쉽고도 일반적인 방법은 [Visual C\+\+ 개발 환경 내에서 빌드](../../ide/building-cpp-projects-in-visual-studio.md)하는 것입니다.  다른 방법은 [명령줄 도구를 사용하여 명령 프롬프트에서 빌드](../../build/building-on-the-command-line.md)하는 것입니다.  두 가지 방법 모두 Visual C\+\+ 소스 편집기나 타사 편집기를 사용하여 소스 파일을 만들 수 있습니다.  
  
 프로그램에서 .vcxproj 파일 대신 메이크파일을 사용하더라도 개발 환경에서 해당 메이크파일을 [외부 프로젝트](../../ide/building-external-projects.md)로 빌드할 수 있습니다.  
  
## 단원 내용  
 [C\/C\+\+ 프로그램 컴파일](../../build/reference/compiling-a-c-cpp-program.md)  
 기계어 코드, 링커 지시문, 섹션, 외부 참조 및 함수\/데이터 이름이 들어 있는 개체 파일을 만드는 컴파일러에 대해 설명합니다.  
  
 [연결](../../build/reference/linking.md)  
 컴파일러에서 만들어진 개체 파일의 코드와 정적으로 링크된 라이브러리의 코드를 결합하여 이름 참조를 확인한 다음 실행 파일을 만드는 링커에 대해 설명합니다.  
  
 [릴리스 빌드](../../build/reference/release-builds.md)  
 디버그 빌드에서 릴리스 빌드로 변경하는 이유 및 시기에 대한 정보를 제공하고 디버그 빌드에서 릴리스 빌드로 변경할 때 발생할 수 있는 일부 문제에 대해 설명합니다.  
  
 [코드 최적화](../../build/reference/optimizing-your-code.md)  
 코드 최적화 메커니즘에 대해 설명하는 항목의 링크를 제공합니다.  
  
 [C\/C\+\+ 빌드 도구](../../build/reference/c-cpp-build-tools.md)  
 빌드 출력을 보거나 조작하는 데 사용하는 명령줄 도구에 대해 설명합니다.  
  
 [C\/C\+\+ 빌드 오류](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 목차의 빌드 오류 단원에 대해 소개합니다.  
  
## 관련 단원  
 [C\/C\+\+ 전처리기 참조](../../preprocessor/c-cpp-preprocessor-reference.md)  
 매크로, 연산자 및 지시문을 변환하여 컴파일러에서 사용할 소스 파일을 준비하는 전처리기에 대해 설명합니다.  
  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../../ide/understanding-custom-build-steps-and-build-events.md)  
 빌드 프로세스의 사용자 지정 방법에 대해 설명합니다.  
  
 [C\/C\+\+ 프로그램 빌드](../../build/building-c-cpp-programs.md)  
 Visual Studio의 명령줄 또는 통합 개발 환경에서 프로그램을 빌드하는 방법에 대해 설명하는 항목의 링크를 제공합니다.  
  
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
 통합 개발 환경이나 명령줄에서 컴파일러 옵션을 설정하는 방법에 대해 설명합니다.  
  
 [컴파일러 옵션](../../build/reference/compiler-options.md)  
 컴파일러 옵션의 사용 방법에 대해 설명하는 항목의 링크를 제공합니다.  
  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)  
 통합 개발 환경의 내부 또는 외부에서 링커 옵션을 설정하는 방법에 대해 설명합니다.  
  
 [링커 옵션](../../build/reference/linker-options.md)  
 링커 옵션의 사용 방법에 대해 설명하는 항목의 링크를 제공합니다.  
  
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)  
 컴파일하는 동안 만들어진 .sbr 파일에서 찾아보기 정보 파일\(.bsc\)을 빌드하는 Microsoft Browse Information Maintenance Utility\(BSCMAKE.EXE\)에 대해 설명합니다.  
  
 [LIB 참조](../../build/reference/lib-reference.md)  
 COFF\(Common Object File Format\) 개체 파일의 라이브러리를 만들고 관리하는 Microsoft 라이브러리 관리자\(LIB.exe\)에 대해 설명합니다.  
  
 [EDITBIN 참조](../../build/reference/editbin-reference.md)  
 COFF\(Common Object File Format\) 이진 파일을 수정하는 Microsoft COFF Binary File Editor\(EDITBIN.EXE\)에 대해 설명합니다.  
  
 [DUMPBIN 참조](../../build/reference/dumpbin-reference.md)  
 COFF\(Common Object File Format\) 이진 파일에 대한 정보를 표시하는 Microsoft COFF Binary File Dumper\(DUMPBIN.EXE\)에 대해 설명합니다.  
  
 [NMAKE 참조](../../build/nmake-reference.md)  
 설명 파일에 포함된 명령에 따라 프로젝트를 빌드하는 도구인 Microsoft Program Maintenance Utility\(NMAKE.EXE\)에 대해 설명합니다.