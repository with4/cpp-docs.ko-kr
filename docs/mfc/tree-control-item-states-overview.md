---
title: 트리 컨트롤 항목 상태 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- states, CTreeCtrl items
- tree controls [MFC], item states overview
- CTreeCtrl class [MFC], item states
ms.assetid: 2db11ae0-0d87-499d-8c1f-5e0dbe9e94c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0be7a3da4582a80f3001a9bc951276c955191850
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957288"
---
# <a name="tree-control-item-states-overview"></a>트리 컨트롤 항목 상태 개요
트리 컨트롤의 각 항목 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))의 현재 상태가 되었습니다. 예를 들어, 사용 안 함, 확장 등에 항목 선택할 수 있습니다. 대부분의 경우 트리 컨트롤 항목의 선택과 같은 사용자 작업을 반영 하는 항목의 상태를 자동으로 설정 합니다. 그러나 설정할 수도 있습니다 항목의 상태를 사용 하 여는 [SetItemState](../mfc/reference/ctreectrl-class.md#setitemstate) 멤버 함수를 사용 하 여 항목의 현재 상태를 검색 하 고는 [GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate) 멤버 함수입니다. 전체 목록은 항목 상태를 참조 하십시오. [트리 뷰 컨트롤 상수](http://msdn.microsoft.com/library/windows/desktop/bb759985) Windows sdk에서입니다.  
  
 항목의 현재 상태를 지정 하 여는 *nState* 매개 변수입니다. 트리 컨트롤 항목을 선택 하거나 항목에 포커스를 설정 하는 등의 사용자 작업을 반영 하기 위해 항목의 상태를 변경할 수 있습니다. 또한 응용 프로그램을 비활성화 하거나 숨길 항목 또는 오버레이 이미지 또는 상태 이미지를 지정 하려면 항목의 상태를 변경 될 수 있습니다.  
  
 지정 하거나 항목의 상태를 변경 하는 경우는 *nStateMask* 매개 변수를 설정 하려면 비트 상태를 지정 및 *nState* 매개 변수는 해당 비트에 대 한 새 값을 포함 합니다. 다음 예에서는 부모 항목의 현재 상태를 변경 하는 예를 들어 (지정 된 *hParentItem*)에 `CTreeCtrl` 개체 (`m_treeCtrl`)를 `TVIS_EXPANDPARTIAL`:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#71](../mfc/codesnippet/cpp/tree-control-item-states-overview_1.cpp)]  
  
 상태 변경의 또 다른 예로 항목의 오버레이 이미지를 설정할 수 있습니다. 이를 위해 *nStateMask* 포함 되어야 합니다는 `TVIS_OVERLAYMASK` 값 및 *nState* 8 비트를 사용 하 여 왼쪽 이동 된 오버레이 이미지에 1부터 시작 인덱스를 포함 해야 합니다는 [ INDEXTOOVERLAYMASK](http://msdn.microsoft.com/library/windows/desktop/bb761408) 매크로입니다. 인덱스 0을 오버레이 이미지가 없음을 지정 될 수 있습니다. 오버레이 이미지 해야 추가한 오버레이 이미지의 트리 컨트롤의 목록에 대 한 이전 호출에서는 [CImageList::SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage) 함수입니다. 추가할; 이미지의 1부터 시작 인덱스를 지정 하는 함수 INDEXTOOVERLAYMASK 매크로로 사용 되는 인덱스입니다. 트리 컨트롤 오버레이 이미지 4 개까지 가질 수 있습니다.  
  
 항목의 상태 이미지를 설정 하려면 *nStateMask* 포함 되어야 합니다는 `TVIS_STATEIMAGEMASK` 값 및 *nState* 는 1부터 시작 인덱스를 이동 하는 상태 이미지의 왼쪽 12 비트를 사용 하 여 포함 해야 합니다는 [ INDEXTOSTATEIMAGEMASK](http://msdn.microsoft.com/library/windows/desktop/bb775597) 매크로입니다. 인덱스에는 없음 상태 이미지를 지정 하는 0 일 수 있습니다. 이미지 오버레이 및 상태에 대 한 자세한 내용은 참조 [트리 컨트롤 이미지 목록](../mfc/tree-control-image-lists.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

