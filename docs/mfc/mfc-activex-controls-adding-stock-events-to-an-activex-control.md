---
title: 'MFC ActiveX 컨트롤: ActiveX 컨트롤에 스톡 이벤트 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- EVENT__STOCK_ERROR
- EVENT__STOCK_READYSTATECHANGE
- ReadyStateChange
- EVENT__STOCK_MOUSEMOVE
- EVENT__STOCK_MOUSEUP
- EVENT__STOCK_DBLCLICK
- KeyPress
- EVENT__STOCK_KEYDOWN
- EVENT__STOCK
- EVENT__STOCK_MOUSEDOWN
- EVENT__STOCK_KEYPRESS
- EVENT__STOCK_CLICK
- EVENT__STOCK_KEYUP
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- KeyPress event
- FireDblClick event
- FireMouseDown event
- events [MFC], stock
- FireKeyPress event
- EVENT_STOCK_MOUSEMOVE event
- EVENT_STOCK_CLICK event
- FireClick event
- FireKeyUp event
- FireMouseUp event
- EVENT_STOCK_ERROREVENT event
- EVENT_STOCK_KEYDOWN event
- EVENT_STOCK_MOUSEDOWN event
- EVENT_STOCK_KEYPRESS macro [MFC]
- EVENT_STOCK_KEYUP event
- EVENT_STOCK_DBLCLICK event
- FireError event
- FireKeyDown event
- ReadyStateChange event
- EVENT_STOCK_MOUSEUP event
- FireMouseMove event
- EVENT_STOCK prefix
- EVENT_STOCK_READYSTATECHANGE event
- EVENT_STOCK_KEYPRESS event
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41445015f30eb953675f763652fb85ef3eeb857a
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930789"
---
# <a name="mfc-activex-controls-adding-stock-events-to-an-activex-control"></a>MFC ActiveX 컨트롤: ActiveX 컨트롤에 스톡 이벤트 추가
스톡 이벤트 사용자 지정 이벤트 한다는 점에서 다릅니다 클래스에 의해 자동으로 발생 하는 [COleControl](../mfc/reference/colecontrol-class.md)합니다. `COleControl` 일반 동작으로 인해 발생 하는 이벤트를 발생 하는 미리 정의 된 멤버 함수를 포함 합니다. 구현 되는 일반적인 동작 `COleControl` 포함 단일-및 번 또는 두-clicks 컨트롤과 키보드 이벤트, 변경 내용에 마우스 단추의 상태입니다. 이벤트는 이벤트 앞에 항상 EVENT_STOCK 접두사 재고에 대 한 항목을 매핑합니다.  
  
##  <a name="_core_stock_events_supported_by_classwizard"></a> 지 원하는 스톡 이벤트는 이벤트 추가 마법사  
 `COleControl` 클래스는 다음 표에 나열 된 10 개의 스톡 이벤트를 제공 합니다. 사용 하 여 컨트롤에서 원하는 이벤트를 지정할 수는 [이벤트 추가 마법사](../ide/add-event-wizard.md)합니다.  
  
### <a name="stock-events"></a>스톡 이벤트  
  
