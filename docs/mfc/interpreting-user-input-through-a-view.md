---
title: 뷰를 통해 사용자 입력 해석 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interpreting user input through views [MFC]
- views [MFC], user interface and input
- input [MFC], view class [MFC]
- CView class [MFC], interpreting user input
- user input [MFC], interpreting through view class [MFC]
ms.assetid: f0302a70-661f-4781-8fe7-78f082bef2a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e3ade658046ad789a92bce044d12e5a6e76f7ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349431"
---
# <a name="interpreting-user-input-through-a-view"></a>뷰를 통해 사용자 입력 해석
보기의 다른 멤버 함수를 처리 하 고 모든 사용자 입력 해석 합니다. 일반적으로 처리할 뷰 클래스에 메시지 처리기 멤버 함수를 정의 합니다.  
  
-   Windows [메시지](../mfc/messages.md) 마우스 및 키보드 작업에 의해 생성 됩니다.  
  
-   [명령](../mfc/user-interface-objects-and-command-ids.md) 에서 메뉴, 도구 모음 단추 및 액셀러레이터 키입니다.  
  
 이러한 메시지 처리기 멤버 함수는 다음 작업으로 해석 데이터 입력, 선택, 편집 또는 클립보드의 데이터를 이동 하는 포함 하 여:  
  
-   마우스를 이동, 클릭, 끌기 및가 두 번 클릭  
  
-   키 입력  
  
-   메뉴 명령  
  
 Windows 메시지는 뷰에서 처리 응용 프로그램의 필요에 따라 달라 집니다.  
  
 [메시지 처리 및 매핑 항목](../mfc/message-handling-and-mapping.md) 명령에 메뉴 항목 및 기타 사용자 인터페이스 개체를 할당 하는 방법 및 명령 처리기 함수에 바인딩하는 방법을 설명 합니다. [메시지 처리 및 매핑 항목](../mfc/message-handling-and-mapping.md) 도 MFC 명령이 라우팅하 하는 방법에 대해 설명 하 고 표준 Windows 메시지에 대 한 처리기를 포함 하는 개체를 보냅니다.  
  
 예를 들어 응용 프로그램은 직접 마우스 뷰에 그리기를 구현 해야 할 수 있습니다. Scribble 샘플에서는 처리 하는 방법을 보여 줍니다.는 `WM_LBUTTONDOWN`, `WM_MOUSEMOVE`, 및 `WM_LBUTTONUP` 를 시작 하려면 각각 메시지, 계속 하 고 선 세그먼트의 그리기를 종료 합니다. 반면에 선택 항목으로 보기에서 마우스 클릭을 해석 하 경우에 따라 할 수 있습니다. 보기의 `OnLButtonDown` 처리기 함수는 사용자 그리기 또는 선택 되었는지 확인할 것입니다. 을 선택한 경우 처리기 보기에서 일부 개체의 범위 내에서 클릭 했는지 확인 고 게,이 경우 선택 된 것으로 개체를 표시 하도록 디스플레이가 변경 됩니다.  
  
 보기 잘라내기, 복사, 붙여넣기 또는 클립보드를 사용 하 여 선택한 데이터를 삭제 하 고 편집 메뉴에서 같은 특정 메뉴 명령을 처리할 수도 있습니다. 이러한 처리기는 함수를 호출할 클립보드 관련 멤버의 일부 클래스의 `CWnd` 또는 클립보드에 선택한 데이터 항목을 전송할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [뷰 사용](../mfc/using-views.md)

