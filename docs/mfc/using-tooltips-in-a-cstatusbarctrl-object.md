---
title: "CStatusBarCtrl 개체에서 도구 설명 사용 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CStatusBarCtrl
dev_langs: C++
helpviewer_keywords:
- tool tips [MFC], using in status bars
- status bars [MFC], tool tips
- CStatusBarCtrl class [MFC], tool tips
ms.assetid: a77597a7-43ef-4b8f-87bc-a8ea1dc63dc3
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf522d17d8abfc4b8dbf53baa24255ab23cfa621
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-tooltips-in-a-cstatusbarctrl-object"></a>CStatusBarCtrl 개체에서 도구 설명 사용
상태 표시줄 컨트롤에 도구 설명을 사용 하려면 만듭니다는 `CStatusBarCtrl` 개체는 **SBT_TOOLTIPS** 스타일입니다.  
  
> [!NOTE]
>  사용 하는 경우는 `CStatusBar` 상태 표시줄 구현를 사용 하는 개체는 `CStatusBar::CreateEx` 함수입니다. 포함 된 항목에 대 한 추가 스타일을 지정할 수 있습니다 **CStatusBarCtrl** 개체입니다.  
  
 한 번의 `CStatusBarCtrl` 개체를 만들고 성공적으로, 사용 하 여 [CStatusBarCtrl::SetTipText](../mfc/reference/cstatusbarctrl-class.md#settiptext) 및 [CStatusBarCtrl::GetTipText](../mfc/reference/cstatusbarctrl-class.md#gettiptext) 설정 하 고 특정 창에 대 한 설명 텍스트를 검색 합니다.  
  
 도구 설명 설정 되 면 파트 내 모든 텍스트를 표시할 수 없는 경우 또는 파트에는 아이콘과 텍스트가 없는 경우에 표시 됩니다. 도구 설명 단순 모드에서 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

