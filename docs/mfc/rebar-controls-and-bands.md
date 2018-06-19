---
title: Rebar 컨트롤 및 밴드 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1fac5f83f19fab37604a14e239cf505891c737f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349853"
---
# <a name="rebar-controls-and-bands"></a>Rebar 컨트롤 및 밴드
Rebar 컨트롤의 주 목적은 자식 창, 공용 대화 상자 컨트롤, 메뉴, 도구 모음, 등에 대 한 컨테이너 역할을 하는 것입니다. 이 포함 된 "밴드"의 개념으로 사용할 수 각 rebar 밴드에는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창의 조합을 포함할 수 있습니다.  
  
 클래스 `CReBarCtrl` 를 검색 하기 위해 사용 하 고 특정 rebar 밴드에 대 한 정보를 조작할 수 있는 많은 멤버 함수에:  
  
-   [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) rebar 컨트롤의 현재 밴드의 수를 검색 합니다.  
  
-   [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) 를 초기화 한 **REBARBANDINFO** 지정된 밴드에서 정보가 포함 된 구조입니다. 해당 하는 [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) 멤버 함수입니다.  
  
-   [GetRect](../mfc/reference/crebarctrl-class.md#getrect) 지정된 밴드의 경계 사각형을 검색 합니다.  
  
-   [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) rebar 컨트롤에서 밴드 행의 수를 검색 합니다.  
  
-   [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) 지정된 밴드의 인덱스를 검색 합니다.  
  
-   [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) 밴드의 테두리를 검색 합니다.  
  
 직접 조작 몇 가지 멤버 함수는 특정 rebar 밴드에서 작동할 수 있도록 하는 제공.  
  
 [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) 및 [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) 추가 및 rebar 밴드를 제거 합니다. [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) 및 [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) 특정 rebar 밴드의 현재 크기에 영향을 줍니다. [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) 특정 rebar 밴드의 인덱스를 변경 합니다. [ShowBand](../mfc/reference/crebarctrl-class.md#showband) 하거나 사용자에 게 서 rebar 밴드를 숨깁니다.  
  
 다음 예제에서는 도구 모음으로 밴드를 추가 하는 방법을 보여 줍니다 (`m_wndToolBar`) 기존 rebar 컨트롤 (`m_wndReBar`). 밴드를 초기화 하 여 설명의 `rbi` 구조와 다음 호출에서 `InsertBand` 멤버 함수:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

