---
title: MSBuild (Visual c + +) 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae6e6d826f4bc1e8c9ab6cc28686e4ad1e6e3b02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379265"
---
# <a name="msbuild-visual-c-overview"></a>MSBuild(Visual C++) 개요  
  
MSBuild는 Visual c + + 프로젝트 시스템을 작성 하는 표준입니다. Visual Studio 통합된 개발 환경 (IDE)에서 프로젝트를 빌드할 때 사용 하 여 msbuild.exe 도구, XML 기반 프로젝트 파일 및 설정 (옵션) 파일입니다. Msbuild.exe 및 명령줄에서 프로젝트 파일을 사용할 수 있지만 보다 쉽게 설정을 구성 하 고 프로젝트를 빌드할 수 있도록 IDE 사용자 인터페이스를 제공 합니다. 이 개요에서는 Visual c + + MSBuild 시스템을 사용 하는 방법을 설명 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
  
MSBuild에 대 한 다음 문서를 참조 합니다.  
  
- [MSBuild](/visualstudio/msbuild/msbuild)  
 MSBuild 개념의 개요입니다.  
  
- [MSBuild 참조](/visualstudio/msbuild/msbuild-reference)  
 MSBuild 시스템에 대 한 참조 정보입니다.  
  
- [프로젝트 파일 스키마 참조](/visualstudio/msbuild/msbuild-project-file-schema-reference)  
 MSBuild XML 스키마 요소, 특성 및 부모 및 자식 요소와 함께 나열합니다. 특히 참고는 [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [대상](/visualstudio/msbuild/target-element-msbuild), 및 [작업](/visualstudio/msbuild/task-element-msbuild) 요소입니다.  
  
- [명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)  
 명령줄 인수 및 msbuild.exe로 사용할 수 있는 옵션에 설명 합니다.  
  
- [작업 참조](/visualstudio/msbuild/msbuild-task-reference)  
 MSBuild 작업을 설명합니다. 특히 Visual c + +와 관련 된 이러한 작업을 참고: [BscMake 작업](/visualstudio/msbuild/bscmake-task), [CL 작업](/visualstudio/msbuild/cl-task), [CPPClean 작업](/visualstudio/msbuild/cppclean-task), [LIB 작업](/visualstudio/msbuild/lib-task), [작업 연결할](/visualstudio/msbuild/link-task), [MIDL 작업](/visualstudio/msbuild/midl-task), [MT 작업](/visualstudio/msbuild/mt-task), [RC 작업](/visualstudio/msbuild/rc-task), [SetEnv 작업](/visualstudio/msbuild/setenv-task), [ VCMessage 작업](/visualstudio/msbuild/vcmessage-task), [XDCMake 작업](/visualstudio/msbuild/xdcmake-task), [XSD 작업](/visualstudio/msbuild/xsd-task)합니다.  
  
## <a name="msbuild-on-the-command-line"></a>명령줄에서 MSBuild를  
  
다음 문을 [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) 암시적 또는 명시적 msbuild.exe 도구를 사용 한다고에서는 *project_file* 인수 (Visual c + + 프로젝트.vcxproj 파일) 에 나오는 0 개 또는 더 명령줄 *옵션* 인수입니다.  
  
> **msbuild.exe** [ *project_file* ] [ *옵션* ]  
  
사용 하 여는 **/대상** (또는 **/t**) 및 **/property** (또는 **/p**) 명령줄 옵션 관련 속성 및 포함 된 대상만 재정의 프로젝트 파일에 지정 합니다.  
  
프로젝트 파일의 필수 기능은 지정 하는 것을 *대상*, 프로젝트 및 입력 및 해당 작업을 수행 하는 데 필요한 출력에 적용 되는 특정 연산을 변수인 합니다. 프로젝트 파일에는 기본 대상을 포함할 수 있는 하나 이상의 대상을 지정할 수 있습니다.  
  
하나 이상의 시퀀스를 각 대상 구성 *작업*합니다. 실행 한 명령을 포함 하는.NET Framework 클래스에서 각 작업을 표시 합니다. 예를 들어는 [CL 작업](/visualstudio/msbuild/cl-task) 포함는 [cl.exe](../build/reference/compiling-a-c-cpp-program.md) 명령입니다.  
  
A *작업 매개 변수* 클래스 작업의 속성 이며 일반적으로 실행 명령의 명령줄 옵션을 나타냅니다. 예를 들어는 `FavorSizeOrSpeed` 의 매개 변수는 `CL` 에 해당 하는 작업은 **/Os** 및 **/Ot** 컴파일러 옵션입니다.  
  
추가 작업 매개 변수는 MSBuild 인프라를 지원 합니다. 예를 들어는 `Sources` 작업 매개 변수는 다른 작업에서 사용할 수 있는 작업 집합을 지정 합니다. MSBuild 작업에 대 한 자세한 내용은 참조 [작업 참조](/visualstudio/msbuild/msbuild-task-reference)합니다.  
  
대부분의 작업 입력 및 출력 파일 이름, 경로, 문자열, 숫자 또는 부울 매개 변수 등 필요 합니다. 예를 들어 일반적인 입력 컴파일할.cpp 소스 파일의 이름입니다. 중요 한 입력된 매개 변수는 예를 들어 빌드 구성 및 플랫폼을 지정 하는 문자열 "디버그\|Win32"입니다. 하나 이상의 사용자 정의 XML에 의해 지정 된 입력 및 출력 `Item` 에 포함 된 요소는 `ItemGroup` 요소입니다.  
  
프로젝트 파일 사용자 지정 지정할 수도 *속성* 및 `ItemDefinitionGroup` *항목*합니다. 속성 및 항목 빌드에서 변수로 사용할 수 있는 이름/값 쌍을 형성 합니다. 한 쌍의 이름 구성 요소 정의 *매크로*, 값 구성 요소를 선언 하 고는 *매크로 값*합니다. $를 사용 하 여 액세스 하는 속성 매크로 (*이름*) 표기법 및 항목 매크로 %(를 사용 하 여 액세스*이름*) 표기법입니다.  
  
프로젝트 파일의 다른 XML 요소 수 매크로 테스트 하 고 조건에 따라 매크로의 값을 설정 하거나 빌드 실행을 제어 합니다. 경로 및 파일 이름 같은 구문을 생성 하는 매크로 이름 및 리터럴 문자열을 연결할 수 있습니다. 명령줄에서 **/property** 옵션을 설정 하거나 프로젝트 속성을 재정의 합니다. 명령줄에서 항목을 참조할 수 없습니다.  
  
조건에 따라 MSBuild 시스템은 다른 대상 전후 대상을 실행할 수 있습니다. 또한 시스템 파일 대상을 사용 하는 내보내는 파일 보다 최신 인지에 따라 대상을 작성할 수 있습니다.  
  
## <a name="msbuild-in-the-ide"></a>IDE의 MSBuild  
  
IDE에서 프로젝트 속성을 설정 하 고 다음 프로젝트를 저장 하는 경우 Visual c + + 프로젝트 설정 프로젝트 파일에 씁니다. 프로젝트 파일을 프로젝트에 고유한 설정이 포함 되어 있지만 프로젝트를 빌드해야 하는 데 필요한 모든 설정 포함 되어 있지 않습니다. 프로젝트 파일에 포함 되어 `Import` 의 추가 네트워크를 포함 하는 요소 *파일을 지원 합니다.* 지원 파일에는 나머지 속성, 대상 및 프로젝트를 빌드하는 데 필요한 설정을 포함 합니다.  
  
대부분의 대상 및 지원 파일에서 속성에는 빌드 시스템을 구현 하는 데에 존재 합니다. 다음 섹션에서는 몇 가지 유용한 대상과 MSBuild 명령줄에서 지정할 수 있는 속성에 설명 합니다. 더 많은 대상과 속성을 검색 하려면 지원 파일 디렉터리의 파일을 살펴보십시오.  
  
### <a name="support-file-directories"></a>지원 파일 디렉터리  
  
기본적으로는 기본 Visual c + + 지원 파일은 다음 디렉터리에 있습니다. Microsoft Visual Studio 아래의 디렉터리 MSBuild 아래의 디렉터리는 Visual Studio 2015 및 이전 버전에서 사용 되는 동안 Visual Studio 2017 및 이후 버전에서 사용 됩니다.  
  
|디렉터리|설명|  
|---------------|-----------------|  
|*드라이브*: \Program Files *(x86)* \Microsoft Visual Studio\\*연도*\\*edition*\Common7\IDE\VC\VCTargets\ <br /><br />*드라이브*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86) \v4.0\\*버전*\ |기본 대상 파일 (.targets)을 포함 하 고 대상에서 사용 되는 속성 파일 (.props). 기본적으로 $(VCTargetsPath) 매크로이 디렉터리를 참조합니다.|  
|*드라이브*: \Program Files *(x86)* \Microsoft Visual Studio\\*연도*\\*edition*\Common7\IDE\VC\VCTargets\ 플랫폼\\*플랫폼*\ <br /><br />*드라이브*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*버전*\Platforms\\*플랫폼*\ |대상 및 부모 디렉터리의 속성을 재정의 하는 플랫폼 특정 대상 및 속성 파일을 포함 합니다. 이 디렉터리는이 디렉터리에 있는 대상에서 사용 되는 작업을 정의 하는 DLL도 포함 됩니다.<br /><br /> *플랫폼* 자리 표시자는 ARM, Win32, 또는 x64 나타냅니다 하위 디렉터리입니다.|  
|*드라이브*: \Program Files *(x86)* \Microsoft Visual Studio\\*연도*\\*edition*\Common7\IDE\VC\VCTargets\ 플랫폼\\*플랫폼*\PlatformToolsets\\*도구 집합*\ <br /><br />*드라이브*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*버전*\Platforms\\*플랫폼*\ \ PlatformToolsets\\*도구 집합*\ <br /><br />*드라이브*: \Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*플랫폼*\PlatformToolsets\\*도구 집합*\ |지정 된를 사용 하 여 Visual c + + 응용 프로그램을 생성 하는 빌드를 사용할 수 있는 디렉터리를 포함 *도구 집합*합니다.<br /><br /> *연도* 및 *edition* 자리 표시자는 Visual Studio 2017 및 이후 버전에서 사용 됩니다. *버전* 자리 표시자는 Visual Studio 2012 용 V110, Visual Studio 2013 용 V120 또는 Visual Studio 2015 용 V140 합니다. *플랫폼* 자리 표시자는 ARM, Win32, 또는 x64 나타냅니다 하위 디렉터리입니다. *도구 집합* 자리 표시자 예를 들어 v140 v120_xp Visual Studio 2013 도구 집합 또는 v110_wp80를 사용 하 여 Windows XP 용 빌드를 위해 Visual Studio 2015 도구 집합을 사용 하 여 Windows 앱을 빌드하기 위한 도구 집합 하위 디렉터리를 나타냅니다. Visual Studio 2012 도구 집합을 사용 하 여 Windows Phone 8.0 앱을 빌드하십시오.<br /><br />Visual c + + 2008 또는 Visual c + + 2010 응용 프로그램을 생성 하는 빌드를 사용할 수 있는 디렉터리를 포함 하는 경로 포함 되지 않습니다는 *버전*, 및 *플랫폼* 자리 표시자를 나타냅니다 Itanium, Win32, 또는 x64 하위 디렉터리입니다. *도구 집합* 자리 표시자 v90 또는 v100 도구 집합 하위 디렉터리를 나타냅니다.|  
  