|이벤트(event)|발생 함수|설명|  
|-----------|---------------------|--------------|  
|클릭|**void FireClick)**|컨트롤에서 마우스를 모두 캡처할 때 발생 합니다. **BUTTONUP** (왼쪽, 가운데 또는 오른쪽) 메시지를 수신 하 고 단추를 컨트롤 위에 놓을 합니다. MouseDown 주식형 및 MouseUp 이벤트에는이 이벤트 이전에 발생 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_CLICK)**|  
|매크로나|**void FireDblClick)**|클릭 하 여 유사 하지만 때 발생 한 **BUTTONDBLCLK** 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_DBLCLICK)**|  
|Error|**FireError void (SCODE***scode* **, LPCSTR** `lpszDescription` **, UINT**`nHelpID`**= 0)** |메서드 호출 또는 속성 액세스 범위를 벗어났습니다 ActiveX 컨트롤 내에서 오류가 발생할 때 발생 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_ERROREVENT)**|  
|KeyDown|**FireKeyDown void (짧은** `nChar` **, short**`nShiftState`**)** |발생 시기는 `WM_SYSKEYDOWN` 또는 `WM_KEYDOWN` 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYDOWN)**|  
|키 누름|**FireKeyPress void (짧은\***`pnChar`**)** |발생 시기는 `WM_CHAR` 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYPRESS)**|  
|KeyUp|**FireKeyUp void (짧은** `nChar` **, short**`nShiftState`**)** |발생 시기는 `WM_SYSKEYUP` 또는 `WM_KEYUP` 메시지를 수신 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_KEYUP)**|  
|MouseDown|**FireMouseDown void (짧은** `nButton` **, short** `nShiftState` **, float***x* **, float** *y***)** |있는 경우 발생 합니다. **BUTTONDOWN** (왼쪽, 가운데 또는 오른쪽)를 수신 합니다. 마우스는이 이벤트가 발생 하기 직전에 캡처됩니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEDOWN)**|  
|MouseMove|**FireMouseMove void (짧은** `nButton` **, short** `nShiftState` **, float***x* **, float** *y***)** |WM_MOUSEMOVE 메시지를 받을 때 발생 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEMOVE)**|  
|MouseUp|**FireMouseUp void (짧은** `nButton` **, short** `nShiftState` **, float***x* **, float** *y***)** |있는 경우 발생 합니다. **BUTTONUP** (왼쪽, 가운데 또는 오른쪽)를 수신 합니다. 이 이벤트가 발생 하기 전에 마우스 캡처가 해제 됩니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_MOUSEUP)**|  
|ReadyStateChange|**void FireReadyStateChange)**|한 컨트롤이 받은 데이터의 양으로 인해 다음 준비 상태로 전환 될 때 발생 합니다.<br /><br /> 이벤트 맵 항목: **EVENT_STOCK_READYSTATECHANGE)**|  
  
##  <a name="_core_adding_a_stock_event_using_classwizard"></a> 사용 하 여 스톡 이벤트 추가 된 이벤트 추가 마법사  
 실제 이벤트의 발생은 기본 클래스에 의해 자동으로 처리 하기 때문에 사용자 지정 이벤트 보다 더 적은 작업 스톡 이벤트를 추가 하려면 `COleControl`합니다. 다음 절차를 사용 하 여 개발 된 컨트롤에 스톡 이벤트 추가 [MFC ActiveX 컨트롤 마법사](../mfc/reference/mfc-activex-control-wizard.md)합니다. 키를 누를 때 컨트롤이 활성화 된 KeyPress, 호출 이벤트를 발생 시킵니다. 이 절차는 다른 스톡 이벤트 추가 하려면 데도 사용할 수 있습니다. KeyPress에 대 한 선택 된 스톡 이벤트 이름을 대체 합니다.  
  
#### <a name="to-add-the-keypress-stock-event-using-the-add-event-wizard"></a>KeyPress 스톡 이벤트 추가 마법사를 사용 하 여 이벤트를 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 바로 가기 메뉴를 열고 해당 ActiveX 컨트롤 클래스를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **이벤트 추가**합니다.  
  
     이벤트 추가 마법사가 열립니다.  
  
4.  에 **이벤트 이름** 드롭 다운 목록 `KeyPress`합니다.  
  
5.  **마침**을 클릭합니다.  
  
##  <a name="_core_classwizard_changes_for_stock_events"></a> 스톡 이벤트 추가 마법사 변경 이벤트  
 스톡 이벤트는 컨트롤의 기본 클래스에 의해 처리 되므로, 이벤트 추가 마법사에는 클래스 선언에는 전혀 변경 되지 않습니다. 컨트롤의 이벤트 지도에 이벤트를 추가 하 고에 항목의 합니다. IDL 파일입니다. 컨트롤 클래스 구현에 있는 컨트롤의 이벤트 맵을에 다음 줄 추가 됩니다 (합니다. Cpp) 됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]  
  
 이 코드를 추가 WM_CHAR 메시지를 받고 컨트롤이 활성화 된 때 KeyPress 이벤트를 발생 시킵니다. KeyPress 이벤트의 발생 함수를 호출 하 여 다른 시간에 발생할 수 있습니다 (예를 들어 `FireKeyPress`)에서 제어 코드 내에서.  
  
 이벤트 추가 마법사를 컨트롤의 다음 코드 줄을 추가합니다. IDL 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]  
  
 이 줄은 표준 디스패치 ID KeyPress 이벤트 연결 하 고 컨테이너 KeyPress 이벤트를 예상할 수 있도록 허용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)   
 [COleControl 클래스](../mfc/reference/colecontrol-class.md)
