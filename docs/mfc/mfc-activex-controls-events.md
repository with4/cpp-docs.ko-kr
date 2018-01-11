---
title: "MFC ActiveX 컨트롤: 이벤트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6760f2051542a28e78f5f8f2fa81f6937388d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-events"></a>MFC ActiveX 컨트롤: 이벤트
ActiveX 컨트롤에 컨트롤에 발생 하는 컨테이너를 알리기 위해 이벤트를 사용 합니다. 일반적인 이벤트의 예로 컨트롤, 컨트롤의 상태에는 키보드 및 변경 작업을 사용 하 여 입력 데이터에 대 한 클릭 합니다. 이러한 작업이 발생 하는 경우 컨트롤 컨테이너를 경고 하도록 이벤트를 발생 시킵니다.  
  
 이벤트는 메시지 라고도 합니다.  
  
 MFC는 두 가지 이벤트 종류가 지원: 주식형 및 사용자 지정 합니다. 스톡 이벤트는 이벤트 클래스는 [COleControl](../mfc/reference/colecontrol-class.md) 자동으로 처리 합니다. 스톡 이벤트 목록이 전체 문서를 참조 하십시오. [MFC ActiveX 컨트롤: 스톡 이벤트 추가](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)합니다. 사용자 지정 이벤트는 해당 컨트롤에 특정 한 작업이 수행 될 때 컨테이너에 알리는 수는 제어를 허용 합니다. 몇 가지 예는 컨트롤의 내부 상태 또는 특정 창 메시지를 받을 것입니다.  
  
 제대로 이벤트를 발생 시키는 컨트롤에 대 한 컨트롤 클래스 관련된 이벤트가 발생할 때 호출 해야 하는 멤버 함수에는 컨트롤의 각 이벤트를 매핑해야 합니다. 매핑 메커니즘의 (이벤트 맵 라고 함)이 이벤트에 대 한 정보를 중앙 집중화 하 고 Visual Studio에서 쉽게 액세스 하 고 컨트롤의 이벤트를 조작할 수 있습니다. 헤더에 있는 다음 매크로 의해 선언 된이 이벤트 맵 (합니다. H)에서 컨트롤 클래스 선언의 파일:  
  
 [!code-cpp[NVC_MFC_AxUI#2](../mfc/codesnippet/cpp/mfc-activex-controls-events_1.h)]  
  
 이벤트 맵을 선언한 후 컨트롤의 구현에서 정의 되어야 합니다 (합니다. Cpp) 합니다. 코드의 다음 줄에는 특정 이벤트를 발생 시키는 컨트롤 이벤트 맵을 정의 합니다.  
  
 [!code-cpp[NVC_MFC_AxUI#3](../mfc/codesnippet/cpp/mfc-activex-controls-events_2.cpp)]  
[!code-cpp[NVC_MFC_AxUI#4](../mfc/codesnippet/cpp/mfc-activex-controls-events_3.cpp)]  
  
 MFC ActiveX 컨트롤 마법사를 사용 하 여 프로젝트를 만드는 경우 자동으로 다음이 줄을 추가 합니다. MFC ActiveX 컨트롤 마법사를 사용 하지 않는 경우이 코드를 수동으로 추가 해야 있습니다.  
  
 클래스 뷰를 사용 하면 클래스에서 지 원하는 스톡 이벤트를 추가할 수 있습니다 `COleControl` 또는 사용자가 정의한 사용자 지정 이벤트입니다. 각 새 이벤트에 대 한 클래스 뷰 컨트롤의 이벤트 지도 컨트롤의에 속성 항목이 자동으로 추가합니다. IDL 파일입니다.  
  
 두 문서에서 이벤트를 자세히 설명 합니다.  
  
-   [MFC ActiveX 컨트롤: 스톡 이벤트 추가](../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [MFC ActiveX 컨트롤: 사용자 지정 이벤트 추가](../mfc/mfc-activex-controls-adding-custom-events.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 메서드](../mfc/mfc-activex-controls-methods.md)   
 [COleControl 클래스](../mfc/reference/colecontrol-class.md)
