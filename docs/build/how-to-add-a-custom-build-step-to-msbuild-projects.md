---
title: "방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.addcustombuildstep"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild(c++), 방법: 사용자 지정 빌드 단계 추가"
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 지정 빌드 단계는 사용자가 정의한 빌드의 단계입니다.  사용자 지정 빌드 단계는 표준 컴파일 또는 링크 도구 단계 등의 다른 *명령 도구* 단계와 동일하게 동작합니다.  
  
 프로젝트 파일\(.vcxproj\)에서 사용자 지정 빌드 단계를 지정합니다.  이 단계는 실행할 명령줄, 추가 입력 또는 출력 파일 및 표시할 메시지를 지정할 수 있습니다.  **MSBuild**에서 출력 파일이 해당 입력 파일보다 이전 버전임을 확인하면 사용자 지정 빌드 단계에서 지정한 메시지가 표시되고 명령이 실행됩니다.  
  
 빌드 대상 시퀀스에서 사용자 지정 빌드 단계의 위치를 지정하려면 프로젝트 파일에 있는 `CustomBuildAfterTargets` 및 `CustomBuildBeforeTargets` XML 요소 중 하나 또는 모두를 사용합니다.  예를 들어, 사용자 지정 빌드 단계가 링크 도구 대상 이후 및 매니페스트 도구 대상 이전에 실행되도록 지정할 수 있습니다.  실제로 사용 가능한 대상 집합은 해당 빌드에 따라 달라집니다.  
  
 특정 대상이 실행되기 전에 사용자 지정 빌드 단계를 실행하려면 `CustomBuildBeforeTargets` 요소를 지정하고, 특정 대상이 실행된 후에 이 단계를 실행하려면 `CustomBuildAfterTargets` 요소를 지정하고, 인접한 두 대상 사이에서 이 단계를 실행하려면 두 요소를 모두 지정합니다.  두 요소 모두 지정하지 않으면 사용자 지정 빌드 도구가 기본 위치, 즉 **Link** 대상 이후에 실행됩니다.  
  
 사용자 지정 빌드 단계 및 사용자 지정 빌드 도구는 `CustomBuildBeforeTargets` 및 `CustomBuildAfterTargets` XML 요소에 지정된 정보를 공유합니다.  따라서 이러한 대상은 프로젝트 파일에서 한 번만 지정합니다.  
  
### 사용자 지정 빌드 단계에서 실행될 작업을 정의하려면  
  
1.  프로젝트 파일에 속성 그룹을 추가합니다.  이 속성 그룹에서 다음 예제와 같이 명령, 명령의 입력과 출력 및 메시지를 지정합니다.  이 예제에서는 [연습: MSBuild를 사용하여 Visual C\+\+ 프로젝트 만들기](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)에서 만든 main.cpp 파일로부터 .cab 파일을 만듭니다.  
  
    ```  
    <ItemDefinitionGroup>  
      <CustomBuildStep>  
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>  
        <Outputs>$(TargetName).cab</Outputs>  
        <Inputs>$(TargetFileName)</Inputs>  
      </CustomBuildStep>  
    </ItemDefinitionGroup>  
    ```  
  
### 빌드에서 사용자 지정 빌드 단계가 실행될 위치를 정의하려면  
  
1.  프로젝트 파일에 다음 속성 그룹을 추가합니다.  대상을 모두 정의할 수도 있지만 사용자 지정 단계가 특정 대상 이전 또는 이후에 실행되도록 하려면 하나를 생략하면 됩니다.  이 예제에서는 컴파일 단계가 끝나고 링크 단계가 시작되기 전에 사용자 지정 단계를 수행하도록 **MSBuild**에 지시합니다.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## 참고 항목  
 [연습: MSBuild를 사용하여 Visual C\+\+ 프로젝트 만들기](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [방법: MSBuild 프로젝트에서 빌드 이벤트 사용](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)