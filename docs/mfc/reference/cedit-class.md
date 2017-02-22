---
title: "CEdit Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEdit class"
  - "컨트롤[MFC], edit"
  - "edit controls"
  - "edit controls, 클래스"
  - "line separators in multiline edit controls"
  - "multiline edit control"
  - "구분 문자, in multiline edit controls"
  - "text editors"
  - "text editors, CEdit class"
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 편집 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CEdit : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CEdit::CEdit](../Topic/CEdit::CEdit.md)|생성 된 `CEdit` 컨트롤 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CEdit::CanUndo](../Topic/CEdit::CanUndo.md)|컨트롤 편집 작업을 취소할 수 있는지 여부를 결정 합니다.|  
|[CEdit::CharFromPos](../Topic/CEdit::CharFromPos.md)|줄 및 문자 지정 된 위치에 가장 가까운 문자의 인덱스를 검색합니다.|  
|[CEdit::Clear](../Topic/CEdit::Clear.md)|편집에서 현재 선택 \(있는 경우\) 삭제 \(취소\)를 제어 합니다.|  
|[CEdit::Copy](../Topic/CEdit::Copy.md)|현재 선택 영역 \(있을 경우\) 편집 컨트롤을 클립보드에 복사  **CF\_TEXT** 형식입니다.|  
|[CEdit::Create](../Topic/CEdit::Create.md)|Windows 편집 컨트롤을 만들고이에 연결 된 `CEdit` 개체입니다.|  
|[CEdit::Cut](../Topic/CEdit::Cut.md)|편집에서 현재 선택 \(있는 경우\) 삭제 \(컷\)을 제어 하 고 삭제 된 텍스트를 클립보드에 복사  **CF\_TEXT** 형식입니다.|  
|[CEdit::EmptyUndoBuffer](../Topic/CEdit::EmptyUndoBuffer.md)|\(취소\) 실행 취소 플래그의 편집 컨트롤을 다시 설정합니다.|  
|[CEdit::FmtLines](../Topic/CEdit::FmtLines.md)|소프트 줄 바꿈 문자 포함 켜거나 여러 줄 편집 컨트롤에 설정합니다.|  
|[CEdit::GetCueBanner](../Topic/CEdit::GetCueBanner.md)|텍스트 큐 또는 팁 컨트롤이 비어 있고 포커스가 없는 경우 편집 컨트롤에 표시 되는 텍스트를 검색 합니다.|  
|[CEdit::GetFirstVisibleLine](../Topic/CEdit::GetFirstVisibleLine.md)|편집 컨트롤에 표시 되는 맨 위 줄을 결정합니다.|  
|[CEdit::GetHandle](../Topic/CEdit::GetHandle.md)|여러 줄 편집 컨트롤의 경우 현재 할당 된 메모리에 대 한 핸들을 검색 합니다.|  
|[CEdit::GetHighlight](../Topic/CEdit::GetHighlight.md)|시작 및 끝 문자를 현재 편집 컨트롤에서 강조 표시 된 텍스트 범위를 가져옵니다.|  
|[CEdit::GetLimitText](../Topic/CEdit::GetLimitText.md)|이 텍스트의 최대 크기를 가져옵니다 `CEdit` 포함 될 수 있습니다.|  
|[CEdit::GetLine](../Topic/CEdit::GetLine.md)|편집 컨트롤에서 텍스트 줄을 검색합니다.|  
|[CEdit::GetLineCount](../Topic/CEdit::GetLineCount.md)|여러 줄 편집 컨트롤의 줄 수를 검색합니다.|  
|[CEdit::GetMargins](../Topic/CEdit::GetMargins.md)|왼쪽 및 오른쪽 여백에 가져옵니다 `CEdit`.|  
|[CEdit::GetModify](../Topic/CEdit::GetModify.md)|편집 컨트롤의 내용이 수정 되었는지 여부를 결정 합니다.|  
|[CEdit::GetPasswordChar](../Topic/CEdit::GetPasswordChar.md)|텍스트를 입력할 때 편집 컨트롤에 표시 되는 암호 문자를 검색 합니다.|  
|[CEdit::GetRect](../Topic/CEdit::GetRect.md)|서식 지정 영역을 편집 컨트롤을 가져옵니다.|  
|[CEdit::GetSel](../Topic/CEdit::GetSel.md)|편집 컨트롤에서 현재 선택 영역의 첫 번째 및 마지막 문자 위치를 가져옵니다.|  
|[CEdit::HideBalloonTip](../Topic/CEdit::HideBalloonTip.md)|현재 편집 컨트롤에 연결 된 풍선 팁을 숨깁니다.|  
|[CEdit::LimitText](../Topic/CEdit::LimitText.md)|사용자는 편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 합니다.|  
|[CEdit::LineFromChar](../Topic/CEdit::LineFromChar.md)|지정 된 문자 인덱스를 포함 하는 줄의 줄 번호를 검색 합니다.|  
|[CEdit::LineIndex](../Topic/CEdit::LineIndex.md)|문자 줄 내의 여러 줄 편집 컨트롤의 인덱스를 검색합니다.|  
|[CEdit::LineLength](../Topic/CEdit::LineLength.md)|편집 컨트롤에서 행을 검색합니다.|  
|[CEdit::LineScroll](../Topic/CEdit::LineScroll.md)|여러 줄 편집 컨트롤의 텍스트를 스크롤합니다.|  
|[CEdit::Paste](../Topic/CEdit::Paste.md)|편집 컨트롤의 현재 커서 위치에 클립보드의 데이터를 삽입합니다.  클립보드에 데이터가 있는 경우에 데이터 삽입  **CF\_TEXT** 형식입니다.|  
|[CEdit::PosFromChar](../Topic/CEdit::PosFromChar.md)|지정 된 문자 인덱스의 왼쪽 위 모퉁이의 좌표를 검색합니다.|  
|[CEdit::ReplaceSel](../Topic/CEdit::ReplaceSel.md)|편집 컨트롤에서 현재 선택 영역을 지정한 텍스트로 바꿉니다.|  
|[CEdit::SetCueBanner](../Topic/CEdit::SetCueBanner.md)|텍스트 큐 또는 팁 컨트롤이 비어 있고 포커스가 없는 경우 편집 컨트롤에 표시 되는 텍스트를 설정 합니다.|  
|[CEdit::SetHandle](../Topic/CEdit::SetHandle.md)|여러 줄 편집 컨트롤에서 사용 되는 로컬 메모리 핸들을 설정 합니다.|  
|[CEdit::SetHighlight](../Topic/CEdit::SetHighlight.md)|컨트롤 내에서 현재 표시 되는 텍스트는 강조 표시를 편집 합니다.|  
|[CEdit::SetLimitText](../Topic/CEdit::SetLimitText.md)|이 텍스트의 최대 크기를 설정 `CEdit` 포함 될 수 있습니다.|  
|[CEdit::SetMargins](../Topic/CEdit::SetMargins.md)|왼쪽 및 오른쪽 여백을 설정 하에이 `CEdit`.|  
|[CEdit::SetModify](../Topic/CEdit::SetModify.md)|설정 하거나 편집 컨트롤에 대 한 수정 플래그를 지웁니다.|  
|[CEdit::SetPasswordChar](../Topic/CEdit::SetPasswordChar.md)|설정 하거나 텍스트를 입력할 때 편집 컨트롤에 표시 되는 암호 문자를 제거 합니다.|  
|[CEdit::SetReadOnly](../Topic/CEdit::SetReadOnly.md)|편집 컨트롤의 읽기 전용 상태를 설정합니다.|  
|[CEdit::SetRect](../Topic/CEdit::SetRect.md)|여러 줄 편집 컨트롤의 형식 사각형을 설정 하 고 컨트롤을 업데이트 합니다.|  
|[CEdit::SetRectNP](../Topic/CEdit::SetRectNP.md)|제어 창을 다시 그릴 필요 없이 여러 줄 편집 컨트롤의 형식 사각형을 설정 합니다.|  
|[CEdit::SetSel](../Topic/CEdit::SetSel.md)|편집 컨트롤에서 문자 범위를 선택합니다.|  
|[CEdit::SetTabStops](../Topic/CEdit::SetTabStops.md)|설정 탭에서 여러 줄 편집 컨트롤.|  
|[CEdit::ShowBalloonTip](../Topic/CEdit::ShowBalloonTip.md)|현재 편집 컨트롤에 연결 된 풍선 팁을 표시 합니다.|  
|[CEdit::Undo](../Topic/CEdit::Undo.md)|마지막 컨트롤 편집 작업을 취소합니다.|  
  
