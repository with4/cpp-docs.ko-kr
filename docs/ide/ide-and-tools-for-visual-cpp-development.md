---
title: IDE 및 Visual C++ 개발 도구 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, development tools
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3668fb438c2a0aa7fa14cff97f498a9becc67b36
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705402"
---
# <a name="ide-and-tools-for-visual-c-development"></a>IDE 및 Visual C++ 개발 도구

Visual Studio IDE(통합 개발 환경)의 일부인 Microsoft Visual C++(MSVC)는 다른 언어와 공통된 다양한 창과 도구를 공유합니다. **솔루션 탐색기**, 코드 편집기 및 디버거를 비롯한 이러한 창과 도구에 대해서는 [Visual Studio IDE](/visualstudio/ide/visual-studio-ide)에서 설명합니다. 공유 도구 또는 창에 있는 C++용 기능 집합과 .NET 언어 또는 Javascript용 기능 집합이 약간 다른 경우가 자주 있습니다. 일부 창이나 도구는 Visual Studio Pro 또는 Visual Studio Enterprise에서만 사용할 수 있습니다.

Visual Studio IDE에 있는 공유 도구 외에도, MSVC에는 네이티브 코드 개발 전용으로 사용되는 여러 도구가 있습니다. 이러한 도구의 목록도 이 문서에서 제공합니다. Visual Studio의 각 버전에서 사용할 수 있는 도구 목록은 [Visual Studio 버전의 Visual C++ 도구 및 기능](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)을 참조하세요.

## <a name="creating-a-solution-and-projects"></a>솔루션 및 프로젝트 만들기

*프로젝트*는 기본적으로 실행 파일에 빌드된 이미지 또는 데이터 파일과 같은 소스 코드 파일 및 리소스 집합입니다. Visual Studio 2017은 IntelliSense, 검색 및 디버깅을 완벽하게 지원하므로 사용자가 사용하기를 원하는 모든 빌드 시스템 또는 사용자 지정 빌드 도구를 지원할 수 있습니다.

