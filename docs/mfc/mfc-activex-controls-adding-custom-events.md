---
title: 'MFC ActiveX 컨트롤: 사용자 지정 이벤트 추가 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events [MFC]
- EVENT_CUSTOM prefix [MFC]
- custom events [MFC], adding to ActiveX controls
- EVENT_CUSTOM macro [MFC]
- InCircle method [MFC]
- ClickIn event
- FireClickIn event
- COleControl class [MFC], custom events [MFC]
- Click event, custom events [MFC]
- events [MFC], ActiveX controls
- custom events [MFC]
- FireEvent method, adding custom events
ms.assetid: c584d053-1e34-47aa-958e-37d3e9b85892
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b82232b8f2ad7a5e3bc1ff8fed0e8a38b1a7d66
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33352533"
---
# <a name="mfc-activex-controls-adding-custom-events"></a>MFC ActiveX 컨트롤: 사용자 지정 이벤트 추가
사용자 지정 이벤트 스톡 이벤트 한다는 점에서 다릅니다 클래스에 의해 자동으로 발생 되지 않습니다 `COleControl`합니다. 사용자 지정 이벤트는 컨트롤 개발자는 이벤트에 의해 결정 된 특정 작업을 인식 합니다. 사용자 지정 이벤트에 대 한 이벤트 맵 항목으로 표시 됩니다는 `EVENT_CUSTOM` 매크로입니다. 다음 섹션에는 ActiveX 컨트롤 마법사를 사용 하 여 만든 ActiveX 컨트롤 프로젝트에 대 한 사용자 지정 이벤트를 구현 합니다.  
  
##  <a name="_core_adding_a_custom_event_with_classwizard"></a> 추가 된 사용자 지정 이벤트는 이벤트 추가 마법사  
 다음 절차에는 특정 사용자 지정 이벤트를 ClickIn 추가합니다. 다른 사용자 지정 이벤트를 추가 하려면이 절차를 사용할 수 있습니다. 사용자 지정 이벤트 이름 및 해당 매개 변수 ClickIn 이벤트 이름 및 매개 변수를 대체 합니다.  
  
#### <a name="to-add-the-clickin-custom-event-using-the-add-event-wizard"></a>이벤트 추가 마법사를 사용 하 여 사용자 지정 ClickIn 이벤트를 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 바로 가기 메뉴를 열고 해당 ActiveX 컨트롤 클래스를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **이벤트 추가**합니다.  
  
     이벤트 추가 마법사가 열립니다.  
  
4.  에 **이벤트 이름** 상자, 먼저 모든 기존 이벤트를 선택한 다음 클릭는 **사용자 지정** 라디오 단추를 선택한 다음 입력 `ClickIn`합니다.  
  
5.  에 **내부 이름** 이벤트의 발생 함수 이름을 입력 합니다. 이 예에서는 이벤트 추가 마법사에서 제공 기본값을 사용 합니다 (`FireClickIn`).  
  
6.  라는 매개 변수 추가 `xCoord` (형식 `OLE_XPOS_PIXELS`)를 사용 하 여는 **매개 변수 이름** 및 **매개 변수 형식** 컨트롤입니다.  
  
7.  라는 두 번째 매개 변수 추가 `yCoord` (형식 `OLE_YPOS_PIXELS`).  
  
8.  클릭 **마침** 여 이벤트를 만듭니다.  
  
##  <a name="_core_classwizard_changes_for_custom_events"></a> 사용자 지정 이벤트 추가 마법사 변경 이벤트  
 사용자 지정 이벤트를 추가 하면 해당 변경을 컨트롤 클래스에 않습니다. H입니다. CPP, 및입니다. IDL 파일입니다. 다음 코드 샘플 ClickIn 이벤트에 적용 됩니다.  
  
 다음 줄의 헤더에 추가 됩니다 (합니다. H) 컨트롤 클래스의 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_1.h)]  
  
 이 코드를 호출 하는 인라인 함수 선언 `FireClickIn` 호출 하는 [COleControl::FireEvent](../mfc/reference/colecontrol-class.md#fireevent) 이벤트 추가 마법사를 사용 하 여 정의한 ClickIn 이벤트 및 매개 변수입니다.  
  
 또한 다음 줄의 구현에 있는 컨트롤에 대 한 이벤트 맵에 추가 됩니다 (합니다. 컨트롤 클래스의 CPP) 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_2.cpp)]  
  
 이 코드의 인라인 기능에 ClickIn 이벤트 매핑됩니다 `FireClickIn`, 이벤트 추가 마법사를 사용 하 여 정의 된 매개 변수를 전달 합니다.  
  
 마지막으로, 다음 줄은 컨트롤의에 추가 됩니다. IDL 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_3.idl)]  
  
 이 줄 ClickIn 이벤트 이벤트 추가 마법사 이벤트 목록에서 이벤트의 위치에서 가져온 특정 ID 번호를 할당 합니다. 이벤트 목록에 항목 컨테이너를를 해당 이벤트를 예상할 수 있습니다. 예를 들어 이벤트가 발생할 때 실행 되는 처리기 코드를 제공할 수 있습니다.  
  
