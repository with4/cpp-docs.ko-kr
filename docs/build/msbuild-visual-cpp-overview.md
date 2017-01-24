---
title: "MSBuild(Visual C++) 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "MSBuild 개요"
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MSBuild(Visual C++) 개요
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MSBuild는 Visual c + + 프로젝트 시스템을 구축 하는 표준입니다. Visual Studio 통합된 개발 환경 (IDE)에서 프로젝트를 빌드할 때 사용 하 여 msbuild.exe 도구, 하는 XML 기반 프로젝트 파일 및 설정 (옵션) 파일입니다. Msbuild.exe 및 명령줄에서 프로젝트 파일을 사용할 수 있지만 더 쉽게 설정을 구성 하 고 프로젝트를 빌드할 수 있도록 IDE 사용자 인터페이스를 제공 합니다. 이 개요에서는 Visual c + +는 MSBuild 시스템을 사용 하는 방법을 설명 합니다.  
  
## <a name="prerequisites"></a>필수 조건  
 MSBuild에 대 한 다음 문서를 참조 합니다.  
  
 [MSBuild](MSBuild1.md)  
 MSBuild 개념의 개요입니다.  
  
 [MSBuild 참조](../Topic/MSBuild%20Reference.md)  
 MSBuild 시스템에 대 한 참조 정보입니다.  
  
 [프로젝트 파일 스키마 참조](../Topic/MSBuild%20Project%20File%20Schema%20Reference.md)  
 MSBuild XML 스키마 요소, 특성 및 부모 및 자식 요소와 함께 나열합니다. 특히 참고는 [ItemGroup](../Topic/ItemGroup%20Element%20\(MSBuild\).md), [PropertyGroup](../Topic/PropertyGroup%20Element%20\(MSBuild\).md), [대상](../Topic/Target%20Element%20\(MSBuild\).md), 및 [작업](../Topic/Task%20Element%20\(MSBuild\).md) 요소입니다.  
  
 [명령줄 참조](../Topic/MSBuild%20Command-Line%20Reference.md)  
 명령줄 인수 및 msbuild.exe에 사용할 수 있는 옵션에 설명 합니다.  
  
 [작업 참조](../Topic/MSBuild%20Task%20Reference.md)  
 MSBuild 작업에 설명 합니다. 특히 이러한 작업을 Visual c + +와 관련 된 참고: [BscMake 작업](../Topic/BscMake%20Task.md), [CL 작업](../Topic/CL%20Task.md), [CPPClean 작업](../Topic/CPPClean%20Task.md), [LIB 작업](../Topic/LIB%20Task.md), [링크 작업](../Topic/Link%20Task.md), [MIDL 작업](../Topic/MIDL%20Task.md), [MT 작업](../Topic/MT%20Task.md), [RC 작업](../Topic/RC%20Task.md), [SetEnv 작업](../Topic/SetEnv%20Task.md), [VCMessage 작업](../Topic/VCMessage%20Task.md), [XDCMake 작업](../Topic/XDCMake%20Task.md), [XSD 작업](../Topic/XSD%20Task.md)합니다.  
  
