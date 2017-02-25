---
title: "대화 상자 컨트롤 및 변수 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "대화 상자 컨트롤, 멤버 변수"
  - "대화 상자 컨트롤, 변수 형식"
  - "변수, 대화 상자 컨트롤 멤버 변수"
ms.assetid: f9cd9cea-45a6-4349-8358-e5efbcdcff76
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 대화 상자 컨트롤 및 변수 형식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC를 사용하여 만든 대화 상자 컨트롤에 멤버 변수를 추가하기 위해 [멤버 변수 추가 마법사](../ide/add-member-variable-wizard.md)를 사용할 수 있습니다.  멤버 변수를 추가하는 컨트롤 형식에 따라 대화 상자에 나타나는 옵션이 결정됩니다.  
  
 다음 표에서는 MFC와 [대화 상자 편집기](../mfc/dialog-editor.md)에서 지원되는 모든 대화 상자 컨트롤 형식과 사용 가능한 형식 및 값을 설명합니다.  
  
|컨트롤|컨트롤 형식|컨트롤 변수 형식|값 변수 형식|최소\/최대값\(값 형식에만 해당\)|  
|---------|------------|---------------|-------------|--------------------------|  
|Animation 컨트롤|SysAnimate32|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|없음. 컨트롤에만 해당|N\/A|  
|Button|BUTTON|[CButton](../mfc/reference/cbutton-class.md)|없음. 컨트롤에만 해당|N\/A|  
|Check box|CHECK|[CButton](../mfc/reference/cbutton-class.md)|**BOOL**|최소값\/최대값|  
|Combo box|COMBOBOX|[CComboBox](../mfc/reference/ccombobox-class.md)|[CString](../atl-mfc-shared/reference/cstringt-class.md)|최대 문자|  
|Date time picker 컨트롤|SysDateTimePick32|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|[CTime](../atl-mfc-shared/reference/ctime-class.md)|최소값\/최대값|  
|입력란|EDIT|[CEdit](../mfc/reference/cedit-class.md)|`CString`, int, UINT, long, DWORD, float, double, BYTE, short, BOOL, `COleDateTime` 또는 **COleCurrency**|최소값\/최대값; 일부는 최대 문자를 지원함|  
|Hotkey 컨트롤|msctls\_hotkey32|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|없음. 컨트롤에만 해당|N\/A|  
|목록 상자|LISTBOX|[CListBox](../mfc/reference/clistbox-class.md)|`CString`|최대 문자|  
|List 컨트롤|SysListView32|[CListCtrl](../mfc/reference/clistctrl-class.md)|없음. 컨트롤에만 해당|N\/A|  
|Month Calendar 컨트롤|SysMonthCal32|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|`CTime`|최소값\/최대값|  
|Progress 컨트롤|msctls\_progress32|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|없음. 컨트롤에만 해당|N\/A|  
|Rich Edit 2 컨트롤|RichEdit20A|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|`CString`|최대 문자|  
|Rich Edit 컨트롤|RICHEDIT|`CRichEditCtrl`|`CString`|최대 문자|  
|스크롤 막대\(세로 또는 가로\)|SCROLLBAR|[CScrollBar](../mfc/reference/cscrollbar-class.md)|`int`|최소값\/최대값|  
|Slider 컨트롤|msctls\_trackbar32|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|`int`|최소값\/최대값|  
|Spin 컨트롤|msctls\_updown32|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|없음. 컨트롤에만 해당|N\/A|  
|Tab 컨트롤|SysTabControl32|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|없음. 컨트롤에만 해당|N\/A|  
|Tree 컨트롤|SysTreeView32|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|없음. 컨트롤에만 해당|N\/A|  
  
## 참고 항목  
 [멤버 변수 추가](../ide/adding-a-member-variable-visual-cpp.md)