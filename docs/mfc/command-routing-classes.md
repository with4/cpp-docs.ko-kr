---
title: "명령 라우팅 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.command
dev_langs: C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], classes
ms.assetid: 4b50e689-2c54-4e6c-90f0-37333e22b2a1
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c7e49c92b909abb01f3daec9e16f0e08b2a31c89
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="command-routing-classes"></a>명령 라우팅 클래스
메뉴 또는 마우스 단추 컨트롤 막대를 선택 하 여 사용자 응용 프로그램과 상호 작용 하는 응용 프로그램 메시지 적절 한 명령 대상 개체에 영향을 받는 사용자 인터페이스 개체에서 보냅니다. 명령 대상 클래스에서 파생 된 `CCmdTarget` 포함 [CWinApp](../mfc/reference/cwinapp-class.md), [CWnd](../mfc/reference/cwnd-class.md), [CDocTemplate](../mfc/reference/cdoctemplate-class.md), [CDocument](../mfc/reference/cdocument-class.md), [CView](../mfc/reference/cview-class.md)와 여기서 파생 된 클래스입니다. 프레임 워크 자동 명령 라우팅 명령을 응용 프로그램에서 현재 활성 상태인 가장 적합 한 개체에 의해 처리 될 수 있도록 지원 합니다.  
  
 클래스의 개체 `CCmdUI` 명령 대상 update 명령을 UI에 전달 됩니다 ([ON_UPDATE_COMMAND_UI](reference/message-map-macros-mfc.md#on_update_command_ui)) 사용자가 특정 명령에 대 한 사용자 인터페이스의 상태를 업데이트할 수 있도록 하는 처리기 (예를 들어,를 확인 또는 제거 체크 메뉴 항목에서)입니다. 멤버의 함수를 호출할는 `CCmdUI` UI 개체의 상태를 업데이트 하는 개체입니다. 특정 명령와 관련 된 UI 개체는 메뉴 항목 또는 단추 중 하나 또는 둘 다이 프로세스는 동일 합니다.  
  
 [CCmdTarget](../mfc/reference/ccmdtarget-class.md)  
 수신 하 고 메시지에 응답할 수 있는 개체의 모든 클래스에 대 한 기본 클래스로 사용 됩니다.  
  
 [CCmdUI](../mfc/reference/ccmdui-class.md)  
 메뉴 항목이 나 컨트롤 막대 단추와 같은 사용자 인터페이스 개체 업데이트에 대 한 프로그래밍 인터페이스를 제공 합니다. 명령 대상 개체 수, 사용 하지 않도록 설정, 검사, 및/또는이 개체와 사용자 인터페이스 개체를 지웁니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

