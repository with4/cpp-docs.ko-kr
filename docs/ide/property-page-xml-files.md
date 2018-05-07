---
title: 속성 페이지 XML 규칙 파일 | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property page XML files
ms.assetid: dd9d9734-4387-4098-8ba6-85b93507731d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fcee2c416fba6a959785826781aefd96b0d06d75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="property-page-xml-rule-files"></a>속성 페이지 XML 규칙 파일
IDE에서 프로젝트 속성 페이지 VCTargets 폴더에 XML 파일에 의해 구성 됩니다. 정확한 경로 edition(s)의 Visual Studio 설치 되 고 제품 언어에 따라 달라 집니다. 영어, Visual Studio 2017 Enterprise Edition에 대 한 경로 `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`합니다. XML 파일에는 규칙는 범주 및 개별 속성, 데이터 형식, 기본 값의 이름 및 표시 되는 방법을 설명 합니다. IDE에서 속성을 설정 하는 경우 새 값은 프로젝트 파일에 저장 됩니다.

이러한 파일 및 Visual Studio IDE의 내부 작업은 (는)를 이해 해야 하는 유일한 시나리오는 사용자 지정 속성 페이지를 만들려고 할 또는 (b) 사용자 지정 하려면 프로젝트 속성을 통해 Visual Studio IDE 이외의 다른 방법으로 합니다. 

첫째, 이제는 프로젝트에 대 한 속성 페이지를 열고 (에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭 **솔루션 탐색기** 속성을 선택):
   
![Visual c + + 프로젝트 속성](media/cpp-property-page-2017.png)

각 노드 아래의 **구성 속성** 규칙 라고 합니다. 용어 된를 실행 하 고 일부 출력을 생성 수 있는 속성이 있는 것을 참조 하는 일반적 이지만 규칙 때때로 컴파일러와 같은 단일 도구를 나타냅니다. 각 규칙은 VCTargets 폴더에 xml 파일에서 채워집니다. 예를 들어 위에 표시 되는 C/c + + 규칙 'cl.xml' 채워집니다.

위에 나와 있는 것 처럼 각 규칙에 범주로 구성 되어 있는 속성 집합이 있습니다. 각 하위 노드에 규칙에서 범주를 나타냅니다. 예를 들어 최적화 노드 C/c + + 컴파일러 도구의 모든 최적화와 관련 된 속성을 포함 합니다. 속성 및 해당 값 자체 오른쪽 창에 표 형식으로 렌더링 됩니다.

메모장 이나 XML 편집기 (아래 스냅숏을 참조)에서 cl.xml를 열 수 있습니다. 추가 메타 데이터와 함께 UI에 표시 되 고 아래에 정의 된 속성 목록이 포함 규칙을 루트 노드가 표시 됩니다.

```xml  
<?xml version="1.0" encoding="utf-8"?>
<!--Copyright, Microsoft Corporation, All rights reserved.-->
<Rule Name="CL" PageTemplate="tool" DisplayName="C/C++" SwitchPrefix="/" Order="10" xmlns="http://schemas.microsoft.com/build/2009/properties" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.Categories>
    <Category Name="General" DisplayName="General" />
    <Category Name="Optimization" DisplayName="Optimization" />
    <Category Name="Preprocessor" DisplayName="Preprocessor" />
    <Category Name="Code Generation" DisplayName="Code Generation" />
    <Category Name="Language" DisplayName="Language" />
    <Category Name="Precompiled Headers" DisplayName="Precompiled Headers" />
    <Category Name="Output Files" DisplayName="Output Files" />
    <Category Name="Browse Information" DisplayName="Browse Information" />
    <Category Name="Advanced" DisplayName="Advanced" />
    <Category Name="All Options" DisplayName="All Options" Subtype="Search" />
    <Category Name="Command Line" DisplayName="Command Line" Subtype="CommandLine" />
  </Rule.Categories>
...
``` 

속성 페이지 UI에서에서 구성 속성에서 모든 노드에 해당 하는 XML 파일 한 개 있습니다. 추가 하거나 포함 하거나 프로젝트에서 해당 XML 파일에 위치를 제거 하 여 UI에 규칙을 제거할 수 있습니다. 예를 들어 다음은 Microsoft.CppBuild.targets (수준을 한 단계 높이기 1033 폴더에서) cl.xml를 포함 하는 방법입니다.

