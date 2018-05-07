---
title: '컨테이너: 클라이언트 항목 상태 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5046ea7f3f3775cfe0009afe50f33a6ce6723cc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="containers-client-item-states"></a>컨테이너: 클라이언트 항목 상태
이 문서에서는 다양 한 수명 중에 통과 한 클라이언트 항목 상태에 설명 합니다.  
  
 클라이언트 항목을 생성, 활성화, 수정 및 저장은 것 처럼 여러 상태를 통해 전달 합니다. 항목의 상태 변경, 프레임 워크 호출 될 때마다 [COleClientItem::OnChange](../mfc/reference/coleclientitem-class.md#onchange) 와 `OLE_CHANGED_STATE` 알림입니다. 두 번째 매개 변수는 값은 **COleClientItem::ItemState** 열거 합니다. 다음 중 하나일 수 있습니다.  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 비어 있는 상태에서 클라이언트 항목은 아직 완전히는 항목이 아닙니다. 메모리를 할당 하지만 아직 OLE 항목의 데이터와 함께 초기화 되지 않았습니다. 이 현재 상태는 클라이언트 항목에 대 한 호출을 통해 생성 되 면 **새** 전형적인 2 단계 만들기의 두 번째 단계 아직 수행 하지 않지만 합니다.  
  
 호출을 통해 수행 하는 두 번째 단계에서 `COleClientItem::CreateFromFile` 또는 다른 **CreateFrom * * * xxxx* 함수 항목이 완전히 만들어집니다. OLE 데이터 (파일 또는 클립보드와 같은 다른 원본)에서 연결 된는 `COleClientItem`-파생 된 개체입니다. 이제 항목 로드 됨된 상태입니다.  
  
 항목에 된 서버 창에서 열 보다는 때 컨테이너의 문서에서 위치에서 열, open (또는 완전 개방) 상태입니다. 이 상태에서는 교차 무늬가 일반적으로 위에 그려집니다 항목이 현재 다른 곳에서 임을 나타내기 위해 컨테이너의 창에 항목의 표시 합니다.  
  
 항목 위치에 활성화 된 전달, 일반적으로 활성 상태를 통해 간단 하 게 합니다. 다음은 메뉴, 도구 모음 및 컨테이너의 다른 사용자 인터페이스 구성 요소 서버는 병합 UI 활성 상태를 입력 합니다. 이러한 사용자 인터페이스 구성 요소가 있는지를 활성 상태에서 UI 활성 상태를 구분합니다. 그렇지 않은 경우 활성 상태로 UI 활성 상태와 유사합니다. 서버에서 실행 취소를 지 원하는 경우 서버가 로드 또는 열린 상태에 도달할 때까지 OLE 항목의 실행 취소 상태 정보를 유지 하는 데 필요 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컨테이너](../mfc/containers.md)   
 [정품 인증](../mfc/activation-cpp.md)   
 [컨테이너: 클라이언트 항목 알림](../mfc/containers-client-item-notifications.md)   
 [추적기](../mfc/trackers.md)   
 [CRectTracker 클래스](../mfc/reference/crecttracker-class.md)
