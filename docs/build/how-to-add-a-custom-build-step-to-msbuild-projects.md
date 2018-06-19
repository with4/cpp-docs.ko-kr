---
title: '방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.addcustombuildstep
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa8d433b782d8436f6211ab9efe55fcaad3492ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367994"
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>방법: MSBuild 프로젝트에 사용자 지정 빌드 단계 추가
사용자 지정 빌드 단계에는 빌드에 사용자 지정 단계가입니다. 다른 모든 메서드처럼 동작 사용자 지정 빌드 단계 *명령 도구* 표준 컴파일 또는 링크 도구 단계 등의 단계입니다.  
  
 프로젝트 파일 (.vcxproj)에서 사용자 지정 빌드 단계를 지정 합니다. 단계는 추가 입력 또는 출력 파일 및 표시할 메시지를 실행 하는 명령줄을 지정할 수 있습니다. 경우 **MSBuild** 임을 확인 출력 파일이 입력된 파일을 고려 하 여 만료 된 메시지를 표시 하 고 명령을 실행 합니다.  
  
 빌드 대상 시퀀스의 사용자 지정 빌드 위치 단계를 지정 하려면 하나 또는 둘 다의 사용은 `CustomBuildAfterTargets` 및 `CustomBuildBeforeTargets` 프로젝트 파일의 XML 요소입니다. 예를 들어 사용자 지정 빌드 단계 후 링크 도구 대상 및 매니페스트 도구, 대상 보다 먼저 실행 되도록 지정할 수 있습니다. 실제 사용 가능한 대상 집합이 특정 빌드에 따라 달라 집니다.  
  
 지정 된 `CustomBuildBeforeTargets` 특정 대상이 실행 하기 전에 사용자 지정 빌드 단계를 실행 하는 요소는 `CustomBuildAfterTargets` 특정 대상이 실행 된 후의 단계를 실행 하는 요소 또는 인접 한 두 대상 간에 단계를 실행 하려면 두 요소입니다. 사용자 지정 빌드 도구 실행 후의 기본 위치에 두 요소를 지정 하는 경우는 **링크** 대상입니다.  
  
 사용자 지정 빌드 단계와 사용자 지정 빌드 도구에 지정 된 정보를 공유는 `CustomBuildBeforeTargets` 및 `CustomBuildAfterTargets` XML 요소입니다. 따라서 프로젝트 파일의 대상만 한 번만 지정 합니다.  
  
### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>사용자 지정 빌드 단계에서 실행 되는 작업을 정의 하려면  
  
1.  프로젝트 파일에 속성 그룹을 추가 합니다. 이 속성 그룹의 다음 예제와 같이 명령, 입력 및 출력 및 메시지를 지정 합니다. 이 예제에서 만든 main.cpp 파일에서.cab 파일을 만듭니다. [연습: Visual c + + 프로젝트를 만들려면 MSBuild를 사용 하 여](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)합니다.  
  
    ```  
    <ItemDefinitionGroup>  
      <CustomBuildStep>  
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>  
        <Outputs>$(TargetName).cab</Outputs>  
        <Inputs>$(TargetFileName)</Inputs>  
      </CustomBuildStep>  
    </ItemDefinitionGroup>  
    ```  
  
### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>빌드에 사용자 지정 빌드 단계가 실행할 위치를 정의 하려면  
  
1.  프로젝트 파일에 다음 속성 그룹을 추가 합니다. 대상을 모두 지정 하거나 사용자 지정 단계 이전 또는 특정 대상 이후에 실행 하 려 할 경우 하나를 생략할 수 있습니다. 이 예에서는 지시 **MSBuild** 컴파일 단계 끝나고 링크 단계가 시작 되기 전에 사용자 지정 단계를 수행 하려면.  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [연습: MSBuild를 사용 하 여 Visual c + + 프로젝트 만들기](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [방법: MSBuild 프로젝트에서 빌드 이벤트 사용](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [방법: MSBuild 프로젝트에 사용자 지정 빌드 도구 추가](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)