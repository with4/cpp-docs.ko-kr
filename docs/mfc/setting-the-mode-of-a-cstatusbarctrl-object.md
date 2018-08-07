---
title: CStatusBarCtrl 개체의 모드 설정 | Microsoft Docs
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
- simple mode and status bar controls
- IsSimple method, using
- SetSimple method [MFC]
- status bar controls [MFC], simple and nonsimple modes
- non-simple mode and status bar controls
- CStatusBarCtrl class [MFC], simple and nonsimple modes
ms.assetid: ca6076e5-1501-4e33-8d35-9308941e46c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdad5073b3f566ad43d25258ca0b5e173f52fb57
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956813"
---
# <a name="setting-the-mode-of-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체의 모드 설정
두 가지 방식에 대 한는 `CStatusBarCtrl` 개체: 단순 및 비 단순 합니다. 대부분의 경우 상태 표시줄 컨트롤이 텍스트와 아이콘이 나 아이콘 함께 하나 이상의 파트를 갖습니다. 이 비 단순 모드를 라고 합니다. 이 모드에 대 한 자세한 내용은 참조 하십시오. [CStatusBarCtrl 개체의 일부 초기화](../mfc/initializing-the-parts-of-a-cstatusbarctrl-object.md)합니다.  
  
 그러나만 해야 하는 경우 텍스트 한 줄을 표시 하려면 있습니다. 이 경우 단순 모드는 충분 합니다. 모드를 변경 하는 `CStatusBarCtrl` simple로 개체를 호출 하는 [SetSimple](../mfc/reference/cstatusbarctrl-class.md#setsimple) 멤버 함수입니다. 단순 모드에서 상태 표시줄 컨트롤을 호출 하 여 텍스트를 설정의 `SetText` 255에 대 한 값으로 전달 되는 멤버 함수는 *nPane* 매개 변수입니다.  
  
 사용할 수 있습니다는 [IsSimple](../mfc/reference/cstatusbarctrl-class.md#issimple) 하는 모드를 결정 하는 함수는 `CStatusBarCtrl` 개체입니다.  
  
> [!NOTE]
>  및로 단순, 상태 표시줄 개체가 단순 하지 않고에서 변경 하거나 그 반대로 창을 즉시 다시 그려집니다 경우 해당 하는 경우, 정의 된 모든 부분이 자동으로 복원 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