## 설명  
 편집 컨트롤에 사용자가 텍스트를 입력할 수 있는 직사각형 자식 창입니다.  
  
 편집 컨트롤을 대화 상자 템플릿 또는 코드에서 직접 만들 수 있습니다.  두 경우 모두 먼저 생성자를 호출 `CEdit` 생성 하는 `CEdit` 개체를 호출 하 고 있는  [만들기](../Topic/CEdit::Create.md) 멤버 함수를 만들려면 Windows 컨트롤을 편집 하 고 연결할는 `CEdit` 개체.  
  
 건설 1 단계 프로세스에서 파생 된 클래스에서 사용할 수 있습니다 `CEdit`.  생성자는 파생 된 클래스와 호출을 작성 합니다.  **만들기** 에서 생성자 내에서.  
  
 `CEdit`상속에서 중요 한 기능 `CWnd`.  설정에서 텍스트를 검색 하는 `CEdit` 개체, 사용은 `CWnd` 멤버 함수  [SetWindowText](../Topic/CWnd::SetWindowText.md) 및  [GetWindowText](../Topic/CWnd::GetWindowText.md), 설정 또는 여러 줄로 된 컨트롤의 경우에 편집 컨트롤의 전체 내용을 가져옵니다.  텍스트 줄에는 '\\r\\n' 문자 시퀀스를 구분 합니다.  또한 여러 줄 편집 컨트롤 이면 get 및 호출 하 여 컨트롤의 텍스트 부분을 설정 된 `CEdit` 멤버 함수  [GetLine](../Topic/CEdit::GetLine.md),  [SetSel](../Topic/CEdit::SetSel.md),  [GetSel](../Topic/CEdit::GetSel.md), 및  [ReplaceSel](../Topic/CEdit::ReplaceSel.md).  
  
 편집 컨트롤에서 자신의 부모에 보냅니다 Windows 알림 메시지를 처리 하는 경우 \(일반적으로 클래스에서 파생 된 `CDialog`\), 각 메시지에 대 한 부모 클래스 메시지 맵 엔트리와 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 엔트리는 다음과 같은 형식을 사용합니다.  
  
 **ON\_**알림**\(***id, memberFxn***\)**  
  
 위치 `id` 의 편집 컨트롤에서 알림 메시지를 보내는 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 했다고 부모 멤버 함수의 이름입니다.  
  
 상위 함수 프로토타입은 다음과 같습니다.  
  
 **afx\_msg** void memberFxn**\(\);**  
  
 메시지 맵 항목 목록과 부모에 전송 하는 경우에 대 한 설명은 다음과가 같습니다.  
  
