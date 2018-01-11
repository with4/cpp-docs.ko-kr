---
title: "도구 모음 컨트롤에서 드롭다운 단추 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
dev_langs: C++
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01c09cb2bec4b466928557434767ce49948f46ae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>도구 모음 컨트롤에서 드롭다운 단추 사용
표준 누름 단추 외에도 도구 모음에는 드롭다운 단추 있을 수도 있습니다. 드롭 다운 단추는 연결 된 아래쪽 화살표를 통해 일반적으로 표시 됩니다.  
  
> [!NOTE]
>  연결 된 아래쪽 화살표는 경우에 표시 됩니다는 `TBSTYLE_EX_DRAWDDARROWS` 설정 된 확장된 스타일입니다.  
  
 이 화살표 (또는 자체 없는 화살표 있으면 단추)를 클릭 하면 한 `TBN_DROPDOWN` 알림 메시지가 도구 모음 컨트롤의 부모에 전달 됩니다. 그런 다음이 알림 메시지를 처리 하 고 팝업 메뉴; 표시할 수 있습니다. Internet Explorer의 동작과 비슷합니다.  
  
 다음 절차에는 팝업 메뉴가 있는 드롭 다운 도구 모음 단추를 구현 하는 방법을 보여 줍니다.  
  
### <a name="to-implement-a-drop-down-button"></a>드롭다운 단추를 구현 하려면  
  
1.  한 번 프로그램 `CToolBarCtrl` 개체를 만들고, 설정 된 `TBSTYLE_EX_DRAWDDARROWS` 스타일을 다음 코드를 사용 하 여:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]  
  
2.  설정의 `TBSTYLE_DROPDOWN` 새 스타일에 대 한 ([InsertButton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) 또는 [AddButtons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) 또는 기존 ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) 단추가 드롭 다운 단추입니다. 다음 예제에서는 기존 단추에서 수정 된 `CToolBarCtrl` 개체:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]  
  
3.  추가 `TBN_DROPDOWN` 처리기 도구 모음 개체의 부모 클래스입니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]  
  
4.  새 처리기에서 적절 한 팝업 메뉴를 표시 합니다. 다음 코드는 메서드가 두 개를 보여줍니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

