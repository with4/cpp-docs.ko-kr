---
title: 메시지 맵 범위에 대 한 처리기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- handlers [MFC], message-map ranges
- message maps [MFC], message handler functions
- message maps [MFC], ranges
- control-notification messages [MFC]
- command IDs [MFC], message mapping
- message-map ranges [MFC]
- handlers [MFC]
- message handling [MFC], message handler functions
- mappings [MFC], message ranges
- command handling [MFC], command update handlers
- controls [MFC], notifications
- handler functions [MFC], message-map ranges
- handler functions [MFC]
- command update handlers [MFC]
- command routing [MFC], command update handlers
- message ranges [MFC]
- handler functions [MFC], declaring
- message ranges [MFC], mapping
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 896977da8ca57cc17a9fa3b7864e1744ee07f35d
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930825"
---
# <a name="handlers-for-message-map-ranges"></a>메시지 맵 범위에 대한 처리기
이 문서에서는 다양 한 메시지 (메시지 한 개를 하나의 함수에 매핑) 대신 단일 메시지 처리기 함수에 매핑하는 방법을 설명 합니다.  
  
 동일한 방식으로 둘 이상의 메시지 또는 제어 알림을 처리 하는 경우가 있습니다. 이러한 시간에 모든 메시지는 단일 처리기 함수에 매핑할 백업본 수도 있습니다. 메시지 맵 범위를 사용 하면 메시지의 연속 된 범위에 대 한이 작업을 수행할 수 있습니다.  
  
-   명령 Id 범위를 매핑할 수 있습니다.  
  
    -   명령 처리기 함수입니다.  
  
    -   명령 업데이트 처리기 함수입니다.  
  
-   컨트롤 알림 메시지는 컨트롤 Id의 범위에 대 한 메시지 처리기 함수에 매핑할 수 있습니다.  
  
 이 문서에서 다루는 항목은 다음과 같습니다.  
  
-   [메시지 맵 항목을 기록](#_core_writing_the_message.2d.map_entry)  
  
-   [처리기 함수 선언](#_core_declaring_the_handler_function)  
  
-   [명령 Id의 범위에 대 한 예제](#_core_example_for_a_range_of_command_ids)  
  
-   [컨트롤 Id의 범위에 대 한 예](#_core_example_for_a_range_of_control_ids)  
  
##  <a name="_core_writing_the_message.2d.map_entry"></a> 메시지 맵 항목을 기록  
 안에. CPP 파일에서 다음 예제와 같이 메시지 맵 항목을 추가 합니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_1.cpp)]  
  
 메시지 맵 항목의 다음 항목으로 구성 됩니다.  
  
-   메시지 맵 범위 매크로:  
  
    -   [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range)  
  
    -   [ON_UPDATE_COMMAND_UI_RANGE](reference/message-map-macros-mfc.md#on_update_command_ui_range)  
  
    -   [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range)  
  
-   매크로에 매개 변수:  
  
     처음 두 매크로 세 개의 매개 변수를 수행합니다.  
  
    -   범위가 시작 되는 명령 ID  
  
    -   범위를 끝내 명령 ID  
  
    -   메시지 처리기 함수 이름  
  
     명령 Id의 범위는 연속적 이어야 합니다.  
  
     세 번째 매크로 `ON_CONTROL_RANGE`, 추가 첫 번째 매개 변수: 같은 컨트롤 알림 메시지 **EN_CHANGE**합니다.  
  
##  <a name="_core_declaring_the_handler_function"></a> 처리기 함수 선언  
 처리기 함수 선언에 추가 된 합니다. H 파일입니다. 다음 코드는 아래 표시 된 대로 이러한 바인딩을 보여 주는,을 보여줍니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_2.h)]  
  
 단일 명령에 대 한 처리기 함수는 일반적으로 매개 변수를 사용합니다. 업데이트 처리기 함수를 제외 하 고 메시지 맵 범위에 대 한 처리기 함수는 추가 매개 변수를 필요 *nID*, 형식의 **UINT**합니다. 이 매개 변수는 첫 번째 매개 변수입니다. 추가 매개 변수 사용자 실제로 선택 하는 명령을 지정 하는 데 필요한 추가 명령 ID를 수용 합니다.  
  
 처리기 함수를 업데이트 하기 위한 매개 변수 요구 사항에 대 한 자세한 내용은 참조 [예제에 대 한 명령 Id 범위](#_core_example_for_a_range_of_command_ids)합니다.  
  
##  <a name="_core_example_for_a_range_of_command_ids"></a> 명령 범위 Id에 대 한 예제  
 MFC 샘플에서 확대/축소 명령은 같은 명령을 처리 하는 예로 범위를 사용 하면 [HIERSVR](../visual-cpp-samples.md)합니다. 이 명령은 300% 보통 크기의 25% 사이의 크기 조정 보기를 확대 합니다. 확대/축소 명령은이 모양의 메시지 맵 항목으로 처리 하는 범위를 사용 하는 HIERSVR의 뷰 클래스:  
  
 [!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_3.cpp)]  
  
 메시지 맵 엔트리를 쓸 다음 항목을 지정 합니다.  
  
-   두 개의 명령 Id를 시작 하 고 연속 된 범위를 종료 합니다.  
  
     다음은 이러한 **ID_VIEW_ZOOM25** 및 **ID_VIEW_ZOOM300**합니다.  
  
-   명령에 대 한 처리기 함수의 이름입니다.  
  
     여기에서는 `OnZoom`합니다.  
  
 함수 선언은 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_4.h)]  
  
 업데이트 처리기 함수의 경우에는 이와 유사 하며 보다 유용 하는입니다. 쓰려고 매우 일반적 이기 `ON_UPDATE_COMMAND_UI` 명령 수에 대 한 처리기 작성 하거나 복사, 동일한 코드 반복을 찾습니다. 솔루션은 명령 Id 하나를 처리기 함수를 사용 하 여 업데이트의 범위에 매핑하려면는 `ON_UPDATE_COMMAND_UI_RANGE` 매크로입니다. 명령 Id 연속 된 범위를 구성 해야 합니다. 예를 들어 참조는 `OnUpdateZoom` 처리기와 해당 `ON_UPDATE_COMMAND_UI_RANGE` HIERSVR 샘플의 뷰 클래스의 메시지-맵 항목입니다.  
  
 처리기 함수를 단일 명령에 단일 매개 변수를 정상적으로 수행에 대 한 업데이트 *pCmdUI*, 형식의 `CCmdUI*`합니다. 처리기 함수는 달리 메시지 맵 범위에 대 한 업데이트 처리기 함수는 추가 매개 변수가 필요 하지 않습니다 *nID*, 형식의 **UINT**합니다. 사용자가 실제로 선택 되는 명령은 지정 하는 데 필요한 명령 ID에서 발견 되는 `CCmdUI` 개체입니다.  
  
