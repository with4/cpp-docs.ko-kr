---
title: 도구 모음 컨트롤에서 이미지 목록 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- toolbar controls [MFC], image
- image lists [MFC], toolbar controls
- CToolBarCtrl class [MFC], image lists
ms.assetid: ccbe8df4-4ed9-4b54-bb93-9a1dcb3b97eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 76325d2b078f51860cad7fa3fab61ed7c518a41c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382852"
---
# <a name="using-image-lists-in-a-toolbar-control"></a>도구 모음 컨트롤에서 이미지 목록 사용
기본적으로 도구 모음 컨트롤의 단추를 사용 하는 이미지는 단일 비트맵으로 저장 됩니다. 그러나 일련의 이미지 목록에도 단추 이미지를 저장할 수 있습니다. 도구 모음 컨트롤 개체는 최대 세 개의 별도 이미지 목록을 사용할 수 있습니다.:  
  
-   이미지 목록 Contains 이미지를 현재 사용할 수 있는 도구 모음 단추에 사용할 수 있습니다.  
  
-   이미지 목록 현재 해제 되어 있는 도구 모음 단추에 대 한 이미지를 포함을 사용할 수 없습니다.  
  
-   현재 강조 표시 하는 도구 모음 단추에 대 한 이미지 목록 Contains 이미지를 강조 표시 됩니다. 도구 모음을 사용 하는 경우에이 이미지 목록을 사용 하 여 **TBSTYLE_FLAT** 스타일입니다.  
  
 사용 하 여 연결 하면 이러한 이미지 목록은 도구 모음 컨트롤에서 사용 되는 `CToolBarCtrl` 개체입니다. 호출 하 여이 연결이 이루어집니다 [CToolBarCtrl::SetImageList](../mfc/reference/ctoolbarctrl-class.md#setimagelist), [SetDisabledImageList](../mfc/reference/ctoolbarctrl-class.md#setdisabledimagelist), 및 [SetHotImageList](../mfc/reference/ctoolbarctrl-class.md#sethotimagelist)합니다.  
  
 MFC 사용 하 여 기본적으로는 `CToolBar` MFC 응용 프로그램 도구 모음을 구현 하는 클래스입니다. 그러나는 `GetToolBarCtrl` 멤버 함수는 포함 된 검색에 사용할 수 있습니다 `CToolBarCtrl` 개체입니다. 다음에 대 한 호출을 만들 수 있습니다 `CToolBarCtrl` 반환된 된 개체를 사용 하 여 멤버 함수입니다.  
  
 다음 예제에서는 활성화 된 할당 하 여이 기술을 보여 줍니다 (`m_ToolBarImages`)과 사용 안 함 (`m_ToolBarDisabledImages`) 이미지 목록의 `CToolBarCtrl` 개체 (`m_ToolBarCtrl`).  
  
 [!code-cpp[NVC_MFCControlLadenDialog#35](../mfc/codesnippet/cpp/using-image-lists-in-a-toolbar-control_1.cpp)]  
  
> [!NOTE]
>  도구 모음 개체에 의해 사용 되는 이미지 목록을 영구 개체 여야 합니다. 이러한 이유로 일반적으로 MFC 클래스;의 데이터 멤버 이 예제에서는 주 프레임 창 클래스  
  
 이미지 목록은 연결 된 후의 `CToolBarCtrl` 개체, 프레임 워크는 해당 단추 이미지를 자동으로 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CToolBarCtrl 사용](../mfc/using-ctoolbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