```xml  
<PropertyPageSchema Condition="'$(ConfigurationType)' != 'Utility'" Include="$(VCTargetsPath)$(LangID)\cl.xml"/>

``` 
Cl.xml의 모든 데이터를 제거 하는 경우 다음 구조와 /fd 됩니다.
```xml  
<?xml version="1.0" encoding="utf-8"?>
<Rule>
  <Rule.DataSource />
  <Rule.Categories>
    <Category />
        ...
  </Rule.Categories>
  <BoolProperty />
  <EnumProperty />
  <IntProperty />
  <StringProperty />
  <StringListProperty />
</Rule>
``` 

다음 섹션에는 각 주요 요소 및에 첨부할 수 있는 메타 데이터 일부를 설명 합니다.

1. **규칙:** 규칙 xml 파일의 루트 노드는 일반적으로; 많은 특성을 가질 수 있습니다.

```xml    
<Rule Name="CL" PageTemplate="tool" SwitchPrefix="/" Order="10"
          xmlns="http://schemas.microsoft.com/build/2009/properties"
          xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
          xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Rule.DisplayName>
    <sys:String>C/C++</sys:String>
  </Rule.DisplayName>
```  

   a. **이름:** Name 특성은 규칙에 대 한 id입니다. 프로젝트에 대 한 모든 속성 페이지의 xml 파일에서 고유 해야 합니다.

   b. **PageTemplate:** 이 특성의 값 UI 템플릿 컬렉션에서 선택 하는 UI에서 사용 됩니다. 표준 표 형식에서 속성 "도구" 서식 파일을 렌더링합니다. 이 특성에 대 한 다른 기본 제공 값은 "디버거" 및 "일반"입니다. UI 형식에서 이러한 값을 지정 하는 결과 확인 하려면 디버깅 노드 및 일반 노드를 각각 참조. "디버거" 페이지 서식 파일에 대 한 UI 드롭다운 상자를 사용 하 여 규칙에서 여러 범주 하위 노드는 대신 한 페이지 모두에서 서로 다른 속성 범주를 표시 하는 "일반" 템플릿은 다른 디버거 속성 사이 전환 하려면 노드입니다. 이 특성은 UI;에 대 한 제안만 xml 파일은 독립적인 UI 하도록 설계 되었습니다. 다른 UI는이 특성을 사용 하 여 다양 한 용도로 수 있습니다.

  c. **SwitchPrefix:** 스위치에 대 한 명령줄에 사용 되는 접두사입니다. 값이 "/" /ZI, /nologo, /W3 등과 같은 스위치를 초래 합니다.

  d. **순서:** 예상 UI 클라이언트 시스템의 다른 모든 규칙에 비해이 규칙의 상대적 위치에 대 한 제안 사항을입니다.

  e. **xmlns:** 표준 XAML 요소입니다. 나열 된 3 개의 네임 스페이스를 볼 수 있습니다. 이 값은 XAML deserialization에 대 한 네임 스페이스 클래스, XAML 스키마 및 시스템 네임 스페이스에서 각각.

  f. **표시 이름:** 규칙 노드에 대 한 속성 페이지 UI에 표시 되는 이름입니다. 이 값도 지역화 됩니다. 만들었는지 여부 DisplayName 규칙의 자식 요소로 아닌 (예: 이름 또는 SwitchPrefix) 특성으로 인해 내부 지역화 도구 요구 사항입니다. XAML의 관점에서 모두 동일합니다. 따라서 방금 해야 특성을 간단 하 게 표시 하거나 그대로 둡니다.

  g. **데이터 원본:** 에서 읽기 및 쓰기, 속성 값은 있는 위치와 아래에서 설명 하는 그룹화 프로젝트 시스템에 알려 주는 매우 중요 한 속성입니다. Cl.xml, 이러한 값은:

```xml  
       <DataSource Persistence="ProjectFile" ItemType="ClCompile" Label="" HasConfigurationCondition="true" />
```  
   - `Persistence="ProjectFile` 프로젝트 시스템입니다. 프로젝트 파일을 써야 하는 규칙에 대 한 모든 속성 또는 속성 시트 파일 (따라 노드를 사용한 생성 속성 페이지)를 알려 줍니다. 다른 가능한 값은 "UserFile"는 값을.user 파일에 기록 됩니다.

   - `ItemType="ClCompile"` 표시 속성 ItemDefinition 메타 데이터 또는 항목 메타 데이터 (후자의 속성 페이지에서 솔루션 탐색기에서 파일 노드 생성 된 경우에)으로 저장 됩니다는이 항목 형식입니다. 이 필드가 설정 되지 않은 속성을 소스 파일에서 공통 속성으로 기록 됩니다.

   - `Label=""` 속성은로 작성 하는 경우 나타냅니다 `ItemDefinition` 메타 데이터를 부모 ItemDefinitionGroup의 레이블을 비어 있게 됩니다 (모든 MSBuild 요소 레이블을 포함할 수 있습니다). Visual Studio 2017.vcxproj 프로젝트 파일 탐색을 레이블이 지정 된 그룹을 사용 합니다. 대부분의 규칙 속성을 포함 하는 그룹을 레이블로 빈 문자열이 있는지 참고 합니다.

   - `HasConfigurationCondition="true"` (조건 부모 그룹이 나 값 자체에 부착 수) 현재 프로젝트 구성에 대해서만 적용 되도록 구성 조건이 된 값을 붙일 하도록 프로젝트 시스템에 지시 합니다. 예를 들어, 프로젝트 노드 속성 페이지를 열고 속성의 값을 설정 **경고를 오류로 처리** 아래 **구성 속성 > C/c + + 일반** "예"로 합니다. 다음 값은 프로젝트 파일에 기록 됩니다. ItemDefinitionGroup 부모에 연결 된 구성 상태를 확인 합니다.

```xml  
     <ItemDefinitionGroup Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">
        <ClCompile>
           <TreatWarningAsError>true</TreatWarningAsError>
        </ClCompile>
     </ItemDefinitionGroup>
 ```
   Stdafx.cpp, 등의 특정 파일에 대 한 속성 페이지에서이 값이 설정 된 경우 속성 값은 아래와 같이 프로젝트 파일에 stdafx.cpp 항목 아래 작성할 수 있습니다. 메타 데이터 자체에 직접 연결 하는 구성 조건이 방법을 확인 합니다.

 ```xml  
<ItemGroup>
   <ClCompile Include="stdafx.cpp">
      <TreatWarningAsError Condition="‘$(Configuration)|$(Platform)’==’Debug|Win32’">true</TreatWarningAsError>
   </ClCompile>
</ItemGroup>
 ```
   다른 특성 **DataSource** 는 위에 나열 되지 않은 **PersistedName**합니다. 다른 이름을 사용 하 여 프로젝트 파일에서 속성을 나타내는이 특성을 사용할 수 있습니다. 기본적으로이 특성은 속성의로 설정 **이름**합니다. 

   개별 속성 부모 규칙의 데이터 소스를 재정의할 수 있습니다. 이 경우 해당 속성의 값에 대 한 위치는 규칙의 다른 속성에서 달라 집니다.

   h. 여기에 표시 되지 않는 규칙 설명, SupportsFileBatching 등의 다른 특성 있습니다. 이러한 형식에 대 한 설명서를 검색 하 여 규칙 또는 다른 요소에 적용 가능한 특성의 전체 집합을 얻을 수 있습니다. 에 있는 형식에 공용 속성을 확인할 수 또는 `Microsoft.Build.Framework.XamlTypes` 네임 스페이스에는 `Microsoft.Build.Framework .dll` 어셈블리입니다.

   i. **DisplayName**, **PageTemplate**, 및 **순서** 이 있는 UI 관련 속성을 사용할 수 없는 UI에 관계 없이 데이터 모델입니다. 이러한 속성은 거의 확실 속성 페이지를 표시 하는 데 사용 되는 모든 UI에서 사용할 수 있습니다. **DisplayName** 및 **설명** xml 파일의 거의 모든 요소에 있는 두 개의 속성이 있습니다. 다음은 지역화 된 두 개의 속성 및 (이러한 문자열의 지역화 이후 게시물에 설명 되어 있습니다).