##  <a name="_core_calling_fireclickin"></a> FireClickIn 호출  
 이벤트 추가 마법사를 사용 하 여 사용자 지정 ClickIn 이벤트를 추가한 했으므로이 이벤트는 시작 될 시기를 결정 해야 합니다. 호출 하 여이 작업을 수행 `FireClickIn` 적절 한 조치에 발생 합니다. 이 설명에서는 컨트롤이 사용 하는 `InCircle` 함수 내는 `WM_LBUTTONDOWN` 원형 또는 타원형 영역 내부를 클릭할 때 ClickIn 이벤트를 발생 시키는 메시지 처리기입니다. 다음 절차에서는 추가 `WM_LBUTTONDOWN` 처리기입니다.  
  
#### <a name="to-add-a-message-handler-with-the-add-event-wizard"></a>이벤트 추가 마법사와 메시지 처리기를 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 ActiveX 컨트롤 클래스를 선택 합니다.  
  
3.  속성 창에서 클릭 된 **메시지** 단추입니다.  
  
     속성 창에는 ActiveX 컨트롤에 의해 처리 될 수 있는 메시지의 목록이 표시 됩니다. 이미에 굵게 표시 된 모든 메시지에 할당 된 처리기 함수를 포함 합니다.  
  
4.  속성 창에서 처리할 메시지를 선택 합니다. 이 예에서는 선택 `WM_LBUTTONDOWN`합니다.  
  
5.  오른쪽의 드롭다운 목록 상자에서 선택  **\<추가 > OnLButtonDown**합니다.  
  
6.  메시지 처리기 코드 구현에서으로 이동 하려면 클래스 뷰에서 새 처리기 함수를 두 번 클릭 (합니다. ActiveX 컨트롤의 CPP) 파일입니다.  
  
 다음 코드 샘플 호출은 **InCircle** 제어 창 내에서 마우스 왼쪽된 단추를 클릭할 때마다 작동 합니다. 이 샘플에서 찾을 수 있습니다는 `WM_LBUTTONDOWN` 처리기 함수를 `OnLButtonDown`에 [Circ 샘플](../visual-cpp-samples.md) 추상 합니다.  
  
 [!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_4.cpp)]  
  
> [!NOTE]
>  이벤트 추가 마법사가 마우스 단추 작업에 대 한 메시지 처리기를 만들면 기본 클래스의 동일한 메시지 처리기에 대 한 호출 자동으로 추가 됩니다. 이 호출을 제거 하지 마십시오. 컨트롤 스톡 마우스 메시지 중 하나를 사용 하면 마우스 캡처가 올바르게 처리 되도록 기본 클래스의 메시지 처리기를 호출 합니다.  
  
 다음 예에서는 이벤트가 발생할 경우에 클릭 컨트롤 내에서 원형 또는 타원형 영역 내에 발생 합니다. 이 동작을 얻으려면를 배치할 수 있습니다는 `InCircle` 컨트롤의 구현에서 함수 (합니다. Cpp) 됩니다.  
  
 [!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_5.cpp)]  
  
 다음 선언을 추가 해야 합니다는 `InCircle` 컨트롤의 헤더에는 함수 (합니다. H) 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-events_6.h)]  
  
##  <a name="_core_custom_events_with_stock_names"></a> 주식 이름 사용 하 여 사용자 지정 이벤트  
 동일한 컨트롤에 둘 다를 구현 하지 수 있지만 스톡 이벤트로 이름이 같은 사용자 지정 이벤트를 만들 수 있습니다. 예를 들어 스톡 이벤트 클릭 정상적으로 발생 하는 경우에 발생 하지 않는 Click 이라는 사용자 지정 이벤트를 만들 수도 있습니다. 그런 다음 해당 발생 함수를 호출 하 여 언제 든 지 Click 이벤트를 실행 수 있습니다.  
  
 다음 절차는 추가 사용자 지정 클릭 이벤트입니다.  
  
#### <a name="to-add-a-custom-event-that-uses-a-stock-event-name"></a>스톡 이벤트 이름을 사용 하는 사용자 지정 이벤트를 추가 하려면  
  
1.  컨트롤의 프로젝트를 로드합니다.  
  
2.  클래스 뷰에서 바로 가기 메뉴를 열고 해당 ActiveX 컨트롤 클래스를 마우스 오른쪽 단추로 클릭 합니다.  
  
3.  바로 가기 메뉴에서 클릭 **추가** 클릭 하 고 **이벤트 추가**합니다.  
  
     이벤트 추가 마법사가 열립니다.  
  
4.  에 **이벤트 이름** 드롭 다운 목록 스톡 이벤트 이름을 선택 합니다. 이 예에서는 선택 **클릭**합니다.  
  
5.  에 대 한 **이벤트 유형을**선택, **사용자 지정**합니다.  
  
6.  클릭 **마침** 여 이벤트를 만듭니다.  
  
7.  호출 `FireClick` 사용자 코드에서 적절 한 위치에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)   
 [COleControl 클래스](../mfc/reference/colecontrol-class.md)
