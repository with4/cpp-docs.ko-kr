---
title: "연습: 프로젝트 및 솔루션 작업(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "프로젝트[C++]"
  - "프로젝트[C++], 프로젝트 정보"
  - "솔루션[C++]"
  - "솔루션[C++], 솔루션 정보"
ms.assetid: 93a3f290-e294-46e3-876e-e3084d9ae833
caps.latest.revision: 25
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 프로젝트 및 솔루션 작업(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio에서 C\+\+ 프로젝트를 만들고 코드를 추가한 다음 프로젝트를 빌드하여 실행하는 방법은 다음과 같습니다.  이 연습에 나오는 프로젝트는 얼마나 많은 플레이어가 서로 다른 카드 게임을 플레이하고 있는지를 추적하는 프로그램입니다.  
  
 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 프로젝트와 솔루션으로 작업을 구성합니다.  솔루션에는 DLL 및 이 DLL을 참조하는 실행 파일과 같은 둘 이상의 프로젝트가 포함될 수 있습니다.  자세한 내용은 [솔루션 및 프로젝트](../Topic/Solutions%20and%20Projects%20in%20Visual%20Studio.md)을 참조하십시오.  
  
## 사전 요구 사항  
  
-   이 연습을 완료하려면 C\+\+ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
## 프로젝트 만들기  
 프로젝트를 만들려면 먼저 프로젝트 형식 템플릿을 선택합니다.  각 프로젝트 형식에 대해 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 컴파일러 설정을 지정하고 형식에 따라 시작 코드를 생성합니다. 이 시작 코드는 나중에 수정할 수 있습니다.  
  
#### 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자의 왼쪽 창에서 **설치된 템플릿** 노드, **Visual C\+\+** 노드를 차례로 확장한 다음 **Win32**를 선택합니다.  
  
3.  가운데 창의 설치된 템플릿 목록에서 **Win32 콘솔 응용 프로그램**을 선택합니다.  
  
4.  **이름** 상자에 프로젝트의 이름을 입력합니다.  이 예에서는 Game을 입력합니다.  
  
     **위치** 드롭다운 목록에서 기본 위치를 적용하거나 다른 위치를 입력하거나 **찾아보기** 단추를 선택하여 프로젝트를 저장할 디렉터리를 찾아볼 수 있습니다.  
  
     프로젝트를 만들면 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서 해당 프로젝트가 솔루션에 추가됩니다.  기본적으로 솔루션의 이름은 프로젝트 이름과 같습니다.  **솔루션 이름** 상자에서 이름을 변경할 수 있지만 이 예제에서는 기본 이름을 유지합니다.  
  
     **확인** 단추를 선택하여 **Win32 응용 프로그램 마법사**를 시작합니다.  
  
5.  **Win32 응용 프로그램 마법사**의 **개요** 페이지에서 **다음** 단추를 선택합니다.  
  
6.  **응용 프로그램 설정** 페이지의 **응용 프로그램 종류** 아래에서 **콘솔 응용 프로그램**을 선택합니다.  **추가 옵션**에서 **미리 컴파일된 헤더** 설정을 선택 취소한 다음 **빈 프로젝트** 설정을 선택합니다.  **마침** 단추를 선택하여 프로젝트를 만듭니다.  
  
     이제 소스 코드 파일이 없는 프로젝트가 준비되었습니다.  
  
## 솔루션에서 프로젝트 및 파일 구성  
 **솔루션 탐색기**를 사용하여 솔루션에서 프로젝트, 파일 및 기타 리소스를 구성하고 관리할 수 있습니다.  
  
 이 연습 부분에서는 프로젝트에 클래스를 추가하는 방법을 보여 줍니다.  클래스를 추가하면 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서 해당 .h 및 .cpp 파일을 추가합니다.  이제 클래스를 테스트할 주 프로그램의 새 소스 코드 파일을 추가합니다.  
  
#### 프로젝트에 클래스를 추가하려면  
  
1.  **솔루션 탐색기**가 표시되지 않으면 메뉴 모음에서 **보기**, **솔루션 탐색기**를 선택합니다.  
  
2.  **솔루션 탐색기**에서 **헤더 파일** 폴더의 바로 가기 메뉴를 열고 **추가**, **클래스**를 선택합니다.  
  
     **클래스 추가** 대화 상자의 왼쪽 창에서 **Visual C\+\+** 노드를 확장하고 **C\+\+**를 선택한 다음 가운데 창의 설치된 템플릿 목록에서 **C\+\+ 클래스**를 선택합니다.  **추가** 단추를 선택합니다.  
  
3.  **일반 C\+\+ 클래스 마법사**에서 **클래스 이름** 상자에 Cardgame을 입력합니다.  기본 파일 이름과 설정을 수정하지 마십시오.  **마침** 단추를 선택합니다.  
  
4.  Cardgame.h 파일이 편집기에서 열립니다.  다음과 같이 변경합니다.  
  
    -   클래스 정의의 여는 중괄호 뒤에 두 개의 전용 데이터 멤버를 추가합니다.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#100](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_1.h)]  
  
    -   Visual Studio에서 생성된 기본 생성자를 수정합니다.  `public:` 액세스 지정자 뒤에서 다음과 같은 줄을 찾습니다.  
  
         `Cardgame(void);`  
  
         이름이 players인 `int` 형식 매개 변수를 하나 사용하도록 수정합니다.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#101](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_2.h)]  
  
    -   기본 소멸자 뒤에 매개 변수를 사용하지 않고 totalParticipants 값을 반환하는 GetParticipants 정적 상수 멤버 함수에 대한 인라인 선언을 추가합니다.  
  
         [!code-cpp[NVC_Walkthrough_Working_With_Projects#102](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_3.h)]  
  
5.  변경한 후 Cardgame.h 파일은 다음과 유사합니다.  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#103](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_4.h)]  
  
     `#pragma once` 줄은 컴파일러에 파일을 한 번만 포함하도록 지시합니다.  자세한 내용은 [once](../preprocessor/once.md)을 참조하십시오.  
  
     이 헤더 파일에 포함된 다른 C\+\+ 키워드에 대한 자세한 내용은 [class](../cpp/class-cpp.md), [int](../cpp/fundamental-types-cpp.md), [static](../misc/static-cpp.md) 및 [public](../cpp/public-cpp.md)을 참조하십시오.  
  
6.  편집 창에서 **Cardgame.cpp** 탭을 선택하여 편집할 수 있도록 엽니다.  
  
7.  파일에 있는 모든 항목을 삭제하고 다음 코드로 바꿉니다.  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#111](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_5.cpp)]  
  
    > [!NOTE]
    >  코드를 입력할 때 자동 완성 기능을 사용할 수 있습니다.  예를 들어, 이 코드를 입력할 경우 pl 또는 tot를 입력한 다음 Ctrl\+스페이스바를 누르면 자동 완성 기능이 `players` 또는 `totalParticipants`를 자동으로 입력합니다.  
  
     `#include`에 대한 자세한 내용은 [\#include 지시문](../preprocessor/hash-include-directive-c-cpp.md)을 참조하십시오.  
  
## 소스 파일 추가  
 이제 클래스를 테스트할 주 프로그램의 소스 코드 파일을 추가합니다.  
  
#### 새 소스 파일을 추가하려면  
  
1.  **솔루션 탐색기**에서 **소스 파일** 폴더의 바로 가기 메뉴를 열고 **추가**, **새 항목**을 선택합니다.  
  
     **새 항목 추가** 대화 상자의 왼쪽 창에서 **설치됨** 노드, **Visual C\+\+** 노드를 차례로 확장한 다음 **코드**를 선택합니다.  가운데 창에서 **C\+\+ 파일 \(.cpp\)**을 선택합니다.  
  
2.  **이름** 상자에 TestGames.cpp를 입력한 다음 **추가** 단추를 선택합니다.  
  
3.  TestGames.cpp 편집 창에서 다음 코드를 입력합니다.  
  
     [!code-cpp[NVC_Walkthrough_Working_With_Projects#120](../ide/codesnippet/CPP/walkthrough-working-with-projects-and-solutions-cpp_6.cpp)]  
  
## 프로젝트 빌드 및 실행  
 이제 프로젝트를 빌드하고 응용 프로그램을 실행합니다.  
  
#### 프로젝트를 빌드하여 실행하려면  
  
1.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
    > [!NOTE]
    >  **빌드** 메뉴가 표시되지 않는 Express Edition을 사용하는 경우 메뉴 모음에서 **도구**, **설정**, **전문가 설정**을 선택하여 사용하도록 설정합니다.  
  
     빌드의 출력이 **출력** 창에 표시됩니다.  빌드가 성공한 경우 출력은 다음과 같습니다.  
  
  **1\>\-\-\-\-\-\- 빌드 시작: 프로젝트: Game, 구성: Debug Win32 \-\-\-\-\-\-**  
**1\>  TestGames.cpp**  
**1\>  Cardgame.cpp**  
**1\>  코드를 생성하고 있습니다.**  
**1\>  Game.vcxproj \-\> c:\\users\\username\\documents\\visual studio\\Projects\\Game\\Debug\\Game.exe**  
**\=\=\=\=\=\=\=\=\=\= 빌드: 성공 1, 실패 0, 최신 0, 생략 0 \=\=\=\=\=\=\=\=\=\=**     버전과 빌드 구성에 따라 **출력** 창에 다른 단계가 표시될 수 있지만, 프로젝트 빌드가 성공한 경우 마지막 줄은 표시된 출력과 비슷합니다.  
  
     빌드가 실패한 경우 코드를 이전 단계에서 제공된 코드와 비교하십시오.  
  
2.  프로젝트를 실행하려면 메뉴 모음에서 **디버그**, **디버깅하지 않고 시작**을 선택합니다.  다음과 같은 결과가 출력됩니다.  
  
  **4명의 플레이어가 새 게임을 시작했습니다.  이제 플레이어 수는 총 4명입니다.**  
**8명의 플레이어가 새 게임을 시작했습니다.  이제 플레이어 수는 총 12명입니다.**  
**1명의 플레이어가 새 게임을 시작했습니다.  이제 플레이어 수는 총 13명입니다.**  
**5명의 플레이어가 새 게임을 시작했습니다.  이제 플레이어 수는 총 18명입니다.**  
  
## 다음 단계  
 **이전:** [C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md) **다음:** [연습: 프로젝트 빌드\(C\+\+\)](../ide/walkthrough-building-a-project-cpp.md)  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)