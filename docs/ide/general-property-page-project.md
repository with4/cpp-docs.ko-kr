---
title: "일반 속성 페이지 (프로젝트) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.ManagedExtensions
- VC.Project.VCConfiguration.BuildBrowserInformation
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.ATLMinimizesCRunTimeLibraryUsage
- VC.Project.VCConfiguration.ReferencesPath
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.useOfMfc
- VC.Project.VCConfiguration.CharacterSet
- VC.Project.VCGeneralMakefileSettings.ConfigurationType
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.AppSupport
- VC.Project.VCConfiguration.ToolFiles
- VC.Project.VCConfiguration.useOfATL
dev_langs: C++
helpviewer_keywords:
- Clean Build option
- output files, setting directory
- Unicode, creating C++ build configuration
ms.assetid: 593b383c-cd0f-4dcd-ad65-9ec9b4b19c45
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9b702c1835ed1a3b280e6fe38dff91161d92c661
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="general-property-page-project"></a>일반 속성 페이지(프로젝트)
솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 하면 **속성**, **일반** 속성 페이지에는 **구성 속성** 에서 노드는 왼쪽된 창에는 속성의 두 섹션이 표시 됩니다.  
  
-   일반  
  
-   프로젝트 기본값  
  
## <a name="general"></a>일반  
 일반 섹션의 속성은 빌드 프로세스에서 생성 되 고 삭제 될 때 파일에 파일의 위치에 영향을 줄의 **Clean** 옵션 (**빌드** 메뉴)을 선택 합니다.  
  
 **대상 플랫폼**  
 프로젝트를 실행할 플랫폼을 지정합니다. 예를 들어 Windows, Android 또는 iOS입니다. 값 **Windows 10** 유니버설 Windows 플랫폼 프로젝트 대상을 의미 합니다. 이전 버전의 Windows 대상으로 하 고, 버전 옵션이 나타나지 않으면,이 필드의 값 표시 같이 정당한 **Windows**합니다. 이 필드는 프로젝트를 만들 때 설정되는 읽기 전용 필드입니다.  
  
 **Windows SDK 버전**  
 Windows 대상 플랫폼에 대 한 프로젝트에 필요한 Windows SDK 버전을 지정 합니다. Visual Studio 설치 관리자를 사용 하 여 c + + 작업 부하를 설치할 때 Windows SDK의 필수 부분도 설치 됩니다. 컴퓨터에서 다른 Windows SDK 버전을 설정한 경우 각 버전의 설치 된 SDK 도구 드롭다운에 나타납니다.  
  
 Windows 7 또는 Windows Vista를 대상으로 값을 사용 하 여 **8.1**Windows SDK 8.1이 해당 플랫폼 버전과 호환 되므로, 합니다. 에 대 한 적절 한 값을 정의 해야 또한 **_WIN32_WINNT** targetver.h에서 합니다. Windows 7의 경우 0x0601입니다. 참조 [WINVER 및 _WIN32_WINNT 수정](../porting/modifying-winver-and-win32-winnt.md)합니다.  
  
 Windows XP 및 Windows 2003 Server 프로젝트를 빌드하는 라이브러리의 현재 버전을 사용 하도록 Visual Studio에 포함 된 Windows XP 플랫폼 도구 집합을 설치할 수 있습니다. 이 플랫폼 도구 집합을 사용 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Windows XP 용 프로그램 구성](../build/configuring-programs-for-windows-xp.md)합니다. 플랫폼 도구 집합을 변경하는 방법에 대한 자세한 내용은 [방법: 대상 프레임워크 및 플랫폼 도구 집합 수정](../build/how-to-modify-the-target-framework-and-platform-toolset.md)을 참조하세요.  
  
 **대상 플랫폼 최소 버전**  
 프로젝트를 실행할 수 있는 가장 낮은 플랫폼 버전을 지정합니다. 이 속성은 Windows 유니버설 프로젝트와 같이 프로젝트 형식이 지원하는 경우에만 나타납니다. 앱이 최신 Windows SDK 버전의 기능을 활용할 수 있지만 해당 기능이 없는 이전 버전에서도 일부 기능은 손실되지만 실행될 수 있는 경우 이러한 두 속성의 값이 다를 수 있습니다. 이 경우 코드에서 런타임에 실행 중인 플랫폼의 버전을 확인해야 하며, 이전 플랫폼 버전에서 사용할 수 없는 기능은 사용하지 않도록 해야 합니다.  
  
 Visual C++는 이 옵션을 적용하지 않습니다. C# 및 JavaScript와 같은 다른 언어와의 일관성을 위해 및 프로젝트 사용자를 위한 지침으로 포함되었습니다. Visual C++는 최소 버전에서 사용할 수 없는 기능을 사용하는 경우 오류를 생성하지 않습니다.  
  
 **출력 디렉터리**  
 링커 등의 도구가 빌드 프로세스 중에 생성되는 모든 최종 출력 파일을 배치하는 디렉터리를 지정합니다. 일반적으로 이 디렉터리에는 링커, 라이브러리 관리자 또는 BSCMake와 같은 도구의 출력이 포함됩니다. 기본적으로이 속성은 매크로 $(SolutionDir) $(Configuration)로 지정 된 디렉터리 \ \.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A>를 참조하세요.  
  
 **중간 디렉터리**  
 컴파일러 등의 도구가 빌드 프로세스 중에 생성되는 모든 중간 파일을 배치하는 디렉터리를 지정합니다. 일반적으로 이 디렉터리에는 C/C++ 컴파일러, MIDL 및 리소스 컴파일러와 같은 도구의 출력이 포함됩니다. 기본적으로이 속성은 매크로 $(Configuration)로 지정 된 디렉터리 \ \.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A>를 참조하세요.  
  
 **대상 이름**  
 이 프로젝트에서 생성하는 파일 이름을 지정합니다. 이 속성은 기본적으로 매크로 $(ProjectName)가 지정한 파일 이름입니다.  
  
 **대상 확장명**  
 이 프로젝트에서 생성하는 파일 이름 확장명(예: .exe 또는 .dll)을 지정합니다.  
  
 **정리할 때 삭제할 확장명**  
 **Clean** 옵션 (**빌드** 메뉴)은 프로젝트 구성이 빌드되는 중간 디렉터리에서 파일을 삭제 합니다. 이 속성으로 지정 된 확장명을 사용 하 여 파일 됩니다 때 **Clean** 를 실행 하거나 다시 빌드를 수행 하는 경우. 중간 디렉터리에 있는 이러한 확장명의 파일뿐 아니라 빌드 시스템은 위치에 관계없이 알려진 빌드 출력(.obj 파일과 같은 중간 출력 포함)도 삭제합니다. 와일드카드 문자를 지정할 수 있습니다.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>를 참조하세요.  
  
 **빌드 로그 파일**  
 프로젝트를 빌드할 때마다 생성되는 로그 파일에 대해 기본값이 아닌 위치를 지정할 수 있습니다. 기본 위치는 매크로 $(IntDir) $(MSBuildProjectName).log에 의해 지정 됩니다.  
  
 프로젝트 매크로를 사용하여 디렉터리 위치를 변경할 수 있습니다. 참조 [빌드 명령 및 속성에 대 한 일반적인 매크로](../ide/common-macros-for-build-commands-and-properties.md)합니다.  
  
 **플랫폼 도구 집합**  
 프로젝트가 다른 버전의 Visual C++ 라이브러리 및 컴파일러를 대상으로 할 수 있도록 허용합니다. Visual c + + 프로젝트 중 하나는 기본 도구 집합 Visual Studio 또는 Windowx XP에서 실행 될 수 있는 실행 파일을 만드는 도구 집합을 비롯해 Visual Studio의 여러 이전 버전에서 설치 된 도구 집합 중 하나에 의해 설치 대상으로 지정할 수 있습니다. 플랫폼 도구 집합 변경에 대 한 정보를 참조 하십시오. [하는 방법: 대상 프레임 워크 및 플랫폼 도구 집합 수정](../build/how-to-modify-the-target-framework-and-platform-toolset.md)합니다.  
  
