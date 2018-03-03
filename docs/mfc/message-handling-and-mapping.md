---
title: "메시지 처리 및 매핑 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6c13ed0bb19ef1ed2864378e151c6be8d98887
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="message-handling-and-mapping"></a>메시지 처리 및 매핑
이 문서에서는 MFC 프레임 워크에 의해 메시지 및 명령 처리 되는 방법 및 연결을 하는 방법은 해당 처리기 함수를 설명 합니다.  
  
 Windows에 대 한 기존 프로그램에서 Windows 메시지 창 프로시저에서 큰 switch 문에서 처리 됩니다. MFC 대신 사용 하 여 [메시지 맵](../mfc/message-categories.md) 별도 클래스 멤버 함수에 직접 메시지를 매핑할 수 있습니다. 메시지 맵은이 위해 가상 함수를 보다 효율적이 고 가장 적합 한 c + + 개체에서 처리할 메시지를 허용-응용 프로그램, 문서, 뷰 및 등입니다. 컨트롤 Id 또는 단일 메시지 또는 메시지를 명령 Id의 범위를 매핑할 수 있습니다.  
  
 **WM_COMMAND** 메시지-일반적으로 메뉴, 도구 모음 단추 또는 액셀러레이터 키에 의해 생성-또한 메시지 맵 메커니즘을 사용 합니다. MFC는 표준을 정의 [라우팅](../mfc/command-routing.md) 응용 프로그램 간의 메시지 명령, 창, 뷰 및 프로그램의 액티브 문서를 작성 합니다. 이 라우팅은 해야 할 경우 재정의할 수 있습니다.  
  
 메시지 맵 사용자 인터페이스 개체 (예: 메뉴 및 도구 모음 단추)를 업데이트 하는 방법을 지정에 따라 현재 컨텍스트를 사용 하지 않도록 설정 하거나 설정 합니다.  
  
 메시지와 Windows의 메시지 큐에 대 한 일반 정보를 참조 하십시오. [메시지와 메시지 큐](http://msdn.microsoft.com/library/windows/desktop/ms632590) Windows sdk에서입니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [프레임 워크는 메시지 처리기를 호출 하는 방법](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [프레임워크가 메시지 맵을 검색하는 방법](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)  
  
-   [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [상태 표시줄에 명령 정보를 표시 하는 방법](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [사용자 인터페이스 개체의 동적 업데이트](../mfc/how-to-update-user-interface-objects.md)  
  
-   [방법: 템플릿 클래스에 대한 메시지 맵 만들기](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## <a name="see-also"></a>참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)   
 [CWnd 클래스](../mfc/reference/cwnd-class.md)   
 [CCmdTarget 클래스](../mfc/reference/ccmdtarget-class.md)
