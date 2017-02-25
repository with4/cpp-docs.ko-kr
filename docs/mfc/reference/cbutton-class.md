---
title: "CButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "button control [MFC]"
  - "button objects (CButton)"
  - "CButton class"
  - "확인란, button controls"
  - "checkbox buttons"
  - "pushbuttons"
  - "라디오 단추, CButton class"
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 단추 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CButton : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CButton::CButton](../Topic/CButton::CButton.md)|`CButton` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CButton::Create](../Topic/CButton::Create.md)|Windows 단추 컨트롤을 만들고이에 연결 된 `CButton` 개체입니다.|  
|[CButton::DrawItem](../Topic/CButton::DrawItem.md)|재정의 소유자가 그린 그릴 `CButton` 개체입니다.|  
|[CButton::GetBitmap](../Topic/CButton::GetBitmap.md)|이전에 설정 된 비트맵에 대 한 핸들 검색  [SetBitmap](../Topic/CButton::SetBitmap.md).|  
|[CButton::GetButtonStyle](../Topic/CButton::GetButtonStyle.md)|단추 컨트롤 스타일에 대 한 정보를 검색합니다.|  
|[CButton::GetCheck](../Topic/CButton::GetCheck.md)|단추 컨트롤의 선택 상태를 검색합니다.|  
|[CButton::GetCursor](../Topic/CButton::GetCursor.md)|커서 이미지의 핸들을 이전에 설정한 함께 검색  [SetCursor](../Topic/CButton::SetCursor.md).|  
|[CButton::GetIcon](../Topic/CButton::GetIcon.md)|이전에 설정 아이콘의 핸들을 검색 합니다.  [SetIcon](../Topic/CButton::SetIcon.md).|  
|[CButton::GetIdealSize](../Topic/CButton::GetIdealSize.md)|단추 컨트롤의 이상적인 크기를 검색합니다.|  
|[CButton::GetImageList](../Topic/CButton::GetImageList.md)|이미지 단추 컨트롤 목록을 검색합니다.|  
|[CButton::GetNote](../Topic/CButton::GetNote.md)|참고 구성 요소를 현재 명령 링크 컨트롤을 검색합니다.|  
|[CButton::GetNoteLength](../Topic/CButton::GetNoteLength.md)|현재 명령 링크 컨트롤의 문자열을 검색합니다.|  
|[CButton::GetSplitGlyph](../Topic/CButton::GetSplitGlyph.md)|현재 분할 단추 컨트롤에 연결 된 문자를 검색 합니다.|  
|[CButton::GetSplitImageList](../Topic/CButton::GetSplitImageList.md)|이미지 목록 현재 분할 단추 컨트롤에 대 한 검색합니다.|  
|[CButton::GetSplitInfo](../Topic/CButton::GetSplitInfo.md)|현재 분할 단추 컨트롤을 정의 하는 정보를 검색 합니다.|  
|[CButton::GetSplitSize](../Topic/CButton::GetSplitSize.md)|현재 분할 단추 컨트롤의 드롭다운 구성 요소의 경계 사각형을 검색합니다.|  
|[CButton::GetSplitStyle](../Topic/CButton::GetSplitStyle.md)|현재 분할 단추 컨트롤을 정의 하는 분할 단추 스타일을 검색 합니다.|  
|[CButton::GetState](../Topic/CButton::GetState.md)|상태 확인, 강조 상태 및 단추 컨트롤의 포커스 상태를 검색합니다.|  
|[CButton::GetTextMargin](../Topic/CButton::GetTextMargin.md)|여백 단추 컨트롤의 텍스트를 검색합니다.|  
|[CButton::SetBitmap](../Topic/CButton::SetBitmap.md)|단추에 표시할 비트맵을 지정 합니다.|  
|[CButton::SetButtonStyle](../Topic/CButton::SetButtonStyle.md)|단추의 스타일을 변경합니다.|  
|[CButton::SetCheck](../Topic/CButton::SetCheck.md)|단추 컨트롤의 선택 상태를 설정합니다.|  
|[CButton::SetCursor](../Topic/CButton::SetCursor.md)|단추에 표시 되는 커서 이미지를 지정 합니다.|  
|[CButton::SetDropDownState](../Topic/CButton::SetDropDownState.md)|현재 분할 단추 컨트롤의 드롭다운 상태를 설정합니다.|  
|[CButton::SetIcon](../Topic/CButton::SetIcon.md)|단추에 표시 될 아이콘을 지정 합니다.|  
|[CButton::SetImageList](../Topic/CButton::SetImageList.md)|단추 컨트롤은 이미지를 설정합니다.|  
|[CButton::SetNote](../Topic/CButton::SetNote.md)|메모의 현재 명령 링크 컨트롤을 설정합니다.|  
|[CButton::SetSplitGlyph](../Topic/CButton::SetSplitGlyph.md)|지정한 문자는 현재 분할 단추 컨트롤에 연결합니다.|  
|[CButton::SetSplitImageList](../Topic/CButton::SetSplitImageList.md)|이미지 목록 현재 분할 단추 컨트롤에 연결합니다.|  
|[CButton::SetSplitInfo](../Topic/CButton::SetSplitInfo.md)|현재 분할 단추 컨트롤을 정의 하는 정보를 지정 합니다.|  
|[CButton::SetSplitSize](../Topic/CButton::SetSplitSize.md)|현재 분할 단추 컨트롤의 드롭다운 구성 요소의 경계 사각형을 설정합니다.|  
|[CButton::SetSplitStyle](../Topic/CButton::SetSplitStyle.md)|현재 분할 단추 컨트롤의 스타일을 설정합니다.|  
|[CButton::SetState](../Topic/CButton::SetState.md)|강조 단추 컨트롤의 상태를 설정합니다.|  
|[CButton::SetTextMargin](../Topic/CButton::SetTextMargin.md)|단추 컨트롤의 텍스트 여백을 설정합니다.|  
  
