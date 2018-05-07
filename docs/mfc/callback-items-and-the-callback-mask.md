---
title: 콜백 항목 및 콜백 마스크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- callback items in CListCtrl class [MFC]
- CListCtrl class [MFC], callback item and callback mask
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95c896308970ffc6a2040657927dc127eee278ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="callback-items-and-the-callback-mask"></a>콜백 항목 및 콜백 마스크
각각의 해당 항목에 대 한 목록 뷰 컨트롤 레이블 텍스트를 항목의 아이콘의 이미지 목록 인덱스를 일반적으로 저장 하 고 항목의 상태에 대 한 플래그 비트의 집합입니다. 응용 프로그램에 이미 일부 항목에 대 한 정보를 저장 하는 경우에 유용 하는 콜백 항목이으로 개별 항목을 정의할 수 있습니다.  
  
 에 대 한 적절 한 값을 지정 하 여 콜백 항목으로 항목을 정의 `pszText` 및 `iImage` 의 멤버는 **LV_ITEM** 구조 (참조 [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)). 항목의 또는 하위 항목의 텍스트를 관리 하는 응용 프로그램의 경우 지정 된 **LPSTR_TEXTCALLBACK** 에 대 한 값는 `pszText` 멤버입니다. 응용 프로그램은 항목에 대 한 아이콘을 하는 경우 지정는 **I_IMAGECALLBACK** 에 대 한 값은 `iImage` 멤버입니다.  
  
 콜백 항목을 정의 하는 것 외에도 컨트롤의 콜백 마스크를 수정할 수 있습니다. 이 마스크는 컨트롤을 보다는 응용 프로그램을 현재 데이터를 저장 하는 항목 상태를 지정 하는 비트 플래그 집합입니다. 콜백 마스크 모든 특정 항목에 적용 되는 콜백 항목 지정 달리 컨트롤의 항목에 적용 됩니다. 콜백 마스크는 0이 기본적으로 컨트롤이 모든 항목 상태를 추적 합니다. 이 기본 동작을 변경 하려면 다음 값의 조합으로 마스크를 초기화 합니다.  
  
-   `LVIS_CUT` 잘라내기 및 붙여넣기 작업에 대 한 항목이 표시 됩니다.  
  
-   `LVIS_DROPHILITED` 끌어서 놓기 대상으로 항목 강조 표시 됩니다.  
  
-   `LVIS_FOCUSED` 항목에 포커스가 있습니다.  
  
-   `LVIS_SELECTED` 항목이 선택 되어 있습니다.  
  
-   **LVIS_OVERLAYMASK** 응용 프로그램이 각 항목에 대 한 현재 오버레이 이미지의 이미지 목록 인덱스를 저장 합니다.  
  
-   **LVIS_STATEIMAGEMASK** 응용 프로그램이 각 항목에 대 한 현재 상태 이미지의 이미지 목록 인덱스를 저장 합니다.  
  
 검색 하 고이 마스크 설정에 자세한 내용은 참조 하십시오. [CListCtrl::GetCallbackMask](../mfc/reference/clistctrl-class.md#getcallbackmask) 및 [CListCtrl::SetCallbackMask](../mfc/reference/clistctrl-class.md#setcallbackmask)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

