---
title: "Visual Studio에서 C++ 프로젝트 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "빌드[C++], Visual Studio의 빌드 정보"
  - "프로젝트[C++], 빌드"
  - "Visual C++ 프로젝트, 빌드"
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual Studio에서 C++ 프로젝트 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio IDE\(통합 개발 환경\)에는 전체 솔루션이나 전체 솔루션 중 한 개의 프로젝트만 빌드할 수 있는 여러 가지 방법이 있습니다.  또한 빌드 설정을 수정하고 사용자 지정 빌드 단계를 지정하여 개발 프로세스를 보다 효율적으로 만들 수 있습니다.  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서 열리고 **솔루션 탐색기**에서 선택된 솔루션을 빌드하기 위해 다음을 수행할 수 있습니다.  
  
-   메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
-   또는 **솔루션 탐색기**에서 솔루션의 바로 가기 메뉴를 열고 **솔루션 빌드**를 선택합니다.  
  
-   또는 F7 키를 누릅니다.  이 키는 C\/C\+\+ 개발 설정의 기본 키보드 단축키입니다.  
  
-   또는 [명령 창](../Topic/Command%20Window.md)\(메뉴 모음에서 **보기**, **다른 창**, **명령 창** 선택\)에서 `Build.BuildSolution`을 입력합니다.  
  
-   또는 [빠른 실행](../Topic/Quick%20Launch,%20Environment,%20Options%20Dialog%20Box.md) 상자에 `build build solution`이라고 입력합니다.  
  
 **솔루션 탐색기**에서 선택한 프로젝트를 빌드하기 위해 다음을 수행할 수 있습니다.  
  
-   메뉴 모음에서 **빌드**, **\<프로젝트 이름\> 빌드**를 선택합니다.  
  
-   **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **빌드**를 선택합니다.  
  
-   또는 명령 창\(메뉴 모음에서 **보기**, **다른 창**, **명령 창** 선택\)에서 `Build.BuildOnlyProject`를 입력합니다.  
  
-   또는 빠른 실행 상자에 `build project only build only <프로젝트 이름>`이라고 입력합니다.  
  
 Visual Studio에서 Visual C\+\+ 응용 프로그램을 빌드하는 경우 프로젝트의 속성 페이지 대화 상자에서 빌드의 여러 설정을 수정할 수 있습니다.  프로젝트 속성을 설정하는 방법에 대한 자세한 내용은 [프로젝트 속성 사용](../ide/working-with-project-properties.md)을 참조하세요.  
  
 IDE를 사용하여 C\+\+ 프로젝트를 만들고 빌드하며 디버그하는 방법에 대한 예는 [연습: C\+\+로 Visual Studio IDE 탐색](../Topic/Getting%20Started%20with%20C++%20in%20Visual%20Studio.md)을 참조하세요.  IDE를 사용하여 C\+\+\/CLR 프로젝트를 빌드하는 방법에 대한 예는 [연습: Visual Studio에서 CLR을 대상으로 하는 C\+\+ 프로그램 컴파일](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)을 참조하세요.  IDE를 사용하여 Windows 란타임 앱을 만드는 방법에 대한 예는 [C\+\+을 사용하여 첫 번째 Windows 런타임 앱 만들기](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx)를 참조하세요.  
  
 빌드 방법, 빌드 설정 수정 방법 및 사용자 지정 빌드 단계를 지정하는 방법에 대해 자세히 읽어보려면 다음 문서를 참조하세요.  
  
## 단원 내용  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)  
 통합 개발 환경에서 빌드 프로세스를 사용자 지정하는 방법에 대해 설명합니다.  
  
 [빌드 명령 및 속성 매크로](../ide/common-macros-for-build-commands-and-properties.md)  
 문자열이 허용되는 경우 사용할 수 있는 매크로를 나열합니다.  
  
 [외부 프로젝트 빌드](../ide/building-external-projects.md)  
 통합 개발 환경 외부에 있는 장치를 사용하는 프로젝트 빌드에 대해 설명합니다.  
  
 [프로젝트 파일](../ide/project-files.md)  
 .vcxproj 파일의 XML 구조를 제공합니다.  
  
## 관련 단원  
 [VC\+\+ Directories, Projects, Options Dialog Box](http://msdn.microsoft.com/ko-kr/e027448b-c811-4c3d-8531-4325ad3f6e02)  
 실행 파일의 검색 경로를 수정하는 방법과 빌드 중 파일, 라이브러리 파일 및 소스 코드 파일을 포함하는 방법에 대해 설명합니다.  
  
 [Visual Studio에서 응용 프로그램　빌드](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)  
 Visual Studio 내에서 빌드에 대한 정보를 제공합니다.  
  
 [C\/C\+\+ 프로그램 빌드](../build/building-c-cpp-programs.md)  
 명령줄 또는 Visual Studio의 통합 개발 환경에서 프로그램 빌드를 설명하는 항목에 대한 링크를 제공합니다.  
  
 [C\/C\+\+ 빌드 참조](../build/reference/c-cpp-building-reference.md)  
 C\+\+, 컴파일러 및 링커 옵션으로 프로그램 빌드 개요와 추가 빌드 도구에 대한 링크를 제공합니다.  
  
 [이전 버전의 Visual C\+\+에서 프로젝트 업그레이드](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 Visual C\+\+ 6.0 이상 프로젝트를 Visual C\+\+ .NET으로 업그레이드하는 문제를 다루는 항목에 대한 링크를 제공합니다.  
  
 [Porting and Upgrading Programs](http://msdn.microsoft.com/ko-kr/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)  
 응용 프로그램 이식에 대한 자세한 내용을 제공하고 메이크 파일에 대해 설명합니다.  
  
## 참고 항목  
 [Roadmap for Windows Store apps using C\+\+](http://msdn.microsoft.com/ko-kr/0b71e4a4-5d8a-4a20-b2ec-e40062675ec1)