**관리 되는 증분 빌드 사용**  
관리 되는 프로젝트에 대 한이 통해 외부 표시 유형에 대 한 검색 어셈블리를 생성 합니다. 관리 되는 프로젝트에 대 한 변경이 다른 프로젝트에 표시 되지 않는 경우 다음 종속 프로젝트 하지 다시 작성 됩니다. 관리 되는 프로젝트를 포함 하는 솔루션에서 빌드 시간을 크게 개선할 수 있습니다이 있습니다.  
  
## <a name="project-defaults"></a>프로젝트 기본값  
 프로젝트 기본값 섹션의 속성은 수정할 수 있는 기본 속성을 나타냅니다. .Props 파일에서 이러한 속성에 대 한 정의 찾을 수 *설치 디렉터리*\VC\VCProjectDefaults 합니다.  
  
 **구성 유형**  
 선택할 수 있는 여러 구성 형식이 있습니다.  
  
-   **응용 프로그램 (.exe)**, 링커 도구 집합 (C/c + + 컴파일러, MIDL, 리소스 컴파일러, 링커, BSCMake, XML 웹 서비스 프록시 생성기, 사용자 지정 빌드, 사전 빌드, 사전 링크, 사후 빌드 이벤트)를 표시 합니다.  
  
-   **동적 라이브러리 (.dll)**을 링커 도구 집합을 표시, /DLL 링커 옵션을 지정 하 고 CL에 _WINDLL define을 추가 합니다.  
  
