---
title: 메이크파일 프로젝트 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 02/28/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.makefile.project
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, creating
- project files [C++], Makefile projects
ms.assetid: dd077af3-97a8-48fb-baaa-cf7e07ddef61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc854f96f1c41baf28a5af4ca1f253e47d9a8914
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "33336780"
---
# <a name="creating-a-makefile-project"></a>메이크파일 프로젝트 만들기

메이크파일을 사용하여 명령줄에서 빌드하는 기존 소스 코드 프로젝트가 있는 경우, Visual Studio 개발 환경에는 Visual Studio IDE 기능을 최대한 이용할 수 있는 프로젝트로 변환하는 몇 가지 방법이 있습니다. 이 문서에서는 기존 메이크파일을 사용하여 IDE에서 코드를 빌드하는 Visual Studio에서 메이크파일 프로젝트를 만드는 방법에 대해 설명합니다. 또는 **기존 코드 파일에서 새 프로젝트 만들기** 마법사를 사용하여 소스 코드에서 네이티브 MSBuild 프로젝트를 만들 수 있습니다. 자세한 내용은 [방법: 기존 코드로 C++ 프로젝트 만들기](how-to-create-a-cpp-project-from-existing-code.md)를 참조하세요. Visual Studio 2017부터 **폴더 열기** 기능을 사용할 수도 있습니다. 이 기능은 여러 개의 기존 빌드 시스템을 네이티브 Visual Studio 프로젝트인 것처럼 사용할 수 있습니다. 자세한 내용은 [Visual C++의 폴더 열기 프로젝트](non-msbuild-projects.md)를 참조하세요.

Visual Studio를 통해 기존 메이크파일을 사용하여 소스 코드를 열고 빌드하려면 먼저 MakeFile 프로젝트 템플릿을 선택하여 새 프로젝트를 만듭니다. 마법사를 사용하면 메이크파일에서 사용하는 명령과 환경을 지정할 수 있습니다. 그러면 이 프로젝트를 사용하여 Visual Studio 개발 환경에서 코드를 빌드할 수 있습니다.

기본적으로 메이크파일 프로젝트는 솔루션 탐색기에 파일을 표시하지 않습니다. 메이크파일 프로젝트는 프로젝트의 속성 페이지에 반영되는 빌드 설정을 지정합니다.

프로젝트에서 지정하는 출력 파일은 빌드 스크립트가 생성하는 이름에는 영향을 미치지 않으며 의도만 선언합니다. 메이크파일은 여전히 빌드 프로세스를 제어하고 빌드 대상을 지정합니다.

## <a name="to-create-a-makefile-project"></a>메이크파일 프로젝트를 만들려면

1. [Visual C++ 응용 프로그램 마법사를 사용하여 프로젝트 만들기](../ide/creating-desktop-projects-by-using-application-wizards.md) 도움말 항목의 지침을 따릅니다.

1. **새 프로젝트** 대화 상자에서 **Visual C++** > **일반**을 차례로 펼친 다음, [템플릿] 창에서 **메이크파일 프로젝트**를 선택하여 프로젝트 마법사를 엽니다.

1. [응용 프로그램 설정](../ide/application-settings-makefile-project-wizard.md) 페이지에서 디버그 및 일반 정품 빌드에 대한 명령, 출력, 정리 및 다시 빌드 정보를 제공합니다.

1. **마침**을 클릭하여 마법사를 닫고, **솔루션 탐색기**에서 새로 만든 프로젝트를 엽니다.

속성 페이지에서 프로젝트의 속성을 보고 편집할 수 있습니다. 속성 페이지를 표시하는 방법에 대한 자세한 내용은 [Visual C++ 프로젝트 속성 설정](../ide/working-with-project-properties.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[메이크파일 프로젝트 마법사](../ide/makefile-project-wizard.md)<br/>
[메이크파일의 특수 문자](../build/special-characters-in-a-makefile.md)<br/>
[메이크파일의 내용](../build/contents-of-a-makefile.md)<br/>
