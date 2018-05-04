---
title: C + + 콘솔 응용 프로그램 프로젝트 만들기 | Microsoft Docs
description: Visual c + +에서는 Hello World 콘솔 응용 프로그램 만들기
ms.custom: mvc
ms.date: 12/12/2017
ms.topic: tutorial
ms.technology:
- devlang-C++
ms.devlang: C++
dev_langs:
- C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35b7b896dfb2a4c9dd37a9f59476cbc7f23c3902
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="create-a-c-console-app-project"></a>C + + 콘솔 앱 프로젝트 만들기

C + + 프로그래머는 일반적인 시작 지점을 "Hello, world!" 명령줄에서 실행 되는 응용 프로그램입니다. 즉, 어떤 만들게 Visual Studio에서이 단계에서는 합니다.

## <a name="prerequisites"></a>전제 조건

- 설치 하 고 컴퓨터에서 실행 중인 작업의 c + + 데스크톱 개발을 사용한 Visual Studio가 있습니다. 아직 설치 되지 않은 경우 참조 [Visual Studio에서 c + + 설치 지원](../build/vscpp-step-0-installation.md)합니다.

## <a name="create-your-app-project"></a>응용 프로그램 프로젝트 만들기

Visual Studio는 *프로젝트*를 사용하여 앱에 대한 코드를 구성하고 *솔루션*을 사용하여 프로젝트를 구성합니다. 프로젝트 옵션, 구성 및 응용 프로그램을 빌드하는 데 사용 되는 규칙을 포함 하 고 프로젝트의 모든 파일 및 외부 파일 간의 관계를 관리 합니다. 응용 프로그램을 만들려면 먼저 만들어 새 프로젝트 및 솔루션.

1. Visual Studio에서 열고는 **파일** 메뉴 선택 **새로 만들기 > 프로젝트** 열려는 **새 프로젝트** 대화 합니다.

   ![새 프로젝트 대화 상자를 열고](../build/media/vscpp-file-new-project.gif "새 프로젝트 대화 상자를 열려면")

1. 에 **새 프로젝트** 대화 상자에서 **설치 됨**, **Visual c + +** 이미 선택 되지 않은 하 고 다음을 선택 하는 경우는 **빈 프로젝트** 서식 파일입니다. 에 **이름** 필드에, 입력 *HelloWorld*합니다. 선택 **확인** 프로젝트를 만듭니다.

   ![새 프로젝트를 만들고 이름을](../build/media/vscpp-concierge-project-name-callouts.png "이름을 새 프로젝트를 만듭니다")

Visual Studio에서 새로운 빈 프로젝트를 만들 하 고 소스 코드 파일을 추가 하려면 원하는 응용 프로그램의 종류에 맞도록 조정 하기 위해 준비를 만듭니다. 다음을 수행 합니다.

