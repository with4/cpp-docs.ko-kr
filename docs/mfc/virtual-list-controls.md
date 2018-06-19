---
title: 가상 목록 컨트롤 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cache, virtual list control item data
- list controls [MFC], virtual
- list controls [MFC], List view
- virtual list controls
ms.assetid: 319f841f-e426-423a-8276-d93f965b0b45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b580e455aab7ff95beb85c02b8e3ca79dfa8a46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384194"
---
# <a name="virtual-list-controls"></a>가상 목록 컨트롤
가상 목록 컨트롤은 목록 뷰 컨트롤에는 **LVS_OWNERDATA** 스타일입니다. 이 스타일 최대 항목 수를 지원 하도록 컨트롤을 활성화 한 `DWORD` (기본 항목 수로만 확장 프로그램 `int`). 그러나이 스타일의 가장 큰 장점은 한 번에 메모리에 데이터 항목의 하위 집합을 가질 수 있다는 점입니다. 이렇게 하면 가상 목록 뷰 컨트롤의 정보를 데이터베이스의 크기가 큰 사용 하기 위해 적합을 여기서 데이터에 액세스 하는 특정 메서드가에 이미 준비 되어 있습니다.  
  
> [!NOTE]
>  가상 목록 기능을 제공 하는 것 외에도 `CListCtrl`, MFC에 동일한 기능을 제공 된 [CListView](../mfc/reference/clistview-class.md) 클래스입니다.  
  
 가상 목록 컨트롤을 개발할 때 알고 있어야 하는 몇 가지 호환성 문제가 있습니다. 자세한 내용은 Windows SDK에서 목록 뷰 컨트롤 항목의 호환성 문제 섹션을 참조 합니다.  
  
## <a name="handling-the-lvngetdispinfo-notification"></a>LVN_GETDISPINFO 알림 처리  
 가상 목록 컨트롤 항목 정보를 거의 유지 관리합니다. 항목 선택 및 포커스가 정보를 제외한 모든 항목 정보는 컨트롤의 소유자에 의해 관리 됩니다. 통해 프레임 워크에 의해 요청 된 정보는 **LVN_GETDISPINFO** 알림 메시지입니다. 가상 목록 컨트롤 (또는 컨트롤 자체)의 소유자는 요청된 된 정보를 제공 하려면이 알림을 처리 해야 합니다. 쉽게 이렇게 하려면 속성 창을 사용 하 여 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)). 결과 코드는 다음 예제와 같아야 (여기서 `CMyDialog` 가상 목록 컨트롤 개체를 소유 하는 알림을 처리 하는 대화 상자 및):  
  
 [!code-cpp[NVC_MFCControlLadenDialog#23](../mfc/codesnippet/cpp/virtual-list-controls_1.cpp)]  
  
 에 대 한 처리기는 **LVN_GETDISPINFO** 알림 메시지를 보려면 어떤 유형의 정보를 요청 하 고 확인 해야 합니다. 가능한 값은 다음과 같습니다.  
  
-   `LVIF_TEXT` `pszText` 구성원을 입력 해야 합니다.  
  
-   `LVIF_IMAGE` `iImage` 구성원을 입력 해야 합니다.  
  
-   **LVIF_INDENT** 는 *iIndent* 멤버 입력 해야 합니다.  
  
-   `LVIF_PARAM` *lParam* 멤버 입력 해야 합니다. (없음 하위 항목에 대 한 합니다.)  
  
-   `LVIF_STATE` *상태* 멤버 입력 해야 합니다.  
  
 다음 프레임 워크에 다시 요청 된 정보를 제공 해야 합니다.  
  
 (List 컨트롤 개체에 대 한 알림 처리기의 본문에서 가져온) 다음 예제에서 텍스트 버퍼와 항목의 이미지에 대 한 정보를 제공 하 여 하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#24](../mfc/codesnippet/cpp/virtual-list-controls_2.cpp)]  
  
## <a name="caching-and-virtual-list-controls"></a>캐싱 및 가상 목록 컨트롤  
 이 유형의 목록 컨트롤은 이므로 큰 데이터 집합에 대 한 검색 성능 향상을 위해 요청 된 항목 데이터를 캐시 하는 것이 좋습니다. 전송 하 여 캐시를 최적화 하는 캐시 힌트 메커니즘을 제공 하는 프레임 워크는 **LVN_ODCACHEHINT** 알림 메시지입니다.  
  
 다음 예제에서는 범위를 처리기 함수에 전달 된 캐시를 업데이트 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#25](../mfc/codesnippet/cpp/virtual-list-controls_3.cpp)]  
  
 준비 하 고 캐시를 유지 관리에 대 한 자세한 내용은 Windows SDK에서 목록 뷰 컨트롤 항목의 캐시 관리 섹션을 참조 합니다.  
  
## <a name="finding-specific-items"></a>특정 작업 항목 찾기  
 **LVN_ODFINDITEM** 특정 목록 컨트롤 항목을 찾을 수 해야 할 때 가상 목록 컨트롤에서 알림 메시지가 보내집니다. List view 컨트롤 빠른 키 액세스 권한의 받을 때 또는 받을 때 알림 메시지를 보내는 **LVM_FINDITEM** 메시지입니다. 형태로 검색 ־ ֲ는 **LVFINDINFO** 구조 구성원의 **NMLVFINDITEM** 구조입니다. 재정의 하 여이 메시지를 처리는 `OnChildNotify` 함수 목록에 개체를 제어 하 고 확인 처리기의 본문 안에 **LVN_ODFINDITEM** 메시지입니다. 하는 경우 적절 한 작업을 수행 합니다.  
  
 목록 뷰 컨트롤에서 제공 하는 정보를 일치 하는 항목을 검색할 수 있도록 준비 해야 합니다. 일치 하는 항목이 없는 경우에 성공 하면 항목의 인덱스를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

