---
title: "사용자 지정 빌드 도구 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets"
  - "VC.Project.VCCustomBuildTool.Outputs"
  - "VC.Project.VCCustomBuildTool.Command"
  - "VC.Project.VCCustomBuildTool.CommandLine"
  - "VC.Project.VCCustomBuildTool.AdditionalDependencies"
  - "VC.Project.VCCustomBuildTool.Message"
  - "VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets"
  - "VC.Project.VCCustomBuildTool.Description"
  - "VC.Project.VCCustomBuildTool.AdditionalInputs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드 도구(C++), 지정"
  - "빌드(C++), 사용자 지정 빌드 도구"
  - "사용자 지정 빌드 도구(C++), 지정"
ms.assetid: e5161946-8002-418d-991e-219e6a8586f5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 사용자 지정 빌드 도구 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*사용자 지정 빌드 도구*는 특정 입력 파일을 빌드하는 데 필요한 정보를 빌드 시스템에 제공합니다.  사용자 지정 빌드 도구에서는 실행할 명령, 입력 파일 목록, 명령으로 생성되는 출력 파일 목록 및 도구에 대한 설명\(선택 사항\)을 지정합니다.  
  
 사용자 지정 빌드 도구 및 사용자 지정 빌드 단계에 대한 일반적인 내용은 [사용자 지정 빌드 단계 및 빌드 이벤트 이해](../ide/understanding-custom-build-steps-and-build-events.md)를 참조하십시오.  
  
### 사용자 지정 빌드 도구를 지정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **구성 속성**을 클릭하여 **구성** 상자를 활성화합니다.  **구성** 상자에서 사용자 지정 빌드 도구를 지정할 구성을 선택합니다.  
  
3.  **솔루션 탐색기**에서 사용자 지정 빌드 도구에 사용할 입력 파일을 선택합니다.  
  
     **사용자 지정 빌드 도구** 폴더가 표시되지 않으면 선택한 파일의 파일 확장명이 기본 도구와 연결되어 있는 것입니다.  예를 들어 .c 및 .cpp 파일의 기본 도구는 컴파일러입니다.  기본 도구 설정을 재정의하려면 **구성 속성** 노드의 **일반** 폴더에 있는 **항목 형식** 속성에서 **사용자 지정 빌드 도구**를 클릭합니다.  **적용**을 클릭하면 **사용자 지정 빌드 도구** 노드가 표시됩니다.  
  
