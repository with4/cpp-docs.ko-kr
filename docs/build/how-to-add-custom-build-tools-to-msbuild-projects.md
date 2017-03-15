---
title: "방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.addcustombuildtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild(c++), 방법: 사용자 지정 빌드 도구 추가"
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자 지정 빌드 도구는 사용자가 정의한 명령줄 도구이며 특정 파일과 연결되어 있습니다.  
  
 실행할 명령줄, 추가 입력 또는 출력 파일 및 표시할 메시지는 특정 파일에 대해 프로젝트 파일\(.vcxproj\)에서 지정합니다.  **MSBuild**에서 출력 파일이 해당 입력 파일보다 이전 버전임을 확인하면 지정한 메시지가 표시되고 명령줄 도구가 실행됩니다.  
  
 사용자 지정 빌드 도구가 실행되는 시점을 지정하려면 프로젝트 파일에 있는 `CustomBuildBeforeTargets` 및 `CustomBuildAfterTargets` XML 요소 중 하나 또는 모두를 사용합니다.  예를 들어, 사용자 지정 빌드 도구가 MIDL 컴파일러 이후 및 C\/C\+\+ 컴파일러 이전에 실행되도록 지정할 수 있습니다.  특정 대상이 실행되기 전에 도구를 실행하려면 `CustomBuildBeforeTargets` 요소를 지정하고, 특정 대상이 실행된 후에 도구를 실행하려면 `CustomBuildAfterTargets` 요소를 지정하고, 두 대상의 실행 사이에서 도구를 실행하려면 두 요소를 모두 지정합니다.  두 요소 모두 지정하지 않으면 사용자 지정 빌드 도구가 기본 위치, 즉 **MIDL** 대상 이전에 실행됩니다.  
  
 사용자 지정 빌드 단계 및 사용자 지정 빌드 도구는 `CustomBuildBeforeTargets` 및 `CustomBuildAfterTargets` XML 요소에 지정된 정보를 공유합니다.  이러한 대상은 프로젝트 파일에서 한 번만 지정합니다.  
  
### 사용자 지정 빌드 도구를 추가하려면  
  
1.  항목 그룹을 프로젝트 파일에 추가하고 각 입력 파일의 항목을 추가합니다.  명령, 추가 입력 및 출력, 메시지를 다음과 같이 항목 메타데이터로 지정합니다.  이 예제에서는 "faq.txt" 파일이 해당 프로젝트와 동일한 디렉터리에 있는 것으로 가정합니다.  
  
    ```  
    <ItemGroup>  
      <CustomBuild Include="faq.txt">  
        <Message>Copying readme...</Message>  
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>  
        <Outputs>$(OutDir)%(Identity)</Outputs>  
      </CustomBuild>  
    </ItemGroup>  
    ```  
  
### 빌드에서 사용자 지정 빌드 도구가 실행될 위치를 정의하려면  
  
1.  프로젝트 파일에 다음 속성 그룹을 추가합니다.  대상 중 하나 이상을 지정해야 하지만 빌드 단계가 특정 대상 이전 또는 이후에 실행되도록 하는 데만 관심이 있으면 나머지 대상은 생략할 수 있습니다.  이 예제에서는 컴파일이 끝나고 링크가 시작되기 전에 사용자 지정 단계를 수행합니다.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## 참고 항목  
 [연습: MSBuild를 사용하여 Visual C\+\+ 프로젝트 만들기](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [방법: MSBuild 프로젝트에서 빌드 이벤트 사용](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)