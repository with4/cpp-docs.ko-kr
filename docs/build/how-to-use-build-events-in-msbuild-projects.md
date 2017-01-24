---
title: "방법: MSBuild 프로젝트에서 빌드 이벤트 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.usebuildevents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild(c++), 방법: 프로젝트에서 빌드 이벤트 사용"
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: MSBuild 프로젝트에서 빌드 이벤트 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

빌드 이벤트는 빌드 프로세스의 특정 단계에서 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)]가 수행하는 명령입니다.  *빌드 전*; 빌드가 시작 되기 전에 발생 합니다. *링크 전*; 링크 단계 시작 되기 전에 발생하고 *빌드 후* 이벤트는 빌드가 성공적으로 끝난 후 발생 합니다.  빌드 이벤트는 연관 된 빌드 단계가 발생 하는 경우에 발생 합니다.  예를 들어, 링크 단계가 실행되지 않으면 링크 전 이벤트는 발생하지 않습니다.  
  
 세 가지 빌드 이벤트는 실행되는 명령 요소\(`<Command>`\) 및 **MSBuild**가 빌드 이벤트를 수행할 때 표시되는 메시지 요소\(`<Message>`\)로 항목 정의 그룹에서 각각 표현됩니다.  각 요소는 선택적이며, 동일한 요소를 여러 번 지정할 경우 마지막으로 지정된 요소가 우선합니다.  
  
 선택적인 *빌드에 사용* 요소\(`<`*build\-event***UseInBuild**`>`\)는 빌드 이벤트 실행 여부를 나타내기 위해 속성 그룹에 지정될 수 있습니다.  *빌드에 사용* 요소의 내용은 `true` 또는 `false` 값을 가집니다.  기본적으로 빌드 이벤트는 상응하는 *빌드에 사용* 요소가 `false`로 설정되어 있지 않으면 실행됩니다.  
  
 다음 표에는 각 빌드 이벤트 XML 요소가 나열되어 있습니다.  
  
|XML 요소|설명|  
|------------|--------|  
|`PreBuildEvent`|이 이벤트는 빌드 시작 전에 실행됩니다.|  
|`PreLinkEvent`|이 이벤트는 링크 단계 시작 전에 실행됩니다.|  
|`PostBuildEvent`|이 이벤트는 빌드 완료 후에 실행됩니다.|  
  
 다음 표에는 각 *빌드에 사용* 요소가 나열되어 있습니다.  
  
|XML 요소|설명|  
|------------|--------|  
|`PreBuildEventUseInBuild`|*빌드 전* 이벤트를 실행할지 여부를 지정합니다.|  
|`PreLinkEventUseInBuild`|*링크 전* 이벤트를 실행할지 여부를 지정합니다.|  
|`PostBuildEventUseInBuild`|*빌드 후* 이벤트를 실행할지 여부를 지정합니다.|  
  
## 예제  
 다음 예제는 [연습: MSBuild를 사용하여 Visual C\+\+ 프로젝트 만들기](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)에서 만든 myproject.vcxproj 파일의 Project 요소 내부에 추가할 수 있습니다.  *빌드 전* 이벤트는 main.cpp의 복사본을 만들고, *링크 전* 이벤트는 main.obj의 복사본을 만들고, *빌드 후* 이벤트는 myproject.exe의 복사본을 만듭니다.  릴리스 구성을 사용하여 프로젝트가 빌드되는 경우 해당 빌드 이벤트가 실행됩니다.  디버그 구성을 사용하여 프로젝트가 빌드되는 경우에는 해당 빌드 이벤트가 실행되지 않습니다.  
  
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
  
## 참고 항목  
 [MSBuild\(Visual C\+\+\)](../build/msbuild-visual-cpp.md)   
 [연습: MSBuild를 사용하여 Visual C\+\+ 프로젝트 만들기](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)