## <a name="msbuild-on-the-command-line"></a>명령줄에서 MSBuild  
 다음 문을 [명령줄 참조](../Topic/MSBuild%20Command-Line%20Reference.md) 문서에서는 암시적 또는 명시적 msbuild.exe 도구를 사용 한다고 `project file` 인수 (Visual c + + 프로젝트.vcxproj 파일)과 0 개 또는 더 명령줄 `options`합니다.  
  
 **msbuild.exe [** `project file` **] [** `options` **]**  
  
 사용 하는 **/대상** (또는 **/t**) 및 **/property** (또는 **/p**) 속성 및 프로젝트 파일에 지정 된 대상 재정의 하는 명령줄 옵션입니다.  
  
 프로젝트 파일의 필수 기능은 지정 하는 것을 *대상*, 프로젝트 및 입력 및 해당 작업을 수행 하는 데 필요한 출력에 적용 되는 특정 작업 인 합니다. 프로젝트 파일을 기본 대상을 포함할 수 있는 하나 이상의 대상을 지정할 수 있습니다.  
  
 하나 이상의 시퀀스로 구성 되어 각 대상 *작업*합니다. 각 작업은 하나의 실행 명령을 포함 하는.NET Framework 클래스로 표시 됩니다. 예를 들어는 [CL 작업](../Topic/CL%20Task.md) 포함 된 [cl.exe](../build/reference/compiling-a-c-cpp-program.md) 명령입니다.  
  
 A *작업 매개 변수* 클래스 작업의 속성 이며 일반적으로 실행 명령의 명령줄 옵션을 나타냅니다. 예를 들어는 `FavorSizeOrSpeed` 의 매개 변수는 `CL` 에 해당 하는 작업은 **/Os** 및 **/Ot** 컴파일러 옵션입니다.  
  
 추가 작업 매개 변수는 MSBuild 인프라를 지원 합니다. 예를 들어는 `Sources` 작업 매개 변수는 다른 작업에서 사용할 수 있는 작업 집합을 지정 합니다. MSBuild 작업에 대 한 자세한 내용은 참조 [작업 참조](../Topic/MSBuild%20Task%20Reference.md)합니다.  
  
 대부분의 작업에는 입력 및 출력을 파일 이름, 경로 및 문자열, 숫자 또는 부울 매개 변수 같은 필요 합니다. 예를 들어 일반적인 입력에는 컴파일할 소스.cpp 파일의 이름입니다. 중요 한 입력된 매개 변수는 빌드 구성 및 플랫폼, 예를 들어, "디버그 &#124;를 지정 하는 문자열 Win32 "입니다. 하나 이상의 사용자 정의 XML에 의해 지정 된 입력 및 출력 `Item` 에 포함 된 요소는 `ItemGroup` 요소입니다.  
  
 프로젝트 파일을 사용자 정의 지정할 수도 *속성* 및 *항목 정의-그룹**항목*합니다. 속성 및 항목 빌드에서 변수로 사용할 수 있는 이름/값 쌍을 형성 합니다. 한 쌍의 이름 구성 요소 정의 *매크로*, 값 구성 요소를 선언 하 고는 *매크로 값*합니다. 속성 매크로 $를 사용 하 여 액세스 됩니다 (*이름*) 표기법 및 항목 매크로 %(를 사용 하 여 액세스*이름*) 표기법입니다.  
  
 프로젝트 파일의 다른 XML 요소 매크로 테스트 하 고 조건에 따라 매크로의 값을 설정 되거나 빌드 실행을 제어 합니다. 경로 및 파일 이름과 같은 구조를 생성 하는 매크로 이름 및 리터럴 문자열을 연결할 수 있습니다. 명령줄에는 **/property** 옵션을 설정 하거나 프로젝트 속성을 재정의 합니다. 명령줄에서 항목을 참조할 수 없습니다.  
  
 조건에 따라 MSBuild 시스템은 다른 대상 전후 대상을 실행할 수 있습니다. 또한 시스템에서는 대상이 사용 하는 파일은 내보내는 파일 보다 최신 여부에 따라 대상을 빌드할 수 있습니다.  
  
## <a name="msbuild-in-the-ide"></a>IDE에서 MSBuild  
 IDE에서 프로젝트 속성을 설정 하 고 다음 프로젝트를 저장 하는 경우 Visual c + + 프로젝트 설정 프로젝트 파일에 씁니다. 프로젝트 파일을 프로젝트에 고유한 설정이 포함 되어 있지만 프로젝트를 빌드하는 데 필요한 모든 설정을 포함 되어 있지 않습니다. 프로젝트 파일에 포함 되어 `Import` 추가 하는 네트워크를 포함 하는 요소가 *파일을 지원 합니다.* 지원 파일에는 나머지 속성, 대상 및 프로젝트를 빌드하는 데 필요한 설정을 포함 합니다.  
  
 대부분의 대상과 속성의 설치 지원 파일 빌드 시스템을 구현 하는 데에 존재 합니다. 다음 섹션에서는 몇 가지 유용한 대상과 MSBuild 명령줄에서 지정할 수 있는 속성을 설명 합니다. 더 많은 대상과 속성 검색을 지원 파일 디렉터리에서 파일을 탐색 합니다.  
  
### <a name="support-file-directories"></a>지원 파일 디렉터리  
 기본적으로 기본 Visual c + + 지원 파일은 다음 디렉터리에 있습니다.  
  
|디렉터리|설명|  
|---------------|-----------------|  
|*드라이브*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*버전*\|기본 대상 파일 (.targets)을 포함 하 고 대상에서 사용 되는 속성 파일 (.props). 기본적으로 $(VCTargetsPath) 매크로이 디렉터리를 참조합니다.|  
|*드라이브*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*버전*\Platforms\\*플랫폼*\|대상 및 부모 디렉터리의 속성을 재정의 하는 플랫폼 특정 대상 및 속성 파일을 포함 합니다. 이 디렉터리에는이 디렉터리에 있는 대상에서 사용 되는 작업을 정의 하는.dll 파일이 포함 되어 있습니다.<br /><br />  *플랫폼* 자리 표시자를 나타냅니다는 `ARM`, `Win32`, 또는 `x64` 하위 디렉터리입니다.|  
|*드라이브*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\\*버전*\Platforms\\*플랫폼*\PlatformToolsets\\*도구 집합*\|지정 된 Visual c + + 응용 프로그램을 생성 하는 빌드를 사용할 수 있는 디렉터리가 포함 되어 *버전* 도구 집합입니다.<br /><br />  *플랫폼* 자리 표시자를 나타냅니다는 `ARM`, `Win32`, 또는 `x64` 하위 디렉터리입니다.  *도구 집합* 자리 표시자는 Windows, Windows XP 또는 Windows Phone 앱을 빌드하기 위한 도구 집합 하위 디렉터리를 나타냅니다.|  
|*드라이브*: \Program Files\MSBuild\Microsoft.Cpp\v4.0\Platforms\\*플랫폼*\PlatformToolsets\\*도구 집합*\|9.0 또는 Visual c + + 10.0 응용 프로그램을 생성 하는 빌드를 사용할 수 있는 디렉터리를 포함 합니다.<br /><br />  *플랫폼* 자리 표시자를 나타냅니다는 `Itanium`, `Win32`, 또는 `x64` 하위 디렉터리입니다.  *도구 집합* 자리 표시자를 나타냅니다는 `v90` 또는 `v100` 도구 집합 하위 디렉터리입니다.|  
  
### <a name="support-files"></a>지원 파일  
 지원 파일 디렉터리 파일의 확장명을 포함합니다.  
  
|확장명|설명|  
|---------------|-----------------|  
|.targets|포함 `Target` 대상에서 실행 되는 작업을 지정 하는 XML 요소입니다. 포함 될 수도 있습니다 `Property Group`, `Item Group`, `Item Definition Group`, 사용자 정의 및 `Item` 작업 매개 변수를 파일 및 명령줄 옵션을 할당 하는 데 사용 되는 요소입니다.<br /><br /> 자세한 내용은 참조 [Target 요소 (MSBuild)](../Topic/Target%20Element%20\(MSBuild\).md)합니다.|  
|.props|포함 `Property Group` 및 사용자 정의 `Property` 빌드하는 동안 사용 되는 파일 및 매개 변수 설정을 지정 하는 XML 요소입니다.<br /><br /> 포함 될 수도 있습니다 `Item Definition Group` 및 사용자 정의 `Item` 추가 설정을 지정 하는 XML 요소입니다. 항목 정의 그룹에 정의 된 항목은 속성과 비슷하지만 명령줄에서 액세스할 수 없습니다. Visual c + + 프로젝트 파일 자주 사용 하 여 항목 속성 대신 설정을 나타냅니다.<br /><br /> 자세한 내용은 참조 [ItemGroup 요소 (MSBuild)](../Topic/ItemGroup%20Element%20\(MSBuild\).md), [ItemDefinitionGroup 요소 (MSBuild)](../Topic/ItemDefinitionGroup%20Element%20\(MSBuild\).md), 및 [항목 요소 (MSBuild)](../Topic/Item%20Element%20\(MSBuild\).md)합니다.|  
|.xml|선언 하 고 속성 시트 및 속성 페이지 및 텍스트 상자와 목록 상자 컨트롤 같은 IDE 사용자 인터페이스 요소를 초기화 하는 XML 요소를 포함 합니다.<br /><br /> .Xml 파일에는 직접 IDE, 하지 MSBuild 지원합니다. 그러나 IDE 속성의 값은 빌드 속성 및 항목에 할당 됩니다.<br /><br /> 대부분.xml 파일이 로캘별 하위 디렉터리에 있습니다. 예를 들어 영어-미국 지역에 대 한 중인 $(VCTargetsPath) \1033\\합니다.|  
  
## <a name="user-targets-and-properties"></a>사용자 대상 및 속성  
 명령줄에서 MSBuild를 가장 효과적으로 사용 하는 속성 및 대상도 유용 하 고 관련 알 수 있습니다. 대부분의 속성과 대상을 Visual c + + 빌드 시스템을 구현 하는 데 도움이 되며 결과적으로 사용자에 게 유용한 하지 않습니다. 이 섹션에서는 일부 가치가 사용자 기반 속성 및 목표를 설명합니다.  
  
