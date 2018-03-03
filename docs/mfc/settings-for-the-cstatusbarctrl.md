---
title: "CStatusBarCtrl에 대 한 설정을 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CStatusBarCtrl
dev_langs:
- C++
helpviewer_keywords:
- status bar controls [MFC], settings
- CStatusBarCtrl class [MFC], settings
ms.assetid: adeba0c3-17f3-435c-b140-a57845e9ce49
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 814c12b13333d589cb568c5c637f0fa34956847e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="settings-for-the-cstatusbarctrl"></a>CStatusBarCtrl에 대한 설정
기본 위치는 [CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md) 상태 창은 부모 창의 아래쪽을 따라 이지만 지정할 수는 `CCS_TOP` 부모 창의 클라이언트 영역 위쪽에서 열지를 스타일입니다.  
  
 지정할 수 있습니다는 **SBARS_SIZEGRIP** 스타일의 오른쪽 끝에 크기 조정 그립을 포함 하는 `CStatusBarCtrl` 상태 창입니다. 크기 조정 그립 크기 조정 테두리;에 대해 비슷합니다. 해당 사용자를 클릭 하 고 끌어 부모 창의 크기를 조정할 수 있는 사각형 영역입니다.  
  
> [!NOTE]
>  함께 사용 하면는 `CCS_TOP` 및 **SBARS_SIZEGRIP** 스타일, 결과 크기 조정 그립 제대로 작동 하지 않는 있지만 시스템 상태 창에 그립니다.  
  
 상태 창에 대 한 창 프로시저는 자동으로 초기 크기와 컨트롤 창의 위치를 설정합니다. 너비를 부모 창의 클라이언트 영역와 같습니다. 높이 창 테두리의 너비 및 현재 상태 창 장치 컨텍스트로 선택 된 글꼴 메트릭에 기반 합니다.  
  
 창 프로시저는 자동으로 상태 창의 크기를 조정 받을 때마다는 `WM_SIZE` 메시지입니다. 일반적으로 부모 창 크기가 변경 되는 경우 부모 보냅니다는 `WM_SIZE` 상태 창에 메시지입니다.  
  
 호출 하 여 상태 창 그리기 영역의의 최소 높이 설정할 수 있습니다 [SetMinHeight](../mfc/reference/cstatusbarctrl-class.md#setminheight), 최소 높이 지정 하는 픽셀 단위의 합니다. 그리기 영역 창 테두리를 포함 하지 않습니다.  
  
 호출 하 여 상태 창 테두리의 너비를 검색할 [GetBorders](../mfc/reference/cstatusbarctrl-class.md#getborders)합니다. 이 멤버 함수는 가로 테두리, 세로 테두리 및 사각형 사이의 테두리의 너비를 수신 하는 요소가 3 개인 배열에 대 한 포인터를 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStatusBarCtrl 사용](../mfc/using-cstatusbarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