[I 문제가 발생 했습니다.](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>콘솔 응용 프로그램 프로젝트 만들기

Visual Studio는 Windows 및 기타 플랫폼에 대 한 모든 종류의 앱 및 구성 요소를 만들 수 있습니다. **빈 프로젝트** 템플릿 생성 어떤 종류의 앱에 대 한 특정 되지 않습니다. 만들려면는 *콘솔 응용 프로그램*이며 다음 중 하나는 콘솔 또는 명령 프롬프트 창에서 실행 하는 콘솔 하위 시스템을 사용 하도록 응용 프로그램을 Visual Studio를 지시 해야 합니다.

1. Visual Studio에서 열고는 **프로젝트** 메뉴 선택 **속성** 열려는 **HelloWorld 속성 페이지** 대화 합니다.

1. 에 **속성 페이지** 대화 아래에서 **구성 속성**선택, **링커**, **시스템**를 선택한 후 편집 상자 옆에 **하위 시스템** 속성입니다. 표시 되는 드롭다운 메뉴에서 선택 **콘솔 (/ /SUBSYSTEM: CONSOLE)** 합니다. 선택 **확인** 변경 내용을 저장 합니다.

   ![속성 페이지 대화 상자를 열고](../build/media/vscpp-properties-linker-subsystem.gif "속성 페이지 대화 상자를 열려면")

이제 visual Studio 콘솔 창에서 실행 하 여 프로젝트를 빌드할 알고 있습니다. 다음으로, 소스 코드 파일을 추가 하 고 앱에 대 한 코드를 입력 합니다.

[I 문제가 발생 했습니다.](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>소스 코드 파일을 추가 합니다.

1. **솔루션 탐색기**, HelloWorld 프로젝트를 선택 합니다. 메뉴 모음에서 **프로젝트**, **새 항목 추가** 열려는 **새 항목 추가** 대화 상자.

1. 에 **새 항목 추가** 대화 상자에서 **Visual c + +** 아래 **설치 됨** 이미 선택 되지 않은 경우. 가운데 창에서 선택 **c + + 파일 (.cpp)** 합니다. 변경 된 **이름** 를 *HelloWorld.cpp*합니다. 선택 **추가** 를 대화 상자를 닫고 파일을 만듭니다.

   ![HelloWorld.cpp에 대 한 소스 파일을 추가](../build/media/vscpp-add-new-item.gif "HelloWorld.cpp에 대 한 소스 파일을 추가 합니다.")

Visual studio 새로 만든 빈 소스 코드 파일을 만들고 소스 코드를 입력 하 고 편집기 창에서 열립니다.

[I 문제가 발생 했습니다.](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>소스 파일에 코드 추가

1. HelloWorld.cpp 편집기 창에이 코드를 복사 합니다.

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   코드는 편집기 창에서 다음과 같이 표시 됩니다.

   ![Hello World 코드 편집기에서](../build/media/vscpp-hello-world-editor.png "Hello World 코드 편집기에서")

코드 편집기에서 다음과 같이 표시 하는 경우 다음 단계를 수행 하 고 응용 프로그램을 빌드할 준비가 된 것 있습니다.

[I 문제가 발생 했습니다.](#add-a-source-code-file-issues)

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [C + + 프로젝트 빌드 및 실행](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>문제 해결 가이드

여기로 솔루션에 대 한 일반적인 문제에 첫 번째 c + + 프로젝트를 만들 때.

### <a name="create-your-app-project-issues"></a>앱 프로젝트 문제를 만듭니다.

경우는 **새 프로젝트** 대화 상자에 표시 하지 않습니다는 **Visual c + +** 항목 **설치 됨**, Visual Studio의 사본의 없을 가능성이 많습니다는 **데스크톱 c + +를 사용한 개발** 설치 하는 작업입니다. 바로 설치 관리자를 실행할 수는 **새 프로젝트** 대화 상자. 선택 된 **Open Visual Studio 설치 관리자** 설치 관리자를 다시 시작 하는 링크입니다. 경우는 **사용자 계정 컨트롤** 권한을 요청 하는 대화 상자를 선택 **예**합니다. 설치 관리자에 있는지 확인는 **c + + 데스크톱 개발** 작업 체크 인 되 고 선택 **확인** 를 Visual Studio 설치를 업데이트 합니다.

같은 이름의 다른 프로젝트에 이미 있으면 프로젝트에 대해 다른 이름을 선택 또는 기존 프로젝트를 삭제 하 고 다시 시도 하십시오. 기존 프로젝트를 삭제 하려면 파일 탐색기에서 솔루션 폴더 (helloworld.sln 파일이 있는 폴더)를 삭제 합니다.

[돌아가서](#create-your-app-project)합니다.

### <a name="make-your-project-a-console-app-issues"></a>프로젝트는 콘솔 응용 프로그램 문제 확인

표시 되지 않으면 **링커** 아래에 나열 **구성 속성**, 선택 **취소** 를 닫으려면는 **속성 페이지** 대화 한 다음 다음 사항을 확인는 **HelloWorld** 에서 프로젝트를 선택한 **솔루션 탐색기**, 하지는 솔루션 또는 다른 파일이 나 폴더를 다시 시도 하기 전에.

드롭다운 컨트롤에 표시 되지 않습니다는 **하위 시스템** 속성 편집 상자는 속성을 선택 해야 합니다. 포인터를 사용 하 여 선택 하거나 Tab 될 때까지 대화 상자 컨트롤을 통해을 누르면 **하위 시스템** 강조 표시 됩니다. 드롭다운 컨트롤을 선택 하거나 Alt + 아래쪽을 엽니다.

[돌아 가](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>소스 코드 파일 문제를 추가 합니다.

소스 코드 파일에 다른 이름을 지정 하는 것이 좋습니다. 그러나 프로젝트에 동일한 코드가 포함 된 소스 코드 파일을 여러 개를 추가 하지 마십시오.

프로젝트에 잘못 된 형식의 파일을 추가 하는 경우 예를 들어 헤더 파일을 삭제 다시 시도 합니다. 파일을 삭제 하려면 선택에서 **솔루션 탐색기** Delete 키를 누릅니다.

[돌아가서](#add-a-source-code-file)합니다.

### <a name="add-code-to-the-source-file-issues"></a>소스 파일 문제에 코드 추가

소스 코드 파일 편집기 창 다시 열려면를 실수로 닫은 경우 두 번 클릭에 HelloWorld.cpp는 **솔루션 탐색기** 창.

소스 코드 편집기에 아무 것도 아래에 빨간색 물결선 표시, 코드 예제와도 철자, 문장 부호, 및 대/소문자와 일치 하는지 확인 합니다. 대/소문자는 c + + 코드에서 중요 합니다.

[돌아가서](#add-code-to-the-source-file)합니다.

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />