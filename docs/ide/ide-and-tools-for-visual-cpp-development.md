---
title: "IDE 및 Visual c + + 개발 도구 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6ff3f709e5db16f06569ab3406cfef44cabf11
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2018
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE 및 Visual C++ 개발 도구

일부로는 Visual Studio 통합 개발 환경 (IDE), Microsoft Visual c + + (MSVC) 여러 창 및 다른 언어와 공통 된 도구를 공유합니다. 등의 많은 **솔루션 탐색기**, 코드 편집기 및 디버거, [Visual Studio IDE](/visualstudio/ide/visual-studio-ide)합니다. 공유 도구 또는 창에 있는 C++용 기능 집합과 .NET 언어 또는 Javascript용 기능 집합이 약간 다른 경우가 자주 있습니다. 일부 창이나 도구는 Visual Studio Pro 또는 Visual Studio Enterprise에서만 사용할 수 있습니다.

Visual Studio IDE에서 공유 도구 이외에도 MSVC에 특별히 네이티브 코드 개발을 위한 여러 가지 도구가 있습니다. 이러한 도구의 목록도 이 문서에서 제공합니다. Visual Studio의 각 버전에서 사용할 수 있는 도구는 목록에 대 한 참조 [Visual c + + 도구 및 Visual Studio 버전의 기능](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)합니다.

## <a name="creating-a-solution-and-projects"></a>솔루션 및 프로젝트 만들기

A *프로젝트* 는 기본적으로 소스 코드 파일 및 실행 파일에는 기본 제공 하는 이미지 또는 데이터 파일과 같은 리소스 집합입니다. 모든 빌드 시스템 또는 사용자 지정 빌드 도구를 완벽 하 게 지원에 대 한 Intellisense, 검색 및 디버깅을 사용 하려면 visual Studio 2017 지원할 수 있습니다.

- MSBuild는 Visual Studio에 대 한 네이티브 빌드 시스템 및 유니버설 Windows 플랫폼 (UWP) 앱 또는 레거시 Windows 데스크톱 응용 프로그램을 MFC 나 ATL. 사용에 대 한 최상의 적합 MSBuild 기반 c + + 프로젝트에 대 한 자세한 내용은 참조 [만들기 및 관리 MSBuild 기반 프로젝트가](creating-and-managing-visual-cpp-projects.md)합니다.
- CMake는 플랫폼 간 빌드 작업의 c + + 데스크톱 개발을 설치할 때 Visual Studio IDE에 통합 된 시스템입니다. 자세한 내용은 [Visual C++의 CMake 프로젝트](cmake-tools-for-visual-cpp.md)를 참조하세요.
- 폴더 열기 기능을 통해 다른 c + + 빌드를 모든 시스템의 파일을 느슨한 컬렉션을 포함 하 여 사용할 수 있습니다. 빌드 프로그램을 호출 하 고 디버깅 세션을 구성을 간단한 JSON 파일을 만듭니다. 자세한 내용은 참조 [c + + 코드를 Visual Studio로 전환](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/)합니다.

### <a name="project-templates-msbuild"></a>프로젝트 템플릿 (MSBuild)

Visual Studio는 MSBuild 기반 프로젝트가;에 대 한 여러 가지 템플릿이 함께 제공 이러한 템플릿은 시작 코드와 다양 한 기본 프로그램 형식에 필요한 설정을 포함 합니다. 일반적으로 선택 하 여 먼저 **파일** > **새 프로젝트** 프로젝트 템플릿에서 프로젝트를 만들려면 다음 해당 프로젝트에 새 소스 코드 파일을 추가 하거나 제공 된 파일에서 코딩을 시작 합니다. C + + 프로젝트 및 프로젝트 마법사에 관련 된 정보를 참조 하십시오. [만들기 및 Visual c + + 프로젝트 관리](../ide/creating-and-managing-visual-cpp-projects.md)합니다.

### <a name="application-wizards-msbuild"></a>응용 프로그램 마법사 (MSBuild)