- MSBuild는 Visual Studio의 기본 빌드 시스템으로, UWP(유니버설 Windows 플랫폼) 앱이나 MFC 또는 ATL을 사용하는 레거시 Windows 데스크톱 응용 프로그램에 가장 적합한 선택입니다. MSBuild 기반 C++ 프로젝트에 대한 자세한 내용은 [MSBuild 기반 프로젝트 생성 및 관리](creating-and-managing-visual-cpp-projects.md)를 참조하세요.
- CMake는 C++ 워크로드로 데스크톱 개발을 설치할 때, Visual Studio IDE에 통합되는 플랫폼 간 빌드 시스템입니다. 자세한 내용은 [Visual C++의 CMake 프로젝트](cmake-tools-for-visual-cpp.md)를 참조하세요.
- 느슨한 파일 컬렉션을 포함한 다른 모든 C++ 빌드 시스템은 폴더 열기 기능을 통해 지원됩니다. 간단한 JSON 파일을 생성하여 빌드 프로그램을 호출하고 디버깅 세션을 구성합니다. 자세한 내용은 [Visual Studio로 C++ 가져오기](https://blogs.msdn.microsoft.com/vcblog/2017/04/14/bring-your-cpp-code-to-visual-studio/)를 참조하세요.

### <a name="project-templates-msbuild"></a>프로젝트 템플릿(MSBuild)

Visual Studio에는 MSBuild 기반 프로젝트에 대한 여러 템플릿이 제공됩니다. 이 템플릿에는 다양한 기본 프로그램 형식에 필요한 시작 코드와 설정이 포함되어 있습니다. 프로젝트 템플릿에서 프로젝트를 만들려면 일반적으로 먼저 **파일** > **새 프로젝트**를 선택한 다음, 해당 프로젝트에 새 소스 코드 파일을 추가하거나 제공된 파일에서 코딩을 시작합니다. C++ 프로젝트 및 프로젝트 마법사에 대한 자세한 내용은 [Visual C++ 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)를 참조하세요.

### <a name="application-wizards-msbuild"></a>응용 프로그램 마법사(MSBuild)

Visual Studio는 **파일** > **새 프로젝트**를 선택할 때 일부 MSBuild 프로젝트 형식에 대한 마법사를 제공합니다. 마법사는 새 프로젝트를 만드는 과정을 단계별로 안내합니다. 이러한 마법사는 옵션 및 설정이 많은 프로젝트 형식에 유용합니다. 자세한 내용은 [응용 프로그램 마법사를 사용하여 데스크톱 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)를 참조하세요.

## <a name="creating-user-interfaces-with-designers-msbuild"></a>디자이너를 사용하여 사용자 인터페이스 만들기(MSBuild)

프로그램에 사용자 인터페이스가 있는 경우 처음으로 수행할 작업 중 하나로 사용자 인터페이스를 단추, 목록 상자 등의 컨트롤로 채웁니다. Visual Studio에는 시각적 디자인 화면과 각 C++ 응용 프로그램의 특성에 맞는 도구 상자가 있습니다. 어떤 앱 유형을 만들든 간에 관계없이 기본적인 개념은 같습니다. 즉, 도구 상자 창에서 컨트롤을 끌어 디자인 화면의 원하는 위치에 놓으면 됩니다. 백그라운드에서 이러한 모든 작업이 이루어지는 데 필요한 리소스와 코드가 생성됩니다. 그런 다음, 코드를 작성하여 컨트롤에 데이터를 채우거나 모양과 동작을 사용자 지정합니다.

유니버설 Windows 플랫폼 앱의 사용자 인터페이스 디자인에 대한 자세한 내용은 [디자인 및 UI](https://developer.microsoft.com/en-us/windows/design)를 참조하세요.

MFC 응용 프로그램의 사용자 인터페이스 만드는 방법에 대한 자세한 내용은 [MFC 데스크톱 응용 프로그램](../mfc/mfc-desktop-applications.md)을 참조하세요. Win32 Windows 프로그램에 대한 자세한 내용은 [Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)을 참조하세요.

## <a name="writing-and-editing-code"></a>코드 작성 및 편집

### <a name="semantic-colorization"></a>의미 체계 색 지정

프로젝트를 만든 후에는 모든 프로젝트 파일이 **솔루션 탐색기** 창에 표시됩니다. **솔루션 탐색기**에서 .h 또는 .cpp 파일을 클릭하면 파일이 코드 편집기에서 열립니다. 코드 편집기는 C++ 소스 코드용 특수 워드 프로세서입니다. 언어 키워드, 메서드 및 변수 이름, 기타 코드 요소 등을 색으로 구분하여 코드를 더 쉽게 읽고 이해할 수 있도록 해 줍니다.

### <a name="intellisense"></a>IntelliSense

코드 편집기는 또한 전체적으로 IntelliSense라고 하는 몇 가지 기능을 지원합니다. 메서드를 포인터로 가리키면 일부 기본 설명을 볼 수 있습니다. 클래스 변수 이름을 입력한 다음 . 또는 ->를 입력하면 해당 클래스의 인스턴스 멤버의 목록이 표시됩니다. 클래스 이름을 입력한 다음 ::을 입력하면 정적 멤버의 목록이 표시됩니다. 클래스 또는 메서드 이름을 입력하기 시작하면 문을 완료할 제안이 표시됩니다. 자세한 내용은 [IntelliSense 사용](/visualstudio/ide/using-intellisense)을 참조하세요.

### <a name="code-snippets"></a>코드 조각

IntelliSense 코드 조각을 사용하면 일반적으로 사용되거나 복잡한 코드 구문을 바로 가기 키 입력으로 생성할 수 있습니다. 자세한 내용은 [코드 조각](/visualstudio/ide/code-snippets)을 참조하세요.

## <a name="navigating-code"></a>코드 탐색

**보기** 메뉴에서는 코드 파일에서 탐색하기 위한 여러 창 및 도구에 액세스할 수 있습니다. 이러한 창에 대한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조하세요.

### <a name="solution-explorer"></a>솔루션 탐색기

모든 버전의 Visual Studio에서 **솔루션 탐색기** 창을 사용하여 프로젝트 내의 파일 사이를 탐색할 수 있습니다. .h 또는 .cpp 파일 아이콘을 확장하면 파일의 해당 클래스를 볼 수 있습니다. 클래스를 확장하면 해당 멤버가 표시됩니다. 멤버를 두 번 클릭하면 파일 내에서 해당 멤버의 정의 또는 구현으로 이동합니다.

### <a name="class-view-and-code-definition-window"></a>클래스 뷰 및 코드 정의 창

**클래스 뷰** 창을 사용하면 부분 클래스를 비롯하여 전체 파일의 네임스페이스 및 클래스를 볼 수 있습니다. 각 네임스페이스 또는 클래스를 확장하여 해당 멤버를 표시하고, 이러한 멤버를 두 번 클릭하여 소스 파일 내의 해당 위치로 이동할 수 있습니다. **코드 정의 창**을 여는 경우 **클래스 뷰**에서 선택한 형식의 정의 또는 구현을 볼 수 있습니다.

### <a name="object-browser"></a>개체 브라우저

**개체 브라우저**를 사용하여 Windows 런타임 구성 요소(.winmd 파일), .NET 어셈블리, COM 형식 라이브러리에서 형식 정보를 탐색합니다. Win32 DLL에는 사용되지 않습니다.

### <a name="go-to-definitiondeclaration"></a>정의/선언으로 이동

API 이름 또는 멤버 변수에서 F12 키를 누르면 해당 정의로 이동합니다. 정의가 .winmd 파일(UWP 또는 Windows 8.x Store 앱용)에 포함된 경우 개체 브라우저에 형식 정보가 표시됩니다. 변수 또는 형식 이름을 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 옵션을 선택하여 **정의로 이동** 또는 **선언으로 이동**을 선택할 수도 있습니다.

### <a name="find-all-references"></a>모든 참조 찾기

소스 코드 파일에서 형식 이름이나 변수의 메서드 위에 마우스 커서를 놓고 마우스 오른쪽 단추를 클릭한 후에 **모든 참조 찾기**를 선택하면 파일, 프로젝트 또는 솔루션 내에서 해당 형식이 사용된 모든 위치의 목록이 반환됩니다. **모든 참조 찾기**는 지능형이므로 다른 범위의 다른 변수에 동일한 이름이 있더라도 동일한 변수의 인스턴스만 반환합니다.

## <a name="add-and-edit-resources--msbuild"></a>리소스 추가 및 편집(MSBuild)

Visual Studio 데스크톱 프로젝트의 컨텍스트에서 *리소스*라는 용어에는 대화 상자, 아이콘, 지역화 가능한 문자열, 시작 화면, 데이터베이스 연결 문자열 또는 실행 파일에 포함하려는 임의 데이터가 포함됩니다.

네이티브 데스크톱 C++ 프로젝트에서 리소스 추가 및 편집에 대한 자세한 내용은 [리소스 파일 작업](../windows/working-with-resource-files.md)을 참조하세요.

## <a name="build-compile-and-link"></a>빌드(컴파일 및 연결)

메뉴 모음에서 **빌드** > **솔루션 빌드**를 선택하거나 Ctrl+Shift+B 키 조합을 입력하여 프로젝트를 컴파일하고 연결합니다. 실행 코드를 생성하기 위해 Visual Studio는 [MSBuild](/visualstudio/msbuild/msbuild1) 또는 CMake 또는 **폴더 열기**를 통해 설정한 빌드 환경을 사용합니다. MSBuild 프로젝트의 경우 **도구** > **옵션** > **프로젝트 및 솔루션**에서 일반 빌드 옵션을 설정하고 **프로젝트** > **속성**에서 특정 프로젝트에 대한 속성을 설정할 수 있습니다. 빌드 오류 및 경고는 오류 목록에 보고됩니다(Ctrl+\\, E). 비 MSBuild 프로젝트는 솔루션 탐색기에서 생성하는 JSON 파일로 구성됩니다. 사용하는 빌드 시스템에 관계없이 **출력** 창(Alt + 2)은 빌드 프로세스에 대한 정보를 표시합니다. MSBuild 구성에 대한 자세한 내용은 [프로젝트 속성 작업](../ide/working-with-project-properties.md) 및 [Visual Studio에서 C++ 프로젝트 빌드](../ide/building-cpp-projects-in-visual-studio.md)를 참조하세요.

컴파일러(cl.exe) 및 다양한 빌드 관련 독립 실행형 도구(예: NMAKE 및 LIB)를 명령줄에서 바로 사용할 수도 있습니다. 자세한 내용은 [명령줄에서 C/C++ 코드 빌드](../build/building-on-the-command-line.md) 및 [C/C++ 빌드 참조](../build/reference/c-cpp-building-reference.md)를 참조하세요.

## <a name="test"></a>테스트

Visual Studio에는 네이티브 C++ 및 C++/CLI에 대한 단위 테스트 프레임워크가 들어 있습니다. 자세한 내용은 [단위 테스트를 사용하여 코드 확인](/visualstudio/test/unit-test-your-code) 및 [C++용 Microsoft 단위 테스트 프레임워크를 사용하여 C/C++용 단위 테스트 작성](/visualstudio/test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp)을 참조하세요.

## <a name="debug"></a>디버그

프로젝트 구성이 디버그로 설정된 경우 **F5** 키를 눌러 프로그램을 디버그할 수 있습니다. 디버그하는 동안 **F9** 키를 눌러 중단점을 설정하고, **F10** 키를 눌러 코드를 단계별로 진행하고, 지정된 변수 또는 레지스터의 값을 확인하고, 일부 경우에는 코드 변경 후 다시 컴파일하지 않고 디버깅을 계속할 수도 있습니다. 자세한 내용은 [Visual Studio의 디버깅](/visualstudio/debugger/debugging-in-visual-studio)을 참조하세요.

## <a name="deploy-completed-applications"></a>완성된 응용 프로그램 배포

**프로젝트** > **Microsoft Store** 메뉴 옵션을 사용하여 Microsoft Store를 통해 UWP 앱을 고객에게 배포합니다. CRT 배포는 백그라운드에서 자동으로 처리됩니다. 자세한 내용은 [앱 판매](http://go.microsoft.com/fwlink/p/?LinkId=262280)를 참조하세요.

네이티브 C++ 데스크톱 응용 프로그램을 다른 컴퓨터에 배포할 때는 응용 프로그램 자체 및 이 응용 프로그램이 종속되는 라이브러리 파일을 설치해야 합니다. 중앙 배포, 로컬 배포 또는 정적 연결의 세 가지 방법으로 응용 프로그램과 함께 유니버셜 C++ 런타임(UCRT)을 배포할 수 있습니다. 자세한 내용은 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)를 참조하세요.

C++/CLI 프로그램의 배포에 대한 자세한 내용은 [개발자를 위한 배포 가이드](/dotnet/framework/deployment/deployment-guide-for-developers)를 참조하세요.

## <a name="related-articles"></a>관련 문서

|||
|-|-|
|[Visual Studio 버전의 Visual C++ 도구 및 기능](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)|다양한 Visual Studio 버전에서 사용할 수 있는 기능을 보여 줍니다.|
|[MSBuild 기반 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)|Visual Studio의 C++ MSBuild 기반 프로젝트에 대한 개요와 해당 프로젝트를 만들고 관리하는 방법을 설명하는 다른 문서에 대한 링크를 제공합니다.|
|[Visual C++의 CMake 프로젝트](cmake-tools-for-visual-cpp.md).|Visual C++에서 CMake 또는 다른 비 MSBuild 프로젝트를 빌드하는 방법을 설명합니다.|
|[C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)|C++ 프로젝트를 빌드하는 방법을 설명합니다.|
|[데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ 앱 및 배포에 대해 자세히 설명하는 다른 문서로 연결되는 링크에 대한 개요를 제공합니다.|
|[Visual C++ 포팅 및 업그레이드 가이드](../porting/visual-cpp-porting-and-upgrading-guide.md)|이전 버전의 Visual Studio에서 만들어진 C++ 응용 프로그램을 업그레이드하는 방법 및 Visual Studio 이외의 다른 도구를 사용하여 생성된 응용 프로그램을 마이그레이션하는 방법에 대한 자세한 정보입니다.|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio에 포함된 Visual C++의 주요 기능을 설명하고 Visual C++ 설명서의 나머지 부분에 연결합니다.|
