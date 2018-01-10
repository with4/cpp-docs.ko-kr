---
title: "C + + 콘솔 응용 프로그램 프로젝트 빌드 및 실행 | Microsoft Docs"
description: "Visual c + +에 대 한 Visual Studio 지원 설치"
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d71-719d-42dc-90d7-1d0ca31a2f55
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a5b9c250b102b7d8847e99b87139136bc7df808b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="build-and-run-a-c-console-app-project"></a>C + + 콘솔 응용 프로그램 프로젝트 빌드 및 실행

C + + 콘솔 응용 프로그램 프로젝트를 만들고 코드를 입력 했을 때 빌드하고 수 있습니다 및 Visual Studio 내에서 실행 한 다음 명령줄에서 독립 실행형 앱으로 실행 합니다.

## <a name="prerequisites"></a>필수 구성 요소

- 설치 하 고 컴퓨터에서 실행 중인 작업의 c + + 데스크톱 개발을 사용한 Visual Studio가 있습니다. 아직 설치 되지 않은 경우의 단계에 따라 [Visual Studio에서 c + + 설치 지원](../build/vscpp-step-0-installation.md)합니다.

- "Hello, World!" 만들기 프로젝트 및 해당 소스 코드를 입력 합니다. 아직이 경우의 단계에 따라 [c + + 콘솔 응용 프로그램 프로젝트를 만들](../build/vscpp-step-1-create.md)합니다.

Visual Studio는 다음과 같이 표시 하는 경우에 빌드하고 응용 프로그램 실행을 수행할 수 있습니다.

   ![새 프로젝트를 빌드할 준비가](../build/media/vscpp-ready-to-build.png "새 프로젝트를 빌드할 준비가 되었습니다.")

## <a name="build-and-run-your-code-in-visual-studio"></a>빌드 및 Visual Studio에서 코드 실행

1. 프로젝트를 빌드하려면 선택 **솔루션 빌드** 에서 **빌드** 메뉴. **출력** 빌드 프로세스의 결과 창에 표시 합니다.

   ![프로젝트 빌드](../build/media/vscpp-build-solution.gif "프로젝트 빌드")

1. 메뉴 모음에서 코드를 실행 하려면 **디버그**, **디버깅 하지 않고 시작**합니다.

   ![프로젝트 시작](../build/media/vscpp-start-without-debugging.gif "프로젝트 시작")

    콘솔 창이 열리고 응용 프로그램을 실행 합니다. Visual Studio에서 콘솔 응용 프로그램을 시작 하는 경우 코드를 실행 한 다음 인쇄 "계속 하려면 아무 키나 누르십시오. 이어야 합니다. ." 사용자에 게 결과 볼 수 있습니다.

지금까지 첫 번째 만든 "Hello, world!" Visual Studio에서 콘솔 응용 프로그램! 콘솔 창을 닫고 Visual Studio로 되돌아가려면에 키를 누릅니다.

[I 문제가 발생 했습니다.](#build-and-run-your-code-in-visual-studio-issues)

## <a name="run-your-code-in-a-command-window"></a>명령 창에서 코드를 실행 합니다.

일반적으로 Visual Studio에 없는 명령 프롬프트에서 콘솔 응용 프로그램을 실행합니다. Visual Studio에서 앱이 작성 되 면 모든 명령 창에서 실행할 수 있습니다. 찾고 명령 프롬프트 창에서 새 응용 프로그램을 실행 하는 방법은 다음과 같습니다.

1. **솔루션 탐색기**HelloWorld 솔루션을 선택 하 고 상황에 맞는 메뉴를 열려면 마우스 오른쪽 단추로 클릭 합니다. 선택 **파일 탐색기에서 폴더 열기** 열려는 **파일 탐색기** HelloWorld 솔루션 폴더에는 창입니다.

1. 에 **파일 탐색기** 창 Debug 폴더를 엽니다. 이 응용 프로그램, HelloWorld.exe 및 몇 개의 다른 디버깅 파일을 포함합니다. HelloWorld.exe를 선택 하 고 Shift 키를 누른 다음 상황에 맞는 메뉴를 열려면 마우스 오른쪽 단추로 클릭 합니다. 선택 **경로로 복사** 클립보드에 응용 프로그램에 경로 복사 하려면.

1. 명령 프롬프트 창을 열려면 Windows-R 키를 눌러 엽니다는 **실행** 대화 상자. 입력 *cmd.exe* 에 **열려** 텍스트 상자를 눌러 **확인** 명령 프롬프트 창을 실행 하려면.

1. 명령 프롬프트 창에서 마우스 오른쪽 단추를 명령 프롬프트에 응용 프로그램에 대 한 경로 붙여 넣습니다. Enter 키를 눌러 응용 프로그램을 실행 합니다.

   ![명령 프롬프트에서 앱 실행](../build/media/vscpp-run-in-cmd.gif "명령 프롬프트에서 앱 실행")

축 하 합니다, 빌드하고 Visual Studio에서 콘솔 응용 프로그램을 실행 했습니다!

[I 문제가 발생 했습니다.](#run-your-code-in-a-command-window-issues)

## <a name="next-steps"></a>다음 단계

작성 하 고이 간단한 응용 프로그램을 실행 한 보다 복잡 한 프로젝트에 대 한 준비가 됩니다. 참조 [c + + 데스크톱 개발을 위한 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) 자세한 연습 Visual Studio에서 Visual c + +의 기능을 합니다.

## <a name="troubleshooting-guide"></a>문제 해결 가이드

여기로 솔루션에 대 한 일반적인 문제에 첫 번째 c + + 프로젝트를 만들 때.

### <a name="build-and-run-your-code-in-visual-studio-issues"></a>빌드 및 코드 문제의 경우 Visual Studio 실행

소스 코드 편집기에 아무 것도 아래에 빨간색 물결선 표시를 하는 경우 빌드 오류 또는 경고가 있을 수 있습니다. 코드 예제와도 철자, 문장 부호, 및 대/소문자와 일치 하는지 확인 합니다.

[돌아 가.](#build-and-run-your-code-in-visual-studio)

### <a name="run-your-code-in-a-command-window-issues"></a>문제는 명령 창에서 코드 실행

응용 프로그램을 실행 하는 명령줄에서 솔루션 디버그 폴더로 이동할 수 있습니다. 응용 프로그램에 대 한 경로 지정 하지 않고 다른 디렉터리의 응용 프로그램을 실행할 수 없습니다. 그러나 응용 프로그램을 다른 디렉터리에 복사 하 고 여기에서 실행할 수 있습니다.

[돌아 가.](#run-your-code-in-a-command-window)


<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />
