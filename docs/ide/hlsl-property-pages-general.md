---
title: "HLSL 속성 페이지: 일반 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs:
- C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be548966f6e75afde2c137c8beab38903844667c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="hlsl-property-pages-general"></a>HLSL 속성 페이지: 일반
HLSL 컴파일러 (fxc.exe)의 다음 속성을 구성 하려면 사용 하 여 해당 **일반** 속성 페이지. 액세스 하는 방법에 대 한 내용은 **일반** HLSL 폴더 속성 페이지에에서 참조 [프로젝트 속성 작업](../ide/working-with-project-properties.md)합니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **추가 포함 디렉터리**  
 포함 경로에 하나 이상의 디렉터리를 추가합니다. 디렉터리 구분 하려면 세미콜론을 사용 합니다.  
  
 이 속성에 해당 하는 **/I [path]** 명령줄 인수입니다.  
  
 **Entrypoint 이름**  
 셰이더에 대 한 진입점을 지정합니다. 기본적으로 값은 **주**합니다.  
  
 이 속성에 해당 하는 **/E [name]** 명령줄 인수입니다.  
  
 **최적화를 사용 하지 않도록 설정**  
 **아니요 (/od)** 최적화를 사용 하지 않도록 설정 하 고, 그러지 **아니요**합니다. 기본적으로 값은 **아니요 (/od)** 에 대 한 **디버그** 구성 및 **아니요** 에 대 한 **릴리스** 구성 합니다.  
  
 **/Od** HLSL 컴파일러에 명령줄 인수를 암시적으로 적용 된 **/Gfp** 명령줄 인수가 있지만 출력 둘 다를 전달 하 여 생성 되는 출력에 동일한 수 있습니다는 **/Od**  및 **/Gfp** 명령줄 인수 명시적으로 합니다.  
  
 **디버깅 정보를 사용 하도록 설정**  
 **예 (/Zi)** 디버깅 정보를 사용 하도록 설정 하려면, **아니요**합니다. 기본적으로 값은 **(/Zi) 예** 에 대 한 **디버그** 구성 및 **아니요** 에 대 한 **릴리스** 구성 합니다.  
  
 **셰이더 유형**  
 셰이더의 종류를 지정합니다. 다양 한 종류의 셰이더 그래픽 파이프라인의 다른 부분을 구현합니다. 특정 종류의 셰이더 최신 셰이더 모델 에서만에서 사용할 수 있는 (하 여 지정 됩니다는 **Shader Model** 속성)-예를 들어 셰이더 모델 5에에서 도입 된 셰이더를 계산 합니다.  
  
 이 속성에 해당 하는 **[type]** 부분의 **/T [type] _ [모델]** HLSL 컴파일러에 명령줄 인수입니다. **셰이더 모델** 속성 지정는 **[모델]** 인수의 부분입니다.  
  
 **셰이더 모델**  
 셰이더 모델을 지정합니다. 다른 셰이더 모델은 기능이 다릅니다. 일반적으로 최신 셰이더 모델 확장 된 기능을 제공 하지만 셰이더 코드를 실행 하려면 최신 그래픽 하드웨어를 필요로 합니다. 특정 종류의 셰이더 (하 여 지정 됩니다는 **셰이더 형식** 속성) 최신 셰이더 모델 에서만 사용할 수-예를 들어 셰이더 모델 5에에서 도입 된 셰이더를 계산 합니다.  
  
 이 속성에 해당 하는 **[모델]** 부분의 **/T [type] _ [모델]** HLSL 컴파일러에 명령줄 인수입니다. **셰이더 형식** 속성 지정는 **[type]** 인수의 부분입니다.  
  
 **전처리기 정의**  
 HLSL 소스 코드 파일에 적용할 하나 이상의 전처리기 기호 정의 추가 합니다. 세미콜론을 사용해 기호 정의를 사용 합니다.  
  
 이 속성에 해당 하는 **/D [정의]** HLSL 컴파일러에 명령줄 인수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [HLSL 속성 페이지](../ide/hlsl-property-pages.md)   
 [HLSL 속성 페이지: 고급](../ide/hlsl-property-pages-advanced.md)   
 [HLSL 속성 페이지: 출력 파일](../ide/hlsl-property-pages-output-files.md)