---
title: ".vcxproj 및.props 파일 구조 | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- .vcxproj file structure
ms.assetid: 14d0c552-29db-480e-80c1-7ea89d6d8e9c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d48b16d9a4250de8c8c3dfef62fdcfb5c1434960
ms.sourcegitcommit: 6f40bba1772a09ff0e3843d5f70b553e1a15ab50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2018
---
# <a name="vcxproj-and-props-file-structure"></a>.vcxproj 및.props 파일 구조

MSBuild는 Visual Studio;에서 기본 프로젝트 시스템 선택 하는 경우 **파일 | 새 프로젝트** 설정을 가진은 확장명을 가진 XML 프로젝트 파일에 저장 됩니다는 MSBuild 프로젝트를 만드는 Visual c + +에서 `.vcxproj`합니다. .Props 파일 및.targets 파일로 설정 저장 될 수 있는 프로젝트 파일을 가져올 수도 있습니다. 대부분의 경우 프로젝트 파일을 수동으로 편집할 필요가 없습니다 실제로 편집 해야 합니다 하지 것 수동으로 MSBuild 잘 알게 없는 경우. 프로젝트 설정을 수정 하려면 Visual Studio 속성 페이지를 사용 해야 가능 하면 항상 (참조 [프로젝트 속성 작업](working-with-project-properties.md)합니다. 그러나 경우에 따라 프로젝트 파일 또는 속성 시트를 수동으로 수정 해야 할 수 있습니다. 이러한 시나리오에 대 한이 문서는 파일의 구조에 대 한 기본 정보를 포함합니다.

**중요:**

.Vcxproj 파일을 수동으로 편집 하려는 경우 이러한 사항을 고려해 야 합니다.

1. 파일의 구조는이 문서에 설명 된 지정 된 폼을 준수 해야 합니다.

1. 현재 Visual c + + 프로젝트 시스템에서 프로젝트 항목에 와일드 카드를 지원 하지 않습니다. 예를 들어이 지원 되지 않습니다.

   ```xml
   <ClCompile Include="*.cpp"/>
   ```

1. 현재 Visual c + + 프로젝트 시스템에서 프로젝트 항목 경로에 매크로 지원 하지 않습니다. 예를 들어이 지원 되지 않습니다.

   ```xml
   <ClCompile Include="$(IntDir)\generated.cpp"/>
   ```

1. 올바르게 추가, 제거 또는 수정할에서 편집할 때 프로젝트 속성을 가지려면는 **프로젝트 속성** 대화 상자에서 파일에는 각 프로젝트 구성에 대 한 별도 그룹 포함 되어야 하 고 조건을이 형식 이어야 합니다.

   ```xml
   Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'"
   ```

1. 속성 규칙 파일에 지정 된 대로 올바른 레이블이 설정 된 그룹에 각 속성을 지정 해야 합니다. 자세한 내용은 참조 [속성 페이지 xml 규칙 파일](property-page-xml-files.md)합니다.

## <a name="vcxproj-file-elements"></a>.vcxproj 파일 요소

.Vcxproj 파일의 내용을 텍스트 또는 XML 편집기를 사용 하 여 검사할 수 있습니다. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 Visual Studio에서 볼 수 있습니다 선택 **프로젝트 언로드** 를 선택한 다음 **편집 Foo.vcxproj**합니다.

유념 해야 할 첫 번째 사항은 해당 최상위 요소가 특정 한 순서로 표시입니다. 예:

- 대부분의 속성 그룹 및 항목 정의 그룹 Microsoft.Cpp.Default.props에 대 한 가져오기 후에 발생 합니다.
- 모든 대상은 파일의 끝에 가져옵니다.
- 각각 고유한 레이블을 가진 여러 속성 그룹 하며 특정 순서로 발생 합니다.

프로젝트 파일에 있는 요소의 순서는 MSBuild 순차적 계산 모델을 기반으로 하므로 매우 중요 합니다.  모든 가져온된.props와.targets 파일을 포함 하 여 프로젝트 파일 속성의 여러 정의 구성 된 경우 마지막 정의 있는 이전 구성을 재정의 합니다. MSBUild 엔진은 평가 하는 동안 마지막에서 발생 하기 때문에 값 "xyz"는 다음 예에서 컴파일하는 동안 설정 됩니다.

```xml
  <MyProperty>abc</MyProperty>
  <MyProperty>xyz</MyProperty>
```

다음 코드 조각 최소.vcxproj 파일을 보여 줍니다. Visual Studio에서 생성 된 모든.vcxproj 파일은 이러한 최상위 MSBuild 요소를 포함 하 고 (그러나 이러한 각 최상위 요소가 여러 개 포함할 수 있습니다 있습니다)이이 순서 대로 표시 됩니다. `Label` 특성은만으로 사용 되는 Visual Studio에서 signposts 편집 하기 위해 임의 태그가 다른 함수가 없습니다.

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003'>
   <ItemGroup Label="ProjectConfigurations" />
   <PropertyGroup Label="Globals" />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
   <PropertyGroup Label="Configuration" />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
   <ImportGroup Label="ExtensionSettings" />
   <ImportGroup Label="PropertySheets" />
   <PropertyGroup Label="UserMacros" />
   <PropertyGroup />
   <ItemDefinitionGroup />
   <ItemGroup />
   <Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
   <ImportGroup Label="ExtensionTargets" />
 </Project>
```

다음 섹션에서는 이러한 요소 들의 각각의 용도 이러한 방식으로 순서 이유를 설명 합니다.

### <a name="project-element"></a>프로젝트 요소

```xml
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns='http://schemas.microsoft.com/developer/msbuild/2003' >
```

`Project`루트 노드입니다. 사용할 MSBuild 버전 및이 파일은 MSBuild.exe에 전달 될 때 실행할 기본 대상을 지정 합니다.

### <a name="projectconfigurations-itemgroup-element"></a>ProjectConfigurations ItemGroup 요소

```xml
<ItemGroup Label="ProjectConfigurations" />
```

`ProjectConfigurations`프로젝트 구성 설명을 포함합니다. 예는 Debug | Win32, 릴리스 | Win32, 디버그 | ARM 및 기타 등등입니다. 많은 프로젝트 설정이 지정된 된 구성에 따라 다릅니다. 예를 들어 디버그 빌드가 아닌 하지만 릴리스 빌드에 대 한 최적화 속성을 설정 하려는 것입니다.

`ProjectConfigurations` 항목 그룹 빌드 시 사용 되지 않습니다. Visual Studio IDE는 해당 프로젝트를 로드 하기 위해 필요 합니다. 이 항목 그룹.props 파일으로 이동 하 고.vcxproj 파일을 가져올 수 있습니다. 그러나이 경우 추가 하거나 구성을 제거 해야 할 경우 수동으로 편집 해야.props 파일입니다. IDE를 사용할 수 없습니다.

### <a name="projectconfiguration-elements"></a>프로젝트 구성 요소

다음 코드 조각에는 프로젝트 구성을 보여 줍니다. 이 예에서 ' 디버그 | x 64'은 구성 이름입니다. 프로젝트 구성 이름 형식 $(Configuration)|$(Platform).에 있어야 합니다. 프로젝트 구성 노드는 두 개의 속성이 있을 수 있습니다: 구성 및 플랫폼입니다. 이러한 속성은 구성이 활성화 된 경우 여기에서 지정 된 값으로 자동으로 설정 됩니다.

   ```xml
   <ProjectConfiguration Include="Debug|x64">
     <Configuration>Debug</Configuration>
     <Platform>x64</Platform>
   </ProjectConfiguration>
   ```

IDE는 모든 프로젝트 구성 항목에서 사용 되는 구성 및 플랫폼 값의 조합에 대 한 프로젝트 구성의 찾는 데 필요 합니다. 이 종종 프로젝트가 요구이 사항을 충족 하려면 의미 없는 프로젝트 구성에 있을 수 있음을 의미 합니다. 예를 들어, 한 프로젝트는 이러한 구성을 사용 하는 경우:

- 디버그 | Win32
- 소매 | Win32
- 특별 한 32 비트 최적화 | Win32

그런 다음 있어야이 구성에서는 "특별 한 32 비트 최적화"는 x64 의미가 없습니다.

- Debug|x64
- 소매 | x64
- 특별 한 32 비트 최적화 | x64

빌드를 사용 하지 않도록 설정 하 고 모든 구성에 대 한 명령을 배포할 수는 **솔루션 구성 관리자**합니다.

### <a name="globals-propertygroup-element"></a>Globals PropertyGroup 요소

```xml
 <PropertyGroup Label="Globals" />
```

`Globals`프로젝트 수준 설정을 ProjectGuid, RootNamespace, 스토어로 등 포함 / ApplicationTypeRevision 합니다. 마지막 두 대상 OS 정의 하는 경우가 있습니다. 프로젝트 수를 대상으로 단일 운영 체제 때문을 프로젝트 항목 및 참조 조건을 현재 가질 수 없습니다. 이러한 속성은 일반적으로 재정의 되지 다른 위치에서 프로젝트 파일에서 합니다. 이 그룹 구성에 종속 된 없고 따라서 일반적으로 하나의 전역 그룹 파일에 있는 프로젝트입니다.

### <a name="microsoftcppdefaultprops-import-element"></a>Microsoft.Cpp.default.props Import element

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
```

**Microsoft.Cpp.default.props** 속성 시트 Visual Studio와 함께 제공 되며 수정할 수 없습니다. 프로젝트에 대 한 기본 설정을 포함 합니다. 기본값은 스토어로 따라 달라질 수 있습니다.

### <a name="configuration-propertygroup-elements"></a>PropertyGroup 요소 구성

```xml
<PropertyGroup Label="Configuration" />
```

A `Configuration` 속성 그룹에는 연결 된 구성 상태 (같은 `Condition=”'$(Configuration)|$(Platform)'=='Debug|Win32'”`) 구성 별로 하나의 여러 복사본에서 돌아오는 합니다. 이 속성 그룹 특정 구성에 대해 설정 된 속성을 호스팅합니다. 구성 속성 플랫폼 도구 집합을 포함 하 고 또한 시스템 속성 시트의 포함 여부를 제어할 **Microsoft.Cpp.props**합니다. 예를 들어, 속성을 정의 하는 경우 `<CharacterSet>Unicode</CharacterSet>`, 시스템 속성 시트 다음 **microsoft 합니다. Cpp.unicodesupport.props** 포함 됩니다. 검사 하는 경우 **Microsoft.Cpp.props**, 줄이 표시 됩니다: `<Import Condition=”'$(CharacterSet)' == 'Unicode'”   Project=”$(VCTargetsPath)\microsoft.Cpp.unicodesupport.props”/>`합니다.

### <a name="microsoftcppprops-import-element"></a>Microsoft.Cpp.props Import 요소

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
```

**Microsoft.Cpp.props** 컴파일러의 최적화 및 경고 수준 속성과 같은 형식 라이브러리 이름 MIDL 도구 많은 도구 관련 속성에 대 한 기본값을 정의 수 (직접 또는 import를 통해) 속성 시트 속성 및 기타 등등입니다. 또한 바로 위에 속성 그룹에 있는 구성 속성이 정의 되어에 따라 다양 한 시스템 속성 시트를 가져옵니다.

### <a name="extensionsettings-importgroup-element"></a>ExtensionSettings ImportGroup 요소

```xml
<ImportGroup Label="ExtensionSettings" />
```

`ExtensionSettings` 그룹이 빌드 사용자 지정의 일부인 속성 시트에 대 한 가져오기를 포함 합니다. 빌드 사용자 지정 최대 3 개의 파일에 의해 정의 됩니다:.targets 파일,.props 파일 및.xml 파일입니다. 이 가져오기 그룹.props 파일에 대 한 가져오기 포함 되어 있습니다.

### <a name="propertysheets-importgroup-elements"></a>PropertySheets ImportGroup 요소

```xml
<ImportGroup Label="PropertySheets" />
```

`PropertySheets` 그룹 사용자 속성 시트에 대 한 가져오기를 포함 합니다. Visual Studio에서 속성 관리자 뷰를 통해 추가 하는 속성 시트입니다. 이러한 imports 나열 되는 순서는 중요 하며 속성 관리자에 반영 됩니다. 일반적으로 프로젝트 파일의 각 프로젝트 구성에 대 한 가져오기 그룹에서 이러한 종류의 여러 인스턴스를 포함합니다.

### <a name="usermacros-propertygroup-element"></a>UserMacros PropertyGroup 요소

```xml
<PropertyGroup Label="UserMacros" />
```

`UserMacros`속성이 포함 되어 빌드 프로세스를 사용자 지정 하는 데 사용 되는 변수를 만듭니다. 예를 들어 하 $(CustomOutputPath)로 사용자의 사용자 지정 출력 경로 정의 하 고 다른 변수를 정의 하는 데 사용할 사용자 매크로 정의할 수 있습니다. 이 속성 그룹 등의 속성을 보관합니다. Visual Studio에서이 그룹은 채워지지 프로젝트 파일에서 Visual c + + 구성에 대 한 사용자 매크로 지원 하지 않으므로 note 합니다. 사용자 매크로가 속성 시트에서 사용할 수 있습니다.

### <a name="per-configuration-propertygroup-elements"></a>구성별 PropertyGroup 요소

```xml
<PropertyGroup />
```

모든 프로젝트 구성에 대 한 구성 당 하나씩이 속성 그룹의 여러 인스턴스가 있습니다. 각 속성 그룹에 연결 된 구성 조건을 두 개 있어야 합니다. 모든 구성이 없는 경우는 **프로젝트 속성** 대화 올바르게 작동 하지 않습니다. 위의 속성 그룹과 달리 레이블이 없는이 중 하나입니다. 이 그룹에는 프로젝트 수준 구성 설정을 포함합니다. 이러한 설정은 지정 된 항목 그룹의 일부인 모든 파일에 적용 합니다. 빌드 사용자 지정 항목 정의 메타 데이터는 여기에서 초기화 합니다.

이 PropertyGroup 뒤에 야 `<Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />` 전에 레이블 없이 다른 소스 파일에 없는 여야 합니다 (그렇지 않은 경우 프로젝트 속성 편집 올바르게 작동 하지 않습니다).

### <a name="per-configuration-itemdefinitiongroup-elements"></a>구성별 ItemDefinitionGroup 요소

```xml
 <ItemDefinitionGroup />
```

항목 정의 포함 합니다. 이러한 구성 별로 레이블이 없는 PropertyGroup 요소와 동일한 조건 규칙을 따라야 합니다.

### <a name="itemgroup-elements"></a>ItemGroup 요소

```xml
<ItemGroup />
```

프로젝트에서 항목 (소스 파일 등)를 포함합니다. 프로젝트 항목 (즉, 규칙 정의에서 프로젝트 항목으로 처리 되는 항목 형식)에 대 한 조건이 지원 되지 않습니다.

메타 데이터는 모두 동일한 경우에 각 구성에 대 한 조건을 구성 해야 합니다. 예:

   ```xml
   <ItemGroup>
     <ClCompile Include="stdafx.cpp">
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
       <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|x64’">true</TreatWarningAsError>
     </ClCompile>
   </ItemGroup>
   ```

현재 Visual c + + 프로젝트 시스템에서 프로젝트 항목에 와일드 카드를 지원 하지 않습니다.

   ```xml
   <ItemGroup>
     <ClCompile Include="*.cpp"> <!--Error-->
   </ItemGroup>
   ```

현재 Visual c + + 프로젝트 시스템에서 프로젝트 항목에 매크로 지원 하지 않습니다.

   ```xml
   <ItemGroup>
     <ClCompile Include="$(IntDir)\generated.cpp"> <!--not guaranteed to work in all scenarios-->
   </ItemGroup>
   ```

참조 된 항목 그룹에 지정 된 하 고 이러한 제한 사항을 갖습니다.

- 참조 조건을 지원 하지 않습니다.
- 메타 데이터를 참조 조건을 지원 하지 않습니다.

### <a name="microsoftcpptargets-import-element"></a>Microsoft.Cpp.targets Import 요소

```xml
<Import Project="$(VCTargetsPath)\Microsoft.Cpp.targets" />
```

정의 (직접 또는 import를 통해) 빌드, 같은 Visual c + + 대상 등 정리 합니다.

### <a name="extensiontargets-importgroup-element"></a>ExtensionTargets ImportGroup 요소

```xml
<ImportGroup Label="ExtensionTargets" />
```

이 그룹에 사용자 지정 빌드 대상 파일에 대 한 가져오기 포함 되어 있습니다.

## <a name="impact-of-incorrect-ordering"></a>잘못 된 정렬의 영향

Visual Studio IDE는 프로젝트 파일 있는지 위에서 설명한 순서에 따라 달라 집니다. 예를 들어, 속성 페이지에서 속성 값을 정의 하면 IDE는 빈 레이블이 있는 속성 그룹의 속성 정의 일반적으로 배치 합니다. 이렇게 하면 기본 값은 시스템 속성 시트에서 가져온 사용자 정의 값에 의해 무시 됩니다. 마찬가지로, 대상 파일은 위에 정의 된 속성을 차지 하 고 때문에 일반적으로 정의 하지는 않습니다 속성 자체 이후 끝에 가져옵니다. 마찬가지로, 사용자 속성 시트는 시스템 속성 시트 다음 가져옵니다 (통해 포함 **Microsoft.Cpp.props**). 이렇게 하면 사용자 시스템 속성 시트도 가져온 모든 기본값을 재정의할 수 있습니다.

.Vcxproj 파일에서이 레이아웃을 따르지 않습니다 빌드 결과 예상과 되지 않을 수 있습니다. 예를 들어 사용자가 정의 하는 속성 시트 다음 시스템 속성 시트를 실수로 가져올 시스템 속성 시트에서 사용자 설정은 재정의 됩니다.

도 IDE 디자인 타임 환경을 요소의 올바른 순서에 어느 정도에 따라 달라 집니다. 예를 들어,.vcxproj 파일에 없는 경우는 `PropertySheets` 가져오기 그룹에서 IDE에서 사용자가 만든 하는 새 속성 시트를 배치할 위치를 확인 하려면 못할 **속성 관리자**합니다. 이 인해 시스템 시트에서 재정의 되는 사용자 시트 될 수 있습니다. IDE에 의해 사용 되는 추론.vcxproj 파일 레이아웃에 일부 문제가 발생 해도, 하지만이 문서의 앞부분에 표시 되는 구조에서 벗어날 하지는 것이 좋습니다.

## <a name="how-the-ide-uses-element-labels"></a>IDE 요소 레이블을 사용 하는 방법

IDE 설정 하는 경우에 **UseOfAtl** 프로젝트 파일에서 구성 속성 그룹에 기록 되기의 일반 속성 페이지에서 속성을 동안는 **TargetName** 같은 속성 페이지에서 속성 레이블이 없는 구성 속성 그룹에 기록 됩니다. Visual Studio 속성 페이지의 xml 파일에 대 한 각 속성은 쓸 수 있는 위치에 대 한 정보를 살펴봅니다. 에 대 한는 **일반** 속성 페이지 (Visual Studio Enterprise Edition의 영어 버전 가정),이 파일은 `%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\general.xml`합니다. 속성 페이지 XML 규칙 파일에 대 한 규칙 및 모든 해당 속성에 대 한 정적 정보를 정의합니다. 정보의 이러한 한 요소는 대상 파일 (해당 값은 기록할 파일)의 규칙 속성의 기본 위치입니다. 기본 위치는 Label 특성 프로젝트 파일 요소에 의해 지정 됩니다.

## <a name="property-sheet-layout"></a>속성 시트 레이아웃

다음 XML 조각은 속성 시트 (.props) 파일의 최소 레이아웃입니다. .Vcxproj 파일 유사 하며.props 요소의 기능을 이전 토론에서 유추할 수 있습니다.

```xml
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ImportGroup Label="PropertySheets" />
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup />
  <ItemDefinitionGroup />
  <ItemGroup />
</Project>
```

사용자 고유의 속성 시트, VCTargets 폴더에 따라.props 파일 중 하나를 복사 한 용도 맞게 수정 합니다. Visual Studio 2017 Enterprise edition에 대 한 기본 VCTargets 경로가 `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets`합니다.

## <a name="see-also"></a>참고 항목

[프로젝트 속성 사용](working-with-project-properties.md)  
[속성 페이지 XML 파일](property-page-xml-files.md)  
