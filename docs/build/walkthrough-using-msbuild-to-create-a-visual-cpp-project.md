---
title: "연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.walkthrough.createproject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild(c++), 연습: 프로젝트 만들기"
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 연습에서는 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]를 사용하여 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 프로젝트를 명령 프롬프트에서 빌드하는 방법을 보여 줍니다.  이 연습을 통해 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 콘솔 응용 프로그램용 C\+\+ 소스 파일 및 XML 기반 프로젝트 파일을 만드는 방법을 배우게 됩니다.  프로젝트를 빌드한 후에는 빌드 프로세스를 사용자 지정하는 방법을 배웁니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트의 C\+\+ 소스 파일 만들기  
  
-   XML [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트 파일 만들기  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]를 사용하여 프로젝트 빌드  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]를 사용하여 프로젝트 사용자 지정  
  
## 사전 요구 사항  
 이 연습을 진행하려면 먼저 다음 작업을 수행해야 합니다.  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 시스템에 대한 전반적인 이해  
  
## C\+\+ 소스 파일 만들기  
 이 연습에서는 소스 파일 및 헤더 파일이 하나씩 있는 프로젝트를 만듭니다.  소스 파일인 main.cpp에는 콘솔 응용 프로그램의 main 함수가 포함되고,  헤더 파일인 main.h에는 iostream 헤더 파일을 포함하는 코드가 포함됩니다.  이러한 C\+\+ 파일은 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 또는 텍스트 편집기를 사용하여 만들 수 있습니다.  
  
#### 프로젝트의 C\+\+ 소스 파일을 만들려면  
  
1.  프로젝트의 디렉터리를 만듭니다.  
  
2.  main.cpp라는 파일을 만들고 다음 코드를 이 파일에 추가합니다.  
  
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
  
3.  main.h라는 파일을 만들고 다음 코드를 이 파일에 추가합니다.  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## XML MSBuild 프로젝트 파일 만들기  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트 파일은 프로젝트 루트 요소\(\<Project\>\)를 포함하는 XML 파일입니다.  다음 예제 프로젝트에서 \<Project\> 요소에는 자식 요소가 7개 있습니다.  
  
-   프로젝트 구성과 플랫폼, 소스 파일 이름 및 헤더 파일 이름을 지정하는 3개의 항목 그룹 태그\(\<ItemGroup\>\)입니다.  
  
-   Microsoft [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 설정 위치를 지정하는 3개의 가져오기 태그\(\<Import\>\)입니다.  
  
-   프로젝트 설정을 지정하는 속성 그룹 태그\(\<PropertyGroup\>\) 1개  
  
#### MSBuild 프로젝트 파일을 만들려면  
  
1.  텍스트 편집기를 사용하여 `myproject.vcxproj`라는 프로젝트 파일을 만들고 다음과 같은 루트 \<Project\> 요소를 추가합니다.  이 절차의 다음 단계에서 \<Project\> 루트 태그 사이에 루트 요소를 삽입합니다.  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  \<ItemGroup\> 요소에 다음과 같은 두 \<ProjectConfiguration\> 자식 요소를 추가합니다.  이 자식 요소는 32비트 Windows 운영 체제에 대해 디버그 및 릴리스 구성을 지정합니다.  
  
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
  
3.  이 프로젝트에 대한 기본 C\+\+ 설정의 경로를 지정하는 다음과 같은 \<Import\/\> 요소를 추가합니다.  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  두 프로젝트 속성을 지정하는 다음과 같은 속성 그룹 요소\(\<PropertyGroup\>\)를 추가합니다.  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  이 프로젝트에 대한 현재 C\+\+ 설정의 경로를 지정하는 다음과 같은 \<Import\/\> 요소를 추가합니다.  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  \<ItemGroup\> 요소에 다음과 같은 \<ClCompile\> 자식 요소를 추가합니다.  이 자식 요소는 컴파일할 C\/C\+\+ 소스 파일의 이름을 지정합니다.  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  \<ItemGroup\> 요소에 다음과 같은 \<ClInclude\> 자식 요소를 추가합니다.  이 자식 요소는 C\/C\+\+ 소스 파일에서 필요한 헤더 파일의 이름을 지정합니다.  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  이 프로젝트의 대상을 정의하는 파일의 경로를 지정하는 다음과 같은 \<Import\> 요소를 추가합니다.  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### 전체 프로젝트 파일  
 다음 코드는 앞의 절차에서 만든 전체 프로젝트 파일을 보여 줍니다.  
  
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
  
## MSBuild를 사용하여 프로젝트 빌드  
 명령 프롬프트에서 다음 명령을 입력하여 콘솔 응용 프로그램을 빌드합니다.  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]에서는 출력 파일을 저장할 디렉터리를 만든 다음, 프로젝트를 컴파일 및 링크하여 Myproject.exe 프로그램을 생성합니다.  빌드 프로세스가 끝나면 다음 명령을 사용하여 응용 프로그램을 실행합니다.  
  
