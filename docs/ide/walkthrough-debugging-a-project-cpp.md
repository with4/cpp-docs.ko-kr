---
title: "연습: 디버깅 프로젝트 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6c9789a7deafacf09ad615f416a446da4eba8150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-debugging-a-project-c"></a>연습: 프로젝트 디버깅(C++)
이 연습에서는 프로젝트를 테스트할 때 발견 된 문제를 해결 하려면 프로그램을 수정 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
  
-   이 연습에서는 사용자가 C++ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   또한 이전 관련된 연습에 나와 있는 완료 한 것으로 가정 [c + + 데스크톱 개발을 위한 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)합니다.  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>버그가 있는 프로그램을 수정 하려면  
  
1.  발생 하는 상황을 보려면 때는 `Cardgame` 개체가 소멸, 보고에 대 한 소멸자는 `Cardgame` 클래스입니다.  
  
     메뉴 모음에서 **보기**, **클래스 뷰**합니다.  
  
     에 **클래스 뷰** 창 확장는 **게임** 프로젝트 트리를 선택은 **Cardgame** 클래스 멤버와 메서드를 표시 하는 클래스입니다.  
  
     에 대 한 바로 가기 메뉴를 열고는 **~Cardgame(void)** 소멸자를 선택한 후 **정의로 이동**합니다.  
  
2.  감소 된 `totalParticipants` 는 Cardgame 종료 되 면 여는 태그와 닫는 중괄호의 사이 다음 코드를 추가 `Cardgame::~Cardgame` 소멸자입니다.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  변경한 후 Cardgame.cpp 파일은 다음과 같습니다.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
5.  빌드가 완료 되 면 디버그 모드에서 선택 하 여 실행할 **디버그**, **디버깅 시작** F5 키를 선택 하거나 메뉴 모음에서 합니다. 프로그램 첫 번째 중단점에서 일시 중지 됩니다.  
  
6.  메뉴 모음에서 프로그램을 통해 선택 **디버그**, **프로시저 단위 실행**, 하거나 F10 키를 선택 합니다.  
  
     각 Cardgame 생성자를 실행 한 후의 값 다음에 유의 `totalParticipants` 증가 합니다. 경우는 `PlayGames` Cardgame 인스턴스마다 범위를 벗어나면 하 고 삭제 됩니다 (소멸자가 호출)를 고 함수가 반환 `totalParticipants` 감소 합니다. 바로 앞의 `return` 문이 실행 될 `totalParticipants` 0입니다.  
  
7.  계속 종료 될 때까지 프로그램을 단계별로 진행 하거나 선택 하 여 실행 되도록 **디버그**, **실행** F5 키를 선택 하거나 메뉴 모음에서 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 **이전:** [연습: 프로젝트 (c + +) 테스트](../ide/walkthrough-testing-a-project-cpp.md) &#124; **다음:**[연습: 프로그램 (c + +) 배포](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>참고 항목  
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)