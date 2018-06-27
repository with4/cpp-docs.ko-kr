---
title: 트리 컨트롤 끌어서 드롭 작업 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73aa47a2d888c88dd58d114dd4f5ca9a3f086cd3
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956254"
---
# <a name="tree-control-drag-and-drop-operations"></a>트리 컨트롤 끌어서 드롭 작업
트리 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 항목을 끌기 시작할 때 알림을 보냅니다. 컨트롤에서 보냅니다는 [TVN_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) 마우스 왼쪽된 단추와 항목을 끌기 시작할 때 알림 메시지 및 [TVN_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) 알림 메시지를 끌기 시작할 때 마우스 오른쪽 단추로 합니다. 트리 컨트롤 트리 컨트롤 TVS_DISABLEDRAGDROP 스타일을 지정 하 여 이러한 알림을 보내지 못하도록 방지할 수 있습니다.  
  
 호출 하 여 끌기 작업 중에 표시할 이미지를 가져올는 [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) 멤버 함수입니다. 트리 컨트롤 끌고 항목의 레이블을 기반으로 끌기 비트맵을 만듭니다. 트리 컨트롤 이미지 목록 만들어, 비트맵을 추가 하 고에 대 한 포인터를 반환 합니다. 그런 다음는 [CImageList](../mfc/reference/cimagelist-class.md) 개체입니다.  
  
 실제로 항목을 끄는 하는 코드를 제공 해야 합니다. 이미지 목록 기능 끌기 기능을 사용 하 고 처리 하는 [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) 및 [WM_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) (또는 [WM_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)) 끌기 작업이 시작 된 이후에 전송 된 메시지입니다. 이미지 목록 함수에 대 한 자세한 내용은 참조 [CImageList](../mfc/reference/cimagelist-class.md) 에 *MFC 참조* 및 [이미지 목록](http://msdn.microsoft.com/library/windows/desktop/bb761389) Windows sdk에서입니다. 트리 컨트롤 항목을 끌어 하는 방법에 대 한 자세한 내용은 참조 [트리 뷰 항목을 끌어](http://msdn.microsoft.com/library/windows/desktop/bb760017), 또한는 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
 트리 컨트롤의 항목에는 끌어서 놓기 작업의 대상이 될 않을 경우 대상 항목 위에 마우스 커서를 가져갈 때 알아야 해야 합니다. 호출 하 여 확인할 수 있습니다는 [HitTest](../mfc/reference/ctreectrl-class.md#hittest) 멤버 함수입니다. 지점 및 정수 또는의 주소를 지정 된 [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) 마우스 커서의 현재 좌표를 포함 하는 구조입니다. 함수가 반환할 때 정수 또는 구조 트리 컨트롤을 기준으로 마우스 커서의 위치를 나타내는 플래그를 포함 합니다. 커서가 트리 컨트롤의 항목 위에 있는 경우 구조 항목에도의 핸들을 포함 합니다.  
  
 항목은 호출 하 여 끌어서 놓기 작업의 대상 나타낼 수 있습니다는 [SetItem](../mfc/reference/ctreectrl-class.md#setitem) 상태를 설정 하려면 멤버 함수는 `TVIS_DROPHILITED` 값입니다. 이 상태에 있는 항목을 끌어서 놓기 대상을 나타내는 데 사용 된 스타일에 그려집니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

