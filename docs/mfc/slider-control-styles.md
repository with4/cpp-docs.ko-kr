---
title: "슬라이더 컨트롤 스타일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 747f5d55821c6911e80087ebbad65b2169e6fc49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="slider-control-styles"></a>슬라이더 컨트롤 스타일
슬라이더 컨트롤 ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) 세로 또는 가로 방향을 가질 수 있습니다. 어느 쪽에 눈금 표시를 보유할 수 있는 면, 또는 모두 둘 다 합니다. 연속 값의 범위를 지정 하도 사용할 수 있습니다. 이러한 속성은 슬라이더 컨트롤을 만들 때 지정 하는 슬라이더 컨트롤 스타일을 사용 하 여 제어 됩니다.  
  
 `TBS_HORZ` 및 `TBS_VERT` 스타일의 슬라이더 컨트롤의 방향을 결정 합니다. 방향이 지정 하지 않으면 경우 slider 컨트롤 가로 방향입니다.  
  
 `TBS_AUTOTICKS` 스타일 각 증분에 대 한 눈금 표시의 값 범위에 있는 슬라이더 컨트롤을 만듭니다. 이러한 눈금 표시는 호출 하는 경우 자동으로 추가 됩니다는 [SetRange](../mfc/reference/csliderctrl-class.md#setrange) 멤버 함수입니다. 지정 하지 않으면 `TBS_AUTOTICKS`와 같은 멤버 함수를 사용할 수 [SetTic](../mfc/reference/csliderctrl-class.md#settic) 및 [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq), 눈금 표시의 위치를 지정할 수 있습니다. 눈금 표시가 표시 되지 않는 슬라이더 컨트롤을 만들려면 사용할 수 있습니다는 `TBS_NOTICKS` 스타일입니다.  
  
 슬라이더 컨트롤의 양쪽 모두 중 하나 또는 모두에 눈금 표시를 표시할 수 있습니다. 가로 슬라이더 컨트롤에 대 한 지정할 수 있습니다는 `TBS_BOTTOM` 또는 `TBS_TOP` 스타일입니다. 세로 슬라이더 컨트롤에 대 한 지정할 수 있습니다는 `TBS_RIGHT` 또는 `TBS_LEFT` 스타일입니다. (`TBS_BOTTOM` 및 `TBS_RIGHT` 은 기본 설정 합니다.) 양쪽 방향에서 슬라이더 컨트롤의 눈금 표시에 대 한 지정 된 `TBS_BOTH` 스타일입니다.  
  
 슬라이더 컨트롤 지정 하는 경우에 선택 범위를 표시할 수는 `TBS_ENABLESELRANGE` 만들 때 스타일 지정 합니다. 슬라이더 컨트롤에이 스타일을 선택 범위의 시작 및 끝 위치에서 눈금 표시 (세로 대시) 대신 삼각형으로 표시 되 고 선택 영역을 강조 표시 됩니다. 예를 들어, 선택 영역 범위 간단한 예약 응용 프로그램에 유용할 수 있습니다. 사용자는 시간 예정 된 회의 시간을 식별 하는 일에 해당 하는 눈금 표시의 범위를 선택할 수 없습니다.  
  
 기본적으로 슬라이더 컨트롤의 슬라이더의 길이 선택 영역 범위 변경 됨에 따라 달라 집니다. 슬라이더 컨트롤에 있는 경우는 **TBS_FIXEDLENGTH** 스타일을 슬라이더의 길이가 동일 하 게 유지 선택 범위를 변경 하는 경우에 합니다. 에 있는 슬라이더 컨트롤은 **TBS_NOTHUMB** 스타일 슬라이더 포함 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSliderCtrl 사용](../mfc/using-csliderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

