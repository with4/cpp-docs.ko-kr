---
title: '연습: 테스트 프로젝트 (c + +) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- project testing [C++]
- testing projects
- projects [C++], testing
ms.assetid: 88cdd377-c5c8-4201-889d-32f5653ebead
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a9455fa9bf3c9f903f5018a1263978913aa35b2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-testing-a-project-c"></a>연습: 프로젝트 테스트(C++)
디버그 모드에서 프로그램을 실행 하는 경우에 변수 및 개체의 상태를 검사 하는 프로그램을 일시 중지 중단점을 사용할 수 있습니다.  
  
 이 연습에서는 프로그램이 실행 될 때 변수 값을 확인 하 고 다른 값이 기대 하는 이유를 추론 합니다.  
  
## <a name="prerequisites"></a>전제 조건  
  
-   이 연습에서는 사용자가 C++ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
-   또한 이전 관련된 연습에 나와 있는 완료 한 것으로 가정 [c + + 데스크톱 개발을 위한 Visual Studio IDE를 사용 하 여](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md)합니다.  
  
### <a name="to-run-a-program-in-debug-mode"></a>디버그 모드에서 프로그램을 실행 하려면  
  
1.  TestGames.cpp 편집 하기 위해 엽니다.  
  
2.  이 코드 줄을 선택 합니다.  
  
     `Cardgame.solitaire(1);`  
  
3.  메뉴 모음에서 해당 줄에 중단점을 설정 하려면 선택 **디버그**, **중단점 설정/해제**, 하거나 F9 키를 선택 합니다. 줄의 왼쪽에 빨간색 원이 나타납니다. 중단점 설정 되어 있는지 나타냅니다. 중단점을 제거 하려면 있습니다 수 메뉴 명령이 나 F9 키 다시 선택 합니다.  
  
     마우스를 사용 하는 경우 또한 설정 하거나 왼쪽된 여백을 클릭 하 여 중단점을 제거할 수 있습니다.  
  
4.  메뉴 모음에서 **디버그**, **디버깅 시작**, 하거나 F5 키를 선택 합니다.  
  
     프로그램 중단점을 한 줄에 도달 하면 프로그램이 중단 모드 이기 때문에 실행이 일시적으로 중지 합니다. 코드 줄의 왼쪽에 노란색 화살표는 실행 될 다음 줄 임을 나타냅니다.  
  
5.  값을 검사 하는 `Cardgame::totalParticipants` 변수 위로 포인터를 이동 `Cardgame` 다음 도구 설명 창의 왼쪽에 확장 컨트롤 위로 이동 합니다. 변수 이름 `totalParticipants` 12의 해당 값이 표시 됩니다.  
  
     에 대 한 바로 가기 메뉴를 열고는 `Cardgame::totalParticipants` 변수를 선택한 후 **조사식 추가** 에서 해당 변수를 표시 하는 **조사식 1** 창. 또한 변수를 선택 하 고 끌어 수는 **조사식 1** 창.  
  
6.  메뉴 모음에서 코드의 다음 줄으로 선택 **디버그**, **프로시저 단위 실행**, 하거나 F10 키를 선택 합니다.  
  
     값 `Cardgame::totalParticipants` 에 **조사식 1** 창이 이제 13으로 표시 됩니다.  
  
7.  에 대 한 바로 가기 메뉴를 열고는 `return 0;` 문을 선택한 후 **커서까지 실행**합니다. 코드의 왼쪽에 노란색 화살표는 다음 문을 실행 하도록를 가리킵니다.  
  
8.  `Cardgame::totalParticipants` 번호는 Cardgame 종료 될 때 감소 해야 합니다. 이 시점에서 `Cardgame::totalParticipants` 모든 Cardgame 인스턴스가 삭제 되었으므로, 0과 같아야 하지만 **조사식 1** 창 나타냅니다 `Cardgame::totalparticipants` 18 같음. 이 수를 검색 하 고 다음 연습을 완료 하 여 해결 되는 코드의 버그 된다는 의미 [연습: 프로젝트 (c + +) 디버깅](../ide/walkthrough-debugging-a-project-cpp.md)합니다.  
  
9. 메뉴 모음에서 프로그램을 중지 하려면 선택 **디버그**, **디버깅 중지**, 하거나 Shift + F5 바로 가기 키를 선택 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 **이전:** [연습: 프로젝트 (c + +) 빌드](../ide/walkthrough-building-a-project-cpp.md) &#124; **다음:**[연습: 프로젝트 (c + +) 디버깅](../ide/walkthrough-debugging-a-project-cpp.md)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)