##  <a name="_core_example_for_a_range_of_control_ids"></a> 컨트롤의 범위 Id에 대 한 예제  
 다른 흥미로운 사례 컨트롤 Id의 범위에 대 한 컨트롤 알림 메시지를 단일 처리기에 매핑된다 합니다. 사용자에 10 개의 단추를 클릭할 수 있다고 가정 합니다. 모든 10 단추 처리기에 매핑할 메시지-맵 항목은 다음과 같습니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_5.cpp)]  
  
 작성 하는 경우는 `ON_CONTROL_RANGE` 메시지 맵에서 매크로 지정 합니다.  
  
-   특정 컨트롤 알림 메시지입니다.  
  
     여기에서는 **BN_CLICKED**합니다.  
  
-   컨트롤의 연속 된 범위와 연결 된 컨트롤 ID 값입니다.  
  
     다음은 이러한 **IDC_BUTTON1** 및 **IDC_BUTTON10**합니다.  
  
-   메시지 처리기 함수의 이름입니다.  
  
     여기에서는 `OnButtonClicked`합니다.  
  
 처리기 함수를 작성할 때 지정할 때 추가 **UINT** 매개 변수를 다음과 같이 합니다.  
  
 [!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/cpp/handlers-for-message-map-ranges_6.cpp)]  
  
 `OnButtonClicked` 단일 처리기 **BN_CLICKED** 메시지 매개 변수를 사용 합니다. 단추의 범위에 대 한 동일한 처리기 하나를 사용 합니다. **UINT**합니다. 추가 매개 변수를 생성 한 특정 컨트롤을 식별 하는 데 사용 된 **BN_CLICKED** 메시지입니다.  
  
 이 예제에 표시 된 코드는 일반적인: 변환에 전달 된 값은 `int` 메시지 범위 및 대/소문자 인지 어설션 내에서. 그런 다음 몇 가지 다른 동작에 따라 단추가 클릭 되었습니다 걸릴 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [메시지 처리기 함수 선언](../mfc/declaring-message-handler-functions.md)