4.  **사용자 지정 빌드 도구** 노드의 **일반** 폴더에서 사용자 지정 빌드 도구와 연결된 속성을 지정합니다.  
  
    -   **추가 종속성**에서, 정의하고 있는 사용자 지정 빌드 도구에 대한 파일 외의 다른 파일을 지정합니다. 사용자 지정 빌드 도구와 연결된 파일은 암시적으로 해당 도구의 입력 파일이 됩니다.  추가 입력 파일이 사용자 지정 빌드 도구에 꼭 필요한 것은 아닙니다.  추가 입력 파일이 둘 이상 있으면 세미콜론으로 구분합니다.  
  
         **추가 종속성** 파일의 날짜가 입력 파일의 날짜보다 늦으면 사용자 지정 빌드 도구가 실행됩니다.  모든 **추가 종속성** 파일이 입력 파일보다 오래되었고 입력 파일이 **출력** 속성 파일보다 오래되었으면 사용자 지정 빌드 도구는 실행되지 않습니다.  
  
         예를 들어 MyInput.x를 입력 파일로 사용하여 MyInput.cpp를 생성하는 사용자 지정 빌드 도구가 있으며 MyInput.x에는 MyHeader.h라는 헤더 파일이 포함되어 있는 경우,  MyHeader.h를 MyInput.x에 대한 입력 종속성으로 지정할 수 있습니다. 이 경우 빌드 시스템에서는 MyInput.cpp의 날짜가 MyInput.x나 MyHeader.h의 날짜보다 빠르면 MyInput.cpp를 빌드하게 됩니다.  
  
         입력 종속성을 사용하면 사용자 지정 빌드 도구를 원하는 순서대로 실행할 수도 있습니다.  앞의 예제에서 MyHeader.h가 사용자 지정 빌드 도구의 실제 출력 파일이라고 가정할 경우,  MyHeader.h는 MyInput.x에 종속되어 있으므로 빌드 시스템에서는 MyHeader.h를 먼저 빌드한 다음 MyInput.x에 대해 사용자 지정 빌드 도구를 실행합니다.  
  
    -   명령 프롬프트에서 명령을 지정할 때와 같이 **명령줄**에서 명령을 지정합니다.  올바른 명령 또는 배치 파일과 필수 입력 또는 출력 파일을 지정합니다.  배치 파일의 이름 앞에 **call** 배치 명령을 지정해야 이어지는 모든 명령이 실행됩니다.  
  
         MSBuild 매크로를 사용하여 여러 입력 및 출력 파일을 기호로 지정할 수 있습니다.  [!INCLUDE[crabout](../build/reference/includes/crabout_md.md)] 파일의 위치 또는 파일 집합의 이름을 지정하는 방법에 대한 자세한 내용은 [빌드 명령 및 속성 매크로](../ide/common-macros-for-build-commands-and-properties.md)를 참조하십시오.  
  
         '%' 문자는 MSBuild에 예약되어 있으므로 환경 변수를 지정하는 경우 각 **%** 이스케이프 문자를 **%25** 16진수 이스케이프 시퀀스로 바꿉니다.  예를 들어 **%WINDIR%**는 **%25WINDIR%25**로 바꿉니다.  MSBuild는 환경 변수에 액세스하기 전에 각 **%25** 시퀀스를 **%** 문자로 바꿉니다.  
  
    -   **설명**에 사용자 지정 빌드 도구에 대한 설명 메시지를 입력합니다.  메시지는 빌드 시스템에서 이 도구를 처리할 때 **출력** 창에 표시됩니다.  
  
    -   **출력**에 출력 파일의 이름을 지정합니다.  이 속성은 필수 항목이므로 이 속성에 값이 없으면 사용자 지정 빌드 도구가 실행되지 않습니다.  사용자 지정 빌드 도구에 둘 이상의 출력 파일이 있으면 각 파일 이름을 세미콜론으로 구분합니다.  
  
         출력 파일의 이름은 **명령줄** 속성에 지정된 이름과 같아야 합니다.  프로젝트 빌드 시스템에서는 이 파일을 찾아 날짜를 검사합니다.  출력 파일의 날짜가 입력 파일의 날짜보다 늦거나 출력 파일이 없으면 사용자 지정 빌드 도구가 실행됩니다.  모든 **추가 종속성** 파일이 입력 파일보다 오래되었고 입력 파일이 **출력** 속성에 지정된 파일보다 오래되었으면 사용자 지정 빌드 도구는 실행되지 않습니다.  
  
 사용자 지정 빌드 도구에서 생성된 출력 파일이 빌드 시스템에서 작동되도록 하려면 출력 파일을 프로젝트에 수동으로 추가해야 합니다.  사용자 지정 빌드 도구에서는 빌드하는 동안 이 파일을 업데이트합니다.  
  
## 예제  
 parser.l이라는 파일을 프로젝트에 포함하려는 경우  어휘 분석기를 통해 parser.l을 처리하여 동일한 기본 이름\(parser.c\)의 .c 파일을 생성할 수 있습니다.  
  
 먼저, parser.l과 parser.c를 프로젝트에 추가합니다.  이 파일이 없으면 이 파일에 대한 참조를 추가합니다.  parser.l에 사용할 사용자 지정 빌드 도구를 만들고 **명령** 속성에 다음을 입력합니다.  
  
```  
lexer %(FullPath) .\%(Filename).c  
```  
  
 이 명령은 parser.l에 대해 어휘 분석기를 실행하고 parser.c를 프로젝트 디렉터리에 출력합니다.  
  
 **출력** 속성에 다음을 입력합니다.  
  
```  
.\%(Filename).c  
```  
  
 프로젝트를 빌드할 때 빌드 시스템에서는 parser.l과 parser.c의 타임스탬프를 비교한 후,  parser.l의 타임스탬프가 더 최근이거나 parser.c가 없으면 **명령줄** 속성 값을 실행하여 parser.c를 최신 상태로 만듭니다.  parser.c도 프로젝트에 추가되었으므로 빌드 시스템에서는 parser.c를 컴파일하게 됩니다.  
  
## 참고 항목  
 [빌드 명령 및 속성 매크로](../ide/common-macros-for-build-commands-and-properties.md)   
 [빌드 사용자 지정 문제 해결](../ide/troubleshooting-build-customizations.md)