Visual Studio를 선택 하면 일부 MSBuild 프로젝트 형식에 대 한 마법사를 제공 **파일** > **새 프로젝트**합니다. 마법사는 새 프로젝트를 만드는 과정을 단계별로 안내합니다. 이러한 마법사는 옵션 및 설정이 많은 프로젝트 형식에 유용합니다. 자세한 내용은 참조 [만드는 데스크톱 프로젝트에서 사용 하 여 응용 프로그램 마법사](../ide/creating-desktop-projects-by-using-application-wizards.md)합니다.

## <a name="creating-user-interfaces-with-designers-msbuild"></a>디자이너 (MSBuild)를 사용 하 여 사용자 인터페이스 만들기

프로그램에 사용자 인터페이스가 있는 경우 처음으로 수행할 작업 중 하나로 사용자 인터페이스를 단추, 목록 상자 등의 컨트롤로 채웁니다. Visual Studio에는 시각적 디자인 화면과 각 C++ 응용 프로그램의 특성에 맞는 도구 상자가 있습니다. 어떤 앱 유형을 만들든 간에 관계없이 기본적인 개념은 같습니다. 즉, 도구 상자 창에서 컨트롤을 끌어 디자인 화면의 원하는 위치에 놓으면 됩니다. 백그라운드에서 이러한 모든 작업이 이루어지는 데 필요한 리소스와 코드가 생성됩니다. 그런 다음 컨트롤을 데이터로 채우는 또는 모양과 동작을 사용자 지정 코드를 작성 합니다.

