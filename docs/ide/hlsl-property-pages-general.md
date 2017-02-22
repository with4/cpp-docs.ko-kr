---
title: "HLSL 속성 페이지: 일반 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.FXCompilerTool.ShaderModel"
  - "VC.Project.FXCompilerTool.PreprocessorDefinitions"
  - "VC.Project.FXCompilerTool.ShaderType"
  - "VC.Project.FXCompilerTool.EnableDebuggingInformation"
  - "VC.Project.FXCompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.FXCompilerTool.DisableOptimizations"
  - "VC.Project.FXCompilerTool.EntryPointName"
dev_langs: 
  - "C++"
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
caps.latest.revision: 8
author: "BrianPeek"
ms.author: "brpeek"
manager: "ghogen"
caps.handback.revision: 8
---
# HLSL 속성 페이지: 일반
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

HLSL 컴파일러 \(fxc.exe\)의 다음과 같은 속성을 구성 하려면 해당  **일반** 속성 페이지입니다.  에 액세스 하는 방법에 대 한 정보는  **일반** HLSL 폴더에서 속성 페이지를 참조 하십시오. [방법: 속성 페이지로 프로젝트 속성 지정](../misc/how-to-specify-project-properties-with-property-pages.md).  
  
## UI 요소 목록  
 **추가 포함 디렉터리**  
 하나 이상의 디렉터리 포함 경로에 추가합니다.  세미콜론을 사용 하는 디렉터리를 구분 합니다.  
  
 이 속성에 해당 하는 **\/I\[path\]** 명령줄 인수입니다.  
  
 **진입점 이름**  
 셰이더에 대해 진입점을 지정합니다.  기본적으로 값입니다  **주**.  
  
 이 속성에 해당 하는 **\/E\[name\]** 명령줄 인수입니다.  
  
 **최적화를 사용 하지 않도록 설정**  
 **예 \(\/od\)** ; 최적화를 사용 하지 않도록 설정 하려면 그렇지 않으면  **No**.  기본적으로 값입니다  **예 \(\/od\)** 의  **디버그** 구성 및  **No** 에 대 한  **릴리스** 구성.  
  
 **\/Od** HLSL 컴파일러 명령줄 인수를 암시적으로 적용은 **\/Gfp** 명령줄 인수가 있지만 출력 하지 않거나 둘 다를 전달 하 여 생성 된 출력에는 **\/Od** 및 **\/Gfp** 명령줄 인수 명시적으로.  
  
 **디버깅 정보를 사용 합니다.**  
 **예 \(\/Zi\)** 디버깅 정보를 사용 하려면 그렇지 않으면  **No**.  기본적으로 값입니다  **예 \(\/Zi\)** 의  **디버그** 구성 및  **No** 에 대 한  **릴리스** 구성.  
  
 **셰이더 입력**  
 쉐이더의 종류를 지정합니다.  다양 한 종류의 셰이더 그래픽 파이프라인의 다른 부분을 구현합니다.  특정 종류의 셰이더 보다 최신 셰이더 모델 에서만 사용할 수 있습니다 \(에서 지정 되는  **셰이더 모델** 속성\)\-셰이더 셰이더 모델 5에 도입 된 예를 들어, 계산.  
  
 이 속성에 해당는 **\[type\]** 부분을 **\/T \[type\]\_\[model\]** HLSL 컴파일러 명령줄 인수입니다.  **셰이더 모델** 속성을 지정 된 **\[model\]** 인수 부분.  
  
 **쉐이더 모델**  
 셰이더 모델을 지정합니다.  다른 셰이더 모델에는 서로 다른 기능이 있습니다.  일반적으로 최신 셰이더 모델 확장 된 기능을 제공 하지만 셰이더 코드를 실행 하려면 최신 그래픽 하드웨어를 필요로 합니다.  특정 종류의 셰이더 \(의해 지정 되는  **셰이더 입력** 속성\) 최신 셰이더 모델 에서만 사용할 수 있습니다\-셰이더 셰이더 모델 5에 도입 된 예를 들어, 계산.  
  
 이 속성에 해당는 **\[model\]** 부분을 **\/T \[type\]\_\[model\]** HLSL 컴파일러 명령줄 인수입니다.  **셰이더 입력** 속성을 지정 된 **\[type\]** 인수 부분.  
  
 **전처리기 정의**  
 HLSL 소스 코드 파일에 적용 하려면 하나 이상의 전처리기 기호 정의 추가 합니다.  기호 정의 구분 하려면 세미콜론을 사용 합니다.  
  
 이 속성에 해당 하는 **\/D \[definitions\]** HLSL 컴파일러 명령줄 인수입니다.  
  
## 참고 항목  
 [HLSL 속성 페이지](../ide/hlsl-property-pages.md)   
 [HLSL 속성 페이지: 고급](../ide/hlsl-property-pages-advanced.md)   
 [HLSL 속성 페이지: 출력 파일](../ide/hlsl-property-pages-output-files.md)