---
title: 트리 컨트롤 항목 정보 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 724e9d7c4e0ee7db80f024c30e363612cb40fed1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-item-information"></a>트리 컨트롤 항목 정보
트리 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 컨트롤의 항목에 대 한 정보를 검색 하는 멤버 함수의 수를 포함 합니다. [GetItem](../mfc/reference/ctreectrl-class.md#getitem) 멤버 함수 항목에 연결 된 데이터의 일부나 전부를 검색 합니다. 이 데이터 항목의 텍스트, 상태, 이미지, 하위 항목의 수 및 32 비트 응용 프로그램 정의 데이터 값에 포함 될 수 있습니다. 또한 한 [SetItem](../mfc/reference/ctreectrl-class.md#setitem) 항목에 연결 된 데이터의 일부나 전부를 설정할 수 있는 함수입니다.  
  
 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate), [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext), [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata), 및 [GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage) 의 개별 특성을 검색 하는 멤버 함수는 항목입니다. 이러한 각 함수에는 해당 집합 함수는 항목의 특성을 설정 합니다.  
  
 [GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem) 멤버 함수는 현재 항목에 지정된 된 관계를 갖는 트리 컨트롤 항목을 검색 합니다. 이 함수 및 검색할 수는 항목의 부모, 표시 되는 다음 또는 이전 항목는 첫 번째 자식 항목 등. 트리를 탐색 하는 멤버 함수는 또한: [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem), [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem), [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem), [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem), [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem), [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem), [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem), [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem), [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem), 및 [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem)합니다.  
  
 [GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect) 멤버 함수는 트리 컨트롤 항목에 대 한 경계 사각형을 검색 합니다. [GetCount](../mfc/reference/ctreectrl-class.md#getcount) 및 [GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount) 트리 컨트롤의 항목 수 및 현재 표시 된 트리 컨트롤의 창에 각각 있는 항목의 개수를 검색 하는 멤버 함수입니다. 호출 하 여 특정 항목이 표시 되는지 확인할 수 있습니다는 [EnsureVisible](../mfc/reference/ctreectrl-class.md#ensurevisible) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