2.  **범주:** 규칙 범주를 여러 개 있을 수 있습니다. Xml 파일에는 범주가 나열 되어 순서가 동일한 순서는 범주를 표시 하려면 UI 제안 합니다. 예를 들어, UI에 표시 된 대로 C/c + + 노드 아래 항목의 순서 – 일반, 최적화, 전처리기,...  – 해당에 cl.xml와 같습니다. 샘플 범주는 다음과 같습니다.

```xml  
 <Category Name="Optimization">
    <Category.DisplayName>
        <sys:String>Optimization</sys:String>
    </Category.DisplayName>
 </Category>
```
위의 조각과 **이름** 및 **DisplayName** 하기 전에 설명 된 특성을 합니다. 다시 한 번은 다른 특성을 **범주** 를 가질 수 있습니다 위에서 사용 되지 않습니다. Ildasm.exe를 사용 하 여 어셈블리를 검사 하 여 또는 설명서에 대 한 알 수 있습니다.

3. **속성:** xml 파일의 핵심 이므로이 규칙에 대 한 모든 속성의 목록을 포함 합니다. 각 속성에는 위의 XAML 구조에 표시 된 5 개의 가능한 형식 중 하나일 수 있습니다. 물론, 이러한 형식 중 일부만 파일에 있을 수 있습니다. 속성에 다양 하 게 설명할 수 있는 특성의 수 있습니다. 만 설명 하겠지만 **StringProperty** 여기 합니다. 나머지는 매우 비슷합니다.

```xml  
<StringProperty Subtype="file" Name="ObjectFileName" Category="Output Files" Switch="Fo">
  <StringProperty.DisplayName>
    <sys:String>Object File Name</sys:String>
  </StringProperty.DisplayName>
  <StringProperty.Description>
    <sys:String>Specifies a name to override the default object file name; can be file or directory name.(/Fo[name])</sys:String>
  </StringProperty.Description>
</StringProperty>
```
대부분의 코드 조각에 특성 하기 전에 설명 했습니다. 새 하위 형식, 범주 및 스위치는입니다.

   a. **하위 형식** 는 특성에 대해서만 사용할 수 있는 **StringProperty** 및 **StringListProperty**; 컨텍스트 정보를 제공 합니다. 예를 들어 "file"의 값 속성 파일 경로 나타낸다는 것을 의미 합니다. 이러한 컨텍스트 정보를 사용자 파일을 시각적으로 선택할 수 있도록 하는 속성의 편집기로 Windows 탐색기를 제공 하 여 편집 환경을 향상 시키기 위해 사용 됩니다.

   b. **범주:** 이는이 속성이 속하는 범주를 선언 합니다. 이 속성에서 찾으려고 시도 **출력 파일** UI에는 범주입니다.

   c. **스위치:** 때 규칙을 나타내는 도구 – 컴파일러 도구 등이 경우-규칙의 대부분의 속성은 스위치로 도구 실행 파일에 전달 빌드 시간 동안 합니다. 이 특성의 값에 사용할 리터럴 스위치를 나타냅니다. 위의 속성 해당 스위치 이어야 함을 지정 **Fo**합니다. 와 결합 된 **SwitchPrefix** 부모 규칙,이 속성에 대 한 특성으로 실행 파일에 전달 되 **/Fo "디버그\"**  (C/c + +에 대 한 속성 페이지 UI에에서 명령줄에 표시 됨).

   기타 속성 특성은 다음과 같습니다.

   d. **Visible:** 몇 가지 이유로 않으려면 속성을 위해서는 여전히 사용할 수 있는 빌드 시간 동안) (않음 속성 페이지에 표시,이 특성을 false로 설정 합니다.

   e. **읽기 전용:** 속성 페이지에서이 속성의이 값의 읽기 전용 보기를 제공 하려는 경우이 특성을 true로 설정 합니다.

   f. **IncludeInCommandLine:** 일부 속성 빌드 시간 동안 도구에 전달 될 필요가 없습니다. 이 특성을 false로 설정 되 고 전달 되지 것입니다.


