---
title: 범주 메시지 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 051fe93ef689959b0a0beb2b1b0f213adc942446
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929649"
---
# <a name="message-categories"></a>메시지 범주
어떤 종류의 메시지 처리기를 작성할 세 가지 주요 범주에 대 한:  
  
1.  Windows 메시지  
  
     으로 시작 하는 메시지에 주로 여기에 **WM_** WM_COMMAND 제외 하 고 접두사입니다. Windows 메시지 창과 보기에서 처리 됩니다. 이러한 메시지는 메시지를 처리 하는 방법을 결정 하는 데 사용 되는 매개 변수가 있는 경우가 많습니다.  
  
2.  컨트롤 알림  
  
     여기에 해당 부모 창에 컨트롤 및 기타 자식 창을에서 WM_COMMAND 알림 메시지가 포함 됩니다. 예를 들어 편집 컨트롤은 WM_COMMAND 메시지는 사용자가 편집 컨트롤의 텍스트를 변경할 수 있는 동작을 수행한 경우 EN_CHANGE 컨트롤 알림 코드가 포함 된 부모를 보냅니다. 메시지에 대 한 처리기는 창 컨트롤에서 텍스트를 검색 하는 등의 적절 한 방법으로 알림 메시지에 응답 합니다.  
  
     프레임 워크 같은 다른 컨트롤 알림 메시지를 라우팅하고 **WM_** 메시지입니다. 그러나는 예외, 사용자가을 클릭할 때 단추에서 보낸 BN_CLICKED 컨트롤 알림 메시지입니다. 이 메시지는 명령 메시지로 특별 하 게 처리 되며 다른 명령 처럼 라우팅됩니다.  
  
3.  명령 메시지  
  
     여기에 사용자 인터페이스 개체에서 알림 메시지 WM_COMMAND: 메뉴, 도구 모음 단추 및 액셀러레이터 키입니다. 다른 메시지에서 다르게 명령을 처리 하는 프레임 워크 및에 설명 된 대로 많은 종류의 개체를 처리할 수 있습니다 [명령 대상](../mfc/command-targets.md)합니다.  
  
##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows 메시지 및 컨트롤 알림 메시지  
 범주 1 및 2의에서 메시지-Windows 메시지 및 컨트롤 알림에-windows에서 처리할: 클래스에서 파생 된 클래스의 개체 `CWnd`합니다. 여기에 `CFrameWnd`, `CMDIFrameWnd`, `CMDIChildWnd`, `CView`, `CDialog`, 이러한 기본 클래스에서 파생 된 사용자 고유의 클래스입니다. 이러한 개체는 캡슐화 된 `HWND`, Windows 창에 대 한 핸들입니다.  
  
##  <a name="_core_command_messages"></a> 명령 메시지  
 범주 3에 있는 메시지-명령-다양 한 개체에서 처리 될 수: 문서, 문서 템플릿 및 창 및 뷰 외에도 응용 프로그램 개체 자체입니다. 명령을 몇 가지 특정 개체에 직접 영향을 하면 개체가 명령을 처리 하는 것이 좋습니다. 파일 메뉴에서 열기 명령을 응용 프로그램와 논리적으로 연결 된 예를 들어: 응용 프로그램 명령의 받을 때 지정된 된 문서를 엽니다. 따라서 열기 명령에 대 한 처리기는 응용 프로그램 클래스의 멤버 함수입니다. 명령 및 개체에 라우팅될 때 어떻게 하는 방법에 대 한 자세한 내용은 [프레임 워크가 처리기를 호출 하는 방법](../mfc/how-the-framework-calls-a-handler.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크의 메시지 및 명령](../mfc/messages-and-commands-in-the-framework.md)

