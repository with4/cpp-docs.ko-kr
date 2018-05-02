---
title: VC + + 디렉터리 속성 페이지 | Microsoft Docs
ms.custom: ''
ms.date: 04/26/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-ide
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs:
- C++
helpviewer_keywords:
- VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: 25
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8931ecd34acfa1aba0287274acb45d362bdec2cf
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="vc-directories-property-page-windows"></a>VC + + 디렉터리 속성 페이지 (Windows)

Visual Studio는 현재 선택한 프로젝트를 빌드할 때 사용 하는 디렉터리를이 속성 페이지를 사용 합니다. 솔루션의 여러 프로젝트에 대 한 디렉터리를 설정 하려면 사용 하 여 사용자 지정 속성 시트에 설명 된 대로 [재사용 가능 속성 구성을 만드는](working-with-project-properties.md#bkmkPropertySheets)합니다.

이 페이지의 Linux 버전에 대 한 참조 [VC + + 디렉터리 (Linux c + +)](../linux/prop-pages/directories-linux.md)합니다.   

액세스는 **VC + + 디렉터리** 속성 페이지:

1. 경우는 **솔루션 탐색기** 창이 표시 되지 않으면, 다음 주 메뉴 선택 **보기** > **솔루션 탐색기**합니다.
1. 프로젝트 노드 (최상위 솔루션 아님)를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.
1. 왼쪽된 창에는 **속성 페이지** 대화 상자에서 **구성 속성** > **VC + + 디렉터리**합니다.  

VC + + 디렉터리 속성 최상위 솔루션 노드가 아닌 프로젝트에 적용 됩니다. 표시 되지 않으면 **VC + + 디렉터리** 아래 **구성 속성**에서 c + + 프로젝트 노드를 선택는 **솔루션 탐색기** 창: 

![프로젝트 노드를 선택](media/vcppdir.png "VC + + 디렉터리 속성을 보려면 프로젝트 노드를 선택 합니다.")

**VC + + 디렉터리** 플랫폼 간 프로젝트에 대 한 속성 페이지를 다르게 보입니다. Linux c + + 프로젝트에 대 한 정보를 참조 하세요. [VC + + 디렉터리 (Linux c + +)](../linux/prop-pages/directories-linux.md)합니다. 
 
에 익숙한 경우 *프로젝트 속성* Visual Studio에서 있습니다 수 도움이 될 첫 번째 읽기 [프로젝트 속성 작업](working-with-project-properties.md)합니다. 
 
에 대 한 기본 설정을 **VC + + 디렉터리** 속성 프로젝트 형식에 따라 달라 집니다. 데스크톱 프로젝트에 대 한 특정 플랫폼 도구 집합에 대 한 c + + 도구 위치 및 Windows SDK 위치로 포함 됩니다. 변경할 수는 **플랫폼 도구 집합** 및 **Windows SDK 버전** 에 **구성 속성** > **일반** 페이지입니다. 

디렉터리에 대 한 값을 보려면:

1. 속성 중 하나를 선택는 **VC + + 디렉터리** 페이지. 예를 들어 선택 **라이브러리 디렉터리**합니다.
1. 속성 값 필드의 끝에 있는 아래쪽 화살표 단추를 선택 합니다.
1. 드롭 다운 메뉴에서 선택 **편집**합니다.

![라이브러리 디렉터리를 편집](media/vcppdir_libdir_edit.png "라이브러리 경로 편집할 수 대화 상자")

이제 다음과 같은 대화 상자가 표시: 

![라이브러리 디렉터리 표시](media/vcppdir_libdir.png "대화 상자를 추가 하거나 라이브러리 경로 제거 합니다.")

이 대화 상자를 사용 하 여 현재 디렉터리를 볼 수 있습니다. 그러나 디렉터리를 추가 하거나 변경 하려면 원하는 있는지 사용 하 여 **속성 관리자** 속성 시트를 만들거나 기본 사용자 속성 시트를 수정 합니다. 자세한 내용은 참조 [재사용 가능 속성 구성을 만드는](working-with-project-properties.md#bkmkPropertySheets)합니다.

위와 같이 매크로로 지정 됩니다 다양 한 상속 된 경로입니다.  매크로의 현재 값을 검사 하려면 선택은 **매크로** 대화 상자의 오른쪽 아래에는 단추입니다. 참고 많은 매크로 구성 형식에 따라 달라 집니다. 디버그 빌드에서 매크로 릴리스 빌드에서 같은 매크로 다른 경로를 평가할 수 있습니다. 

편집 상자에 일치 하는 일부 또는 전체를 검색할 수 있습니다. 다음 그림은 "WindowsSDK" 문자열이 포함 된 모든 매크로 보여주며, 매크로로 계산 되는 현재 경로 보여 줍니다.

![매크로 값 참조](media/vcppdir_libdir_macros.png "매크로 편집 대화 상자")

참고:이 목록은 입력할 때 채워집니다. 누르지 마세요 **Enter**합니다.

매크로 및 하드 코드 된 경로 가능 하면 대신에 사용 해야 하는 방법에 대 한 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md#bkmkPropertiesVersusMacros)합니다. 

자주 사용 되는 매크로의 목록이 참조 [빌드 명령 및 속성에 대 한 일반적인 매크로](https://docs.microsoft.com/en-us/cpp/ide/common-macros-for-build-commands-and-properties)합니다.

두 가지 방법으로 사용자 고유의 매크로 정의할 수 있습니다.
-   개발자 명령 프롬프트에서 환경 변수를 설정 합니다. 모든 환경 변수는 MSBuild 속성/매크로로 처리 됩니다.
-   .Props 파일에서 사용자 매크로 정의 합니다. 자세한 내용은 참조 [속성 페이지 매크로](working-with-project-properties.md#bkmkPropertiesVersusMacros)합니다. 

자세한 내용은 다음 블로그 게시물을 참조 하십시오.: [VC + + 디렉터리](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [상속 된 속성 및 속성 시트](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), 및 [Visual Studio 2010 c + + 프로젝트 업그레이드 가이드](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx)합니다.  
  
## <a name="directory-types"></a>디렉터리 형식

다음과 같이 다른 디렉터리를 지정할 수도 있습니다.  
  
**실행 가능 디렉터리**<br/>
실행 파일을 검색할 디렉터리입니다. 에 해당 하는 **경로** 환경 변수입니다.

**포함 디렉터리**<br/>
소스 코드에서 참조되는 포함 파일을 검색할 디렉터리입니다. 에 해당 하는 **INCLUDE** 환경 변수입니다.

**참조 디렉터리**<br/>
 디렉터리를 검색 하 여 소스 코드에서 참조 되는 어셈블리 및 모듈 (메타 데이터)에 [#using](../preprocessor/hash-using-directive-cpp.md) 지시문입니다. 에 해당 하는 **LIBPATH** 환경 변수입니다.

**라이브러리 디렉터리**<br/>
라이브러리(.lib) 파일을 검색할 디렉터리입니다. 여기에는 런타임 라이브러리가 포함됩니다. 에 해당 하는 **LIB** 환경 변수입니다. 이 설정은.obj 파일에 적용 되지 않습니다. .obj 파일에 연결 하는 **구성 속성** > **링커** > **일반** 속성 페이지  **추가 라이브러리 종속성** 한 다음 파일의 상대 경로 지정 합니다. 자세한 내용은 참조 [링커 속성 페이지](../ide/linker-property-pages.md)합니다.

**WinRT 라이브러리 디렉터리**<br/>
유니버설 Windows 플랫폼 (UWP) 앱에서 WinRT 라이브러리 파일에 대 한 검색 하는 디렉터리를 사용 합니다. 

**원본 디렉터리**<br/>
IntelliSense에 사용할 소스 파일을 검색할 디렉터리입니다.

**디렉터리 제외**<br/>
각 컴파일 전에 Visual Studio 이전 컴파일 이후에 수정 된 여부는 확인 하는 모든 파일에 타임 스탬프를 쿼리 합니다. 프로젝트에 큰 안정적인 라이브러리를 타임 스탬프 확인에서 이러한 디렉터리를 제외 하 여 빌드 시간을 속도 잠재적으로 수 있습니다.

## <a name="sharing-the-settings"></a>설정 공유

프로젝트 속성을 다른 사용자 또는 여러 컴퓨터와 공유할 수 있습니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.
