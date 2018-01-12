---
title: "연습: 프로젝트 및 솔루션 (c + +) 작업 | Microsoft Docs"
ms.custom: 
ms.date: 12/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- solutions [C++]
- projects [C++], about projects
- projects [C++]
- solutions [C++], about solutions
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a20c0ee933d49465a841b638a8260181d7175ac5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-working-with-projects-and-solutions-c"></a>연습: 프로젝트 및 솔루션 작업(C++)

Visual Studio에서 C++ 프로젝트를 만들고 코드를 추가한 다음 프로젝트를 빌드하여 실행하는 방법은 다음과 같습니다. 이 연습에 나오는 프로젝트는 얼마나 많은 플레이어가 서로 다른 카드 게임을 플레이하고 있는지를 추적하는 프로그램입니다.

Visual Studio에서 프로젝트 및 솔루션의 작업을 구성 합니다. 솔루션에는 DLL 및 이 DLL을 참조하는 실행 파일과 같은 둘 이상의 프로젝트가 포함될 수 있습니다. 자세한 내용은 [솔루션 및 프로젝트](/visualstudio/ide/solutions-and-projects-in-visual-studio)를 참조하세요.

## <a name="before-you-start"></a>시작하기 전에

이 연습을 완료 하려면 15.3 이상이 Visual Studio 2017 버전 있어야 합니다. 간단한 지침은 다음과 같습니다 복사본이 필요한 경우: [Visual Studio에서 c + + 설치 지원](../build/vscpp-step-0-installation.md)합니다. 아직 수행 하지 않은, 하는 경우 다음 단계를 수행 하며 Visual c + +가 제대로 설치 되어 있는지 확인 하는 "Hello, World" 자습서를 통해 설치 후 모든 작동 합니다.

C + + 언어의 기본적인 사항을 이해 하 고 컴파일러, 링커 및 디버거 용도를 알고 있으면 도움이 됩니다. 자습서 창 및 메뉴, 대화 상자를 사용 하는 방법을 익숙한를 가정 합니다.

## <a name="create-a-project"></a>프로젝트 만들기

프로젝트를 만들려면 먼저 프로젝트 형식 템플릿을 선택합니다. 각 프로젝트 형식에 대 한 Visual Studio에서는 컴파일러 설정 및-유형에 따라-나중에 수정할 수 있는 시작 코드를 생성 합니다.

### <a name="to-create-a-project"></a>프로젝트를 만들려면

1. 메뉴 모음에서 **파일 > 새로 만들기 > 프로젝트**합니다.

1. 왼쪽된 창에는 **새 프로젝트** 대화 상자에서 **설치 됨** 선택 **Visual c + +**아직 열려 있지 않은 경우, 합니다.

1. 가운데 창에서 설치 된 템플릿 목록에서 선택 **Windows 콘솔 응용 프로그램**합니다.

1. 프로젝트에 대 한 이름을 입력 된 **이름** 상자입니다. 이 예에서는 입력 **게임**합니다.

   기본 위치를 적용할 수 있습니다는 **위치** 드롭 다운 목록에서 다른 위치를 입력 하거나 선택 된 **찾아보기** 단추 프로젝트를 저장 하려는 디렉터리를 찾습니다.

   프로젝트를 만들 때 Visual Studio 솔루션에 프로젝트를 추가 합니다. 기본적으로 솔루션의 이름은 프로젝트 이름과 같습니다. 이름을 변경할 수 있습니다는 **솔루션 이름** 상자의 하지만이 예제에 대 한 기본 이름을 유지 합니다.

1. **확인** 단추를 선택하여 프로젝트를 만듭니다.

   Visual Studio 새 솔루션 및 프로젝트 파일을 만들고 생성 된 Game.cpp 소스 코드 파일에 대 한 편집기를 엽니다.

## <a name="organize-projects-and-files"></a>프로젝트 및 파일 구성

사용할 수 있습니다 **솔루션 탐색기** 구성 하 고 프로젝트, 파일 및 솔루션의 다른 리소스를 관리 합니다.

이 연습 부분에서는 프로젝트에 클래스를 추가하는 방법을 보여 줍니다. 클래스에 추가 하면 Visual Studio에서 해당.h 및.cpp 파일을 추가 합니다. 결과 볼 수 **솔루션 탐색기**합니다.

### <a name="to-add-a-class-to-a-project"></a>프로젝트에 클래스를 추가하려면

1. 경우는 **솔루션 탐색기** 메뉴 모음에서 Visual Studio의 창이 표시 되지 않으면, 선택 **보기 > 솔루션 탐색기**합니다.

1. **솔루션 탐색기**, 선택는 **게임** 프로젝트. 메뉴 모음에서 **프로젝트 > 클래스 추가**합니다.

1. 에 **클래스 추가** 대화 상자에서 입력 *Cardgame* 에 **클래스 이름** 상자입니다. 기본 파일 이름과 설정을 수정하지 마십시오. **확인** 단추를 선택합니다.

   Visual Studio 새 파일을 만들고 프로젝트에 추가 합니다. 볼 수는 **솔루션 탐색기** 창. Cardgame.cpp 및 Cardgame.h 파일이 편집기에서 열립니다.

