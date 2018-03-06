---
title: "메이크파일 프로젝트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: article
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f487126b58dddc0243646ebce7faa2754ffa7053
ms.sourcegitcommit: 4e01d36ffa64ea11bacf589f79d2f1df947e2510
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="creating-a-makefile-project"></a>메이크파일 프로젝트 만들기

메이크파일을 사용 하 여 명령줄에서 작성 하는 기존 소스 코드 프로젝트를 사용 하도록 설정한 경우 Visual Studio 개발 환경에 여러 가지 방법으로 Visual Studio IDE 기능을 사용할 수 있는 프로젝트에 설정 합니다. 이 문서에서는 IDE에서 코드를 작성 하 여 기존 메이크파일을 사용 하는 Visual Studio에서 메이크파일 프로젝트를 만드는 방법을 설명 합니다. 사용할 수 있습니다는 **기존 코드 파일에서 새 프로젝트 만들기** 마법사를 소스 코드 로부터 네이티브 MSBuild 프로젝트를 만듭니다. 자세한 내용은 [방법: 기존 코드로 C++ 프로젝트 만들기](how-to-create-a-cpp-project-from-existing-code.md)를 참조하세요. Visual Studio 2017 년부터 사용할 수도 있습니다는 **폴더 열기** 큐브인 것 처럼 네이티브 Visual Studio 프로젝트에 여러 기존 빌드 시스템을 사용할 수 있는 기능을 합니다. 자세한 내용은 [Visual C++의 폴더 열기 프로젝트](non-msbuild-projects.md)를 참조하세요.

Visual Studio를 열고 기존 메이크파일을 사용 하 여 소스 코드를 작성을 사용 하려면 먼저 MakeFile 프로젝트 템플릿을 선택 하 여 새 프로젝트를 만듭니다. 마법사를 사용 하면 명령 및 환경에서 사용자의 메이크파일을 사용 하는 지정할 수 있습니다. Visual Studio 개발 환경에서 프로그램 코드를 빌드하려면 다음이 프로젝트를 사용할 수 있습니다.

기본적으로 메이크파일 프로젝트 파일이 솔루션 탐색기에 표시 됩니다. 메이크파일 프로젝트에 프로젝트의 속성 페이지에 반영 되는 빌드 설정을 지정 합니다.

프로젝트에서 지정하는 출력 파일은 빌드 스크립트가 생성하는 이름에는 영향을 미치지 않으며 의도만 선언합니다. 여전히 메이크파일을 빌드 프로세스를 제어 하 게 되 고 빌드 대상을 지정 합니다.

## <a name="to-create-a-makefile-project"></a>메이크파일 프로젝트를 만들려면

1. 도움말 항목의 지침에 따라 [Visual c + + 응용 프로그램 마법사로 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md)합니다.

1. 에 **새 프로젝트** 대화 상자에서 **Visual c + +** > **일반** 선택한 후 **메이크파일 프로젝트** 에 템플릿 창 프로젝트 마법사를 엽니다.

1. 에 [응용 프로그램 설정](../ide/application-settings-makefile-project-wizard.md) 페이지에서 명령 출력을 정리 하 고, 디버그 및 소매에 대 한 다시 빌드 정보 빌드를 제공 합니다.

1. 클릭 **마침** 는 마법사를 닫고에서 새로 만든된 프로젝트를 열 **솔루션 탐색기**합니다.

속성 페이지에서 프로젝트의 속성을 보고 편집할 수 있습니다. 참조 [Visual c + + 프로젝트 속성 설정](../ide/working-with-project-properties.md) 속성 페이지를 표시 하는 방법에 대 한 정보에 대 한 합니다.

## <a name="see-also"></a>참고 항목

[메이크파일 프로젝트 마법사](../ide/makefile-project-wizard.md)<br/>
[메이크파일의 특수 문자](../build/special-characters-in-a-makefile.md)<br/>
[메이크파일의 내용](../build/contents-of-a-makefile.md)<br/>
