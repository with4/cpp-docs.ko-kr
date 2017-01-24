---
title: "CListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListBox 클래스"
  - "목록 상자"
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
caps.latest.revision: 26
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 목록 상자의 기능을 제공합니다.  
  
## 구문  
  
```  
class CListBox : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CListBox::CListBox](../Topic/CListBox::CListBox.md)|`CListBox` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CListBox::AddString](../Topic/CListBox::AddString.md)|목록 상자에 문자열을 추가합니다.|  
|[CListBox::CharToItem](../Topic/CListBox::CharToItem.md)|사용자 지정을 제공 하는 재정의 `WM_CHAR` 문자열이 없는 소유자 그리기 목록 상자에 대 한 처리 합니다.|  
|[CListBox::CompareItem](../Topic/CListBox::CompareItem.md)|정렬 된 소유자 그리기 목록 상자에서 새 항목의 위치를 결정 하는 프레임 워크에서 호출 합니다.|  
|[CListBox::Create](../Topic/CListBox::Create.md)|Windows 목록 상자를 만들고 연결 하는 `CListBox` 개체입니다.|  
|[CListBox::DeleteItem](../Topic/CListBox::DeleteItem.md)|사용자는 소유자 그리기 목록 상자에서 항목을 삭제할 때 프레임 워크에 의해 호출 됩니다.|  
|[CListBox::DeleteString](../Topic/CListBox::DeleteString.md)|목록 상자에서 문자열을 삭제합니다.|  
|[CListBox::Dir](../Topic/CListBox::Dir.md)|파일 이름, 드라이브, 또는 둘 다에서 현재 디렉터리 목록 상자에 추가합니다.|  
|[CListBox::DrawItem](../Topic/CListBox::DrawItem.md)|소유자 그리기 목록 상자 변경 내용을 시각적 측면이 때 프레임 워크에서 호출 됩니다.|  
|[CListBox::FindString](../Topic/CListBox::FindString.md)|목록 상자에서 문자열을 검색 합니다.|  
|[CListBox::FindStringExact](../Topic/CListBox::FindStringExact.md)|지정 된 문자열을 일치 하는 첫 번째 목록 상자 문자열을 찾습니다.|  
|[CListBox::GetAnchorIndex](../Topic/CListBox::GetAnchorIndex.md)|목록 상자에서 현재 앵커 항목의 인덱스를 검색합니다.|  
|[CListBox::GetCaretIndex](../Topic/CListBox::GetCaretIndex.md)|다중 선택 목록 상자에서 포커스를 가진 항목의 인덱스를 확인 합니다.|  
|[CListBox::GetCount](../Topic/CListBox::GetCount.md)|목록 상자에 문자열을 반환합니다.|  
|[CListBox::GetCurSel](../Topic/CListBox::GetCurSel.md)|목록 상자에서 현재 선택된 된 문자열의 인덱스를 반환합니다.|  
|[CListBox::GetHorizontalExtent](../Topic/CListBox::GetHorizontalExtent.md)|목록 상자를 가로로 스크롤할 수 픽셀 단위로 너비를 반환 합니다.|  
|[CListBox::GetItemData](../Topic/CListBox::GetItemData.md)|목록 상자 항목에 연결 된 32 비트 값을 반환 합니다.|  
|[CListBox::GetItemDataPtr](../Topic/CListBox::GetItemDataPtr.md)|목록 상자 항목에 포인터를 반환 합니다.|  
|[CListBox::GetItemHeight](../Topic/CListBox::GetItemHeight.md)|목록 상자의 항목 높이 결정합니다.|  
|[CListBox::GetItemRect](../Topic/CListBox::GetItemRect.md)|현재 표시 되는 목록 상자 항목의 경계 사각형을 반환 합니다.|  
|[CListBox::GetListBoxInfo](../Topic/CListBox::GetListBoxInfo.md)|각 열에 항목을 검색합니다.|  
|[CListBox::GetLocale](../Topic/CListBox::GetLocale.md)|목록 상자에 대 한 로캘 식별자를 검색합니다.|  
|[CListBox::GetSel](../Topic/CListBox::GetSel.md)|목록 상자 항목의 선택 상태를 반환합니다.|  
|[CListBox::GetSelCount](../Topic/CListBox::GetSelCount.md)|다중 선택 목록 상자에 현재 선택 된 문자열을 반환 합니다.|  
|[CListBox::GetSelItems](../Topic/CListBox::GetSelItems.md)|목록 상자에 현재 선택 된 문자열의 인덱스를 반환 합니다.|  
|[CListBox::GetText](../Topic/CListBox::GetText.md)|목록 상자 항목을 버퍼에 복사합니다.|  
|[CListBox::GetTextLen](../Topic/CListBox::GetTextLen.md)|목록 상자 항목의 바이트 길이 반환 합니다.|  
|[CListBox::GetTopIndex](../Topic/CListBox::GetTopIndex.md)|목록 상자에서 첫 번째 표시 문자열의 인덱스를 반환합니다.|  
|[CListBox::InitStorage](../Topic/CListBox::InitStorage.md)|목록 상자 항목 및 문자열에 대 한 메모리 블록을 preallocates.|  
|[CListBox::InsertString](../Topic/CListBox::InsertString.md)|목록 상자의 특정 위치에 문자열을 삽입합니다.|  
|[CListBox::ItemFromPoint](../Topic/CListBox::ItemFromPoint.md)|점 가장 가까운 목록 상자 항목의 인덱스를 반환합니다.|  
|[CListBox::MeasureItem](../Topic/CListBox::MeasureItem.md)|목록 상자의 크기를 결정 하는 소유자 그리기 목록 상자를 만들 때 프레임 워크에 의해 호출 됩니다.|  
|[CListBox::ResetContent](../Topic/CListBox::ResetContent.md)|목록 상자에서 항목을 모두 지웁니다.|  
|[CListBox::SelectString](../Topic/CListBox::SelectString.md)|검색 한 문자열을 단일 선택 목록 상자에서 선택 합니다.|  
|[CListBox::SelItemRange](../Topic/CListBox::SelItemRange.md)|선택 또는 다중 선택 목록 상자에서 문자열의 범위를 선택 취소 합니다.|  
|[CListBox::SetAnchorIndex](../Topic/CListBox::SetAnchorIndex.md)|확장된 된 선택 하려면 다중 선택 목록 상자에서 앵커를 설정 합니다.|  
|[CListBox::SetCaretIndex](../Topic/CListBox::SetCaretIndex.md)|포커스 사각형 다중 선택 목록 상자에서 지정 된 인덱스에 있는 항목 수를 설정합니다.|  
|[CListBox::SetColumnWidth](../Topic/CListBox::SetColumnWidth.md)|다중 열 목록 상자의 열 너비를 설정합니다.|  
|[CListBox::SetCurSel](../Topic/CListBox::SetCurSel.md)|목록 상자 문자열을 선택합니다.|  
|[CListBox::SetHorizontalExtent](../Topic/CListBox::SetHorizontalExtent.md)|목록 상자를 가로로 스크롤할 수 픽셀 단위로 너비를 설정 합니다.|  
|[CListBox::SetItemData](../Topic/CListBox::SetItemData.md)|목록 상자 항목에 연결 된 32 비트 값을 설정 합니다.|  
|[CListBox::SetItemDataPtr](../Topic/CListBox::SetItemDataPtr.md)|목록 상자 항목에 포인터를 설정합니다.|  
|[CListBox::SetItemHeight](../Topic/CListBox::SetItemHeight.md)|목록 상자에서 항목의 높이 설정합니다.|  
|[CListBox::SetLocale](../Topic/CListBox::SetLocale.md)|목록 상자에 대 한 로캘 식별자를 설정합니다.|  
|[CListBox::SetSel](../Topic/CListBox::SetSel.md)|선택 또는 다중 선택 목록 상자에서는 목록 상자 항목을 선택 취소 합니다.|  
|[CListBox::SetTabStops](../Topic/CListBox::SetTabStops.md)|목록 상자에서 탭 위치를 설정합니다.|  
|[CListBox::SetTopIndex](../Topic/CListBox::SetTopIndex.md)|목록 상자에서 보이는 첫 번째 문자열의 인덱스를 설정합니다.|  
|[CListBox::VKeyToItem](../Topic/CListBox::VKeyToItem.md)|사용자 지정을 제공 하는 재정의 `WM_KEYDOWN` 목록 상자에 대 한 처리는  **LBS\_WANTKEYBOARDINPUT** 스타일 집합입니다.|  
  
## 설명  
 목록 상자는 사용자가 선택 하 고 있습니다 파일 이름과 같은 항목의 목록을 표시 합니다.  
  
 단일 선택 목록 상자에서 사용자가 하나의 항목만을 선택할 수 있습니다.  다중 선택 목록 상자에 항목의 범위를 선택할 수 있습니다.  항목을 선택할 때 강조 표시 되 고 목록 상자의 부모 창에 알림 메시지를 보냅니다.  
  
 목록 상자에서 대화 상자 템플릿 또는 코드에서 직접 만들 수 있습니다.  직접 만드는 데 생성은 `CListBox` 개체를 호출 하 고는  [만들기](../Topic/CListBox::Create.md) Windows 목록 상자 컨트롤을 만들고 연결할 수 있는 멤버 함수는 `CListBox` 개체.  목록 상자에서 대화 상자 템플릿 사용 하려면 목록 상자를 대화 상자 클래스에 변수를 선언 하 고 사용 `DDX_Control` 대화 상자 클래스의 `DoDataExchange` 함수는 컨트롤에 멤버 변수를 연결할 수 있습니다.  \(제어 변수를 대화 상자 클래스에 추가 하면이 자동으로 수행 됩니다.\)  
  
 건설 1 단계 프로세스에서 파생 된 클래스에서 사용할 수 있습니다 `CListBox`.  생성자는 파생 된 클래스와 호출을 작성 합니다.  **만들기** 에서 생성자 내에서.  
  
 목록 상자에서 해당 부모에 보낸 Windows 알림 메시지를 처리 하는 경우 \(일반적으로 클래스에서 파생 된  [CDialog](../../mfc/reference/cdialog-class.md)\), 각 메시지에 대 한 부모 클래스 메시지 맵 엔트리와 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 엔트리는 다음과 같은 형식을 사용합니다.  
  
 `ON_Notification( id, memberFxn )`  
  
 위치 `id` 알림 메시지를 보내는 목록 상자 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 했다고 부모 멤버 함수의 이름입니다.  
  
 상위 함수 프로토타입은 다음과 같습니다.  
  
 `afx_msg void memberFxn( );`  
  
 메시지 맵 항목 목록과 부모에 전송 하는 경우에 대 한 설명은 다음과가 같습니다.  
  
-   **ON\_LBN\_DBLCLK** 사용자 목록 상자에 문자열을 두 번 클릭 합니다.  이 목록 상자는의  [LBS\_NOTIFY](../../mfc/reference/list-box-styles.md) 스타일이 알림 메시지를 전송 합니다.  
  
-   **ON\_LBN\_ERRSPACE** 목록 상자 요청을 충족 시키기 위해 충분 한 메모리를 할당할 수 없습니다.  
  
-   **ON\_LBN\_KILLFOCUS** 목록 상자가 입력된 포커스를 잃을.  
  
-   **ON\_LBN\_SELCANCEL** 현재 목록 상자의 선택이 취소 됩니다.  목록 상자에 있는 경우에이 메시지가 보내집니다는  **LBS\_NOTIFY** 스타일입니다.  
  
-   **ON\_LBN\_SELCHANGE** 선택 목록 상자에서 변경 되었습니다.  선택 영역에서 변경 된 경우이 알림이 전송 되지 않는다는  [CListBox::SetCurSel](../Topic/CListBox::SetCurSel.md) 멤버 함수입니다.  이 알림 포함 된 목록 상자에만 적용 되는  **LBS\_NOTIFY** 스타일.  **LBN\_SELCHANGE** 알림 메시지를 보낼 다중 선택 목록 상자에 대 한 화살표 키를 누를 때마다 선택 영역이 변경 되지 않는 경우에.  
  
-   **ON\_LBN\_SETFOCUS** 목록 상자의 입력된 포커스를 받지.  
  
-   **ON\_WM\_CHARTOITEM** 없는 문자열에는 소유자 그리기 목록 상자의 수신은 `WM_CHAR` 메시지.  
  
-   **ON\_WM\_VKEYTOITEM** 목록 상자에는  **LBS\_WANTKEYBOARDINPUT** 받는 스타일은 `WM_KEYDOWN` 메시지.  
  
 만들 경우는 `CListBox` 대화 상자 \(대화 상자 리소스\)를 통해 개체의 `CListBox` 개체 대화 상자를 닫으면 자동으로 소멸.  
  
 만들 경우는 `CListBox` 개체 해야 파괴 하는 창에는 `CListBox` 개체.  사용자가 만든 경우는 `CListBox` 개체는 스택에 자동으로 소멸 됩니다.  만들 경우는 `CListBox` 개체를 사용 하 여 힙에  **새** 해야 호출 함수를  **삭제** 사용자는 부모 창의 닫을 때 파괴 개체에.  
  
 모든 메모리를 할당 하는 경우는 `CListBox` 개체, 재정의 `CListBox` 할당을 삭제 하는 소멸자입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CTRLTEST MFC 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)