## 설명  
 단추 컨트롤을 클릭할 수 하는 작은 사각형 자식 창입니다.  단추는 레이블을 지정할 수 및 텍스트 없이 표시 단독으로 또는 그룹에서 사용할 수 있습니다.  사용자가 클릭 하면 단추는 일반적으로 모양이 변경 됩니다.  
  
 일반적인 단추, 확인란, 라디오 단추 및 누름 단추입니다.  A `CButton` 개체 수, 이러한 따라는  [단추 스타일](../../mfc/reference/button-styles.md) 지정한에 의해 초기화 된  [만들기](../Topic/CButton::Create.md) 멤버 함수.  
  
 또한는  [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) 파생 클래스에서 `CButton` 비트맵 이미지 대신 텍스트를 표시 하는 단추 컨트롤을 만들 수 있습니다.  A `CBitmapButton` 단추의, 아래로, 포커스 및 비활성화 상태에 대 한 별도 비트맵을 가질 수 있습니다.  
  
 단추 컨트롤을 대화 상자 템플릿 또는 코드에서 직접 만들 수 있습니다.  두 경우 모두 먼저 생성자를 호출 `CButton` 를 생성 하는 `CButton` 개체입니다. 다음 호출에서  **만들기** 멤버 함수를 만들려면 Windows 단추 컨트롤 및 그의 `CButton` 개체.  
  
 건설 1 단계 프로세스에서 파생 된 클래스에서 사용할 수 있습니다 `CButton`.  생성자는 파생 된 클래스와 호출을 작성 합니다.  **만들기** 에서 생성자 내에서.  
  
 단추 컨트롤에서 자신의 부모에 보냅니다 Windows 알림 메시지를 처리 하는 경우 \(일반적으로 클래스에서 파생 된  [CDialog](../../mfc/reference/cdialog-class.md)\), 각 메시지에 대 한 부모 클래스 메시지 맵 엔트리와 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 엔트리는 다음과 같은 형식을 사용합니다.  
  
 **ON\_**Notification**\(**`id`, `memberFxn`**\)**  
  
 위치 `id` 알림 메시지를 보내는 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 했다고 부모 멤버 함수의 이름입니다.  
  
 상위 함수 프로토타입은 다음과 같습니다.  
  
 **afx\_msg** `void` `memberFxn` **\( \);**  
  
 잠재적인 메시지 맵 엔트리는 다음과 같습니다.  
  
|맵 엔트리|때 부모에 게 보낸...|  
|-----------|-------------------|  
|**ON\_BN\_CLICKED**|사용자가 단추를 클릭 합니다.|  
|**ON\_BN\_DOUBLECLICKED**|사용자 단추를 두 번 클릭 합니다.|  
  
 만들 경우는 `CButton` 대화 상자 리소스에서 개체는 `CButton` 개체 대화 상자를 닫으면 자동으로 소멸 합니다.  
  
 만들 경우는 `CButton` 개체는 창 내에서 파괴를 해야 합니다.  만들 경우의 `CButton` 개체를 사용 하 여 힙에  **새** 해야 호출 함수를  **삭제** 컨트롤 개체에서 사용자가 창의 닫을 때 삭제 단추.  사용자가 만든 경우는 `CButton` 은 부모 개체는 스택, 또는에 포함 된, 자동으로 소멸 됩니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CButton`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CBitmapButton Class](../../mfc/reference/cbitmapbutton-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)