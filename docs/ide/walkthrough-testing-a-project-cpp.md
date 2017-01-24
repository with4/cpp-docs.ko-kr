---
title: "연습: 프로젝트 테스트(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "프로젝트 테스트[C++]"
  - "프로젝트[C++], 테스트"
  - "프로젝트 테스트"
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 프로젝트 테스트(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

디버그 모드에서 프로그램을 실행하면 중단점을 사용하여 프로그램을 일시 중지하고 변수나 개체의 상태를 검사할 수 있습니다.  
  
 이 연습에서는 프로그램이 실행될 때 변수의 값을 조사하고 그 값이 예상과 다른 이유를 추론합니다.  
  
## 사전 요구 사항  
  
-   이 연습에서는 사용자가 C\+\+ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   사용자가 [C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)에 기재된 초기 관련된 연습을 완수했다는 것을 또한 의미합니다.  
  
### 디버그 모드에서 프로그램을 실행하려면  
  
1.  편집할 TestGames.cpp를 엽니다.  
  
2.  이 코드 줄을 선택합니다.  
  
     `Cardgame.solitaire(1);`  
  
3.  이 줄에 중단점을 설정하려면 메뉴 모음에서 **디버그**, **중단점 설정\/해제**를 선택하거나 F9 키를 선택합니다.  줄 왼쪽에 중단점이 설정되었음을 나타내는 빨간색 원이 나타납니다.  중단점을 제거하려면 메뉴 명령 또는 F9 키를 다시 선택합니다.  
  
     마우스를 사용하는 경우 왼쪽 여백을 클릭해서 중단점을 설정하거나 제거할 수도 있습니다.  
  
4.  메뉴 모음에서 **디버그**, **디버깅 시작**을 선택하거나 F5 키를 선택합니다.  
  
     중단점이 설정된 줄에 도달하면 현재 프로그램의 모드가 중단 모드이므로 프로그램의 실행이 일시 중지됩니다.  코드 줄의 왼쪽에 표시되는 노란색 화살표는 실행할 다음 줄을 나타냅니다.  
  
5.  `Cardgame::totalParticipants` 변수 값을 조사하려면 포인터를 `Cardgame` 위로 이동한 후 도구 설명 창 왼쪽에 있는 확장 컨트롤 위로 이동합니다.  변수 이름 `totalParticipants` 및 해당 값 12가 표시됩니다.  
  
     `Cardgame::totalParticipants` 변수를 얻기 위해 바로 가기 메뉴를 열고 난 다음 **조사식 추가** 를 선택하여 **조사식 1** 의 변수를 표시합니다.  변수를 선택하여 **조사식 1** 창에 끌어 놓을 수도 있습니다.  
  
6.  코드의 다음 줄로 진행하려면 메뉴 모음에서 **디버그**, **프로시저 단위 실행**을 선택하거나 F10 키를 선택합니다.  
  
     **조사식 1** 창의 `Cardgame::totalParticipants` 값이 이제 13으로 표시됩니다.  
  
7.  `return 0;` 문에 대한 바로 가기 메뉴를 열고 **커서까지 실행**을 선택합니다.  코드 왼쪽의 노란색 화살표는 실행할 다음 문을 나타냅니다.  
  
8.  Cardgame가 종료하면 `Cardgame::totalParticipants` 숫자가 감소합니다.  여기서 모든 Cardgame 인스턴스가 삭제되었으므로 `Cardgame::totalParticipants`가 0이어야 하지만 **조사식 1** 창은 `Cardgame::totalparticipants`가 18임을 나타냅니다.  다음 연습, [연습: 프로젝트 디버깅\(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)을 완료해서 검색 및 수정할 수 있는 버그가 코드에 있음을 나타냅니다.  
  
9. 프로그램을 중지하려면 메뉴 모음에서 **디버그**, **디버깅 중지** 또는 Shift\+F5 바로 가기 키를 선택합니다.  
  
## 다음 단계  
 **이전:** [연습: 프로젝트 빌드\(C\+\+\)](../ide/walkthrough-building-a-project-cpp.md) &#124; **다음:** [연습: 프로젝트 디버깅\(C\+\+\)](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/ko-kr/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)