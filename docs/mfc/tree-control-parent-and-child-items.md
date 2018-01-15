---
title: "트리 컨트롤 부모 및 자식 항목 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: feaf59932da66be2bf269316c7ee9587d4037b3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-parent-and-child-items"></a>트리 컨트롤 부모 및 자식 항목
트리 컨트롤의 모든 항목 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 연결 된 자식 항목 이라고 하는 하위 항목의 목록을 사용할 수 있습니다. 하나 이상의 자식 항목이 포함 된 항목을 부모 항목을 라고 합니다. 자식 항목을 해당 부모 항목 아래에 표시 되 고 부모에 종속 되었음을 나타내기 위해 들여쓰게 됩니다. 부모가 없는 항목은 계층의 최상위에 있으며은 루트 항목 이라고 합니다.  
  
 지정된 된 시간에 하위 항목의 부모 항목의 목록의 상태 수 중 하나 확장 하거나 축소할 수 있습니다. 상태 확장 되 면 자식 항목이 부모 항목 아래에 표시 됩니다. 축소 된 경우에 자식 항목이 표시 되지 않습니다. 목록 확장 / 축소 된 상태 간의 부모 항목을 두 번 클릭할 때 또는 부모 있으면 자동으로 전환 된 **TVS_HASBUTTONS** 스타일을 사용자가 부모 항목에 연결 된 단추를 클릭 합니다. 응용 프로그램 확장 하거나 자식 항목을 사용 하 여 축소할 수는 [확장](../mfc/reference/ctreectrl-class.md#expand) 멤버 함수입니다.  
  
 호출 하 여 트리 컨트롤에 항목을 추가 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) 멤버 함수입니다. 핸들을 반환 하는이 함수는 **HTREEITEM** 형식 항목을 고유 하 게 식별 합니다. 항목을 추가할 때 새 항목의 부모 항목의 핸들을 지정 해야 합니다. 지정 하는 경우 **NULL** 또는 **TVI_ROOT** 값에 대 한 부모 항목 핸들 대신는 [TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452) 구조 또는 `hParent` 매개 변수를 항목을 추가 하면 루트 항목입니다.  
  
 트리 컨트롤에서 보냅니다는 [TVN_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537) 알림 메시지 되려고 할 때 하위 항목의 부모 항목의 목록을 확장 하거나 축소할 수 있습니다. 알림의 통해 변경 되지 않도록 하거나의 자식 항목 목록의 상태에 종속 된 부모 항목의 특성을 설정할 수 있습니다. 트리 컨트롤은 목록의 상태를 변경한 후 보냅니다는 [TVN_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533) 알림 메시지입니다.  
  
 자식 항목 목록이 확장 되 면 부모 항목을 기준으로 들여씁니다. 들여쓰기 크기를 사용 하 여 설정할 수 있습니다는 [SetIndent](../mfc/reference/ctreectrl-class.md#setindent) 현재 크기를 사용 하 여 검색 또는 멤버 함수는 [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