1. Cardgame.h 파일을 편집 하 고 이러한 변경 합니다.

   - 클래스 정의의 여는 중괄호 뒤에 두 개의 전용 데이터 멤버를 추가합니다.
      <!--      [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)] -->

      ```cpp
      int players;
      static int totalParticipants;
      ```

   - Visual Studio에서 생성된 기본 생성자를 수정합니다. `public:` 액세스 지정자 뒤에서 다음과 같은 줄을 찾습니다.

      `Cardgame();`

      형식의 매개 변수를 사용 하려면이 생성자를 수정 `int`명명 된 *플레이어*합니다.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]-->
      `Cardgame(int players);`

   - 기본 소멸자 뒤에 대 한 인라인 선언을 추가 `static int` 라는 멤버 함수가 *GetParticipants* 매개 변수를 사용 하 고 반환 하 고 `totalParticipants` 값입니다.

      <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]-->
      `static int GetParticipants() { return totalParticipants; }`

   변경한 후 Cardgame.h 파일은 다음과 유사합니다.

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]-->
   ```cpp
   #pragma once
   class Cardgame
   {
       int players;
       static int totalParticipants;
   public:
       Cardgame(int players);
       ~Cardgame(void);
       static int GetParticipants() { return totalParticipants; }
   };
   ```

   줄 `#pragma once` 컴파일러가 헤더 파일을 한 번만 포함 하도록 지정 합니다. 자세한 내용은 참조 [면](../preprocessor/once.md)합니다. 이 헤더 파일의 다른 c + + 키워드에 대 한 정보를 참조 하십시오. [클래스](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [정적](../cpp/storage-classes-cpp.md), 및 [공용](../cpp/public-cpp.md)합니다.

1. 선택 된 **Cardgame.cpp** 편집 열고 편집할 창 맨 위에 있는 탭입니다.

1. 파일에 있는 모든 항목을 삭제하고 다음 코드로 바꿉니다.

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]-->
   ```cpp
   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   int Cardgame::totalParticipants = 0;

   Cardgame::Cardgame(int players)
       : players(players)
   {
       totalParticipants += players;
       cout << players << " players have started a new game.  There are now "
            << totalParticipants << " players in total." << endl;
   }

   Cardgame::~Cardgame()
   {
   }
   ```

   > [!NOTE]
   > 코드를 입력할 때 자동 완성 기능을 사용할 수 있습니다. 예를 들어 키보드에서이 코드를 입력 하면 입력할 수 있는 *pl* 또는 *tot* 고 Ctrl + 스페이스바를 누릅니다. 자동 완성 입력 `players` 또는 `totalParticipants` 드립니다.

## <a name="add-test-code-to-your-main-function"></a>테스트 코드를 main 함수 추가

새 기능을 테스트 하는 앱에 일부 코드를 추가 합니다.

### <a name="to-add-test-code-to-the-project"></a>프로젝트에 테스트 코드를 추가 하려면

1. Game.cpp 편집기 창에서 기존 코드를 다음 코드로 바꿉니다.

   <!--[!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]-->
   ```cpp
   // Game.cpp : Defines the entry point for the console application.
   //

   #include "stdafx.h"
   #include "Cardgame.h"
   #include <iostream>

   using namespace std;

   void PlayGames()
   {
       Cardgame bridge(4);
       Cardgame blackjack(8);
       Cardgame solitaire(1);
       Cardgame poker(5);
   }

   int main()
   {
       PlayGames();
       return 0;
   }
   ```
이 코드는 테스트 함수 추가 `PlayGames`, 소스 코드 및 호출에서 `main`합니다. 

## <a name="build-and-run-your-app-project"></a>응용 프로그램 프로젝트 빌드 및 실행

다음으로 프로젝트를 빌드하고 응용 프로그램을 실행 합니다.

### <a name="to-build-and-run-the-project"></a>프로젝트를 빌드하여 실행하려면

1. 메뉴 모음에서 **빌드 > 솔루션 빌드**를 선택합니다.

   에 빌드 출력이 표시 됩니다는 **출력** 창. 빌드가 성공한 경우 출력은 다음과 같습니다.

   ```Output
   1>------ Build started: Project: Game, Configuration: Debug Win32 ------
   1>  stdafx.cpp
   1>  Game.cpp
   1>  Cardgame.cpp
   1>  Generating Code...
   1>  Game.vcxproj -> C:\Users\username\Source\Repos\Game\Debug\Game.exe
   ========== Build: 1 succeeded, 0 failed, 0 up-to-date, 0 skipped ==========
   ```

   **출력** 창에는 빌드 구성에 따라 다른 단계가 표시 될 수 있지만 마지막 줄은 표시 된 출력과 비슷합니다 프로젝트 빌드가 성공한 경우.

   빌드 성공 하지 못한 코드는 이전 단계에 표시 되는 코드를 비교 합니다.

1. 메뉴 모음에서 프로젝트를 실행 하려면 **디버그 > 디버깅 하지 않고 시작**합니다. 콘솔 창이 나타나고 출력이 다음과 유사 합니다.

   ```Output
   4 players have started a new game.  There are now 4 players in total.
   8 players have started a new game.  There are now 12 players in total.
   1 players have started a new game.  There are now 13 players in total.
   5 players have started a new game.  There are now 18 players in total.
   ```
콘솔 창을 닫으려면 키를 누릅니다.

축, 응용 프로그램 프로젝트와 솔루션 성공적으로 빌드한 했습니다. Visual Studio에서 c + + 코드 프로젝트를 빌드하는 방법에 대 한 자세한 내용은 연습을 계속 합니다.

## <a name="next-steps"></a>다음 단계

**이전:** [c + + 데스크톱 개발을 위한 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)합니다.  
**다음:** [연습: 프로젝트 (c + +) 빌드](../ide/walkthrough-building-a-project-cpp.md)합니다.

## <a name="see-also"></a>참고 항목

[C++ 언어 참조](../cpp/cpp-language-reference.md)  
[C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)