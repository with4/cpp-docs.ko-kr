---
title: '연습: MSBuild를 사용 하 여 Visual c + + 프로젝트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.walkthrough.createproject
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88366f78556ebcab6dc7b796cdeeefd402b99721
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392564"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기
이 연습에서는 사용 하는 방법을 보여 줍니다. [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 명령 프롬프트에서 Visual c + + 프로젝트를 빌드하려고 합니다. C + + 소스 파일 및 Visual c + + 콘솔 응용 프로그램에 대 한 XML 기반 프로젝트 파일을 만드는 방법에 설명 합니다. 프로젝트를 빌드한 후 빌드 프로세스를 사용자 지정 하는 방법에 설명 합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트에 대 한 c + + 소스 파일을 만듭니다.  
  
-   만든 XML [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트 파일입니다.  
  
-   사용 하 여 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트를 빌드할 수 있습니다.  
  
-   사용 하 여 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트를 사용자 지정할 수 있습니다.  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 진행하려면 먼저 다음 작업을 수행해야 합니다.  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   기본적으로 이해는 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 시스템입니다.  
  
## <a name="creating-the-c-source-files"></a>C + + 소스 파일을 만드는 중  
 이 연습에서 소스 파일 및 헤더 파일을 포함 하는 프로젝트를 만듭니다. 소스 파일 main.cpp 콘솔 응용 프로그램에 대 한 main 함수를 포함합니다. 헤더 파일 main.h iostream 헤더 파일을 포함 하는 코드를 포함 합니다. 사용 하 여 이러한 c + + 파일을 만들 수 있습니다 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 또는 텍스트 편집기입니다.  
  
#### <a name="to-create-the-c-source-files-for-your-project"></a>프로젝트에 대 한 c + + 소스 파일을 만들려면  
  
1.  프로젝트에 대 한 디렉터리를 만듭니다.  
  
2.  Main.cpp 라는 파일을 만들고이 파일에 다음 코드를 추가 합니다.  
  
    ```cpp  
    // main.cpp : the application source code.  
    #include <iostream>  
    #include "main.h"  
    int main()  
    {  
       std::cout << "Hello, from MSBuild!\n";  
       return 0;  
    }  
    ```  
  
3.  Main.h 라는 파일을 만들고이 파일에 다음 코드를 추가 합니다.  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## <a name="creating-the-xml-msbuild-project-file"></a>XML MSBuild 프로젝트 파일 만들기  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트 파일은 프로젝트 루트 요소를 포함 하는 XML 파일 (\<프로젝트 >). 다음 예제에서는 프로젝트에서는 \<프로젝트 > 요소는 7 개의 자식 요소를 포함 합니다.  
  
-   3 개 항목 그룹 태그 (\<ItemGroup >) 프로젝트 구성 및 플랫폼, 소스 파일 이름 및 헤더 파일 이름을 지정 하는 합니다.  
  
-   3 개의 태그를 가져옵니다 (\<가져올 >) Microsoft Visual c + + 설정의 위치를 지정 하는 합니다.  
  
-   속성 그룹 태그 (\<PropertyGroup >) 프로젝트 설정을 지정 하는 합니다.  
  
#### <a name="to-create-the-msbuild-project-file"></a>MSBuild 프로젝트 파일을 만들려면  
  
1.  텍스트 편집기를 사용 하 여 명명 된 프로젝트 파일을 만드는 `myproject.vcxproj`, 한 다음 루트 다음 추가 \<프로젝트 > 요소입니다. 루트 간의 다음 절차의 단계에 요소를 삽입 \<프로젝트 > 태그:  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  다음 두 개의 추가 \<프로젝트 구성 > 자식 요소에는 \<ItemGroup > 요소입니다. 자식 요소가 지정 디버그 및 릴리스 구성을 32 비트 Windows 운영 체제:  
  
    ```xml  
    <ItemGroup>  
      <ProjectConfiguration Include="Debug|Win32">  
        <Configuration>Debug</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
      <ProjectConfiguration Include="Release|Win32">  
        <Configuration>Release</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
    </ItemGroup>  
  
    ```  
  
3.  다음 추가 \<가져오기 / >이 프로젝트에 대 한 기본 c + + 설정의 경로 지정 하는 요소:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  다음 속성 그룹 요소 추가 (\<PropertyGroup >) 두 프로젝트 속성을 지정 하는:  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  다음 추가 \<가져오기 / >이 프로젝트에 대 한 현재 c + + 설정의 경로 지정 하는 요소:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  다음 추가 \<ClCompile > 자식 요소에는 \<ItemGroup > 요소입니다. 자식 요소에는 컴파일할 C/c + + 소스 파일의 이름을 지정 합니다.  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  다음 추가 \<ClInclude > 자식 요소에는 \<ItemGroup > 요소입니다. 자식 요소에는 C/c + + 소스 파일에 대 한 헤더 파일의 이름을 지정합니다.  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  다음 추가 \<가져오기 >이 프로젝트의 대상을 정의 하는 파일의 경로 지정 하는 요소:  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### <a name="complete-project-file"></a>전체 프로젝트 파일  
 다음 코드는 이전 절차에서 만든 전체 프로젝트 파일을 보여 줍니다.  
  
```xml  
<Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup>  
    <ProjectConfiguration Include="Debug|Win32">  
      <Configuration>Debug</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
    <ProjectConfiguration Include="Release|Win32">  
      <Configuration>Release</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  <PropertyGroup>  
    <ConfigurationType>Application</ConfigurationType>  
    <PlatformToolset>v120</PlatformToolset>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
  <ItemGroup>  
    <ClCompile Include="main.cpp" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClInclude Include="main.h" />  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
</Project>  
```  
  
## <a name="using-msbuild-to-build-your-project"></a>MSBuild를 사용 하 여 프로젝트를 빌드  
 콘솔 응용 프로그램을 빌드하려면 명령 프롬프트에서 다음 명령을 입력 합니다.  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 출력 파일에 대 한 디렉터리를 만듭니다. 컴파일 및 Myproject.exe 프로그램을 생성 하도록 프로젝트를 연결 합니다. 빌드 프로세스가 완료 되 면 응용 프로그램을 실행 하려면 다음 명령을 사용 합니다.  
  
```  
myproject  
```  
  
 응용 프로그램 "MSBuild에서: Hello!" 나타내야 합니다. 콘솔 창에 표시합니다.  
  
## <a name="customizing-your-project"></a>프로젝트 사용자 지정  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 미리 정의 된 빌드 대상을 실행, 사용자 정의 속성을 적용 하 고 사용자 지정 도구, 이벤트를 사용 하 여 및 빌드 단계 수 있습니다. 이 섹션에서는 다음 작업을 보여 줍니다.  
  
-   사용 하 여 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 빌드 대상을 사용 합니다.  
  
-   사용 하 여 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 빌드 속성을 사용 합니다.  
  
-   사용 하 여 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 64 비트 컴파일러 및 도구입니다.  
  
-   사용 하 여 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 다른 도구 집합과 함께 합니다.  
  
-   추가 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 사용자 지정 합니다.  
  
### <a name="using-msbuild-with-build-targets"></a>빌드 대상으로 MSBuild를 사용 하 여  
 A *빌드 대상* 빌드하는 동안 실행 될 수 있는 미리 정의 된 또는 사용자 정의 명령 명명 된 집합입니다. 대상 명령줄 옵션을 사용 하 여 (**/t**) 빌드 대상을 지정할 수 있습니다. 경우에 `myproject` 예제 프로젝트, 미리 정의 된 **클린** 대상 디버그 폴더의 모든 파일을 삭제 하 고 새 로그 파일을 만듭니다.  
  
 명령 프롬프트에서 정리 하려면 다음 명령을 입력 `myproject`합니다.  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### <a name="using-msbuild-with-build-properties"></a>MSBuild를 사용 하 여 빌드 속성  
 속성의 명령줄 옵션 (**/p**) 프로젝트 빌드 파일에서 속성을 재정의할 수 있습니다. 에 `myproject` 예제 프로젝트, 릴리스 또는 디버그 빌드 구성을 지정는 `Configuration` 속성입니다. 작성된 된 응용 프로그램을 실행 하려고 하는 운영 체제에서 지정 된는 `Platform` 속성입니다.  
  
 명령 프롬프트에서의 디버그 빌드를 만들려면 다음 명령을 입력 하 고 `myproject` 32 비트 Windows에서 실행 되는 응용 프로그램입니다.  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 가정은 `myproject` 프로젝트 64 비트 Windows 및 명명 된 사용자 지정 운영 체제에 대 한 다른 구성에 대 한 구성을 정의 하는 예제 `myplatform`합니다.  
  
 명령 프롬프트에서 릴리스를 만들려면 다음 명령을 작성 하는 형식이 64 비트 Windows에서 실행 됩니다.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 명령 프롬프트에 대 한 릴리스 빌드를 만들려면 다음 명령을 입력 `myplatform`합니다.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>64 비트 컴파일러 및 도구와 함께 MSBuild 사용  
 설치한 Visual c + + 64 비트 windows에서는 기본적으로 64 비트 x64 네이티브 및 크로스 도구 설치 됩니다. 구성할 수 있습니다 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 설정 하 여 응용 프로그램을 작성 하는 64 비트 컴파일러 및 도구를 사용 하 여 `PreferredToolArchitecture` 속성입니다. 이 속성 프로젝트 구성 또는 플랫폼 속성에는 영향을 주지 않습니다. 32 비트 버전의 도구는 기본적으로 사용 됩니다. 64 비트 버전의 컴파일러 및 도구를 지정 하려면 다음 속성 그룹 요소 후 Myproject.vcxproj 프로젝트 파일에 추가 된 `Microsoft.Cpp.default.props` \<가져오기 / > 요소:  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 명령 프롬프트에서 64 비트 도구를 사용 하 여 응용 프로그램을 빌드하도록 하려면 다음 명령을 입력 합니다.  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="using-msbuild-with-a-different-toolset"></a>다른 도구 집합으로 MSBuild를 사용 하 여  
 도구 집합 및 라이브러리가 다른 버전의 Visual c + + 설치 되어 있는 경우 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 에 맞게 응용 프로그램 현재 Visual c + + 버전 작성 하거나 다른 버전을 설치 합니다. 예를 들어, 설치한 경우 [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]는 Microsoft.Cpp.props 후 Myproject.vcxproj 프로젝트 파일에 다음 속성 그룹 요소를 추가, Windows XP 용 Visual c + + 11.0 도구 집합을 지정 하려면, `<Import />` 요소:  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 Visual c + + 11.0 Windows XP 도구 집합을 사용 하 여 프로젝트를 다시 작성 하려면 다음 명령 중 하나를 입력 합니다.  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### <a name="adding-msbuild-customizations"></a>사용자 지정 MSBuild를 추가합니다.  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 빌드 프로세스를 사용자 지정 하는 다양 한 방법을 제공 합니다. 다음 항목에서는 사용자 지정 빌드 단계, 도구 및 이벤트를 추가 하는 방법을 보여 프로그램 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트:  
  
-   [방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)  
  
-   [방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [방법: MSBuild 프로젝트에서 빌드 이벤트 사용](../build/how-to-use-build-events-in-msbuild-projects.md)