---
title: 컨트롤에 항목 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding items
ms.assetid: 715994bd-340d-4ad2-9882-411654137830
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eab0c7cb1aebf1675d078aa99941edfd9afdc5a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-items-to-the-control"></a>컨트롤에 항목 추가
목록 컨트롤에 항목을 추가 하려면 ([CListCtrl](../mfc/reference/clistctrl-class.md))의 여러 버전 중 하나를 호출 하는 [InsertItem](../mfc/reference/clistctrl-class.md#insertitem) 있는 정보에 따라 멤버 함수입니다. 한 버전에서는 [LV_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 준비 하는 구조입니다. 때문에 `LV_ITEM` 구조에 많은 멤버가 포함 되어, 목록 컨트롤 항목의 특성에 대 한 제어 강화 해야 합니다.  
  
 두 가지 중요 한 멤버 (관련 하 여 보고서 뷰)는 `LV_ITEM` 구조는 `iItem` 및 `iSubItem` 멤버입니다. `iItem` 멤버는 구조를 참조 하는 항목의 0부터 시작 인덱스와 `iSubItem` 구조 항목에 대 한 정보를 포함 하는 경우 구성원은 1부터 시작 인덱스는 하위 항목 또는 0입니다. 이러한 두 멤버를 확인 항목, 유형 및 목록 컨트롤은 보고서 뷰에서 때 표시 되는 하위 항목 정보의 값 당 합니다. 자세한 내용은 참조 [CListCtrl::SetItem](../mfc/reference/clistctrl-class.md#setitem)합니다.  
  
 추가 멤버는 해당 항목의 텍스트, 아이콘, 상태 및 항목 데이터를 지정합니다. "데이터 항목" 목록 뷰 항목에 연결 된 응용 프로그램 정의 값입니다. 에 대 한 자세한 내용은 `LV_ITEM` 구조, 참조 [CListCtrl::GetItem](../mfc/reference/clistctrl-class.md#getitem)합니다.  
  
 다른 버전의 `InsertItem` 하나 이상의 별도 값, 멤버에 해당 하는 `LV_ITEM` 구조를 지원 하려면 해당 멤버만 초기화할 수 있도록 합니다. 일반적으로 목록 항목에 대 한 저장소를 관리 하는 목록 컨트롤 하지만에 저장할 수 있습니다는 정보 중 일부 응용 프로그램 대신 "콜백 항목입니다."를 사용 하 여 자세한 내용은 참조 [콜백 항목 및 콜백 마스크](../mfc/callback-items-and-the-callback-mask.md) 이 항목의 및 [콜백 항목 및 콜백 마스크](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows sdk에서입니다.  
  
 자세한 내용은 참조 [목록 뷰 항목 추가 및 하위 항목](http://msdn.microsoft.com/library/windows/desktop/bb774736)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

