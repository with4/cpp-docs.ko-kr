---
title: '방법: MSBuild 프로젝트에서 빌드 이벤트 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.usebuildevents
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: use build events in projects'
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2367c85dbd4a4ef7b10d927592c0fb10a417f0e6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369775"
---
# <a name="how-to-use-build-events-in-msbuild-projects"></a>방법: MSBuild 프로젝트에서 빌드 이벤트 사용
빌드 이벤트는 명령 하는 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] 빌드 프로세스의 특정 단계에서 수행 합니다. *빌드 전* 이벤트 빌드가 시작 되기 전에 발생; *링크 전* 는 링크 단계가 시작 되기 전에 이벤트 발생 및 *빌드 후* 빌드 후 이벤트 발생 성공적으로 종료 됩니다. 빌드 이벤트는 연관된 빌드 단계가 수행될 때만 발생합니다. 예를 들어 링크 단계가 실행 되지 않는 경우에 링크 전 이벤트 발생 하지 않습니다.  
  
 각 3 개 빌드 이벤트 명령 요소에 의해 항목 정의 그룹에 표시 됩니다 (`<Command>`) 실행 되는 메시지 요소 (`<Message>`) 즉 선택할 때 표시 된 **MSBuild** 빌드 이벤트를 수행 합니다. 각 요소는 선택적 이며 같은 요소를 여러 번 지정 하면 마지막으로 나타나는 우선적으로 적용 합니다.  
  
 선택적 *빌드에 사용 하 여* 요소 (`<`* 빌드-이벤트 ***UseInBuild**`>`) 빌드 이벤트 실행 되는지 여부를 나타내는 속성 그룹에 지정할 수 있습니다. 콘텐츠의 값은 *빌드에 사용 하 여* 요소 중 하나는 `true` 또는 `false`합니다. 빌드 이벤트 하지 않는 한 기본적으로 실행 하면 해당 *빌드에 사용 하 여* 로 설정 된 `false`합니다.  
  
 다음 표에서 각 빌드 이벤트 XML 요소를 보여 줍니다.  
  
|XML 요소|설명|  
|-----------------|-----------------|  
|`PreBuildEvent`|이 이벤트는 빌드가 시작 되기 전에 실행 됩니다.|  
|`PreLinkEvent`|이 이벤트는 링크 단계가 시작 되기 전에 실행 됩니다.|  
|`PostBuildEvent`|이 이벤트는 빌드가 완료 된 후 실행 됩니다.|  
  
 다음 표에서 각 *빌드에 사용 하 여* 요소:  
  
|XML 요소|설명|  
|-----------------|-----------------|  
|`PreBuildEventUseInBuild`|실행할지 여부를 지정 된 *빌드 전* 이벤트입니다.|  
|`PreLinkEventUseInBuild`|실행할지 여부를 지정 된 *링크 전* 이벤트입니다.|  
|`PostBuildEventUseInBuild`|실행할지 여부를 지정 된 *빌드 후* 이벤트입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서 만든 myproject.vcxproj 파일의 프로젝트 요소 안에 추가 될 수 있습니다 [연습: Visual c + + 프로젝트를 만들려면 MSBuild를 사용 하 여](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)합니다. A *빌드 전* 이벤트는 main.cpp의 복사본 있으며 *링크 전* main.obj;의 복사본 및 이벤트는 *빌드 후* 이벤트 myproject.exe의 복사본을 만듭니다. 릴리스 구성을 사용 하 여 프로젝트를 빌드할 빌드 이벤트가 실행 됩니다. 디버그 구성을 사용 하 여 프로젝트를 빌드할 빌드 이벤트는 실행 되지 않습니다.  
  
```  
<ItemDefinitionGroup>  
  <PreBuildEvent>  
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>  
    <Message>Making a copy of main.cpp </Message>  
  </PreBuildEvent>  
  <PreLinkEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>  
    <Message>Making a copy of main.obj</Message>  
  </PreLinkEvent>  
  <PostBuildEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>  
    <Message>Making a copy of myproject.exe</Message>  
  </PostBuildEvent>  
</ItemDefinitionGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>  
</PropertyGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>  
</PropertyGroup>  
```  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild (Visual c + +)](../build/msbuild-visual-cpp.md)   
 [연습: MSBuild를 사용하여 Visual C++ 프로젝트 만들기](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)