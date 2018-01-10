---
title: "사용자 지정 빌드 단계 속성 페이지: 일반 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs: C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 63e599a2a24716de2de3e23cb3a7c2342b036b81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="custom-build-step-property-page-general"></a>사용자 지정 빌드 단계 속성 페이지: 일반
프로젝트 구성과 프로젝트의 대상 플랫폼이 조합되면 프로젝트를 빌드할 때 수행할 사용자 지정 단계를 지정할 수 있습니다.  

이 페이지의 Linux 버전에 대 한 참조 [사용자 지정 빌드 단계 속성 (Linux c + +)](../linux/prop-pages/custom-build-step-linux.md)합니다.
  
## <a name="uielement-list"></a>UI 요소 목록  
 **명령줄**  
 사용자 지정 빌드 단계에서 실행할 명령입니다.  
  
 **설명**  
 사용자 지정 빌드 단계를 실행할 때 표시되는 메시지입니다.  
  
 **출력**  
 사용자 지정 빌드 단계에서 생성되는 출력 파일입니다. 증분 빌드가 올바로 작동하려면 이 설정이 필요합니다.  
  
 **추가 종속성**  
 사용자 지정 빌드 단계에 사용할 추가 입력 파일의 세미콜론으로 구분한 목록입니다.  
  
 **이후 실행 및 실행 하기 전에**  
 이러한 옵션은 나열된 대상 기준으로 빌드 프로세스에서 사용자 지정 빌드 단계가 실행되는 때를 정의합니다. 가장 일반적으로 나열되는 대상은 빌드 프로세스의 주요 단계를 나타내는 BuildGenerateSources, BuildCompile, BuildLink입니다. 종종 나열되는 다른 대상은 Midl, CLCompile, Link입니다.  
  
 출력을 콘텐츠로 처리  
 이 옵션은 .appx 패키지의 모든 콘텐츠 파일을 포함하는 Windows 스토어 또는 Windows Phone 앱에만 의미가 있습니다.  
  
### <a name="to-specify-a-custom-build-step"></a>사용자 지정 빌드 단계를 지정하려면  
  
1.  메뉴 모음에서 **프로젝트**, **속성**을 선택합니다. 자세한 내용은 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
2.  에 **속성 페이지** 대화 상자에서 이동 하는 **구성 속성**, **사용자 지정 빌드 단계**, **일반** 페이지.  
  
3.  설정을 수정합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 페이지](../ide/property-pages-visual-cpp.md)