유니버설 Windows 플랫폼 앱에 대 한 사용자 인터페이스 디자인에 대 한 자세한 내용은 참조 [디자인과 UI](https://developer.microsoft.com/en-us/windows/design)합니다.

MFC 응용 프로그램에 대 한 사용자 인터페이스를 작성 하는 방법에 대 한 자세한 내용은 참조 [MFC 데스크톱 응용 프로그램](../mfc/mfc-desktop-applications.md)합니다. Win32 Windows 프로그램에 대 한 정보를 참조 하십시오. [Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)합니다.

## <a name="writing-and-editing-code"></a>코드 작성 및 편집

### <a name="semantic-colorization"></a>의미 체계 색 지정

모든 프로젝트 파일에 표시 됩니다는 프로젝트를 만든 후의 **솔루션 탐색기** 창. .H 또는.cpp 파일에 대해 클릭할 때 **솔루션 탐색기**, 파일이 코드 편집기에서 열립니다. 코드 편집기는 C++ 소스 코드용 특수 워드 프로세서입니다. 언어 키워드, 메서드 및 변수 이름, 기타 코드 요소 등을 색으로 구분하여 코드를 더 쉽게 읽고 이해할 수 있도록 해 줍니다.

### <a name="intellisense"></a>IntelliSense

코드 편집기는 또한 전체적으로 IntelliSense라고 하는 몇 가지 기능을 지원합니다. 메서드를 포인터로 가리키면 일부 기본 설명을 볼 수 있습니다. 클래스 변수 이름을 입력한 다음 . 또는 ->를 입력하면 해당 클래스의 인스턴스 멤버의 목록이 표시됩니다. 클래스 이름을 입력한 다음 ::을 입력하면 정적 멤버의 목록이 표시됩니다. 클래스 또는 메서드 이름을 입력하기 시작하면 문을 완료할 제안이 표시됩니다. 자세한 내용은 [IntelliSense 사용](/visualstudio/ide/using-intellisense)을 참조하세요.

### <a name="code-snippets"></a>코드 조각

IntelliSense 코드 조각을 사용하면 일반적으로 사용되거나 복잡한 코드 구문을 바로 가기 키 입력으로 생성할 수 있습니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.

## <a name="navigating-code"></a>코드 탐색

**보기** 메뉴에서는 코드 파일에서 탐색 하기 위한 다양 한 창과 도구에 대 한 액세스를 제공 합니다. 이러한 창에 대 한 자세한 내용은 참조 하십시오. [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)합니다.

### <a name="solution-explorer"></a>솔루션 탐색기

Visual Studio의 모든 버전에서 사용 하 여는 **솔루션 탐색기** 프로젝트 내의 파일 사이 탐색 하는 창입니다. .h 또는 .cpp 파일 아이콘을 확장하면 파일의 해당 클래스를 볼 수 있습니다. 클래스를 확장하면 해당 멤버가 표시됩니다. 멤버를 두 번 클릭하면 파일 내에서 해당 멤버의 정의 또는 구현으로 이동합니다.

### <a name="class-view-and-code-definition-window"></a>클래스 뷰 및 코드 정의 창

사용 하 여는 **클래스 뷰** 를 partial 클래스를 포함 하 여 모든 파일에서 네임 스페이스 및 클래스를 봅니다. 각 네임스페이스 또는 클래스를 확장하여 해당 멤버를 표시하고, 이러한 멤버를 두 번 클릭하여 소스 파일 내의 해당 위치로 이동할 수 있습니다. 여는 경우는 **코드 정의 창**에서 선택 하면 정의 또는 형식의 구현을 볼 수 있습니다 **클래스 뷰**합니다.

### <a name="object-browser"></a>개체 브라우저

사용 하 여 **개체 브라우저** .NET 어셈블리와 COM 형식 라이브러리를 Windows 런타임 구성 요소 (.winmd 파일)에서 형식 정보를 탐색 합니다. Win32 DLL에는 사용되지 않습니다.

### <a name="go-to-definitiondeclaration"></a>정의/선언으로 이동

API 이름 또는 멤버 변수에서 F12 키를 누르면 해당 정의로 이동합니다. 정의가 경우 (UWP 또는 Windows 8.x 스토어 앱)에 대 한.winmd 파일에 형식 정보가 개체 브라우저에서에 표시 됩니다. 선택할 수도 있습니다 **정의로 이동** 또는 **선언으로 이동** 변수 또는 형식 이름을 마우스 오른쪽 단추로 클릭 하 고 상황에 맞는 메뉴에서 옵션을 선택 하 여 합니다.

### <a name="find-all-references"></a>모든 참조 찾기

소스 코드 파일에서 형식 또는 메서드 또는 변수 이름 위로 마우스 커서를 놓고 마우스 오른쪽 단추로 클릭 하 고 선택 **모든 참조 찾기** 파일, 프로젝트 또는 솔루션에서 모든 위치의 목록이 반환할는 형식이 사용 됩니다. **모든 참조 찾기** 는 지능형 이므로 다른 범위의 다른 변수에 동일한 이름이 있는 경우에 동일한 동일한 변수의 인스턴스만 반환 합니다.

## <a name="add-and-edit-resources--msbuild"></a>추가 리소스 및 편집 (MSBuild)

용어 *리소스* Visual Studio의 컨텍스트에서 데스크톱 프로젝트에는 대화 상자, 아이콘, 지역화 가능한 문자열, 시작 화면, 데이터베이스 연결 문자열 또는에 포함 하려는 임의 데이터가 등이 포함 되어는 실행 파일입니다.

네이티브 데스크톱 c + + 프로젝트에 리소스 추가 및 편집에 대 한 자세한 내용은 참조 하십시오. [리소스 파일 작업](../windows/working-with-resource-files.md)합니다.

## <a name="build-compile-and-link"></a>빌드 (컴파일 및 링크)

선택 **빌드** > **솔루션 빌드** 메뉴 모음 또는 컴파일하고 프로젝트를 연결 하 고 Ctrl + Shift + B 키 조합을 입력 합니다. Visual Studio에서는 실행 코드를 만들려면 다음을 사용 합니다. [MSBuild](/visualstudio/msbuild/msbuild1) 를 통해 설정 CMake 또는 무엇이 든 빌드 환경 또는 **폴더 열기**합니다. MSBuild 프로젝트에 대 한 일반 빌드 옵션에서 설정한 **도구** > **옵션** > **프로젝트 및 솔루션** 속성을 설정할 수 있습니다 특정 프로젝트에 대 한 **프로젝트** > **속성**합니다. 빌드 오류 및 경고는 오류 목록에 보고 됩니다 (Ctrl +\\, E). JSON 파일을 만들려면 솔루션 탐색기에서 비 MSBuild 프로젝트 구성 됩니다. 모든 빌드를 사용 하면 시스템의 **출력** 창 (Alt + 2) 빌드 프로세스에 대 한 정보를 표시 합니다. MSBuild 구성에 대 한 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md) 및 [Visual Studio에서 c + + 프로젝트 빌드](../ide/building-cpp-projects-in-visual-studio.md)합니다.

