---
title: 도구 모음 컨트롤에서 드롭다운 단추 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
dev_langs:
- C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e76db0bacd7984c97fd8e2696b3543f6e9bf66b
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953245"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>도구 모음 컨트롤에서 드롭다운 단추 사용
표준 누름 단추 외에도 도구 모음에는 드롭다운 단추 있을 수도 있습니다. 드롭 다운 단추는 연결 된 아래쪽 화살표를 통해 일반적으로 표시 됩니다.  
  
> [!NOTE]
>  연결 된 아래쪽 화살표는 확장 스타일 TBSTYLE_EX_DRAWDDARROWS 설정 된 경우에 표시 됩니다.  
  
 이 화살표 (또는 단추 자체 없는 화살표 있는 경우)에서 사용자가 도구 모음 컨트롤의 부모에 TBN_DROPDOWN 알림 메시지가 보내집니다. 그런 다음이 알림 메시지를 처리 하 고 팝업 메뉴; 표시할 수 있습니다. Internet Explorer의 동작과 비슷합니다.  
  
 다음 절차에는 팝업 메뉴가 있는 드롭 다운 도구 모음 단추를 구현 하는 방법을 보여 줍니다.  
  
### <a name="to-implement-a-drop-down-button"></a>드롭다운 단추를 구현 하려면  
  
1.  한 번에 `CToolBarCtrl` 개체를 만들고, 다음 코드를 사용 하 여 TBSTYLE_EX_DRAWDDARROWS 스타일을 설정 합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  에 대 한 새로운 TBSTYLE_DROPDOWN 스타일을 설정 ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) 또는 [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) 또는 기존 ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) 단추가 드롭 다운 단추입니다. 다음 예제에서는 기존 단추에서 수정 된 `CToolBarCtrl` 개체:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  도구 모음 개체의 부모 클래스에 TBN_DROPDOWN 처리기를 추가 합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  새 처리기에서 적절 한 팝업 메뉴를 표시 합니다. 다음 코드는 메서드가 두 개를 보여줍니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

