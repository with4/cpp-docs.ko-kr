---
title: Visual Studio에서 C++ 프로젝트 빌드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++ projects, building
- projects [C++], building
- builds [C++], about building in Visual Studio
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7008e7fe670471301968482fbd4c6c758f0ff5e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33340504"
---
# <a name="building-c-projects-in-visual-studio"></a>Visual Studio에서 C++ 프로젝트 빌드
Visual Studio IDE(통합 개발 환경)에는 전체 솔루션이나 전체 솔루션 중 한 개의 프로젝트만 빌드할 수 있는 여러 가지 방법이 있습니다. 또한 빌드 설정을 수정하고 사용자 지정 빌드 단계를 지정하여 개발 프로세스를 보다 효율적으로 만들 수 있습니다.  
  
 Visual Studio에서 열리고 **솔루션 탐색기**에서 선택된 솔루션을 빌드하려면 다음을 수행할 수 있습니다.  
  
-   메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
-   또는 **솔루션 탐색기**에서 솔루션의 바로 가기 메뉴를 열고 **솔루션 빌드**를 선택합니다.  
  
-   또는 F7 키를 누릅니다. 이 키는 C/C++ 개발 설정의 기본 키보드 단축키입니다.  
  
-   또는 [명령 창](/visualstudio/ide/reference/command-window)(메뉴 모음에서 **보기**, **다른 창**, **명령 창** 선택)에서 `Build.BuildSolution`을 입력합니다.  
  
-   또는 [빠른 실행](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) 상자에 `build build solution`을 입력합니다.  
  
 **솔루션 탐색기**에서 선택한 프로젝트를 빌드하기 위해 다음을 수행할 수 있습니다.  
  
-   메뉴 모음에서 **빌드**, **\<프로젝트 이름>** 빌드를 선택합니다.  
  
-   **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **빌드**를 선택합니다.  
  
-   또는 명령 창(메뉴 모음에서 **보기**, **다른 창**, **명령 창** 선택)에서 `Build.BuildOnlyProject`을 입력합니다.  
  
-   또는 빠른 실행 상자에 `build project only build only <project name>`을 입력합니다.  
  
 Visual Studio에서 Visual C++ 응용 프로그램을 빌드하는 경우 프로젝트의 속성 페이지 대화 상자에서 빌드의 여러 설정을 수정할 수 있습니다. 프로젝트 속성 설정 방법에 대한 자세한 내용은 [프로젝트 속성 작업](../ide/working-with-project-properties.md)을 참조하세요.  
  
 IDE를 사용하여 C++ 프로젝트를 만들고 빌드하며 디버그하는 방법에 대한 예는 [연습: C++로 Visual Studio IDE 탐색](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)을 참조하세요. IDE를 사용하여 C++/CLR 프로젝트를 빌드하는 방법에 대한 예제는 [연습: Visual Studio에서 CLR을 대상으로 하는 C++ 프로그램 컴파일](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)을 참조합니다. IDE를 사용하여 Windows 런타임 앱을 만드는 방법에 대한 예제는 [C++을 사용하여 첫 번째 Windows 런타임 앱 만들기](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx)를 참조하세요.  
  
 빌드 방법, 빌드 설정 수정 방법 및 사용자 지정 빌드 단계를 지정하는 방법에 대해 자세히 읽어보려면 다음 문서를 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)  
 통합 개발 환경에서 빌드 프로세스를 사용자 지정하는 방법에 대해 설명합니다.  
  
 [빌드 명령 및 속성에 대한 일반 매크로](../ide/common-macros-for-build-commands-and-properties.md)  
 문자열이 허용되는 경우 사용할 수 있는 매크로를 나열합니다.  
  
 [외부 프로젝트 빌드](../ide/building-external-projects.md)  
 통합 개발 환경 외부에 있는 장치를 사용하는 프로젝트 빌드에 대해 설명합니다.  
  
 [프로젝트 파일](../ide/project-files.md)  
 .vcxproj 파일의 XML 구조를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [VC++ 디렉터리, 프로젝트, 옵션 대화 상자](vcpp-directories-property-page.md)  
 (MSBuild 프로젝트만) 실행 파일의 검색 경로를 수정하는 방법과 빌드 중 파일, 라이브러리 파일 및 소스 코드 파일을 포함하는 방법에 대해 설명합니다.  
  
 [컴파일 및 빌드](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Visual Studio 내에서 빌드에 대한 정보를 제공합니다.  
  
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)  
 명령줄 또는 Visual Studio의 통합 개발 환경에서 프로그램 빌드를 설명하는 항목에 대한 링크를 제공합니다.  
  
 [C/C++ 빌드 참조](../build/reference/c-cpp-building-reference.md)  
 C++, 컴파일러 및 링커 옵션으로 프로그램 빌드 개요와 추가 빌드 도구에 대한 링크를 제공합니다.  
  
 [이전 버전의 Visual C++에서 프로젝트 업그레이드](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 C++ 프로젝트를 최신 버전의 컴파일러 도구 집합으로 업그레이드하는 문제를 다루는 항목에 대한 링크를 제공합니다.  
  
[Visual C++ 포팅 및 업그레이드 가이드](../porting/visual-cpp-porting-and-upgrading-guide.md)  
  이전 버전의 Visual Studio에서 만들어진 C++ 앱을 업그레이드하는 방법 및 Visual Studio 이외의 다른 도구를 사용해서 만들어진 응용 프로그램을 마이그레이션하는 방법에 대한 자세한 설명입니다.  
  
## <a name="see-also"></a>참고 항목  
 [유니버설 Windows 앱(C++)](../windows/universal-windows-apps-cpp.md)