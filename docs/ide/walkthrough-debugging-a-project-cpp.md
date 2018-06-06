---
title: '연습: 프로젝트 디버깅(C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- projects [C++], debugging
- project debugging [C++]
- debugging projects
ms.assetid: a5cade77-ba51-4b03-a7a0-6897e3cd6a59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ecfda5e2549b3aa9be1f0471e301cc2a21c6fd5a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340036"
---
# <a name="walkthrough-debugging-a-project-c"></a>연습: 프로젝트 디버깅(C++)
이 연습에서는 프로젝트를 테스트할 때 발견한 문제를 해결하려면 프로그램을 수정합니다.  
  
## <a name="prerequisites"></a>전제 조건  
  
-   이 연습에서는 사용자가 C++ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   또한 [C++ 데스크톱 개발에 Visual Studio IDE 사용](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)에 나열된 이전 관련 연습을 완료했다고 가정합니다.  
  
### <a name="to-fix-a-program-that-has-a-bug"></a>버그가 있는 프로그램을 수정하려면  
  
1.  `Cardgame` 개체가 제거될 때 발생하는 상황을 보려면 `Cardgame` 클래스에 대한 소멸자를 봅니다.  
  
     메뉴 모음에서 **보기**, **클래스 뷰**를 차례로 선택합니다.  
  
     **클래스 뷰** 창에서 **게임** 프로젝트 트리를 확장하고 **Cardgame** 클래스를 선택하여 클래스 멤버와 메서드를 표시합니다.  
  
     **~Cardgame(void)** 에 대한 바로 가기 메뉴를 연 다음, **정의로 이동**을 선택합니다.  
  
2.  Cardgame이 종료될 때 `totalParticipants`을 감소하려면 `Cardgame::~Cardgame` 소멸자의 여는 중괄호와 닫는 중괄호 사이에 다음 코드를 추가합니다.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#110](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_1.cpp)]  
  
3.  변경한 후 Cardgame.cpp 파일은 다음과 유사합니다.  
  
     [!code-cpp[NVC_Walkthrough_Debugging_A_Project#111](../ide/codesnippet/CPP/walkthrough-debugging-a-project-cpp_2.cpp)]  
  
4.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
5.  빌드가 완료되면 메뉴 모음에서 **디버그** 및 **디버깅 시작**을 선택하거나 F5 키를 선택하여 디버그 모드에서 실행합니다. 프로그램은 첫 번째 중단점에서 일시 중지됩니다.  
  
6.  프로그램을 단계별로 실행하려면 메뉴 모음에서 **디버그**, **프로시저 단위 실행**을 선택하거나 F10 키를 선택합니다.  
  
     각 Cardgame 생성자가 실행된 후 `totalParticipants`의 값이 증가합니다. 각 Cardgame 인스턴스가 범위를 벗어나고 삭제될 때(소멸자가 호출될 때) `PlayGames` 기능이 반환되는 경우 `totalParticipants`가 감소합니다. `return` 문이 실행되기 바로 전에 `totalParticipants`는 0과 같습니다.  
  
7.  메뉴 모음에서 **디버그**, **실행**을 선택하거나 F5 키를 선택하여 종료될 때까지 프로그램을 단계별로 실행을 계속하거나 실행되게 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 **이전:** [연습: 프로젝트(C++) 테스트](../ide/walkthrough-testing-a-project-cpp.md) &#124; **다음:**[연습: 프로그램(C++) 배포](../ide/walkthrough-deploying-your-program-cpp.md)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)