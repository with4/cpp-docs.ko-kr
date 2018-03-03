---
title: "스핀 단추 멤버 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6f0abfd5803ea4b4d4b4478104790e0f56e5afc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="spin-button-member-functions"></a>스핀 단추 멤버 함수
spin 컨트롤에 사용할 수 있는 여러 멤버 함수 ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). 이러한 함수를 사용 하 여 스핀 단추의 다음 특성을 변경 해야 합니다.  
  
-   **가속** 화살표 단추를 누르고 때 위치 변경 내용을 비율을 조정할 수 있습니다. 가속을 사용 하려면 사용 하 여는 [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) 및 [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) 멤버 함수입니다.  
  
-   **기본** 버디 창 캡션에 위치를 표시 하는 데 기본 (10 또는 16)을 변경할 수 있습니다. 기본 작업을 하려면 사용 된 [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) 및 [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) 멤버 함수입니다.  
  
-   **버디 창** 버디 창의 동적으로 설정할 수 있습니다. 쿼리하거나 변경는 컨트롤의 버디 창 사용는 [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) 및 [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) 멤버 함수입니다.  
  
-   **위치** 쿼리 하 고 위치를 변경할 수 있습니다. 사용 위치를 직접 작업 하는 [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) 및 [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) 멤버 함수입니다. 동료 컨트롤의 캡션 (예를 들어 경우에는 친구는 편집 컨트롤) 변경 있을 수도 있으므로 `GetPos` 현재 캡션을 검색 하 고 그에 따라 위치를 조정 합니다.  
  
-   **범위** 스핀 단추에 대 한 최대 및 최소 위치를 변경할 수 있습니다. 기본적으로 최대값은 0으로 설정 하 고 최소 100으로 설정 됩니다. 기본 최대값 기본 최소값 보다 작기 때문 화살표 단추로 동작은 비 직관적인 합니다. 사용 하 여 범위를 설정 합니다는 일반적으로 [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 멤버 함수입니다. 쿼리 범위를 사용 하려면 [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSpinButtonCtrl 사용](../mfc/using-cspinbuttonctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

