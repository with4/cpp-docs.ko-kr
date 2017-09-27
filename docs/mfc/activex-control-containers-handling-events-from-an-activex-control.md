---
title: "ActiveX 컨트롤 컨테이너: ActiveX 컨트롤에서 이벤트를 처리 합니다. | Microsoft Docs"
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
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 3903be230f130aeaeb1953faf73a0c8af4c3492f
ms.openlocfilehash: a8fb283d8b5b8afbf3b06e27495ccc957e0099ad
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤에서 보낸 이벤트 처리
이 문서에서는 ActiveX 컨트롤 컨테이너에서 ActiveX 컨트롤에 대 한 이벤트 처리기를 설치 하려면 속성 창을 사용 하 여 설명 합니다. 이벤트 처리기는 특정 이벤트 (컨트롤)에서 알림 받기 및 응답에 일부 작업을 수행 하는 데 사용 됩니다. 이 알림은 이벤트를 "발생" 라고 합니다.  
  
> [!NOTE]
>  이 문서는 대화 상자 기반 ActiveX 컨트롤 컨테이너 프로젝트 라는 컨테이너와 절차 및 코드에서 예로 Circ 라는 포함 된 컨트롤을 사용 합니다.  
  
 이벤트 단추를 사용 하 여 속성 창에서 ActiveX 컨트롤 컨테이너 응용 프로그램에서 발생할 수 있는 이벤트의 지도 만들 수 있습니다. 이벤트 싱크 맵"' 라는이 맵에서 생성 되어 컨트롤 컨테이너 클래스에 이벤트 처리기를 추가할 때 Visual c + +에서 유지 관리 합니다. 이벤트 맵 항목을 사용 하 여 구현 되는 각 이벤트 처리기를 이벤트 처리기 컨테이너 멤버 함수는 특정 이벤트를 매핑합니다. 이 이벤트 처리기 함수에는 ActiveX 컨트롤 개체에 의해 지정 된 이벤트가 발생할 때 호출 됩니다.  
  
 이벤트 싱크 맵에 대 한 자세한 내용은 참조 하십시오. [이벤트 싱크 맵](../mfc/reference/event-sink-maps.md) 에 *클래스 라이브러리 참조*합니다.  
  
##  <a name="_core_event_handler_modifications_to_the_project"></a>프로젝트에 이벤트 처리기 수정  
 속성 창을 사용 하 여 이벤트 처리기를 추가 하려면 이벤트 싱크 맵 선언 되 고 프로젝트에 정의 합니다. 다음 문이 컨트롤에 추가 됩니다. Cpp 처음 이벤트 처리기를 추가 합니다. 이 코드에서는 대화 상자 클래스에 대 한 이벤트 싱크 맵 선언 (이 경우 `CContainerDlg`):  
  
 [!code-cpp[NVC_MFC_AxCont#8](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]  
[!code-cpp[NVC_MFC_AxCont#9](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]  
  
 이벤트 맵 항목 속성 창을 사용 하 여 이벤트를 추가 하는 대로 (`ON_EVENT`)이 추가 이벤트 싱크 맵 및 이벤트 처리기 함수에 추가 된 컨테이너의 구현 (합니다. Cpp) 합니다.  
  
 다음 예제에서는 선언 라는 이벤트 처리기, `OnClickInCircCtrl`, Circ 컨트롤에 대 한 **ClickIn** 이벤트:  
  
 [!code-cpp[NVC_MFC_AxCont#10](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]  
  
 또한, 다음 템플릿을에 추가 되는 `CContainerDlg` 클래스 구현 (합니다. 이벤트 처리기 멤버 함수에 대 한 CPP) 파일:  
  
 [!code-cpp[NVC_MFC_AxCont#11](../mfc/codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]  
  
 이벤트 싱크 매크로에 대 한 자세한 내용은 참조 하십시오. [이벤트 싱크 맵](../mfc/reference/event-sink-maps.md) 에 *클래스 라이브러리 참조*합니다.  
  
#### <a name="to-create-an-event-handler-function"></a>이벤트 처리기 함수를 만들려면  
  
1.  클래스 뷰에서 ActiveX 컨트롤이 있는 대화 상자 클래스를 선택 합니다. 이 예제에서는 `CContainerDlg`합니다.  
  
2.  속성 창에서 클릭 된 **이벤트** 단추입니다.  
  
3.  속성 창에서 포함 된 ActiveX 컨트롤의 컨트롤 ID를 선택 합니다. 이 예제에서는 `IDC_CIRCCTRL1`합니다.  
  
     속성 창에 포함 된 ActiveX 컨트롤에 의해 실행 될 수 있는 이벤트의 목록이 표시 됩니다. 이미에 굵게 표시 된 모든 멤버 함수를 할당 된 처리기 함수가 있습니다.  
  
4.  원하는 이벤트를 처리 하는 대화 상자 클래스를 선택 합니다. 이 예에서는 선택 **클릭**합니다.  
  
5.  오른쪽의 드롭다운 목록 상자에서 선택 ** \<추가 > ClickCircctrl1**합니다.  
  
6.  이벤트 처리기 코드 구현에서으로 이동 하려면 클래스 뷰에서 새 처리기 함수를 두 번 클릭 (합니다. Cpp)의 `CContainerDlg`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)


