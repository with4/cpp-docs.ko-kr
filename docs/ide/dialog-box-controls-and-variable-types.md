---
title: 대화 상자 컨트롤 및 변수 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls, member variables
- dialog box controls, variable types
- variables, dialog box control member variables
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2fbae37072f50898181334a9059a7dc9c6a83a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33335067"
---
# <a name="dialog-box-controls-and-variable-types"></a>대화 상자 컨트롤 및 변수 형식
MFC를 사용하여 만든 대화 상자 컨트롤에 멤버 변수를 추가하는 데 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md)를 사용할 수 있습니다. 멤버 변수를 추가하는 컨트롤의 형식은 대화 상자에 표시되는 옵션을 결정합니다.  
  
 다음 표에서는 MFC에서 지원되는 모든 대화 상자 컨트롤 형식, [대화 상자 편집기](../windows/dialog-editor.md) 및 사용할 수 있는 형식과 값을 설명합니다.  
  
|Control|컨트롤 형식|제어 변수 형식|변수 값 형식|최소값/최대값(값 형식에만 해당)|  
|-------------|------------------|---------------------------|-------------------------|-----------------------------------------|  
|애니메이션 컨트롤|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|없음; 컨트롤에만 해당|N/A|  
|단추|BUTTON|[CButton](../mfc/reference/cbutton-class.md)|없음; 컨트롤에만 해당|N/A|  
|확인란|CHECK|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|최소값/최대값|  
|콤보 상자|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|최대 문자|  
|날짜 시간 선택 컨트롤|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|최소값/최대값|  
|편집 상자|편집|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime` 또는 **COleCurrency**|최소값/최대값; 일부 지원 최대 문자|  
|바로 가기 키 컨트롤|msctls_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|없음; 컨트롤에만 해당|N/A|  
|목록 상자|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|최대 문자|  
|목록 컨트롤|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|없음; 컨트롤에만 해당|N/A|  
|MonthCalendar 컨트롤|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|최소값/최대값|  
|Progress 컨트롤|msctls_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|없음; 컨트롤에만 해당|N/A|  
|Rich Edit 2 컨트롤|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|최대 문자|  
|Rich Edit 컨트롤|RICHEDIT|`CRichEditCtrl`|`CString`|최대 문자|  
|스크롤 막대(가로 또는 세로)|SCROLLBAR|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|최소값/최대값|  
|Slider 컨트롤|msctls_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|최소값/최대값|  
|Spin 컨트롤|msctls_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|없음; 컨트롤에만 해당|N/A|  
|탭 컨트롤|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|없음; 컨트롤에만 해당|N/A|  
|트리 컨트롤|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|없음; 컨트롤에만 해당|N/A|  
  
## <a name="see-also"></a>참고 항목  
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)