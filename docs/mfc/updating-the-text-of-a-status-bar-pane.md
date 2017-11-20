---
title: "상태 표시줄 창의 텍스트 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- ON_UPDATE_COMMAND_UI macro [MFC]
- user interface objects [MFC], updating
- text, status bar
- CStatusBar class [MFC], updating
- SetText method [MFC]
- panes, status bar
- status bars [MFC], updating
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e447b6b8d4895bf0103995742fe0b2a5c8d62484
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="updating-the-text-of-a-status-bar-pane"></a>상태 표시줄 창의 텍스트 업데이트
이 문서에서는 MFC 상태 표시줄 창에 표시 되는 텍스트를 변경 하는 방법에 설명 합니다. 상태 표시줄-window 개체 클래스의 [CStatusBar](../mfc/reference/cstatusbar-class.md) -여러 개의 "창이 있습니다."를 포함 합니다. 각 창에 정보를 표시 하는 데 사용할 수 있는 상태 표시줄의 사각형 영역입니다. 예를 들어 많은 응용 프로그램 맨 오른쪽 창에 CAPS LOCK, NUM LOCK 및 다른 키의 상태를 표시 합니다. 응용 프로그램 에서도 대개 유용한 정보가 표시 (0 창)에서 가장 왼쪽 창에서 "메시지 창입니다." 라고도 함 예를 들어 기본 MFC 상태 표시줄 메시지 창을 사용 하 여 현재 선택 된 메뉴 항목이 나 도구 모음 단추를 설명 하는 문자열을 표시 합니다. 이 그림에서 [상태 표시줄](../mfc/status-bar-implementation-in-mfc.md) MFC 응용 프로그램 마법사로 만든 응용 프로그램에서 상태 표시줄을 표시 합니다.  
  
 기본적으로 MFC 허용 하지 않습니다는 `CStatusBar` 창 고 창을 만들 때. 사용 해야 창을 활성화 하려면는 `ON_UPDATE_COMMAND_UI` 매크로 상태는 각 창에 대 한 가로 막대형 차트 및 창을 업데이트 합니다. 창 보내지 않는 **WM_COMMAND** 메시지 (그렇지 않으면 도구 모음 단추 처럼), 코드를 수동으로 입력 해야 합니다.  
  
 예를 들어, 하나의 창에는 `ID_INDICATOR_PAGE` 명령 식별자로 문서에서 현재 페이지 번호를 포함 합니다. 다음 절차에는 상태 표시줄에서 새 창을 만드는 방법을 설명 합니다.  
  
### <a name="to-make-a-new-pane"></a>새 창을 표시 하려면  
  
1.  정의 창의 명령 id입니다.  
  
     에 **보기** 메뉴를 클릭 하 여 **리소스 뷰**합니다. 프로젝트 리소스를 마우스 오른쪽 단추로 클릭 하 고 클릭 **리소스 기호**합니다. 리소스 기호 대화 상자에서 클릭 `New`합니다. 명령 ID 이름 입력: 예를 들어 `ID_INDICATOR_PAGE`합니다. 리소스 기호 대화 상자에 제안 된 값을 적용 하거나, id 값을 지정 합니다. 예: `ID_INDICATOR_PAGE`를 기본값 그대로 사용 합니다. 리소스 기호 대화 상자를 닫습니다.  
  
2.  창에 표시할 기본 문자열을 정의 합니다.  
  
     리소스 뷰 열기를 두 번 클릭 **문자열 테이블** 응용 프로그램에 대 한 리소스 종류를 나열 하는 창에 있습니다. 와 **문자열 테이블** 편집기 열기 선택 **새 문자열** 에서 **삽입** 메뉴. 문자열 속성 창에서 창의 명령 ID를 선택 합니다 (예를 들어 `ID_INDICATOR_PAGE`) "페이지"와 같은 기본 문자열 값을 입력 하 고 있습니다. 문자열 편집기를 닫습니다. (컴파일러 오류를 방지 하려면 기본 문자열 필요 합니다.)  
  
3.  창에 추가 된 **표시기** 배열입니다.  
  
     에 해당 합니다. CPP를 찾습니다는 **표시기** 배열입니다. 이 배열의 모든 왼쪽에서 오른쪽 순서로 상태 표시줄의 표시기에 대 한 명령 Id를 나열합니다. 배열에서 해당 시점에서 창의 명령 ID에 대 한 여기 표시 된 대로 입력 `ID_INDICATOR_PAGE`:  
  
     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_1.cpp)]  
  
 창에 텍스트를 표시 하는 권장된 방법은 호출 하는 것은 **SetText** 클래스의 멤버 함수 `CCmdUI` 창에 대 한 업데이트 처리기 함수에 있습니다. 예를 들어 정수 변수를 설정 하려면 수 `m_nPage` 현재 페이지 번호와 사용 하 여 포함 된 **SetText** 창의 텍스트를 해당 숫자의 문자열 버전을 설정 하 합니다.  
  
> [!NOTE]
>  **SetText** 방법은 것이 좋습니다. 호출 하 여 약간 더 낮은 수준에서이 작업을 수행할 수는 `CStatusBar` 멤버 함수 `SetPaneText`합니다. 그렇더라도 업데이트 처리기 여전히 필요합니다. 업데이트 처리기가 없는 창에 대, MFC를 자동으로 비활성화 창에서 내용을 지우고 합니다.  
  
 다음 절차에는 창에 텍스트를 표시 하는 업데이트 처리기 함수를 사용 하는 방법을 보여 줍니다.  
  
#### <a name="to-make-a-pane-display-text"></a>텍스트 표시 창을 표시 하려면  
  
1.  명령에 대 한 명령 업데이트 처리기를 추가 합니다.  
  
     수동으로 처리기에 대 한 프로토타입이 다음과 같이 추가 대 한 `ID_INDICATOR_PAGE` (에 해당 합니다. H):  
  
     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_2.h)]  
  
2.  에 해당 합니다. CPP 파일에서 처리기의 정의 다음과 같이 추가 대 한 `ID_INDICATOR_PAGE` (에 해당 합니다. CPP):  
  
     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_3.cpp)]  
  
     이 처리기의 마지막 세 줄은 텍스트를 표시 하는 코드입니다.  
  
3.  적절 한 메시지 맵에 추가 `ON_UPDATE_COMMAND_UI` 매크로 대 한 다음 그림과 같이 `ID_INDICATOR_PAGE` (에 해당 합니다. CPP):  
  
     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/cpp/updating-the-text-of-a-status-bar-pane_4.cpp)]  
  
 값을 정의 하면는 `m_nPage` 멤버 변수 (클래스의 `CMainFrame`),이 방법을 사용 하면 페이지 번호를 동일한 방식으로 다른 지표는 응용 프로그램을 업데이트 하도록 유휴 처리 하는 동안 창에 표시 합니다. 경우 `m_nPage` 다음 유휴 루프 중 표시 변경 내용입니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [사용자 인터페이스 개체 업데이트 (프로그램 상태가 변경 됨에 따라 도구 모음 단추 및 메뉴 항목을 업데이트 하는 방법)](../mfc/how-to-update-user-interface-objects.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 상태 표시줄 구현](../mfc/status-bar-implementation-in-mfc.md)   
 [CStatusBar 클래스](../mfc/reference/cstatusbar-class.md)
