---
title: CStatusBarCtrl 개체의 일부 초기화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- CStatusBarCtrl class [MFC], simple mode
- status bars [MFC], declaring parts of
- simple status bars [MFC]
- status bars [MFC], icons
- status bars [MFC], simple mode
- icons, using in status bars
- CStatusBarCtrl class [MFC], declaring parts of
ms.assetid: 60e8f285-d2d8-424a-a6ea-2fc548370303
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89cea1516924530f821003affd96e2848687882b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344346"
---
# <a name="initializing-the-parts-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체의 일부 초기화
기본적으로 상태 표시줄에는 별도 창을 사용 하 여 상태 정보가 표시 됩니다. (부분 라고도 함) 이러한 창의 텍스트 문자열, 아이콘 또는 둘 다 포함할 수 있습니다.  
  
 사용 하 여 [SetParts](../mfc/reference/cstatusbarctrl-class.md#setparts) 개수 부분 및 길이 정의 하려면 상태 표시줄을 갖습니다. 상태 표시줄의 부분을 만든 후에 확인에 대 한 호출 [SetText](../mfc/reference/cstatusbarctrl-class.md#settext) 및 [SetIcon](../mfc/reference/cstatusbarctrl-class.md#seticon) 텍스트 또는 상태 표시줄의 특정 부분에 대 한 아이콘을 설정 합니다. 부품 성공적으로 설정 되 면 컨트롤이 자동으로 그려집니다.  
  
 다음 예제에서는 기존 초기화 `CStatusBarCtrl` 개체 (`m_StatusBarCtrl`) 4 개의 창으로 다음 두 번째 부분에서 (IDI_ICON1) 아이콘 및 일부 텍스트를 설정 합니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#31](../mfc/codesnippet/cpp/initializing-the-parts-of-a-cstatusbarctrl-object_1.cpp)]  
  
 모드 설정에 대 한 자세한 내용은 `CStatusBarCtrl` 단순, 참조에 개체 [CStatusBarCtrl 개체의 모드 설정](../mfc/setting-the-mode-of-a-cstatusbarctrl-object.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

