---
title: "업데이트 처리기가 호출 하는 경우 | Microsoft Docs"
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
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eaf2773a2d9e393c783a39e01c75f8efa62796df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="when-update-handlers-are-called"></a>업데이트 처리기가 호출되는 시점
에서는 오류가 발생 하는 파일 메뉴에서 마우스를 클릭할 경우를 가정해 볼는 `WM_INITMENUPOPUP` 메시지입니다. 사용자가 볼 수 있도록 메뉴가 드롭다운 전에 프레임 워크의 업데이트 메커니즘 전체적으로 파일 메뉴에 있는 모든 항목을 업데이트 합니다.  
  
 이 작업을 수행 하려면 프레임 워크 경로 표준 명령 라우팅 따라 팝업 메뉴의 모든 메뉴 항목에 대 한 명령을 업데이트 합니다. 라우팅에 명령 대상 하는 적절 한 메시지-맵 항목을 사용 하 여 update 명령을 비교 하 여 메뉴 항목을 업데이트할 수 (폼의 `ON_UPDATE_COMMAND_UI`) 및 "업데이트 처리기" 함수를 호출 합니다. 따라서 6 메뉴 항목과 함께 메뉴의 경우 6 개의 업데이트 명령이 전송 됩니다. 업데이트 처리기 메뉴 항목의 명령 ID에 대 한 있으면 업데이트를 수행 하 라고 합니다. 그렇지 않으면 프레임 워크 해당 명령 ID에 대 한 처리기를 있는지 여부를 확인 하 고 사용 하거나 적절 하 게 메뉴 항목을 사용 하지 않도록 설정 합니다.  
  
 프레임 워크를 찾을 수 없는 경우는 `ON_UPDATE_COMMAND_UI` 명령이 라우팅하는 동안 항목을 자동으로 활성화할 사용자 인터페이스 개체가 없는 경우는 `ON_COMMAND` 항목 어딘가에 동일한 명령 id입니다. 그렇지 않으면 사용자 인터페이스 개체를 비활성화합니다. 따라서는 사용자 인터페이스 개체를 사용할 수 있도록 개체 생성 하는 명령에 대 한 처리기를 제공 하거나에 대 한 업데이트 처리기를 제공 합니다. 이 항목의 그림을 참조 [사용자 인터페이스 개체 및 명령 Id](../mfc/user-interface-objects-and-command-ids.md)합니다.  
  
 사용자 인터페이스 개체의 기본 설정이 사용 하지 않도록 설정 하는 것이 불가능 합니다. 자세한 내용은 참조는 [m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable) 클래스의 멤버 `CFrameWnd` 에 *MFC 참조*합니다.  
  
 메뉴 초기화가 발생 하는 응용 프로그램을 수신 하는 경우 프레임 워크에서 자동는 `WM_INITMENUPOPUP` 메시지입니다. 유휴 루프 중 프레임 워크의 명령 라우팅 단추 업데이트 처리기에 대 한 거의 동일한 방법으로 메뉴에 대해서와 마찬가지로 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 사용자 인터페이스 개체 업데이트](../mfc/how-to-update-user-interface-objects.md)

