---
title: "연습: 프로젝트 빌드(C++) | Microsoft Docs"
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
  - "프로젝트 빌드[C++]"
  - "프로젝트[C++], 빌드"
  - "프로젝트 빌드[C++]"
ms.assetid: d459bc03-88ef-48d0-9f9a-82d17f0b6a4d
caps.latest.revision: 14
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 프로젝트 빌드(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 연습에서는 코드에 일부러 Visual C\+\+ 구문 오류를 포함한 다음 어떠한 컴파일 오류가 발생하는지 확인하고 이를 수정하는 방법에 대해 살펴봅니다.  프로젝트를 컴파일하면 어디에 어떠한 문제가 있는지 표시하는 오류 메시지가 나타납니다.  
  
## 사전 요구 사항  
  
-   이 연습에서는 사용자가 C\+\+ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   또한 [C\+\+ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)에 기재된 초기 관련 연습을 수행해야 합니다.  
  
### 컴파일 오류를 수정하려면  
  
1.  TestGames.cpp에서 마지막 줄의 세미콜론을 삭제하여 다음과 같이 만듭니다.  
  
     `return 0`  
  
2.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
3.  **오류 목록** 창의 메시지에 프로젝트 빌드에 오류가 있는 것으로 표시되어 있습니다.  설명을 다음과 같이 나타납니다.  
  
     `error C2143: syntax error : missing ';' before '}'`  
  
     이 오류에 대한 도움말 정보를 보려면 **오류 목록** 창에서 오류를 강조 표시한 후 F1 키를 선택합니다.  
  
4.  구문 오류가 발생한 줄의 끝에 세미콜론을 다시 추가합니다.  
  
     `return 0;`  
  
5.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
     프로젝트가 성공적으로 컴파일되었다는 메시지가 **출력** 창에 표시됩니다.  
  
  **1\>\-\-\-\-\-\- 빌드 시작: 프로젝트: Game, 구성: Debug Win32 \-\-\-\-\-\-**  
**1\>  TestGames.cpp**  
**1\>  Game.vcxproj \-\> C:\\Users\\\<username\>\\Documents\\Visual Studio *\<version\>*\\Projects\\Game\\Debug\\Game.exe**  
**\=\=\=\=\=\=\=\=\=\= 빌드: 성공 1, 실패 0, 최신 0, 생략 0 \=\=\=\=\=\=\=\=\=\=**  
  
## 다음 단계  
 **이전:** [연습: 프로젝트 및 솔루션 작업\(C\+\+\)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md) &#124; **다음:** [연습: 프로젝트 테스트\(C\+\+\)](../ide/walkthrough-testing-a-project-cpp.md)  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [DELETE\_PENDING\_Building and Debugging](http://msdn.microsoft.com/ko-kr/9f6ba537-5ea0-46fb-b6ba-b63d657d84f1)