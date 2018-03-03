---
title: "스핀 단추 스타일 | Microsoft Docs"
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
- styles [MFC], CSpinButtonCtrl
- CSpinButtonCtrl class [MFC], styles
- styles [MFC], spin button control
- spin button control, styles
ms.assetid: fb4a7f6f-9182-47be-bccf-0728fdc5332f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa4b2ae42175e2d4fc2ddb3317ef76b6b4dec8d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="spin-button-styles"></a>스핀 단추 스타일
스핀 단추에 대 한 설정의 많은 ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) 스타일에 의해 제어 됩니다. 사용 하 여 다음 스타일을 설정할 수 있습니다는 **속성** 대화 상자 편집기의 창.  
  
-   **방향** 세로 또는 가로입니다. 화살표 단추 방향을 제어합니다. 연관 된 `UDS_HORZ` 스타일입니다.  
  
-   **맞춤** 연결 되지 않은 왼쪽 또는 오른쪽 중 하나입니다. 스핀 단추 위치를 제어합니다. 왼쪽 및 오른쪽 버디 창 옆에 있는 스핀 단추를 놓습니다. 스핀 단추를 수용 하기 위해 버디 창의 너비 감소 합니다. 연관 된 `UDS_ALIGNLEFT` 및 `UDS_ALIGNRIGHT` 스타일입니다.  
  
-   **Auto Buddy** 스핀 단추에 대 한 버디 창으로 콤보 상자의 이전 창을 Z-순서에서 자동으로 선택 합니다. 대화 상자 템플릿을 스핀 단추 탭 순서에서 앞에 표시 되는 컨트롤입니다. 연관 된 `UDS_AUTOBUDDY` 스타일입니다.  
  
-   **Buddy Integer 설정** spin 컨트롤을 현재 위치 변경 될 때 버디 창의 캡션을 줄입니다. 연관 된 `UDS_SETBUDDYINT` 스타일입니다.  
  
-   **No Thousands** 1000을 삽입 하지 않습니다 버디 창의 캡션의 값에 구분 기호입니다. 연관 된 `UDS_NOTHOUSANDS` 스타일입니다.  
  
    > [!NOTE]
    >  Buddy 컨트롤에서 정수 값을 대화 상자 데이터 교환 (DDX)를 사용 하려는 경우에이 스타일을 설정 합니다. `DDX_Text`포함 된 천 구분 기호를 허용 하지 않습니다.  
  
-   **줄 바꿈** "로 줄 바꿈할" 값이 증가 하거나 감소 하는 컨트롤의 범위를 넘어 위치가 있습니다. 연관 된 `UDS_WRAP` 스타일입니다.  
  
-   **화살표 키** 스핀 단추 위쪽 화살표 및 아래쪽 화살표 키를 누를 때 늘이거나 줄일 위치를 사용 하면 됩니다. 연관 된 `UDS_ARROWKEYS` 스타일입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSpinButtonCtrl 사용](../mfc/using-cspinbuttonctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

