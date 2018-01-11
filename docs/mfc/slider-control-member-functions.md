---
title: "슬라이더 컨트롤 멤버 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1bd6c1d05ce7b137e6153ad2ea3fc5df99565a52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="slider-control-member-functions"></a>슬라이더 컨트롤 멤버 함수
응용 프로그램에 있는 슬라이더 슬라이더 컨트롤에 대 한 정보를 검색할 컨트롤의 멤버 함수를 호출할 수 있습니다 ([CSliderCtrl](../mfc/reference/csliderctrl-class.md))의 특성을 변경할 수 있습니다.  
  
 사용 합니다 (즉, 사용자가 선택한 값) 슬라이더의 위치를 검색할는 [GetPos](../mfc/reference/csliderctrl-class.md#getpos) 멤버 함수입니다. 슬라이더의 위치를 설정 하려면는 [SetPos](../mfc/reference/csliderctrl-class.md#setpos) 멤버 함수입니다. 언제 든 지 사용할 수 있습니다는 `VerifyPos` 멤버 함수를 슬라이더 최소값과 최대값 사이 인지 확인 합니다.  
  
 슬라이더 컨트롤의 범위는 집합 슬라이더 컨트롤을 나타낼 수 있는 인접 하는 값입니다. 대부분의 응용 프로그램에서 사용 하 여는 [SetRange](../mfc/reference/csliderctrl-class.md#setrange) 멤버 함수를 처음 만들 때의 슬라이더 컨트롤의 범위를 설정 합니다. 슬라이더 컨트롤을 사용 하 여 만든 후 응용 프로그램 범위를 동적으로 변경할 수는 [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) 및 [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) 멤버 함수입니다. 일반적으로 동적으로 변경할 수 범위를 허용 하는 응용 프로그램 사용자는 슬라이더 컨트롤과 함께 작업을 마치고 나면 최종 범위 설정을 검색 합니다. 이 설정을 검색 하려면 사용 된 [GetRange](../mfc/reference/csliderctrl-class.md#getrange), [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax), 및 [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) 멤버 함수입니다.  
  
 응용 프로그램이 사용할 수는 `TBS_AUTOTICKS` 을 자동으로 표시 하는 슬라이더 컨트롤의 눈금 표시 스타일입니다. 그러나 응용 프로그램을 위치 또는 눈금 표시의 빈도 제어 하는 경우 멤버 함수의 번호 사용할 수 있습니다.  
  
 눈금 표시의 위치를 설정 하려면 응용 프로그램이 사용할 수는 [SetTic](../mfc/reference/csliderctrl-class.md#settic) 멤버 함수입니다. [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq) 멤버 함수를 통해 눈금 슬라이더 컨트롤의 범위에 일정 한 간격으로 표시 된 표시를 설정 하는 응용 프로그램입니다. 예를 들어 응용 프로그램 1 ~ 100의 범위에만 10 눈금 표시를 표시 하려면이 멤버 함수를 사용할 수 있습니다.  
  
 에 해당 하는 눈금 표시는 범위에서 인덱스를 검색 하려면 사용 된 [GetTic](../mfc/reference/csliderctrl-class.md#gettic) 멤버 함수입니다. [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray) 멤버 함수는 이러한 인덱스의 배열을 검색 합니다. 클라이언트 좌표에서 눈금 표시의 위치를 검색 하려면 사용 된 [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos) 멤버 함수입니다. 응용 프로그램 사용 하 여 눈금 표시의 수를 검색할 수는 [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) 멤버 함수입니다.  
  
 [ClearTics](../mfc/reference/csliderctrl-class.md#cleartics) 슬라이더 컨트롤의 눈금 표시의 모든 멤버 함수를 제거 합니다.  
  
 슬라이더 컨트롤의 행 크기에 따라 결정 슬라이더 응용 프로그램을 받으면를 이동 하는 정도 **TB_LINEDOWN** 또는 **TB_LINEUP** 알림 메시지입니다. 마찬가지로, 페이지 크기에 대 한 응답에 따라 결정 된 **TB_PAGEDOWN** 및 **TB_PAGEUP** 알림 메시지입니다. 응용 프로그램에서 검색 하 고 사용 하 여 행 및 페이지 크기 값을 설정할 수는 [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize), [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize), [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize), 및 [SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize) 멤버 함수입니다.  
  
 응용 프로그램의 슬라이더 컨트롤의 크기를 검색할 수 멤버 함수를 사용할 수 있습니다. [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect) 멤버 함수는 슬라이더에 대 한 경계 사각형을 검색 합니다. [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect) 슬라이더 컨트롤 채널에 대 한 경계 사각형을 검색 하는 멤버 함수입니다. (채널의 영역에 따른은 슬라이더를 이동 하 고 강조를 포함 하는 범위를 선택 합니다.)  
  
 슬라이더 컨트롤에 있는 경우는 `TBS_ENABLESELRANGE` 스타일을 사용자에서 인접 하는 값의 범위를 선택할 수 있습니다. 동적으로 조정 되도록 선택 범위를 허용 하는 멤버 함수는 여러 합니다. [SetSelection](../mfc/reference/csliderctrl-class.md#setselection) 멤버 함수는 시작 및 끝 선택의 위치를 설정 합니다. 응용 프로그램 설정을 사용 하 여 검색할 수 사용자 선택 범위 설정 완료 되 면는 [GetSelection](../mfc/reference/csliderctrl-class.md#getselection) 멤버 함수입니다. 사용자의 선택을 사용 하 여는 [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSliderCtrl 사용](../mfc/using-csliderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

