---
title: "CComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBox 클래스"
  - "콤보 상자, CComboBox objects"
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 콤보 상자의 기능을 제공합니다.  
  
## 구문  
  
```  
class CComboBox : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CComboBox::CComboBox](../Topic/CComboBox::CComboBox.md)|`CComboBox` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CComboBox::AddString](../Topic/CComboBox::AddString.md)|문자열을 목록 상자 또는 콤보 상자, 목록 상자에 대 한 정렬 된 위치에 목록 끝에 추가 된  **CBS\_SORT** 스타일.|  
|[CComboBox::Clear](../Topic/CComboBox::Clear.md)|삭제 \(취소\) 있을 경우 편집 컨트롤에 현재 선택 합니다.|  
|[CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md)|정렬 된 소유자가 그린 콤보 상자에서 새 목록 항목의 상대적 위치를 결정 하는 프레임 워크에서 호출 합니다.|  
|[CComboBox::Copy](../Topic/CComboBox::Copy.md)|현재 선택 영역에 있는 경우 클립보드에 복사  **CF\_TEXT** 형식입니다.|  
|[CComboBox::Create](../Topic/CComboBox::Create.md)|콤보 상자를 만들고 연결 하는 `CComboBox` 개체입니다.|  
|[CComboBox::Cut](../Topic/CComboBox::Cut.md)|삭제 \(컷\) 모든 편집에서 제어 하 고 삭제 된 텍스트를 클립보드에 복사 하는 경우 현재 선택 항목을  **CF\_TEXT** 형식입니다.|  
|[CComboBox::DeleteItem](../Topic/CComboBox::DeleteItem.md)|소유자가 그린 콤보 상자에서 목록 항목을 삭제 하면 프레임 워크에서 호출 됩니다.|  
|[CComboBox::DeleteString](../Topic/CComboBox::DeleteString.md)|콤보 상자의 목록 상자에서 문자열을 삭제합니다.|  
|[CComboBox::Dir](../Topic/CComboBox::Dir.md)|파일 이름 목록을 콤보 상자의 목록 상자에 추가합니다.|  
|[CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md)|소유자가 그린 콤보 상자를 변경의 시각적 측면이 때 프레임 워크에서 호출 됩니다.|  
|[CComboBox::FindString](../Topic/CComboBox::FindString.md)|첫 번째 콤보 상자의 목록 상자에 지정 된 접두사를 포함 하는 문자열을 찾습니다.|  
|[CComboBox::FindStringExact](../Topic/CComboBox::FindStringExact.md)|지정 된 문자열과 일치 하는 첫 번째 목록 상자 \(콤보 상자\)에서 문자열을 찾습니다.|  
|[CComboBox::GetComboBoxInfo](../Topic/CComboBox::GetComboBoxInfo.md)|정보에 대 한 검색은 `CComboBox` 개체입니다.|  
|[CComboBox::GetCount](../Topic/CComboBox::GetCount.md)|콤보 상자의 목록 상자 항목을 검색합니다.|  
|[CComboBox::GetCueBanner](../Topic/CComboBox::GetCueBanner.md)|콤보 상자 컨트롤에 표시 되는 큐 텍스트를 가져옵니다.|  
|[CComboBox::GetCurSel](../Topic/CComboBox::GetCurSel.md)|있는 경우 콤보 상자의 목록 상자에서 현재 선택된 된 항목의 인덱스를 검색 합니다.|  
|[CComboBox::GetDroppedControlRect](../Topic/CComboBox::GetDroppedControlRect.md)|화면 좌표 표시 \(삭제\)를 목록 상자의 드롭다운 콤보 상자를 검색합니다.|  
|[CComboBox::GetDroppedState](../Topic/CComboBox::GetDroppedState.md)|드롭다운 콤보 상자의 목록 상자 \(삭제\)를 볼 수 있는지 확인 합니다.|  
|[CComboBox::GetDroppedWidth](../Topic/CComboBox::GetDroppedWidth.md)|콤보 상자의 드롭다운 목록 상자 부분 너비 허용 되는 최소값을 검색 합니다.|  
|[CComboBox::GetEditSel](../Topic/CComboBox::GetEditSel.md)|콤보 상자의 편집 컨트롤에서 현재 선택 영역의 시작 및 끝 문자 위치를 가져옵니다.|  
|[CComboBox::GetExtendedUI](../Topic/CComboBox::GetExtendedUI.md)|콤보 상자 확장된 사용자 인터페이스 또는 기본 사용자 인터페이스가 있는지 여부를 결정 합니다.|  
|[CComboBox::GetHorizontalExtent](../Topic/CComboBox::GetHorizontalExtent.md)|콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 픽셀 단위로 너비를 반환 합니다.|  
|[CComboBox::GetItemData](../Topic/CComboBox::GetItemData.md)|지정한 콤보 상자 항목에 연결 된 응용 프로그램에서 제공한 32 비트 값을 검색 합니다.|  
|[CComboBox::GetItemDataPtr](../Topic/CComboBox::GetItemDataPtr.md)|지정한 콤보 상자 항목에 연결 된 응용 프로그램에서 제공한 32 비트 포인터를 검색 합니다.|  
|[CComboBox::GetItemHeight](../Topic/CComboBox::GetItemHeight.md)|콤보 상자의 목록 항목의 높이 검색합니다.|  
|[CComboBox::GetLBText](../Topic/CComboBox::GetLBText.md)|콤보 상자의 목록 상자에서 문자열을 가져옵니다.|  
|[CComboBox::GetLBTextLen](../Topic/CComboBox::GetLBTextLen.md)|콤보 상자의 목록 상자에 문자열의 길이 가져옵니다.|  
|[CComboBox::GetLocale](../Topic/CComboBox::GetLocale.md)|콤보 상자에 대 한 로캘 식별자를 검색합니다.|  
|[CComboBox::GetMinVisible](../Topic/CComboBox::GetMinVisible.md)|현재 콤보 상자의 드롭다운 목록에 표시 되는 항목의 최소 수를 가져옵니다.|  
|[CComboBox::GetTopIndex](../Topic/CComboBox::GetTopIndex.md)|콤보 상자의 목록 상자 부분에 표시 되는 첫 번째 항목의 인덱스를 반환합니다.|  
|[CComboBox::InitStorage](../Topic/CComboBox::InitStorage.md)|항목 및 콤보 상자의 목록 상자 부분에서 문자열에 대 한 메모리 블록을 preallocates.|  
|[CComboBox::InsertString](../Topic/CComboBox::InsertString.md)|콤보 상자의 목록 상자에 문자열을 삽입합니다.|  
|[CComboBox::LimitText](../Topic/CComboBox::LimitText.md)|콤보 상자의 편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 합니다.|  
|[CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md)|소유자가 그린 콤보 상자를 만들 때 콤보 상자 크기를 결정 하는 프레임 워크에서 호출 됩니다.|  
|[CComboBox::Paste](../Topic/CComboBox::Paste.md)|편집 컨트롤의 현재 커서 위치에 클립보드의 데이터를 삽입합니다.  클립보드에 데이터가 있는 경우에 데이터 삽입  **CF\_TEXT** 형식입니다.|  
|[CComboBox::ResetContent](../Topic/CComboBox::ResetContent.md)|모든 항목의 목록에서 상자 및 콤보 상자 컨트롤 편집 제거 합니다.|  
|[CComboBox::SelectString](../Topic/CComboBox::SelectString.md)|콤보 상자의 목록 상자에서 문자열을 검색 하는 문자열이 있으면 문자열을 목록 상자에서 선택 및 편집 컨트롤에 문자열을 복사 합니다.|  
|[CComboBox::SetCueBanner](../Topic/CComboBox::SetCueBanner.md)|콤보 상자 컨트롤에 표시 되는 큐 텍스트를 설정 합니다.|  
|[CComboBox::SetCurSel](../Topic/CComboBox::SetCurSel.md)|콤보 상자의 목록 상자에서 문자열을 선택합니다.|  
|[CComboBox::SetDroppedWidth](../Topic/CComboBox::SetDroppedWidth.md)|콤보 상자의 드롭다운 목록 상자 부분 너비 허용 되는 최소값을 설정 합니다.|  
|[CComboBox::SetEditSel](../Topic/CComboBox::SetEditSel.md)|콤보 상자의 편집 컨트롤에서 문자를 선택합니다.|  
|[CComboBox::SetExtendedUI](../Topic/CComboBox::SetExtendedUI.md)|기본 사용자 인터페이스 또는 확장된 사용자 인터페이스에 있는 콤보 상자를 선택 된  **CBS\_DROPDOWN** 또는  **CBS\_DROPDOWNLIST** 스타일입니다.|  
|[CComboBox::SetHorizontalExtent](../Topic/CComboBox::SetHorizontalExtent.md)|콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 픽셀 단위로 너비를 설정 합니다.|  
|[CComboBox::SetItemData](../Topic/CComboBox::SetItemData.md)|콤보 상자에 지정 된 항목과 연관 된 32 비트 값을 설정 합니다.|  
|[CComboBox::SetItemDataPtr](../Topic/CComboBox::SetItemDataPtr.md)|콤보 상자에 지정 된 항목과 연관 된 32 비트 포인터를 설정 합니다.|  
|[CComboBox::SetItemHeight](../Topic/CComboBox::SetItemHeight.md)|콤보 상자 또는 콤보 상자의 편집 컨트롤 \(또는 정적 텍스트\) 부분의 높이의 목록 항목 높이 설정합니다.|  
|[CComboBox::SetLocale](../Topic/CComboBox::SetLocale.md)|콤보 상자에 대 한 로캘 식별자를 설정합니다.|  
|[CComboBox::SetMinVisibleItems](../Topic/CComboBox::SetMinVisibleItems.md)|현재 콤보 상자의 드롭다운 목록에 표시 되는 항목의 최소 수를 설정합니다.|  
|[CComboBox::SetTopIndex](../Topic/CComboBox::SetTopIndex.md)|위쪽에 지정 된 인덱스에 항목을 표시할 콤보 상자의 목록 상자 부분을 알려 줍니다.|  
|[CComboBox::ShowDropDown](../Topic/CComboBox::ShowDropDown.md)|표시 하거나 숨깁니다.이 콤보 상자의 목록 상자에서  **CBS\_DROPDOWN** 또는  **CBS\_DROPDOWNLIST** 스타일입니다.|  
  
## 설명  
 콤보 상자 목록 상자의 정적 컨트롤 또는 편집 컨트롤을 결합으로 구성 됩니다.  컨트롤의 목록 상자 부분에 항상 표시 될 수 있습니다 또는 컨트롤 옆의 드롭다운 화살표를 선택할 때만 드롭다운 수 있습니다.  
  
 목록 상자에서 현재 선택한 항목 \(있는 경우\) 편집 컨트롤 또는 정적에 나타납니다.  또한 콤보 상자는 드롭다운 목록 스타일 경우 사용자 목록에서 항목 중 하나를 초기 문자를 입력할 수 있습니다 및 목록 상자에 표시 되는 경우 초기 문자 다음 항목이 강조 표시 됩니다.  
  
 다음 표에서 세 가지 콤보 상자 비교  [스타일](../../mfc/reference/combo-box-styles.md).  
  
|스타일|때 목록 상자를 볼 수 있습니까?|정적 또는 편집 컨트롤?|  
|---------|------------------------|-------------------|  
|단순|항상|Edit|  
|드롭다운|삭제 하면|Edit|  
|드롭다운 목록|삭제 하면|Static|  
  
 만들 수 있는 `CComboBox` 개체에서 대화 상자 템플릿 또는 코드에서 직접.  두 경우 모두 먼저 생성자를 호출 `CComboBox` 를 생성 하는 `CComboBox` 개체입니다. 다음 호출의  [만들기](../Topic/CComboBox::Create.md) 컨트롤에 연결 하는 멤버 함수는 `CComboBox` 개체입니다.  
  
 콤보 상자에서 해당 부모에 보낸 Windows 알림 메시지를 처리 하는 경우 \(일반적으로 클래스에서 파생 된 `CDialog`\), 각 메시지에 대 한 부모 클래스 메시지 맵 엔트리와 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 엔트리는 다음과 같은 형식을 사용합니다.  
  
 **ON\_**Notification**\(**`id`**,**`memberFxn`**\)**  
  
 위치 `id` 알림 메시지를 보내는 콤보 상자 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 했다고 부모 멤버 함수의 이름입니다.  
  
 상위 함수 프로토타입은 다음과 같습니다.  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 특정 알림을 보낼 순서를 예측할 수 없습니다.  특히는  **CBN\_SELCHANGE** 알림 전이나 후 발생할 수 있습니다는  **CBN\_CLOSEUP** 알림.  
  
 잠재적인 메시지 맵 엔트리는 다음과 같습니다.  
  
-   **ON\_CBN\_CLOSEUP** \(Windows 3.1 및 나중에.\) 콤보 상자의 목록 상자를 닫았습니다.  이 알림 메시지에 있는 콤보 상자에 보내지지는  [CBS\_SIMPLE](../../mfc/reference/combo-box-styles.md) 스타일입니다.  
  
-   **ON\_CBN\_DBLCLK** 콤보 상자의 목록 상자에 문자열을 두 번 클릭할.  콤보 상자와이 알림 메시지를 보낼만  **CBS\_SIMPLE** 스타일입니다.  콤보 상자에  [CBS\_DROPDOWN](../../mfc/reference/combo-box-styles.md) 또는  [CBS\_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) 목록 상자 한 번의 클릭을 숨기 므, 두 번 클릭이 발생할 수 없는 스타일.  
  
-   **ON\_CBN\_DROPDOWN** 드롭다운 콤보 상자의 목록 상자 것 \(될 수 표시\).  이 알림 메시지를 콤보 상자에 대 한 발생할 수 있습니다는  **CBS\_DROPDOWN** 또는  **CBS\_DROPDOWNLIST** 스타일입니다.  
  
-   **ON\_CBN\_EDITCHANGE** 사용자가 콤보 상자의 편집 컨트롤 부분에 텍스트 변경 하는 동작을 수행한.  달리는  **CBN\_EDITUPDATE** 메시지에이 메시지를 보낼 Windows 화면 업데이트 후.  콤보 상자에 있는 경우 전송 되는  **CBS\_DROPDOWNLIST** 스타일입니다.  
  
-   **ON\_CBN\_EDITUPDATE** 변경된 된 텍스트를 나타내려면 콤보 상자의 편집 컨트롤 부분입니다.  컨트롤의 텍스트 서식을 지정한 후 있지만 텍스트를 표시 하기 전에이 알림 메시지를 보냅니다.  콤보 상자에 있는 경우 전송 되는  **CBS\_DROPDOWNLIST** 스타일입니다.  
  
-   **ON\_CBN\_ERRSPACE** 콤보 상자에서 특정 요청을 충족 시키기 위해 충분 한 메모리를 할당할 수 없습니다.  
  
-   **ON\_CBN\_SELENDCANCEL** \(Windows 3.1 및 나중에.\) 사용자의 선택은 취소 해야 나타냅니다.  사용자가 항목을 클릭 하 고 다른 창 또는 콤보 상자의 목록 상자를 숨길 수 있는 컨트롤을 클릭.  전에이 알림 메시지를 보낼의  **CBN\_CLOSEUP** 알림 메시지는 사용자의 선택 영역을 무시 하도록 지정 합니다.  **CBN\_SELENDCANCEL** 또는  **CBN\_SELENDOK** 알림 메시지를 보낼 경우에는  **CBN\_CLOSEUP** 알림 메시지가 보내집니다 \(경우 콤보 상자와 마찬가지로  **CBS\_SIMPLE** 스타일\).  
  
-   **ON\_CBN\_SELENDOK** 사용자가 항목을 선택 및 다음 ENTER 키를 누를 또는 콤보 상자의 목록 상자를 숨기려면 아래쪽 화살표 키를 클릭 합니다.  전에이 알림 메시지를 보낼는  **CBN\_CLOSEUP** 메시지가 사용자의 선택 유효 하지 것입니다.  **CBN\_SELENDCANCEL** 또는  **CBN\_SELENDOK** 알림 메시지를 보낼 경우에는  **CBN\_CLOSEUP** 알림 메시지가 보내집니다 \(경우 콤보 상자와 마찬가지로  **CBS\_SIMPLE** 스타일\).  
  
-   **ON\_CBN\_KILLFOCUS** 콤보 상자가 입력된 포커스를 잃을.  
  
-   **ON\_CBN\_SELCHANGE** 콤보 상자의 목록 상자 선택 영역 사용자 목록 상자에서를 클릭 하거나 화살표 키를 사용 하 여 선택 영역을 변경으로 인해 변경 될 수 있습니다.  이 메시지를 처리 하는 경우 콤보 상자의 편집 컨트롤에서 텍스트만을 통해 검색할 수 있습니다 `GetLBText` 또는 다른 유사한 함수.  `GetWindowText`를 사용할 수 없습니다.  
  
-   **ON\_CBN\_SETFOCUS** 콤보 상자가 입력된 포커스를 받습니다.  
  
 만들 경우는 `CComboBox` 대화 상자 \(대화 상자 리소스\)를 통해 개체의 `CComboBox` 개체 대화 상자를 닫으면 자동으로 소멸.  
  
 포함 하는 경우는 `CComboBox` 개체를 다른 창에 개체를 하지 않아도 파괴를 합니다.  사용자가 만든 경우는 `CComboBox` 개체는 스택에 자동으로 소멸 됩니다.  만들 경우의 `CComboBox` 개체를 사용 하 여 힙에  **새** 해야 호출 함수를  **삭제** Windows 콤보 상자 소멸 되 면 파기 하는 개체.  
  
 **참고** 처리 하려는 경우 `WM_KEYDOWN` 및 `WM_CHAR` 메시지를 경우에 서브 클래스 편집 및 목록 상자 컨트롤, 클래스에서 파생 되는 콤보 상자의 `CEdit` 및 `CListBox`, 및 파생된 클래스에 해당 메시지에 대 한 처리기를 추가 합니다.  자세한 내용은 [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us.Q174667](http://support.microsoft.com/default.aspx?scid=kb;en-us.Q174667) 및  [CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CTRLBARS MFC 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)