-   **메이크파일**, 메이크파일 도구 집합 (NMake)을 표시 합니다.  
  
-   **정적 라이브러리 (.lib)**, 라이브러리 관리자 도구 집합 (링커를 라이브러리 관리자로 대체 하 고 XML 웹 서비스 프록시 생성기를 생략 점을 제외 하 고 링커 도구 집합과 같음)을 표시 합니다.  
  
-   **유틸리티**, 유틸리티 도구 집합 (MIDL, 사용자 지정 빌드, 사전 빌드, 사후 빌드 이벤트)를 표시 합니다.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A>를 참조하세요.  
  
 **MFC 사용**  
 MFC 프로젝트가 MFC DLL에 정적 또는 동적으로 연결하는지를 지정합니다. 비 MFC 프로젝트를 선택할 수 **표준 Windows 라이브러리 사용** MFC를 사용할 때 포함 되는 다양 한 Win32 라이브러리에 연결 합니다.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>를 참조하세요.  
  
 **ATL 사용**  
 ATL 프로젝트가 ATL .DLL에 정적 또는 동적으로 연결하는지를 지정합니다. 항목을 이외의 지정한 경우 **atl 사용 안 함**, 컴파일러의에 define이 추가 됩니다 **명령줄** 속성 페이지.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL%2A>를 참조하세요.  
  
 **문자 집합**  
 _UNICODE 또는 _MBCS를 설정해야 하는지를 정의합니다. 해당하는 경우 링커 진입점에도 영향을 줍니다.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>를 참조하세요.  
  
 **공용 언어 런타임 지원**  
 로 인해는 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 사용 합니다.  
  
 프로그래밍 방식으로 이 속성에 액세스하려면 <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>를 참조하세요.  
  
**대상.NET Framework 버전**  
관리 되는 프로젝트의 대상.NET framework 버전을 지정합니다.  
  
 **전체 프로그램 최적화**  
 지정 된 [/GL](../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션 및 [/LTCG](../build/reference/ltcg-link-time-code-generation.md) 링커 옵션입니다. 기본적으로 디버그 구성에 대 한 비활성화 이며 소매 구성에 대해 사용 하도록 설정 합니다.  
  
 **Windows 스토어 응용 프로그램 지원**  
 이 프로젝트에 Windows 스토어 앱 지원 하는지 여부를 지정 합니다. 자세한 내용은 참조 [/ZW (Windows 런타임 컴파일)](../build/reference/zw-windows-runtime-compilation.md), 및 Windows 개발자 센터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)