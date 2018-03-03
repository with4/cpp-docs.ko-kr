---
title: "트리 컨트롤 사용 | Microsoft Docs"
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
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ea3b7e0348cb21aa4338293f7cc1119e380f92dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-tree-controls"></a>트리 컨트롤 사용
트리 컨트롤의 일반적인 사용 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 아래의 패턴을 따릅니다.  
  
-   컨트롤이 만들어집니다. 컨트롤이 대화 상자 템플릿에 지정 될 경우 또는 사용 중인 경우 `CTreeView`, 대화 상자 또는 보기를 만들 때 자동 생성 됩니다. 트리 컨트롤 다른 창의 자식 창으로 만들려는 경우 사용 하 여는 [만들기](../mfc/reference/ctreectrl-class.md#create) 멤버 함수입니다.  
  
-   트리 컨트롤 이미지를 사용 하도록 하려는 경우 호출 하 여 이미지 목록을 설정 [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)합니다. 호출 하 여 들여쓰기를 변경할 수도 있습니다 [SetIndent](../mfc/reference/ctreectrl-class.md#setindent)합니다. 이 작업을 수행 하는 데 좋은 시간이 중인 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (컨트롤에 대 한 대화 상자에서) 또는 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (views)에 대 한 합니다.  
  
-   호출 하 여 데이터를 컨트롤에 추가 된 `CTreeCtrl`의 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) 각 데이터 항목에 대해 한 번씩 함수입니다. `InsertItem`자식 항목을 추가 하는 경우와 같이 나중 참조 하는 데 사용할 수는 항목에 핸들을 반환 합니다. 데이터를 초기화 하는 데 좋은 시간이 중인 `OnInitDialog` (컨트롤에 대 한 대화 상자에서) 또는 `OnInitialUpdate` 보기.  
  
-   사용자가 컨트롤과 상호 작용하여 다양한 알림 메시지가 전송됩니다. 각 추가 하 여 처리할 메시지를 처리 하는 함수를 지정할 수는 **ON_NOTIFY_REFLECT** 컨트롤 창의 메시지 맵에 추가 하 여 매크로 `ON_NOTIFY` 매크로를 부모 창의 메시지 맵에 있습니다. 참조 [트리 컨트롤 알림 메시지](../mfc/tree-control-notification-messages.md) 이 항목 뒷부분의 가능한 알림 목록에 대 한 합니다.  
  
-   다양한 Set 멤버 함수를 호출하여 컨트롤에 대한 값을 설정합니다. 만들 수 있는 변경 내용 들여쓰기를 설정 하 고 텍스트, 이미지 또는 항목에 연결 된 데이터 변경에 포함 됩니다.  
  
-   다양 한 Get 함수를 사용 하 여 컨트롤의 내용을 검사할 수 있습니다. 부모, 자식 및 형제는 지정 된 항목에 대 한 핸들을 검색할 수 있도록 하는 함수가 있는 트리 컨트롤의 콘텐츠를 이동할 수 있습니다. 특정 노드의 자식을 정렬할 수 있습니다.  
  
-   컨트롤과 마친 경우 제대로 소멸 되었는지 확인 합니다. 이 뷰일 경우 또는 트리 컨트롤이 대화 상자에 있으면 해당 및 `CTreeCtrl` 개체는 자동으로 제거 됩니다. 그렇지 않은 경우 컨트롤 및 `CTreeCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