컴파일러 (cl.exe) 및 여러 다른 빌드 관련 독립 실행형 도구 예: NMAKE 및 LIB 명령줄에서 직접 사용할 수 있습니다. 자세한 내용은 참조 [명령줄에서 빌드 C/c + + 코드](../build/building-on-the-command-line.md) 및 [C/c + + 빌드 참조](../build/reference/c-cpp-building-reference.md)합니다.

## <a name="test"></a>테스트

Visual Studio에는 네이티브 C++ 및 C++/CLI에 대한 단위 테스트 프레임워크가 들어 있습니다. 자세한 내용은 참조 [단위 테스트를 사용 하 여 코드 확인](/visualstudio/test/unit-test-your-code) 및 [단위 테스트 작성 C/c + + 용 Microsoft 단위 테스트 프레임 워크에 대 한 c + +](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)

## <a name="debug"></a>디버그

키를 눌러 프로그램을 디버깅할 수 **F5** 프로젝트 구성이 디버그로 설정 된 경우. 디버깅 하면 키를 눌러 중단점을 설정할 수 있는 동안 **F9**, 키를 눌러 코드를 단계별로 **F10**, 지정 된 변수 또는 레지스터의 값을 확인 하 고도 경우에 따라 코드에서 변경 내용을 확인 및 계속 다시 컴파일하지 않고 디버깅 합니다. 자세한 내용은 [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)을 참조하세요.

## <a name="deploy-completed-applications"></a>완성 된 응용 프로그램 배포

Microsoft 스토어를 통해 고객에 게는 UWP 앱을 배포할는 **프로젝트** > **저장소** 메뉴 옵션입니다. CRT 배포는 백그라운드에서 자동으로 처리됩니다. 자세한 내용은 [앱 판매](http://go.microsoft.com/fwlink/p/?LinkId=262280)를 참조하세요.

네이티브 C++ 데스크톱 응용 프로그램을 다른 컴퓨터에 배포할 때는 응용 프로그램 자체 및 이 응용 프로그램이 종속되는 라이브러리 파일을 설치해야 합니다. 응용 프로그램으로 유니버설 c + + 런타임 UCRT ()를 배포 하는 방법은 세 가지가: 중앙 배포, 로컬 배포 또는 정적 링크 합니다. 자세한 내용은 참조 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)합니다.

C + 배포에 대 한 자세한 내용은 + /CLI 프로그램 참조 [개발자를 위한 배포 가이드](/dotnet/framework/deployment/deployment-guide-for-developers),

## <a name="related-articles"></a>관련 문서

|||
|-|-|
|[Visual Studio 버전의 Visual C++ 도구 및 기능](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|다양한 Visual Studio 버전에서 사용할 수 있는 기능을 보여 줍니다.|
|[MSBuild 기반 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)|C + + MSBuild 기반 프로젝트가 Visual Studio 및 링크를 만들고 관리 하는 방법을 설명 하는 다른 문서에 대 한 개요를 제공 합니다.|
|[Visual c + +에서 프로젝트 CMake](cmake-tools-for-visual-cpp.md)합니다.|CMake 또는 Visual c + +에서 다른 비 MSBuild 프로젝트를 구축 하는 방법에 설명 합니다.|
|[C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)|C++ 프로젝트를 빌드하는 방법을 설명합니다.|
|[데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ 앱 및 배포에 대해 자세히 설명하는 다른 문서로 연결되는 링크에 대한 개요를 제공합니다.|
|[Visual C++ 포팅 및 업그레이드 가이드](../porting/visual-cpp-porting-and-upgrading-guide.md)|이전 버전의 Visual Studio에서 만들어진 c + + 응용 프로그램을 업그레이드 하는 방법 및 Visual Studio 이외의 다른 도구를 사용 하 여 만든 응용 프로그램을 마이그레이션하는 방법에 대 한 자세한 정보입니다.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio에 포함된 Visual C++의 주요 기능을 설명하고 Visual C++ 설명서의 나머지 부분에 연결합니다.|
