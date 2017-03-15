---
title: "연습: 프로젝트 디버깅(C++) | Microsoft Docs"
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
  - "프로젝트 디버깅"
  - "프로젝트 디버깅[C++]"
  - "프로젝트[C++], 디버깅"
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 프로젝트 디버깅(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 단계에서는 프로그램을 수정하여 프로젝트를 테스트할 때 발견된 문제를 해결합니다.  
  
## 사전 요구 사항  
  
-   이 연습에서는 사용자가 C\+\+ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   사용자가 [C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)에 기재된 초기 관련된 연습을 완수했다는 것을 또한 의미합니다.  
  
### 버그가 있는 프로그램을 수정하려면  
  
1.  `Cardgame` 개체가 소멸될 때 발생하는 동작을 확인하려면 `Cardgame` 클래스의 소멸자를 확인합니다.  
  
     메뉴 모음에서 **보기**, **클래스 보기**를 선택합니다.  
  
     **클래스 뷰** 창에서, **게임** 프로젝트 트리 확장하고 **Cardgame** 클래스를 선택하면 클래스 멤버와 메서드가 표시됩니다.  
  
     해당 **~Cardgame\(void\)** 소멸자에 대한 바로 가기 메뉴를 열고 **정의로 이동**을 선택합니다.  
  
2.  카드 게임이 끝날 때 `totalParticipants` 수가 줄어들도록 하려면 `Cardgame::~Cardgame` 소멸자의 여는 중괄호와 닫는 중괄호 사이에 다음 코드를 추가합니다.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  변경한 후 Cardgame.cpp 파일은 다음과 유사합니다.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
5.  빌드가 완료 되면 메뉴 바에서 **디버깅**, **디버깅 시작**, 또는 F5키를 선택하여 디버그 모드에서 실행합니다.  첫 번째 중단점에서 프로그램 실행이 일시 중지됩니다.  
  
6.  선택 메뉴 모음에서 프로그램을 단계적 실행을 위해, **디버그**, **프로시저 단위 실행**, F10 키를 선택합니다.  
  
     각 Cardgame 생성자가 실행된 후에는 `totalParticipants` 의 값이 증가합니다.  `PlayGames` 함수가 반환될 때, 각 Cardgame 인스턴스마다 범위를 벗어나서 삭제되고 \(소멸자가 호출됨\), `totalParticipants` 이 감소합니다.  `return` 문이 실행되기 바로 전에 `totalParticipants` 는 0입니다.  
  
7.  종료 될 때까지 프로그램을 통해 단계별로 계속하거나 메뉴 바에서 **디버그**, **실행**, 또는 F5키를 선택하여 실행 되도록 합니다.  
  
## 다음 단계  
 **이전:** [연습: 프로젝트 테스트\(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md) &#124; **다음:** [연습: 프로그램 배포\(C\+\+\)](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/ko-kr/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)