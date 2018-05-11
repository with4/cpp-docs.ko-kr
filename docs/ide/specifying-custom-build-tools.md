---
title: 사용자 지정 지정 빌드 도구 | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildTool.CustomBuildToolBeforeTargets
- VC.Project.VCCustomBuildTool.Outputs
- VC.Project.VCCustomBuildTool.Command
- VC.Project.VCCustomBuildTool.CommandLine
- VC.Project.VCCustomBuildTool.AdditionalDependencies
- VC.Project.VCCustomBuildTool.Message
- VC.Project.VCCustomBuildTool.CustomBuildToolAfterTargets
- VC.Project.VCCustomBuildTool.Description
- VC.Project.VCCustomBuildTool.AdditionalInputs
dev_langs:
- C++
helpviewer_keywords:
- build tools (C++), specifying
- custom build tools (C++), specifying
- builds (C++), custom build tools
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b8fc10d2a94ab4b26a47991d3dc8923afb28ca3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="specify-custom-build-tools"></a>사용자 지정 빌드 도구 지정

A *사용자 지정 빌드 도구* 빌드 시스템에서 특정 입력된 파일을 빌드하는 데 필요한 정보를 제공 합니다. 사용자 지정 빌드 도구를 실행 하는 명령을, 입력된 파일의 목록, 명령에 의해 생성 되는 출력 파일의 목록과 도구에 대 한 설명을 지정 합니다.

사용자 지정 빌드 도구 및 사용자 지정 빌드 단계에 대 한 일반 정보를 참조 하십시오. [이해 사용자 지정 빌드 단계 및 빌드 이벤트](../ide/understanding-custom-build-steps-and-build-events.md)합니다.

### <a name="to-specify-a-custom-build-tool"></a>사용자 지정 빌드 도구를 지정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../ide/working-with-project-properties.md)합니다.

1. 선택 **구성 속성** 사용할 수 있도록는 **구성** 상자입니다. 에 **구성** 상자에서 사용자 지정 빌드 도구를 지정 하려는 구성을 선택 합니다.

1. **솔루션 탐색기**, 사용자 지정 빌드 도구에 대 한 입력된 파일을 선택 합니다.

   경우는 **사용자 지정 빌드 도구** 폴더가 표시 되지 않으면, 선택한 파일의 파일 확장명은 기본 도구와 연결 합니다. 예를 들어.c 및.cpp 파일의 기본 도구는 컴파일러입니다. 기본 도구 설정을 재정의 하는 **구성 속성** 노드는 **일반** 폴더에는 **항목 형식** 속성을 선택 **사용자 지정 빌드 도구**합니다. 선택 **적용** 및 **사용자 지정 빌드 도구** 노드가 표시 됩니다.

