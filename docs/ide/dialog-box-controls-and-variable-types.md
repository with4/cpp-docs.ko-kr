---
title: "대화 상자 컨트롤 및 변수 형식 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 744b9da2db456a72ed386806d8a4aa34c5942f69
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-box-controls-and-variable-types"></a>대화 상자 컨트롤 및 변수 형식
사용할 수는 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md) MFC를 사용 하 여 만든 대화 상자 컨트롤 멤버 변수를 추가 합니다. 멤버 변수를 추가 하는 컨트롤의 형식 대화 상자에 표시 되는 옵션을 결정 합니다.  
  
 다음 표에서 MFC에서 지원 되는 모든 대화 상자 컨트롤 형식에 설명 하며 [대화 상자 편집기](../windows/dialog-editor.md)는 사용할 수 있는 형식 및 값입니다.  
  
|Control|컨트롤 형식|제어 변수 형식|변수 값 형식|최소/최대 값 (값 형식에만 해당)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|애니메이션 컨트롤|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
|단추|단추|[CButton](../mfc/reference/cbutton-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
|확인란|확인|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|최소값/최대값|  
|콤보 상자|콤보 상자|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|최대 문자|  
|날짜 시간 선택 컨트롤|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|최소값/최대값|  
|편집 상자|편집|[CEdit](../mfc/reference/cedit-class.md)|`CString`int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime`, 또는 **COleCurrency**|최소값/최대값입니다. 일부 지원 최대 문자|  
|바로 가기 키 컨트롤|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
|목록 상자|목록 상자|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|최대 문자|  
|목록 컨트롤|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
|MonthCalendar 컨트롤|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|최소값/최대값|  
|Progress 컨트롤|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
|서식 있는 편집 2 컨트롤|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|최대 문자|  
|Rich Edit 컨트롤|RICHEDIT|`CRichEditCtrl`|`CString`|최대 문자|  
|(가로 또는 세로 스크롤 막대|스크롤 막대|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|최소값/최대값|  
|Slider 컨트롤|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|최소값/최대값|  
|Spin 컨트롤|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
|탭 컨트롤|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
|트리 컨트롤|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|해당 항목이 없습니다. 컨트롤에만|N/A|  
  
## <a name="see-also"></a>참고 항목  
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)