### <a name="support-files"></a>지원 파일  
  
이러한 확장명의 파일을 포함 하는 지원 파일 디렉터리:  
  
|확장명|설명|  
|---------------|-----------------|  
|.targets|포함 `Target` 대상에서 실행 되는 작업을 지정 하는 XML 요소입니다. 포함 될 수도 있습니다 `PropertyGroup`, `ItemGroup`, `ItemDefinitionGroup`, 사용자 정의 및 `Item` 파일 및 명령줄 옵션의 작업 매개 변수를 할당 하는 데 사용 되는 요소입니다.<br /><br /> 자세한 내용은 참조 [Target 요소 (MSBuild)](/visualstudio/msbuild/target-element-msbuild)합니다.|  
|.props|포함 `Property Group` 및 사용자 정의 `Property` 빌드하는 동안 사용 되는 파일 및 매개 변수 설정을 지정 하는 XML 요소입니다.<br /><br /> 포함 될 수도 있습니다 `ItemDefinitionGroup` 및 사용자 정의 `Item` 추가 설정을 지정 하는 XML 요소입니다. 항목 정의 그룹에 정의 된 항목은 속성과 비슷하지만 명령줄에서 액세스할 수 없습니다. Visual c + + 프로젝트 파일 속성 대신 항목 설정을 나타내는 데 주로 사용 합니다.<br /><br /> 자세한 내용은 참조 [ItemGroup 요소 (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), [ItemDefinitionGroup 요소 (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild), 및 [Item 요소 (MSBuild)](/visualstudio/msbuild/item-element-msbuild)합니다.|  
|.xml|선언 하 고 속성 시트 및 속성 페이지, 텍스트 상자와 목록 상자 컨트롤 같은 IDE 사용자 인터페이스 요소를 초기화 하는 XML 요소를 포함 합니다.<br /><br /> .Xml 파일에는 직접 IDE, 하지 MSBuild 지원합니다. 그러나 IDE 속성의 값은 빌드 속성 및 항목에 할당 됩니다.<br /><br /> 대부분.xml 파일이 로캘별 하위 디렉터리에 있습니다. 예를 들어 영어-미국 지역에 대 한 중인 $(VCTargetsPath) \1033\\합니다.|  
  
## <a name="user-targets-and-properties"></a>사용자 대상 및 속성  
  
명령줄에서 MSBuild를 가장 효과적으로 사용 하는 속성 및 대상도 유용 하 고 관련 알 수 있습니다. 대부분의 속성 및 대상에 Visual c + + 빌드 시스템을 구현 하는 데 도움이 하며 결과적으로 사용자에 게 관련 되지 않습니다. 이 섹션에서는 일부 좋은지를 사용자 기반 속성 및 대상을 설명 합니다.  

### <a name="platformtoolset-property"></a>플랫폼 도구 집합 속성  
  
`PlatformToolset` 속성 결정 빌드에는 Visual c + + 도구 집합이 사용 됩니다. 기본적으로 현재 도구 집합이 사용 됩니다. 이 속성이 설정 된 경우 속성의 값이 리터럴 문자열을 특정 플랫폼에 대 한 프로젝트를 빌드하는 데 필요한 속성 및 대상 파일이 있는 디렉터리의 경로와 연결 됩니다. 해당 플랫폼 도구 집합 버전을 사용 하 여 빌드하는 플랫폼 도구 집합 설치 되어야 합니다.  
  
예를 들어 설정 된 `PlatformToolset` 속성을 `v140` 응용 프로그램을 빌드하려면 Visual c + + 2015 도구 및 라이브러리를 사용 하려면:  
  
`msbuild myProject.vcxproj /p:PlatformToolset=v140`  
  
### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture 속성  
  
`PreferredToolArchitecture` 속성 32 비트 또는 64 비트 컴파일러 및 도구는 빌드에 사용 되는지 여부를 결정 합니다. 이 속성 출력 플랫폼 아키텍처 또는 구성에 영향을 주지 않습니다. 기본적으로 MSBuild 사용 하 여 x86 버전의 컴파일러 및이 속성을 설정 하지 않으면 도구입니다.  
  
예를 들어 설정는 `PreferredToolArchitecture` 속성을 `x64` 응용 프로그램을 빌드하는 64 비트 컴파일러 및 도구를 사용 하도록 합니다.  
  
`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="useenv-property"></a>UseEnv 속성  
  
기본적으로 현재 프로젝트에 대 한 플랫폼별 설정을 PATH, INCLUDE, LIB, LIBPATH, 구성 및 플랫폼 환경 변수를 재정의 합니다. 설정의 `UseEnv` 속성을 `true` 환경 변수 재정의 되지 않도록 보장할 수 있습니다.  
  
`msbuild myProject.vcxproj /p:UseEnv=true`  
  
### <a name="targets"></a>대상  
  
Visual c + + 지원 파일에서 대상을 수백 있습니다. 그러나 대부분은 시스템 기반 대상 사용자를 무시할 수입니다. 대부분의 시스템 대상 밑줄 (_)에 접두사로 수도 있고 "호출 후", "이전" 또는 "Post" "이전", "Compute", "PrepareFor"로 시작 하는 이름.  
  
다음 표에서 몇 가지 유용한 사용자 기반 대상을 나열합니다.  
  
|대상|설명|  
|------------|-----------------|  
|BscMake|Microsoft Browse Information Maintenance Utility 도구 실행 bscmake.exe 합니다.|  
|빌드|프로젝트를 빌드합니다.<br /><br /> 프로젝트에 대 한 기본 대상입니다.|  
|ClCompile|Visual c + + 컴파일러 도구 실행 cl.exe 합니다.|  
|정리|삭제 임시 및 중간 파일을 작성 합니다.|  
|Lib|Microsoft 32 비트 라이브러리 관리자 도구를 실행 lib.exe 합니다.|  
|링크|Visual c + + 링커 도구 실행 link.exe 합니다.|  
|ManifestResourceCompile|매니페스트 리소스의 목록을 추출한 다음 Microsoft Windows 리소스 컴파일러 도구를 실행 rc.exe 합니다.|  
|Midl|인터페이스 정의 언어 (MIDL) 컴파일러 도구 실행 midl.exe 합니다.|  
|다시 빌드|정리 하 고 프로젝트를 빌드합니다.|  
|ResourceCompile|Microsoft Windows 리소스 컴파일러 도구의 실행 rc.exe 합니다.|  
|XdcMake|XML 문서 도구 실행 xdcmake.exe 합니다.|  
|Xsd|XML 스키마 정의 도구 실행 xsd.exe 합니다.|  
  
## <a name="see-also"></a>참고 항목  
  
[MSBuild(Visual C++)](../build/msbuild-visual-cpp.md)