### <a name="platformtoolset-property"></a>플랫폼 도구 집합 속성  
  `PlatformToolset` 속성 빌드에 사용 되는 어떤 Visual c + + 도구 집합을 결정 합니다. 속성의 값은 리터럴 문자열을 특정 플랫폼에 대 한 프로젝트를 빌드하는 데 필요한 속성 및 대상 파일을 포함 하는 디렉터리의 경로와 연결 됩니다.  
  
 설정의 `PlatformToolset` 속성을 `v110` 사용 하 여 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] 도구 및 라이브러리 응용 프로그램을 빌드해야 합니다.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v110`  
  
 설정의 `PlatformToolset` 속성을 `v100` 사용 하 여 [!INCLUDE[cpp_dev10_long](../build/includes/cpp_dev10_long_md.md)] 도구 및 라이브러리 응용 프로그램을 빌드해야 합니다.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v100`  
  
 설정의 `PlatformToolset` 속성을 `v90` 를 사용 하 여 Visual c + + 2008 도구 및 라이브러리 응용 프로그램을 작성 합니다. Visual c + + 2008 도구 집합은이 속성을 적용 하려면 컴퓨터에 이미 설치 되어 있어야 합니다.  
  
 `msbuild myProject.vcxproj /p:PlatformToolset=v90`  
  
### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture 속성  
  `PreferredToolArchitecture` 속성은 32 비트 또는 64 비트 컴파일러 및 도구는 빌드에 사용 되는지 여부를 결정 합니다. 이 속성 출력 플랫폼 아키텍처 또는 구성에 영향을 주지 않습니다. 기본적으로 MSBuild 사용 하는 x86 버전의 컴파일러와 도구가이 속성이 설정 되지 않은 경우 나는 경우 설정 값으로 이외의 `x64`합니다.  
  
 설정의 `PreferredToolArchitecture` 속성을 `x64` 응용 프로그램을 작성 하는 64 비트 컴파일러 및 도구를 사용 하 여 합니다.  
  
 `msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="useenv-property"></a>UseEnv 속성  
 기본적으로 현재 프로젝트에 대 한 플랫폼별 설정을 PATH, INCLUDE, LIB, LIBPATH, 구성 및 플랫폼 환경 변수를 재정의 합니다. 설정의 `UseEnv` 속성을 `true` 환경 변수 재정의 되지 않도록 보장 합니다.  
  
 `msbuild myProject.vcxproj /p:UseEnv=true`  
  
### <a name="targets"></a>대상  
 Visual c + + 지원 파일에서 대상으로 수백 개가 나와 있습니다. 그러나 대부분은 시스템 기반 대상 사용자를 무시할 수입니다. 대부분의 시스템 대상 접두사는 밑줄 (_) 또는 "After", "사전" 또는 "Post" "이전", "계산", "PrepareFor"로 시작 하는 이름을 가진입니다.  
  
 다음 표에서 몇 가지는 것이 좋습니다 사용자 기반 대상을 나열합니다.  
  
|대상|설명|  
|------------|-----------------|  
|BscMake|Microsoft 찾아보기 정보 유지 관리 유틸리티 도구를 실행 하 여 bscmake.exe 합니다.|  
|빌드|프로젝트를 빌드합니다.<br /><br /> 이 프로젝트에 대 한 기본 대상입니다.|  
|ClCompile|Visual c + + 컴파일러 도구를 실행 하 여 cl.exe 합니다.|  
|정리|파일을 작성 하는 임시 및 중간 삭제.|  
|Lib|Microsoft 32 비트 라이브러리 관리자 도구를 실행 하 여 lib.exe 합니다.|  
|링크|Visual c + + 링커 도구를 실행 하 여 link.exe 합니다.|  
|ManifestResourceCompile|매니페스트에서 리소스의 목록을 추출 및 Microsoft Windows 리소스 컴파일러 도구를 실행 하 여 다음 rc.exe 합니다.|  
|Midl|인터페이스 정의 MIDL (Microsoft Language) 컴파일러 도구를 실행 하 여 midl.exe 합니다.|  
|다시 빌드|정리 하 고 프로젝트를 빌드합니다.|  
|ResourceCompile|Microsoft Windows 리소스 컴파일러 도구를 실행 하 여 rc.exe 합니다.|  
|XdcMake|XML 설명서 도구를 실행 하 여 xdcmake.exe 합니다.|  
|Xsd|XML 스키마 정의 도구를 실행 하 여 xsd.exe 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild (Visual c + +)](../build/msbuild-visual-cpp.md)