1. 에 **사용자 지정 빌드 도구** 노드에는 **일반** 폴더를 빌드 도구에 연결 된 사용자 지정 속성을 지정 합니다.

   - **추가 종속성**, 정의 되 고 있는 사용자 지정 빌드 도구 하나 이상 추가 파일 지정 (사용자 지정 빌드 도구와 관련 된 암시적으로 간주 도구에 대 한 입력). 입력 파일을 추가 사용자 지정 빌드 도구에 대 한 요구 사항은 아닙니다. 추가 입력이 여러 개 있는 경우 세미콜론으로 구분 합니다.

      경우는 **추가 종속성** 사용자 지정 빌드 도구를 실행 한 다음 파일의 날짜가 입력된 파일 보다 나중입니다. 모든 경우의 **추가 종속성** 입력된 파일 보다 오래 된 파일 및 입력된 파일 보다 오래 된는 **출력** 속성 파일을 다음 사용자 지정 빌드 도구 실행 되지 않습니다.

      예를 들어 입력으로 MyInput.x 걸리고 MyInput.cpp와 MyInput.x MyHeader.h 헤더 파일에 포함 되어 있는지를 생성 하는 사용자 지정 빌드 도구를 있다고 가정 합니다. MyInput.x에 대 한 입력된 종속성으로 MyHeader.h를 지정할 수 있습니다 하 않으며 MyInput.x 또는 MyHeader.h에 대하여 오래 되었을 때 빌드 시스템 MyInput.cpp 빌드됩니다.

      입력된 종속성을 사용 하는 사용자 지정 빌드 도구를 원하는 순서로 실행할 수도 있습니다. 앞의 예에서 MyHeader.h가 실제로 사용자 지정 빌드 도구의 출력을 가정 합니다. MyHeader.h MyInput.x의 종속 이기 때문에 빌드 시스템 MyInput.x에서 사용자 지정 빌드 도구를 실행 하기 전에 Myheader.h을 먼저 만듭니다.

   - **명령줄**, 명령 프롬프트에서 지정 된 경우에 따라 명령을 지정 합니다. 올바른 명령 또는 배치 파일을 지정 하 고 필수 입력 또는 출력 파일입니다. 지정 된 **호출** 이후 모든 명령은 실행은 보장 하려면 배치 파일의 이름 앞에 명령을 배치 합니다.

      여러 입력 및 출력 파일은 MSBuild 매크로 함께 기호로 지정할 수 있습니다. 파일의 위치 또는 파일 집합의 이름을 지정 하는 방법에 대 한 정보를 참조 하십시오. [빌드 명령 및 속성에 대 한 일반적인 매크로](../ide/common-macros-for-build-commands-and-properties.md)합니다.

      각 환경 변수 대체를 지정 하는 경우 '%' 문자가 MSBuild에 의해 예약 되어 있으므로 **%** 이스케이프 문자는 **%25** 16 진수 이스케이프 시퀀스입니다. 예를 들어 대체 **% WINDIR %** 와 **%25WINDIR %25**합니다. 각 MSBuild 대체 **%25** 가진 시퀀스는 **%** 환경 변수에 액세스 하기 전에 문자입니다.

   - **설명**,이 사용자 지정 빌드 도구에 대 한 설명 메시지를 입력 합니다. 메시지에 인쇄 되며는 **출력** 빌드 시스템에서이 도구를 처리할 때 창입니다.

   - **출력**, 출력 파일의 이름을 지정 합니다. 이 항목은 필수 항목입니다. 이 속성에 대 한 값이 없는 사용자 지정 빌드 도구 실행 되지 않습니다. 사용자 지정 빌드 도구 둘 이상의 출력에 있는 경우 파일 이름은 세미콜론으로 구분 합니다.

      출력 파일의 이름이 동일 해야에 지정 되어는 **명령줄** 속성입니다. 프로젝트 빌드 시스템 파일에 대 한 모양과 날짜를 검사 합니다. 출력 파일이 입력된 파일 보다 최신 또는 출력 파일을 찾을 수 없는 경우에 사용자 지정 빌드 도구 실행 됩니다. 모든 경우의 **추가 종속성** 입력된 파일 보다 오래 된 파일 및 입력된 파일에 지정 된 파일 보다 오래 된는 **출력** 속성을 사용자 지정 빌드 도구를 실행 합니다.

빌드 시스템의 사용자 지정 빌드 도구에 의해 생성 된 출력 파일에서 작동 되도록 하려는 경우 프로젝트에 수동으로 추가 해야 있습니다. 사용자 지정 빌드 도구에서는 빌드하는 동안 파일을 업데이트 합니다.

## <a name="example"></a>예제

프로젝트에서 parser.l 라는 파일을 포함 하도록 한다고 가정 합니다. 어휘 분석기가 **lexer.exe**, 실행 파일 경로에 있습니다. Parser.l.c 파일은 동일한 기본 이름을 (parser.c)를 생성 하 고 처리를 사용 하려는.

먼저 parser.l와 parser.c 프로젝트에 추가 합니다. 파일이 아직 존재 하지 않는 경우 파일에 대 한 참조를 추가 합니다. Parser.l에 대 한 사용자 지정 빌드 도구를 만들고에서 다음을 입력에서 **명령을** 속성:

> **렉서 %(FullPath) 합니다. \%.C (파일 이름)**

이 명령은 parser.l에서 어휘 분석기를 실행 하 고 프로젝트 디렉터리에 parser.c를 출력 합니다.

에 **출력** 속성을 다음과 같이 입력 합니다.

> **. \%.C (파일 이름)**

프로젝트를 빌드할 때 빌드 시스템 parser.l 및 parser.c의 타임 스탬프를 비교 합니다. Parser.l 보다 최신 이거나 parser.c가 존재 하지 않는 빌드 시스템의 값은 실행 된 **명령줄** parser.c 최신 상태로 속성입니다. 또한 parser.c 프로젝트에 추가 합니다 빌드 시스템 parser.c를 컴파일합니다.

## <a name="see-also"></a>참고자료

[빌드 명령 및 속성에 대한 일반 매크로](../ide/common-macros-for-build-commands-and-properties.md)  
[빌드 사용자 지정 문제 해결](../ide/troubleshooting-build-customizations.md)  