```  
myproject  
```  
  
 응용 프로그램의 콘솔 창에 "Hello, from MSBuild\!"가 표시됩니다.  
  
## 프로젝트 사용자 지정  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]를 사용하면 미리 정의된 빌드 대상을 실행하고, 사용자 정의 속성을 적용할 수 있고 사용자 지정 도구, 이벤트 및 빌드 단계를 사용할 수 있습니다.  이 단원에서는 다음 작업에 대해 설명합니다.  
  
-   빌드 대상과 함께 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 사용  
  
-   빌드 속성과 함께 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 사용  
  
-   64비트 컴파일러 및 도구에서 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]를 사용합니다.  
  
-   다른 도구 집합과 함께 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 사용  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 사용자 지정 추가  
  
### 빌드 대상과 함께 MSBuild 사용  
 *빌드 대상*은 빌드 중에 실행할 수 있는 미리 정의되거나 사용자 정의된 명령의 명명된 집합입니다.  빌드 대상을 지정하려면 대상 명령줄 옵션\(**\/t**\)을 사용합니다.  `myproject` 예제 프로젝트의 경우 미리 정의된 **clean** 대상은 Debug 폴더에서 모든 파일을 삭제하고 새 로그 파일을 만듭니다.  
  
 `myproject`를 정리하려면 명령 프롬프트에 다음 명령을 입력합니다.  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### 빌드 속성과 함께 MSBuild 사용  
 속성 명령줄 옵션\(**\/p**\)을 사용하면 프로젝트 빌드 파일에서 속성을 재정의할 수 있습니다.  `myproject` 예제 프로젝트에서 릴리스 또는 디버그 빌드 구성은 `Configuration` 속성으로 지정되고,  빌드한 응용 프로그램을 실행할 운영 체제는 `Platform` 속성으로 지정됩니다.  
  
 32비트 Windows에서 실행될 `myproject` 응용 프로그램의 디버그 빌드를 만들려면 명령 프롬프트에서 다음 명령을 입력합니다.  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 `myproject` 예제 프로젝트에서 64비트 Windows용 구성 및 사용자 지정 운영 체제용으로 `myplatform`이라는 다른 구성도 정의하는 것으로 가정해 봅니다.  
  
 이 경우 64비트 Windows에서 실행되는 릴리스 빌드를 만들려면 명령 프롬프트에서 다음 명령을 입력합니다.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 `myplatform`용 릴리스 빌드를 만들려면 명령 프롬프트에서 다음 명령을 입력합니다.  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### 64비트 컴파일러 및 도구에 MSBuild 사용  
 64비트 Windows에 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]를 설치한 경우 기본적으로 64비트 x64 네이티브 및 Cross Tools가 설치됩니다.  응용 프로그램을 빌드하려고 64비트 컴파일러 및 도구를 사용하기 위해 `PreferredToolArchitecture` 속성을 설정하여 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]를 구성할 수 있습니다.  이 속성은 프로젝트 구성 또는 플랫폼 속성에 영향을 주지 않습니다.  기본적으로 32비트 버전의 도구가 사용됩니다.  64비트 버전의 컴파일러 및 도구를 지정하려면 `Microsoft.Cpp.default.props` \<Import \/\> 요소 다음에 Myproject.vcxproj 프로젝트 파일에 다음과 같은 속성 그룹 요소를 추가합니다.  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 64비트 도구를 사용하여 응용 프로그램을 빌드하려면 명령 프롬프트에서 다음 명령을 입력합니다.  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### 다른 도구 집합과 함께 MSBuild 사용  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)]이 설치된 다른 버전을 위한 도구 집합과 라이브러리가 있는 경우 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]는 최신 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 버전 또는 다른 설치된 버전을 위한 응용 프로그램을 빌드할 수 있습니다.  예를 들어, [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)]를 설치한 경우 Windows XP용 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 도구 집합을 지정하려면 Microsoft.Cpp.props `<Import />` 요소 뒤에 다음 속성 그룹 요소를 Myproject.vcxproj 프로젝트 파일에 추가합니다.  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 Windows XP 도구 집합을 사용하여 프로젝트를 다시 빌드하려면 다음 명령 중 하나를 입력합니다.  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### MSBuild 사용자 지정 추가  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]에서는 빌드 프로세스를 사용자 지정할 수 있는 다양한 방법을 제공합니다.  다음 항목은 사용자 지정 빌드 단계, 도구 및 이벤트를 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 프로젝트에 추가하는 방법을 보여 줍니다.  
  
-   [방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)  
  
-   [방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [방법: MSBuild 프로젝트에서 빌드 이벤트 사용](../build/how-to-use-build-events-in-msbuild-projects.md)