---
title: "(보고서 뷰) 컨트롤에 열을 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c08a497b80b01523dd66bb02b657d611193ed11c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-columns-to-the-control-report-view"></a>컨트롤에 열 추가(보고서 뷰)
> [!NOTE]
>  다음 절차 중 하나에 적용 한 [CListView](../mfc/reference/clistview-class.md) 또는 [CListCtrl](../mfc/reference/clistctrl-class.md) 개체입니다.  
  
 목록 컨트롤 보고서 뷰에 있는 경우 각 목록 컨트롤 항목의 다양 한 하위 항목을 구성 하는 방법 열 표시 됩니다. 이 조직은 목록 컨트롤 항목의 연결 된 하위 항목 및 목록 컨트롤의 열 간에 일대일로 대응으로 구현 됩니다. 하위 항목에 대 한 자세한 내용은 참조 하십시오. [컨트롤에 항목 추가](../mfc/adding-items-to-the-control.md)합니다. Windows 95 및 Windows 98 탐색기의 세부 정보 보기에서 보고서 보기에서는 목록 컨트롤의 예로 제공 됩니다. 첫 번째 열에는 폴더, 파일 아이콘 및 레이블 나열 됩니다. 다른 열 파일 크기, 파일 형식, 마지막으로 수정한 날짜 및 등을 나열 합니다.  
  
 컨트롤에 있는 경우에는 열을 볼 수 있지만 언제 든 지는 목록 컨트롤에 열을 추가할 수 있습니다는 `LVS_REPORT` 스타일 비트가 설정 되어 있습니다.  
  
 각 열에 연관 된 헤더 항목 (참조 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) 열의 레이블을 지정 하 고 사용자가 열의 크기를 조정할 수 있도록 하는 개체입니다.  
  
 목록 컨트롤에서 보고서 보기를 지 원하는 경우에 목록 컨트롤 항목에 각 하위 항목에 대 한 열을 추가 해야 합니다. 열을 준비 함으로써 추가 [LV_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) 구조와 다음에 대 한 호출을 만드는 [열 삽입](../mfc/reference/clistctrl-class.md#insertcolumn)합니다. 필요한 열 (헤더 항목 이라고 함)를 추가한 후 다시 정렬할 수 있습니다 이러한 멤버 함수 및 포함된 된 헤더 컨트롤에 속한 스타일을 사용 하 여 합니다. 자세한 내용은 참조 [헤더 컨트롤의 항목 순서 지정](../mfc/ordering-items-in-the-header-control.md)합니다.  
  
> [!NOTE]
>  목록 컨트롤을으로 만들 경우는 **LVS_NOCOLUMNHEADER** 스타일과 열을 삽입 하려는 시도 무시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