-   **ON\_EN\_CHANGE** 사용자는 텍스트 편집 컨트롤에서 변경한 작업을 수행 한다고 했습니다.  달리는  **EN\_UPDATE** 알림 메시지가이 알림 메시지를 보낼 표시 Windows 업데이트 후.  
  
-   **ON\_EN\_ERRSPACE** 편집 컨트롤 특정 요청을 충족 시키기 위해 충분 한 메모리를 할당할 수 없습니다.  
  
-   **ON\_EN\_HSCROLL** 편집 컨트롤의 가로 스크롤 막대를 클릭할.  화면 업데이트 되기 전에 부모 창에 알립니다.  
  
-   **ON\_EN\_KILLFOCUS** 편집 컨트롤이 입력된 포커스를 잃었을.  
  
-   **ON\_EN\_MAXTEXT** 현재 삽입 문자 편집 컨트롤의 지정 된 수를 초과 했기 때문에 잘립니다.  편집 컨트롤에 없는 경우에 전달 된  **ES\_AUTOHSCROLL** 삽입 될 문자의 개수 및 스타일 편집 컨트롤의 너비를 초과 합니다.  편집 컨트롤에 없는 경우에 전달 된  **ES\_AUTOVSCROLL** 스타일 및 총 줄에서 텍스트 삽입 결과로 편집 컨트롤의 높이 초과 합니다.  
  
-   **ON\_EN\_SETFOCUS** 편집 컨트롤에 입력된 포커스를 받을 때 전송 합니다.  
  
-   **ON\_EN\_UPDATE** 변경된 된 텍스트를 나타내려면 편집 컨트롤입니다.  컨트롤의 텍스트 서식을 지정한 후 했지만 창 크기를 변경할 수 있도록 해당 텍스트가 필요한 경우 스크린 하기 전에 전송 됩니다.  
  
-   **ON\_EN\_VSCROLL** 편집 컨트롤의 세로 스크롤 막대를 클릭 합니다.  화면 업데이트 되기 전에 부모 창에 알립니다.  
  
 만들면는 `CEdit` 대화 상자에서 내 개체는 `CEdit` 개체 대화 상자를 닫으면 자동으로 소멸 합니다.  
  
 만들 경우는 `CEdit` 대화 상자 편집기를 사용 하 여 대화 상자 리소스에서 개체의 `CEdit` 개체 대화 상자를 닫으면 자동으로 소멸 합니다.  
  
 만들 경우는 `CEdit` 해야 파괴 하는 창 내의 개체입니다.  사용자가 만든 경우는 `CEdit` 개체는 스택에 자동으로 소멸 됩니다.  만들면는 `CEdit` 개체를 사용 하 여 힙에  **새** 해야 호출 함수를  **삭제** 편집 컨트롤 개체에서 사용자는 Windows 종료 되 면 파기 합니다.  모든 메모리를 할당 하는 경우는 `CEdit` 개체, 재정의 `CEdit` 할당을 삭제 하는 소멸자입니다.  
  
 편집 컨트롤에 특정 스타일을 수정 하려면 \(같은  **ES\_READONLY**\)를 사용 하지 않고 컨트롤에 특정 메시지를 보내야 합니다  [ModifyStyle](../Topic/CWnd::ModifyStyle.md).  볼  [편집 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775464) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 에 대 한 자세한 내용은 `CEdit`을 참조 하십시오.  
  
-   [컨트롤](../../mfc/controls-mfc.md)  
  
-   기술 자료 문서 Q259949: INFO: Setcaretpos\(\)는 적합 하지 않은 CEdit 또는 CRichEditCtrl 컨트롤  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CEdit`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [MFC 샘플 CALCDRIV](../../top/visual-cpp-samples.md)   
 [MFC 샘플 CMNCTRL2](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)