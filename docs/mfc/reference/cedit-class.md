---
title: CEdit 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
dev_langs:
- C++
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72bf4ffb56ad34926b3a47d86d7609aae5dff4f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="cedit-class"></a>CEdit Class
Windows 편집 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|생성 된 `CEdit` control 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|편집 컨트롤 작업을 취소할 수 있는지 여부를 결정 합니다.|  
|[CEdit::CharFromPos](#charfrompos)|지정된 된 위치에 가장 가까운 문자에 대 한 줄과 문자 인덱스를 검색합니다.|  
|[CEdit::Clear](#clear)|삭제 (취소) 편집에서 현재 선택한 (있을 경우)를 제어 합니다.|  
|[CEdit::Copy](#copy)|현재 선택 영역 복사 (있는 경우) 편집 컨트롤의 클립보드에 **CF_TEXT** 형식입니다.|  
|[CEdit::Create](#create)|Windows 편집 컨트롤을 만들고에 연결 된 `CEdit` 개체입니다.|  
|[CEdit::Cut](#cut)|삭제 (컷) 편집에서 현재 선택한 (있을 경우)을 제어 하 고 삭제 된 텍스트를 클립보드에 복사 **CF_TEXT** 형식입니다.|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|한 편집 실행 취소 플래그 (취소) 컨트롤을 다시 설정합니다.|  
|[CEdit::FmtLines](#fmtlines)|여러 줄 편집 컨트롤 내에서 소프트 줄 바꿈 문자를 포함 하거나 해제를 설정합니다.|  
|[CEdit::GetCueBanner](#getcuebanner)|텍스트 큐 또는 컨트롤 비어 있고 포커스가 없는 경우에 편집 컨트롤에 팁으로 표시 되는 텍스트를 검색 합니다.|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|편집 컨트롤에서 표시 되는 맨 위에 있는 줄을 결정합니다.|  
|[CEdit::GetHandle](#gethandle)|여러 줄 편집 컨트롤에 대 한 현재 할당 된 메모리에 대 한 핸들을 검색 합니다.|  
|[CEdit::GetHighlight](#gethighlight)|시작 값과 현재 편집 컨트롤에 강조 표시 된 텍스트 범위에 있는 문자 끝의 인덱스를 가져옵니다.|  
|[CEdit::GetLimitText](#getlimittext)|이 텍스트의 최대 크기를 가져옵니다 `CEdit` 포함 될 수 있습니다.|  
|[CEdit::GetLine](#getline)|편집 컨트롤에서 텍스트 줄을 검색합니다.|  
|[CEdit::GetLineCount](#getlinecount)|여러 줄 편집 컨트롤에 있는 줄의 수를 검색 합니다.|  
|[CEdit::GetMargins](#getmargins)|이 대 한 왼쪽 및 오른쪽 여백을 가져옵니다 `CEdit`합니다.|  
|[CEdit::GetModify](#getmodify)|편집 컨트롤의 내용을 수정 되었는지 여부를 결정 합니다.|  
|[CEdit::GetPasswordChar](#getpasswordchar)|사용자가 텍스트를 입력 하면 편집 컨트롤에 표시 되는 암호 문자를 검색 합니다.|  
|[CEdit::GetRect](#getrect)|편집 컨트롤의 서식 지정 영역을 가져옵니다.|  
|[CEdit::GetSel](#getsel)|편집 컨트롤에서 현재 선택 항목의 첫 문자와 마지막 문자 위치를 가져옵니다.|  
|[CEdit::HideBalloonTip](#hideballoontip)|현재 편집 컨트롤과 관련 된 모든 풍선 설명을 숨깁니다.|  
|[CEdit::LimitText](#limittext)|사용자가 편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 합니다.|  
|[CEdit::LineFromChar](#linefromchar)|지정된 된 문자 인덱스를 포함 하는 줄의 줄 번호를 검색 합니다.|  
|[CEdit::LineIndex](#lineindex)|여러 줄 편집 컨트롤 내에서 한 줄의 문자 인덱스를 검색 합니다.|  
|[CEdit::LineLength](#linelength)|Edit 컨트롤의 줄 길이 검색합니다.|  
|[CEdit::LineScroll](#linescroll)|여러 줄 편집 컨트롤의 텍스트가 스크롤됩니다.|  
|[CEdit::Paste](#paste)|클립보드의 현재 커서 위치에 있는 편집 컨트롤에 데이터를 삽입합니다. 데이터를 클립보드에 데이터를 포함 하는 경우에 삽입 **CF_TEXT** 형식입니다.|  
|[CEdit::PosFromChar](#posfromchar)|지정 된 문자 인덱스의 왼쪽 위 모퉁이의 좌표를 검색합니다.|  
|[CEdit::ReplaceSel](#replacesel)|지정 된 텍스트 편집 컨트롤에서 현재 선택 영역을 바꿉니다.|  
|[CEdit::SetCueBanner](#setcuebanner)|텍스트 큐 또는 컨트롤 비어 있고 포커스가 없는 경우에 편집 컨트롤에 팁으로 표시 되는 텍스트를 설정 합니다.|  
|[CEdit::SetHandle](#sethandle)|여러 줄 편집 컨트롤에 의해 사용 될 로컬 메모리에 핸들을 설정 합니다.|  
|[CEdit::SetHighlight](#sethighlight)|현재에서 표시 되는 텍스트의 범위는 밝은 편집 컨트롤입니다.|  
|[CEdit::SetLimitText](#setlimittext)|이 텍스트의 최대 크기를 설정 `CEdit` 포함 될 수 있습니다.|  
|[CEdit::SetMargins](#setmargins)|왼쪽 및 오른쪽 여백을 설정 하 고이 대 한 `CEdit`합니다.|  
|[CEdit::SetModify](#setmodify)|설정 하거나 편집 컨트롤에 대 한 수정 플래그를 지웁니다.|  
|[CEdit::SetPasswordChar](#setpasswordchar)|설정 하거나 사용자가 텍스트를 입력 하면 편집 컨트롤에 표시 되는 암호 문자를 제거 합니다.|  
|[CEdit::SetReadOnly](#setreadonly)|편집 컨트롤의 읽기 전용 상태를 설정합니다.|  
|[CEdit::SetRect](#setrect)|여러 줄 편집 컨트롤의 서식 지정 영역을 설정 하 고는 컨트롤을 업데이트 합니다.|  
|[CEdit::SetRectNP](#setrectnp)|제어 창 다시 그리기 하지 않고 여러 줄 편집 컨트롤의 서식 지정 영역을 설정 합니다.|  
|[CEdit::SetSel](#setsel)|편집 컨트롤에서 문자 범위를 선택합니다.|  
|[CEdit::SetTabStops](#settabstops)|설정 탭에 여러 줄 편집 컨트롤입니다.|  
|[CEdit::ShowBalloonTip](#showballoontip)|현재 편집 컨트롤과 연결 된 풍선 팁에 표시 됩니다.|  
|[CEdit::Undo](#undo)|마지막 편집 컨트롤 작업을 취소합니다.|  
  
## <a name="remarks"></a>설명  
 편집 컨트롤에는 사용자가 텍스트를 입력할 수 있는 사각형 자식 창입니다.  
  
 대화 상자 템플릿에서 또는 코드에서 직접 편집 컨트롤을 만들 수 있습니다. 두 경우 모두 먼저 생성자 호출 `CEdit` 생성 하는 `CEdit` 개체를 다음 호출는 [만들기](#create) 멤버 함수를 만들려면 Windows 편집 컨트롤에 연결 하 고는 `CEdit` 개체입니다.  
  
 생성에서 파생 된 클래스에서 프로세스인 수 `CEdit`합니다. 생성자는 파생된 클래스와 호출에 대 한 작성 **만들기** 에서 생성자 내에서.  
  
 `CEdit` 중요 한 기능을 상속 `CWnd`합니다. 설정 하 고 텍스트를 검색 한 `CEdit` 개체를 가져오려면는 `CWnd` 멤버 함수 [SetWindowText](cwnd-class.md#setwindowtext) 및 [GetWindowText](cwnd-class.md#getwindowtext), 있는 set 또는 get 편집의 전체 내용을 제어 하 고, 경우에도 것 여러 줄로 된 컨트롤이입니다. 여러 줄로 된 컨트롤의 텍스트 줄 문자 시퀀스 '\r\n'로 구분 됩니다. 또한 여러 줄 편집 컨트롤의 경우 가져오고 호출 하 여 컨트롤의 텍스트의 일부 설정의 `CEdit` 멤버 함수 [GetLine](#getline), [SetSel](#setsel), [GetSel](#getsel), 및 [ ReplaceSel](#replacesel)합니다.  
  
 부모에 편집 컨트롤에서 보낸 Windows 알림 메시지를 처리 하려는 경우 (일반적으로 클래스에서 파생 `CDialog`), 각 메시지에 대 한 부모 클래스에는 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 항목은 다음 형식을 사용 합니다.  
  
 **ON_** 알림 **(** *id, memberFxn * * *)**  
  
 여기서 `id` 알림 메시지를 전송 하는 편집 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 한 부모 멤버 함수의 이름입니다.  
  
 부모의 함수 프로토타입에 다음과 같습니다.  
  
 **afx_msg** void memberFxn **();**  
  
 다음은 잠재적인 메시지 맵 항목 목록과 부모로 전송 되 하는 경우에 대 한 설명을입니다.  
  
- **ON_EN_CHANGE** 사용자가 편집 컨트롤의 텍스트를 변경할 수 있는 동작을 수행한 합니다. 와 달리는 **EN_UPDATE** 알림 메시지를 Windows 업데이트는 표시 된 후이 알림 메시지가 전달 됩니다.  
  
- **ON_EN_ERRSPACE** 편집 컨트롤에서 특정 요청을 충족 하기 위해 충분 한 메모리를 할당할 수 없습니다.  
  
- **ON_EN_HSCROLL** 사용자가 편집 컨트롤의 가로 스크롤 막대를 클릭 합니다. 부모 창에는 화면 업데이트 되기 전에 알림이 전송 됩니다.  
  
- **ON_EN_KILLFOCUS** 편집 컨트롤이 입력된 포커스를 잃을 합니다.  
  
- **ON_EN_MAXTEXT** 현재 삽입 지정 된 편집 컨트롤에 대 한 문자 수를 초과 했습니다 및 잘렸습니다. 편집 컨트롤에 없는 경우에 전달는 **ES_AUTOHSCROLL** 스타일 및 삽입할 문자 수는 편집 컨트롤의 너비를 초과 합니다. 편집 컨트롤에 없는 경우에 전달는 **ES_AUTOVSCROLL** 스타일과 텍스트 삽입에서 발생 하는 줄의 총 수는 편집 컨트롤의 높이 초과 합니다.  
  
- **ON_EN_SETFOCUS** 편집 컨트롤이 입력된 포커스를 받을 때 보냅니다.  
  
- **ON_EN_UPDATE** 편집 컨트롤이 바뀐된 텍스트 표시 되려고 합니다. 컨트롤 텍스트의 서식을 지정한 되었으나 것 화면 텍스트 창 크기를 변경할 수 있도록 필요에 따라 보내집니다.  
  
- **ON_EN_VSCROLL** 사용자가 편집 컨트롤의 세로 스크롤 막대를 클릭 합니다. 부모 창에는 화면 업데이트 되기 전에 알림이 전송 됩니다.  
  
 만드는 경우는 `CEdit` 대화 상자 내에서 개체는 `CEdit` 개체는 사용자가 대화 상자를 닫을 때 자동으로 제거 됩니다.  
  
 만드는 경우는 `CEdit` 대화 상자 편집기를 사용 하 여 대화 상자 리소스에서 개체는 `CEdit` 개체는 사용자가 대화 상자를 닫을 때 자동으로 제거 됩니다.  
  
 만드는 경우는 `CEdit` 개체 창으로 삭제 해야 할 수도 있습니다. 만드는 경우는 `CEdit` 개체 스택, 자동으로 삭제 됩니다. 만드는 경우는 `CEdit` 개체를 사용 하 여 힙에 **새** 함수를 호출한 다음 **삭제** 사용자 Windows 종료 될 때 소멸 시킬 개체에서 컨트롤을 편집 합니다. 에 메모리를 할당 하는 경우는 `CEdit` 개체, 재정의 `CEdit` 할당을 삭제 하는 소멸자입니다.  
  
 Edit 컨트롤의 특정 스타일을 수정 하려면 (같은 **ES_READONLY**)를 사용 하는 대신 해당 컨트롤에 특정 메시지를 보내야 [ModifyStyle](cwnd-class.md#modifystyle)합니다. 참조 [컨트롤 스타일 편집](http://msdn.microsoft.com/library/windows/desktop/bb775464) in the Windows SDK입니다.  
  
 대 한 자세한 내용은 `CEdit`를 참조 하세요.  
  
- [컨트롤](../../mfc/controls-mfc.md)  
  
-   기술 자료 문서 Q259949: 정보: SetCaretPos()은 적합 하지 않은 CEdit 또는 CRichEditCtrl 컨트롤  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="canundo"></a>  CEdit::CanUndo  
 마지막 편집 작업을 취소할 수 있으면 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 호출 마지막 편집 작업을 취소 하면 0이 아니고는 **실행 취소** 멤버 함수가 고, 0은 실행 취소할 수 없는 경우.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::Undo](#undo)합니다.  
  
##  <a name="cedit"></a>  CEdit::CEdit  
 `CEdit` 개체를 생성합니다.  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>설명  
 사용 하 여 [만들기](#create) Windows 편집 컨트롤을 생성 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>  CEdit::CharFromPos  
 0부터 시작 줄 및 지정된 된 점이이 가장 가까운 문자의 문자 인덱스를 검색 하려면이 함수 호출 `CEdit` 컨트롤  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 이 클라이언트 영역에 있는 점의 좌표 `CEdit` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 낮은 순서로 문자 인덱스 **단어**, 및의 상위에 있는 줄 인덱스 **단어**합니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용 가능 합니다.  
  
 자세한 내용은 참조 [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>  CEdit::Clear  
 삭제 하려면 (clear) 현재 선택 영역 (있는 경우) 편집 컨트롤에이 함수를 호출 합니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>설명  
 수행한 삭제 **지우기** 호출 하 여 실행 취소 될 수는 [실행 취소](#undo) 멤버 함수입니다.  
  
 현재 선택 영역을 삭제 하 고 삭제 된 내용을 클립보드에 배치 하려면 호출는 [잘라내기](#cut) 멤버 함수입니다.  
  
 자세한 내용은 참조 [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>  CEdit::Copy  
 이 함수를 호출 복사 현재 선택 영역 (있는 경우)를 클립보드에 편집 컨트롤에 **CF_TEXT** 형식입니다.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>  CEdit::Create  
 Windows 편집 컨트롤을 만들고에 연결 된 `CEdit` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 편집 컨트롤의 스타일을 지정합니다. 어떠한 조합의 적용 [스타일 편집](styles-used-by-mfc.md#edit-styles) 컨트롤에 있습니다.  
  
 `rect`  
 편집 컨트롤의 크기와 위치를 지정합니다. 일 수 있습니다는 `CRect` 개체 또는 `RECT` 구조입니다.  
  
 `pParentWnd`  
 편집 컨트롤의 부모 창 (일반적으로 `CDialog`). 않아야 **NULL**합니다.  
  
 `nID`  
 편집 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CEdit` 두 단계를 수행에서 하는 개체입니다. 먼저를 호출 하는 `CEdit` 생성자 및 호출 합니다 **만들기**, Windows 편집 컨트롤을 만들고에 연결 하는 `CEdit` 개체입니다.  
  
 때 **만들기** 실행 되 면 Windows 보냅니다는 [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635), [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634), [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619), 및 [WM_ GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) 편집 컨트롤에는 메시지입니다.  
  
 기본적으로 이러한 메시지의 처리는 [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), 및 [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) 멤버 함수 에 `CWnd` 기본 클래스입니다. 기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CEdit`, 메시지 맵을 새 클래스에 추가 하 고 위의 메시지 처리기 멤버 함수를 재정의 합니다. 재정의 `OnCreate`, 예를 들어 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.  
  
 다음 적용 [창 스타일](styles-used-by-mfc.md#window-styles) 를 편집 컨트롤입니다.  
  
- **WS_CHILD** 항상  
  
- **WS_VISIBLE** Usually  
  
- **WS_DISABLED** 거의  
  
- **WS_GROUP** 컨트롤을 그룹화  
  
- **WS_TABSTOP** 탭 이동 순서에 편집 컨트롤을 포함 하려면  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>  CEdit::Cut  
 편집 컨트롤에 현재 선택 항목 (있는 경우) (잘라내기)을 삭제 하려면이 함수를 호출 하 고 삭제 된 텍스트를 클립보드에 복사 **CF_TEXT** 형식입니다.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>설명  
 수행한 삭제 **잘라내기** 호출 하 여 실행 취소 될 수는 [실행 취소](#undo) 멤버 함수입니다.  
  
 삭제 된 텍스트를 클립보드에 배치 하지 않고 현재 선택 영역을 삭제 하려면 호출는 [지우기](#clear) 멤버 함수입니다.  
  
 자세한 내용은 참조 [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer  
 편집 컨트롤의 실행 취소 플래그 (암호화 되지 않음)를 다시 설정 하려면이 함수를 호출 합니다.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>설명  
 편집 컨트롤이 이제 없게 됩니다 마지막 작업을 취소할 수 있습니다. 편집 컨트롤 내에서 작업을 취소할 수 될 때마다 실행 취소 플래그가 설정 됩니다.  
  
 실행 취소 플래그는 자동으로 선택이 취소 될 때마다는 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) 또는 [SetHandle](#sethandle) `CWnd` 멤버 함수가 호출 됩니다.  
  
 자세한 내용은 참조 [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>  CEdit::FmtLines  
 여러 줄 편집 컨트롤 내에서 소프트 줄 바꿈 문자를 포함 하거나 해제를 설정 하려면이 함수를 호출 합니다.  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAddEOL*  
 소프트 줄 바꿈 문자를 삽입할 수 있는지 지정 합니다. 값이 **TRUE** ; 문자를 삽입 값 **FALSE** 제거 합니다.  
  
### <a name="return-value"></a>반환 값  
 있는 경우 0이 아닌 형식 발생 합니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 소프트 줄 바꿈을 두 개의 캐리지 리턴 및 줄 바꿈 때문에 중단 되는 줄의 끝에 삽입 된 줄 바꿈 이루어져 있습니다. 하드 줄 바꿈을 하나의 캐리지 리턴 및 줄 바꿈 이루어져 있습니다. 하드 줄 바꿈을으로 끝나는 줄 영향을 받지 않는 `FmtLines`합니다.  
  
 경우에 Windows 응답할는 `CEdit` 개체는 여러 줄 편집 컨트롤입니다.  
  
 `FmtLines` 반환 되는 버퍼에만 영향을 [GetHandle](#gethandle) 및에서 반환 된 텍스트 [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627)합니다. 있기 편집 컨트롤에서 텍스트의 표시에 영향을 주지 않습니다.  
  
 자세한 내용은 참조 [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>  CEdit::GetCueBanner  
 텍스트 큐 또는 컨트롤 비어 있을 때의 편집 컨트롤에 팁으로 표시 되는 텍스트를 검색 합니다.  
  
```  
BOOL GetCueBanner(
    LPWSTR lpszText,  
    int cchText) const;  
  
CString GetCueBanner() const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `lpszText`  
 큐 텍스트를 포함 하는 문자열에 대 한 포인터입니다.  
  
 [in] `cchText`  
 받을 수 있는 문자의 수입니다. 포함 하는 종료 `NULL` 문자입니다.  
  
### <a name="return-value"></a>반환 값  
 첫 번째 오버 로드에 대 한 `true` 메서드가 성공 상태가 아니면 `false`합니다.  
  
 두 번째 오버 로드에 대 한 한 [CString](../../atl-mfc-shared/using-cstring.md) 방법이 고, 그러지 않으면 경우 큐 텍스트를 포함 하는 빈 문자열 ("").  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) 메시지는 Windows SDK에 설명 되어 있습니다. 자세한 내용은 참조는 [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695) 매크로입니다.  
  
##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine  
 편집 컨트롤에서 표시 되는 맨 위에 있는 줄을 확인 하려면이 함수를 호출 합니다.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>반환 값  
 맨 위에 표시 되는 줄의 0부터 시작 하는 인덱스입니다. 단일 행 편집 컨트롤에 대 한 반환 값은 0입니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>  CEdit::GetHandle  
 여러 줄 편집 컨트롤에 현재 할당 된 메모리에 대 한 핸들을 검색 하려면이 함수를 호출 합니다.  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 편집 컨트롤의 콘텐츠를 보유 하는 버퍼를 식별 하는 로컬 메모리 핸들입니다. 단일 행 편집 컨트롤에 메시지를 보내는 것과 같은 오류가 발생 하는 경우 반환 값은 0입니다.  
  
### <a name="remarks"></a>설명  
 핸들은 로컬 메모리 핸들 및 중 하나에서 사용할 수는 **로컬** 로컬 메모리를 사용 하는 Windows 메모리 함수의 매개 변수로 처리 합니다.  
  
 **GetHandle** 만 여러 줄 편집 컨트롤에 의해 처리 됩니다.  
  
 호출 **GetHandle** 대화 상자를 사용 하 여 만든 경우에 대화 상자에서 여러 줄 편집 컨트롤에 대 한는 **DS_LOCALEDIT** 스타일 플래그를 설정 합니다. 경우는 **DS_LOCALEDIT** 스타일 설정 되지 않은, 0이 아닌 반환 값을 계속 받아볼 수 있지만 반환 된 값을 사용할 수 없습니다.  
  
> [!NOTE]
> **GetHandle** Windows 95/98에서는 작동 하지 않습니다. 호출 하는 경우 **GetHandle** Windows 95/98에서 반환 됩니다. **NULL**합니다. **GetHandle** Windows NT 버전 3.51 이상에서 설명한 대로 작동 합니다.  
  
 자세한 내용은 참조 [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>  CEdit::GetHighlight  
 현재 편집 컨트롤에 강조 표시 된 텍스트 범위에서 첫 문자와 마지막 문자 인덱스를 가져옵니다.  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `pichStart`|강조 표시 된 텍스트 범위에서 첫 번째 문자의 0부터 시작 인덱스입니다.|  
|[out] `pichEnd`|강조 표시 된 텍스트 범위에서 마지막 문자의 0부터 시작 인덱스입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getlimittext"></a>  CEdit::GetLimitText  
 이 대 한 텍스트 제한 하려면이 함수를 호출 `CEdit` 개체입니다.  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 텍스트 크기 제한 (바이트)이 `CEdit` 개체입니다.  
  
### <a name="remarks"></a>설명  
 텍스트 제한은 텍스트 편집 컨트롤이 수락할 수 있는 바이트의 최대 크기입니다.  
  
> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용 가능 합니다.  
  
 자세한 내용은 참조 [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="getline"></a>  CEdit::GetLine  
 편집 컨트롤에서 텍스트 줄을 검색 하려면이 함수를 호출 하 고에 `lpszBuffer`합니다.  
  
```  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer,  
    int nMaxLength) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 편집 컨트롤에서 여러 줄 검색 하려면 줄 번호를 지정 합니다. 줄 번호는 0부터 시작 합니다. 값이 0 첫 번째 줄을 지정합니다. 이 매개 변수는 단일 행 편집 컨트롤에 의해 무시 됩니다.  
  
 `lpszBuffer`  
 줄의 복사본을 수신 하는 버퍼를 가리킵니다. 버퍼의 첫 번째 단어는 최대 버퍼에 복사할 수 있는 문자 수를 지정 해야 합니다.  
  
 `nMaxLength`  
 버퍼에 복사할 수 있는 바이트의 최대 수를 지정 합니다. `GetLine` 이 값의 첫 번째 단어에서 배치 `lpszBuffer` Windows 호출 하기 전에.  
  
### <a name="return-value"></a>반환 값  
 실제로 복사 된 바이트 수입니다. 지정 된 줄 번호가 반환 값 0은 `nIndex` 편집 컨트롤의 줄 번호 보다 큽니다.  
  
### <a name="remarks"></a>설명  
 복사한 행에 null 종결 문자가 없습니다.  
  
 자세한 내용은 참조 [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::GetLineCount](#getlinecount)합니다.  
  
##  <a name="getlinecount"></a>  CEdit::GetLineCount  
 여러 줄 편집 컨트롤에는 줄 수를 검색 하려면이 함수를 호출 합니다.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 여러 줄의 줄 수가 포함 하는 정수 편집 컨트롤입니다. 편집 컨트롤에 없는 텍스트를 입력 하는 경우 반환 값은 1입니다.  
  
### <a name="remarks"></a>설명  
 `GetLineCount` 여러 줄 편집 컨트롤만 처리 됩니다.  
  
 자세한 내용은 참조 [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>  CEdit::GetMargins  
 이 편집 컨트롤의 왼쪽 및 오른쪽 여백을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>반환 값  
 낮은 순서로 왼쪽된 여백 너비 **단어** 와 높은 순서로 오른쪽 여백 너비 **단어**합니다.  
  
### <a name="remarks"></a>설명  
 여백은 픽셀 단위로 측정 됩니다.  
  
> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용 가능 합니다.  
  
 자세한 내용은 참조 [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)합니다.  
  
##  <a name="getmodify"></a>  CEdit::GetModify  
 편집 컨트롤의 내용을 수정 되었는지 여부를 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>반환 값  
 편집 컨트롤 내용이 수정 되었습니다. 0이 아닌 남아 있는 경우에 0 변경 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 Windows 편집 컨트롤의 내용이 변경 되었는지 여부를 나타내는 내부 플래그를 유지 관리 합니다. 편집 컨트롤이 처음 만들어질 하 고 호출 하 여 선택을 취소도 될 수 있습니다이 플래그가 해제 되 고 [SetModify](#setmodify) 멤버 함수입니다.  
  
 자세한 내용은 참조 [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar  
 사용자가 텍스트를 입력 하면 편집 컨트롤에 표시 되는 암호 문자를 검색 하려면이 함수를 호출 합니다.  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 입력 한 문자 대신 표시할 문자를 지정 합니다. 반환 값은 `NULL` 암호 문자가 있는 경우.  
  
### <a name="remarks"></a>설명  
 편집 컨트롤을 만드는 경우는 **ES_PASSWORD** 스타일에는 컨트롤을 지 원하는 DLL의 기본 암호 문자를 결정 합니다. 매니페스트 또는 [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) 메서드 확인 수 있도록 지 원하는 DLL은 편집 컨트롤입니다. 기본 암호 문자는 별표 user32.dll 편집 컨트롤을 지 원하는 경우 ('* ', U + 002A). Comctl32.dll 버전 6 편집 컨트롤을 지 원하는 경우 기본 문자는 검정색 원 ('●', U + 25CF)입니다. 공용 컨트롤 DLL 및 버전 지 원하는 방법에 대 한 자세한 내용은 참조 [셸 및 공용 컨트롤 버전](http://msdn.microsoft.com/library/windows/desktop/bb776779)합니다.  
  
 이 메서드는 전송 된 [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>  CEdit::GetRect  
 편집 컨트롤의 서식 지정 영역을 가져오려면이 함수를 호출 합니다.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `RECT` 구조체 서식 지정 영역입니다.  
  
### <a name="remarks"></a>설명  
 서식 지정 영역에 텍스트 편집 컨트롤 창 크기에 독립적인 제한 사각형이입니다.  
  
 가 여러 줄 편집 컨트롤의 서식 지정 영역을 수정할 수는 [SetRect](#setrect) 및 [SetRectNP](#setrectnp) 멤버 함수입니다.  
  
 자세한 내용은 참조 [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::LimitText](#limittext)합니다.  
  
##  <a name="getsel"></a>  CEdit::GetSel  
 시작과 끝의 반환 값 또는 매개 변수를 사용 하 여 편집 컨트롤에서 현재 선택한 (있는 경우)의 문자 위치를 가져오려면이 함수를 호출 합니다.  
  
```  
DWORD GetSel() const;  
  
void GetSel(
    int& nStartChar,  
    int& nEndChar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartChar`  
 현재 선택한 항목의 첫 번째 문자의 위치를 받게 됩니다 하는 정수에 대 한 참조입니다.  
  
 `nEndChar`  
 현재 선택 항목의 끝을 지나서 선택 되지 않은 첫 번째 문자의 위치를 받게 됩니다 하는 정수에 대 한 참조입니다.  
  
### <a name="return-value"></a>반환 값  
 버전을 반환 하는 `DWORD` 상위 word에서 선택 항목의 끝 다음 하위 단어의 시작 위치와 선택 되지 않은 첫 번째 문자의 위치를 포함 하는 값을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip  
 현재 편집 컨트롤과 관련 된 모든 풍선 설명을 숨깁니다.  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="limittext"></a>  CEdit::LimitText  
 사용자가 편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 하려면이 함수를 호출 합니다.  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nChars`  
 입력할 수 있는 텍스트의 바이트 단위로 지정 합니다. 텍스트 길이 설정 되어이 매개 변수가 0 이면 **UINT_MAX** 바이트입니다. 이것은 기본적인 동작입니다.  
  
### <a name="remarks"></a>설명  
 입력할 수 있는 텍스트에만 제한 텍스트 제한을 변경 합니다. 편집 컨트롤에 이미 모든 텍스트 없습니다 영향을 주지도 않습니다 것 영향을 복사 하 여 편집 컨트롤에서 텍스트의 길이 [SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수에 `CWnd`합니다. 응용 프로그램에서 사용 하는 경우는 `SetWindowText` 함수에 대 한 호출에서 지정 된 편집 컨트롤에 많은 텍스트를 배치 하려면 `LimitText`, 사용자에 편집 컨트롤에서 텍스트를 삭제할 수 있습니다. 그러나 텍스트 제한 기존 텍스트를 새 텍스트로 대체에서 사용자를 하지 것입니다, 그리고 현재 선택 영역을 삭제 하지 않는 한 문자 제한에는 텍스트입니다.  
  
> [!NOTE]
>  Win32에서 (Windows NT 및 Windows 95/98) [SetLimitText](#setlimittext) 이 함수를 대체 합니다.  
  
 자세한 내용은 참조 [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>  CEdit::LineFromChar  
 지정된 된 문자 인덱스를 포함 하는 줄의 줄 번호를 검색 하려면이 함수를 호출 합니다.  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 편집 컨트롤의 텍스트에 원하는 문자에 대 한 0부터 시작 인덱스 값을 포함 하거나-1을 포함 합니다. 경우 `nIndex` 은-1, 캐럿을 포함 하는 줄, 현재 줄을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 로 지정 된 문자 인덱스를 포함 하는 줄의 0부터 시작 줄 번호 `nIndex`합니다. 경우 `nIndex` 은-1, 선택 항목의 첫 번째 문자를 포함 하는 줄 번호 반환 됩니다. 선택 영역이 없는 경우 현재 줄 번호 반환 됩니다.  
  
### <a name="remarks"></a>설명  
 문자 인덱스에는 편집 컨트롤의 시작 부분부터 문자 수입니다.  
  
 이 멤버 함수는 여러 줄 편집 컨트롤에서만 사용 됩니다.  
  
 자세한 내용은 참조 [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>  CEdit::LineIndex  
 여러 줄 편집 컨트롤 내에서 한 줄의 문자 인덱스를 검색 하려면이 함수를 호출 합니다.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nLine`  
 원하는 줄 편집 컨트롤의 텍스트에 대 한 인덱스 값을 포함 하거나-1을 포함 합니다. 경우 `nLine` 은-1, 캐럿을 포함 하는 줄, 현재 줄을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 지정 된 줄의 문자 인덱스 `nLine` 또는 지정된 된 줄 번호는 편집 컨트롤의 줄 번호 보다 클 경우-1입니다.  
  
### <a name="remarks"></a>설명  
 문자 인덱스에 지정된 된 줄에 편집 컨트롤의 처음부터 문자의 수입니다.  
  
 이 멤버 함수는 여러 줄 편집 컨트롤에서만 처리 됩니다.  
  
 자세한 내용은 참조 [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="linelength"></a>  CEdit::LineLength  
 Edit 컨트롤의 줄 길이 검색합니다.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nLine`  
 줄 길이 검색할 문자의 0부터 시작 하는 인덱스입니다. 기본값은 -1입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값의 길이은 단일 행 편집 컨트롤에 대 한 `TCHAR`s 편집 컨트롤의 텍스트입니다.  
  
 반환 값은 길이, 다중 행 편집 컨트롤에 대 한 `TCHAR`로 지정 된 줄의 s는 `nLine` 매개 변수입니다. 에 대 한 [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] 텍스트 길이이 줄에서 바이트 수에는 유니코드 텍스트에 대 한 길이 줄에 있는 문자의 수입니다. 길이 줄의 끝에 캐리지 리턴 문자가 포함 되지 않습니다.  
  
 경우는 `nLine` 매개 변수가 보다 많은 컨트롤에 있는 문자의 수를 반환 값은 0입니다.  
  
 경우는 `nLine` 매개 변수가-1 이면 반환 값은 선택 된 문자를 포함 하는 줄의 선택 하지 않은 문자 수입니다. 예를 들어 다음 줄의 끝부터 8 번째 문자까지 한 줄의 4 번째 문자에서 선택 영역 확장, 반환 값은 10입니다. 즉, 첫 번째 줄에 다음 7 개 문자 3입니다.  
  
 에 대 한 자세한 내용은 `TCHAR` 입력, 참조는 `TCHAR` 테이블에서 행에에서 [Windows 데이터 형식](http://msdn.microsoft.com/library/windows/desktop/aa383751)합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 지원 되는 [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::LineIndex](#lineindex)합니다.  
  
##  <a name="linescroll"></a>  CEdit::LineScroll  
 여러 줄 편집 컨트롤의 텍스트를 스크롤하려면이 함수를 호출 합니다.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLines`  
 세로로 스크롤할 줄 수를 지정 합니다.  
  
 `nChars`  
 가 가로로 스크롤하도록 문자 위치의 수를 지정 합니다. 편집 컨트롤 중 하나에 있으면이 값은 무시 됩니다는 **ES_RIGHT** 또는 **ES_CENTER** 스타일입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.  
  
 편집 컨트롤의에서 텍스트의 마지막 줄을 지 나 편집 컨트롤이 세로로 스크롤되지 않습니다. 현재 줄로 지정 된 줄 수를 더한 경우 `nLines` 줄 편집 컨트롤의 총 수를 초과 하면, 마지막 줄 편집 컨트롤의 편집 컨트롤 창의 위쪽 스크롤할 수 있도록 조정 되는 값입니다.  
  
 `LineScroll` 용도 모든 줄의 마지막 문자를 지난 사이 이동 합니다.  
  
 자세한 내용은 참조 [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::GetFirstVisibleLine](#getfirstvisibleline)합니다.  
  
##  <a name="paste"></a>  CEdit::Paste  
 에 클립보드의 데이터를 삽입 하려면이 함수 호출의 `CEdit` 삽입 지점에 있습니다.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>설명  
 데이터를 클립보드에 데이터를 포함 하는 경우에 삽입 **CF_TEXT** 형식입니다.  
  
 자세한 내용은 참조 [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>  CEdit::PosFromChar  
 이 지정 된 문자 위치 (왼쪽 위 모퉁이)을 가져오려면이 함수를 호출 `CEdit` 개체입니다.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nChar`  
 지정 된 문자의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 로 지정 된 문자의 왼쪽 위 모퉁이의 좌표 `nChar`합니다.  
  
### <a name="remarks"></a>설명  
 문자는 0부터 시작 인덱스 값을 제공 하 여 지정 됩니다. 경우 `nChar` 이 마지막 문자 인덱스 보다 크면 `CEdit` 개체를 반환 값이 마지막 문자 바로 다음에 오는 문자 위치 좌표를 지정 `CEdit` 개체입니다.  
  
> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용 가능 합니다.  
  
 자세한 내용은 참조 [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::LineFromChar](#linefromchar)합니다.  
  
##  <a name="replacesel"></a>  CEdit::ReplaceSel  
 로 지정 된 텍스트로 편집 컨트롤에서 현재 선택 영역을 대체 하려면이 함수를 호출 `lpszNewText`합니다.  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszNewText`  
 대체 텍스트를 포함 하는 null로 끝나는 문자열을 가리킵니다.  
  
 `bCanUndo`  
 이 기능을 실행 취소할 수 있는지를 지정 하려면이 매개 변수의 값을 설정 **TRUE** 합니다. 기본값은 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 편집 컨트롤에서 텍스트의 일부만을 바꿉니다. 사용 하 여 모든 텍스트를 대체 하려면는 [CWnd::SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수입니다.  
  
 현재 선택 없으면 대체 텍스트는 현재 커서 위치에 삽입 됩니다.  
  
 자세한 내용은 참조 [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::LineIndex](#lineindex)합니다.  
  
##  <a name="setcuebanner"></a>  CEdit::SetCueBanner  
 텍스트 신호로 표시 또는 팁, 편집에서 컨트롤이 비어을 제어 하는 텍스트를 설정 합니다.  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lpszText`  
 편집 컨트롤에 표시할 큐를 포함 하는 문자열에 대 한 포인터입니다.  
  
 [in] `fDrawWhenFocused`  
 경우 `false`, 사용자가 편집 컨트롤에 컨트롤의 포커스를 제공 하는 경우 큐 배너 그려집니다.  
  
 경우 `true`, 컨트롤에 포커스가 있는 경우에 큐 배너 그려집니다. 큐 배너에는 컨트롤에 입력 하기 시작할 때 사라집니다.  
  
 기본값은 `false`입니다.  
  
### <a name="return-value"></a>반환 값  
 `true` 메서드가 성공 하면 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) 메시지는 Windows SDK에 설명 되어 있습니다. 자세한 내용은 참조는 [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703) 매크로입니다.  
  
### <a name="example"></a>예제  
 다음 예제는 [CEdit::SetCueBanner](#setcuebanner) 메서드.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>  CEdit::SetHandle  
 여러 줄 편집 컨트롤에 의해 사용 될 로컬 메모리에 핸들을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>매개 변수  
 *hBuffer*  
 로컬 메모리에 대 한 핸들을 포함합니다. 이 핸들에 대 한 이전 호출에서 만든 것 이어야는 [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows 함수를 사용 하는 **LMEM_MOVEABLE** 플래그입니다. Null로 끝나는 문자열을 포함 하는 메모리 간주 됩니다. 없는 경우 할당된 된 메모리의 첫 번째 바이트를 0으로 설정 되어야 합니다.  
  
### <a name="remarks"></a>설명  
 편집 컨트롤은 해당 버퍼를 할당 하는 대신 현재 표시 된 텍스트를 저장 하는이 버퍼를 사용 합니다.  
  
 이 멤버 함수는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.  
  
 새 메모리 핸들을 설정 하는 응용 프로그램을 먼저 사용 해야는 [GetHandle](#gethandle) 현재 메모리 버퍼에 핸들을 가져오고 사용 하 여 해당 메모리를 확보 하는 멤버 함수는 **LocalFree** Windows 함수입니다.  
  
 `SetHandle` 실행 취소 버퍼를 지웁니다 (의 [CanUndo](#canundo) 멤버 함수는 0을 반환 합니다) 및 내부 수정 플래그 (의 [GetModify](#getmodify) 멤버 함수는 0을 반환 합니다). Edit 컨트롤 창은 다시 그려집니다.  
  
 대화 상자를 만든 경우에 대화 상자에서 여러 줄 편집 컨트롤에서이 멤버 함수를 사용할 수는 **DS_LOCALEDIT** 스타일 플래그를 설정 합니다.  
  
> [!NOTE]
> **GetHandle** Windows 95/98에서는 작동 하지 않습니다. 호출 하는 경우 **GetHandle** Windows 95/98에서 반환 됩니다. **NULL**합니다. **GetHandle** Windows NT 버전 3.51 이상에서 설명한 대로 작동 합니다.  
  
 자세한 내용은 참조 [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), 및 [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>  CEdit::SetHighlight  
 현재에서 표시 되는 텍스트의 범위는 밝은 편집 컨트롤입니다.  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `ichStart`|강조 표시 하는 텍스트 범위에서 첫 번째 문자의 0부터 시작 인덱스입니다.|  
|[in] `ichEnd`|강조 표시 하는 텍스트 범위에서 마지막 문자의 0부터 시작 인덱스입니다.|  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="setlimittext"></a>  CEdit::SetLimitText  
 이 대 한 텍스트 제한을 설정 하려면이 함수를 호출 `CEdit` 개체입니다.  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMax`  
 새 텍스트 제한, 문자입니다.  
  
### <a name="remarks"></a>설명  
 텍스트 제한은 문자는 허용할 수 있는 편집 컨트롤에서 텍스트의 최대 크기입니다.  
  
 입력할 수 있는 텍스트에만 제한 텍스트 제한을 변경 합니다. 편집 컨트롤에 이미 모든 텍스트 없습니다 영향을 주지도 않습니다 것 영향을 복사 하 여 편집 컨트롤에서 텍스트의 길이 [SetWindowText](cwnd-class.md#setwindowtext) 멤버 함수에 `CWnd`합니다. 응용 프로그램에서 사용 하는 경우는 `SetWindowText` 함수에 대 한 호출에서 지정 된 편집 컨트롤에 많은 텍스트를 배치 하려면 `LimitText`, 사용자에 편집 컨트롤에서 텍스트를 삭제할 수 있습니다. 그러나 텍스트 제한 기존 텍스트를 새 텍스트로 대체에서 사용자를 하지 것입니다, 그리고 현재 선택 영역을 삭제 하지 않는 한 문자 제한에는 텍스트입니다.  
  
 이 함수를 대체 [LimitText](#limittext) win32에서 합니다.  
  
 자세한 내용은 참조 [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)합니다.  
  
##  <a name="setmargins"></a>  CEdit::SetMargins  
 이 편집 컨트롤의 왼쪽 및 오른쪽 여백을 설정 하려면이 메서드를 호출 합니다.  
  
```  
void SetMargins(
    UINT nLeft,  
    UINT nRight);
```  
  
### <a name="parameters"></a>매개 변수  
 *nLeft*  
 새 왼쪽된 여백 (픽셀)에서의 너비입니다.  
  
 *nRight*  
 새 오른쪽 여백 (픽셀)에서의 너비입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 멤버 함수는 Windows 95 및 Windows NT 4.0부터 사용 가능 합니다.  
  
 자세한 내용은 참조 [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl)합니다.  
  
##  <a name="setmodify"></a>  CEdit::SetModify  
 설정 하거나 편집 컨트롤에 대 한 수정된 된 플래그를 해제 하려면이 함수를 호출 합니다.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bModified`  
 값이 **TRUE** 이면 텍스트가 수정 된 값을 **FALSE** 는 수정 되지 않습니다 나타냅니다. 수정된 된 플래그는 기본적으로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 수정된 된 플래그는 편집 컨트롤 내의 텍스트를 수정 했는지 여부를 나타냅니다. 사용자는 텍스트를 변경할 때마다 자동으로 설정 됩니다. 해당 값으로 검색할 수 있습니다는 [GetModify](#getmodify) 멤버 함수입니다.  
  
 자세한 내용은 참조 [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::GetModify](#getmodify)합니다.  
  
##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar  
 설정 하거나 사용자가 텍스트를 입력할 때 편집 컨트롤에 표시 되는 암호 문자를 제거 하려면이 함수를 호출 합니다.  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>매개 변수  
 *ch*  
 사용자가 입력 문자 대신에 표시할 문자를 지정 합니다. 경우 *ch* 은 0으로, 사용자가 입력 한 실제 문자는 표시 됩니다.  
  
### <a name="remarks"></a>설명  
 암호 문자 설정 된 경우 사용자가 각 문자에 대 한 해당 문자가 표시 됩니다.  
  
 이 멤버 함수에 영향을 주지 여러 줄 편집 컨트롤에 있습니다.  
  
 경우는 `SetPasswordChar` 멤버 함수를 호출 `CEdit` 로 지정 된 문자를 사용 하 여 표시 되는 문자 모두를 다시 그릴 *ch*합니다.  
  
 편집 컨트롤이 만들어진 경우는 [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) 스타일이, 기본 암호 문자는 별표로 설정 됩니다 ( **\***). 이 스타일이 제거 됩니다 `SetPasswordChar` 사용 하 여 호출 *ch* 0으로 설정 합니다.  
  
 자세한 내용은 참조 [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>  CEdit::SetReadOnly  
 편집 컨트롤의 읽기 전용 상태를 설정 하려면이 함수를 호출 합니다.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bReadOnly`  
 설정 하거나 제거 편집 컨트롤의 읽기 전용 상태 여부를 지정 합니다. 값이 **TRUE** 상태 설정 읽기 전용으로, **FALSE** 읽기/쓰기 상태를 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 작업이 완료 되 면 또는 0 이면 오류 발생 하는 경우에 0이 아닙니다.  
  
### <a name="remarks"></a>설명  
 현재 설정을 테스트 하 여 있습니다는 [ES_READONLY](styles-used-by-mfc.md#edit-styles) 플래그의 반환 값에 [CWnd::GetStyle](cwnd-class.md#getstyle)합니다.  
  
 자세한 내용은 참조 [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>  CEdit::SetRect  
 지정된 된 좌표를 사용 하 여 사각형의 크기를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `RECT` 구조 또는 `CRect` 서식 사각형의 새 크기를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.  
  
 사용 하 여 `SetRect` 서식을 지정 하는 여러 줄의 사각형 컨트롤을 편집 합니다. 서식 지정 영역에 텍스트 편집 컨트롤 창 크기에 독립적인 제한 사각형이입니다. 편집 컨트롤이 처음 만들어질 때 서식 지정 영역은 편집 컨트롤 창의 클라이언트 영역으로 같습니다. 사용 하 여는 `SetRect` 멤버 함수를 편집 컨트롤 창 보다 크거나 작을 응용 프로그램 서식 지정 영역 보장할 수 있습니다.  
  
 편집 컨트롤에 스크롤 막대에 없는 경우 텍스트가 클리핑됩니다, 래핑되지 않으면, 서식 지정 영역 창 보다 큰 경우. 편집 컨트롤에 테두리를 서식 지정 영역 테두리의 크기에 따라 줄어듭니다. 반환 하는 사각형을 조정 하는 경우는 `GetRect` 멤버 함수를 제거한 다음 테두리의 크기에 사각형을 전달 하기 전에 `SetRect`합니다.  
  
 때 `SetRect` 호출 되는 편집 컨트롤의 텍스트는 또한 다시 포맷 하 고 다시 표시 됩니다.  
  
 자세한 내용은 참조 [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>  CEdit::SetRectNP  
 여러 줄 편집 컨트롤의 서식 지정 영역을 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 가리키는 `RECT` 구조 또는 `CRect` 사각형의 새 크기를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 서식 지정 영역에 텍스트 편집 컨트롤 창 크기에 독립적인 제한 사각형이입니다.  
  
 `SetRectNP` 동일는 `SetRect` 멤버 함수 제외 하 고 편집 컨트롤 창을 다시 그려지지 않습니다.  
  
 편집 컨트롤이 처음 만들어질 때 서식 지정 영역은 편집 컨트롤 창의 클라이언트 영역으로 같습니다. 호출 하 여는 `SetRectNP` 멤버 함수를 편집 컨트롤 창 보다 크거나 작을 응용 프로그램 서식 지정 영역 보장할 수 있습니다.  
  
 편집 컨트롤에 스크롤 막대에 없는 경우 텍스트가 클리핑됩니다, 래핑되지 않으면, 서식 지정 영역 창 보다 큰 경우.  
  
 이 멤버는 여러 줄 편집 컨트롤에 의해서만 처리 됩니다.  
  
 자세한 내용은 참조 [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::SetRect](#setrect)합니다.  
  
##  <a name="setsel"></a>  CEdit::SetSel  
 편집 컨트롤에서 문자 범위를 선택 하려면이 함수를 호출 합니다.  
  
```  
void SetSel(
    DWORD dwSelection,  
    BOOL bNoScroll = FALSE);

 
void SetSel(
    int nStartChar,  
    int nEndChar,  
    BOOL bNoScroll = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwSelection*  
 하위 단어의 시작 위치 및 상위 단어의 끝 위치를 지정합니다. 하위 단어는 0-단어는-1의 모든 텍스트 편집 컨트롤에 선택 됩니다. 하위 단어가-1 이면 현재 선택이 제거 됩니다.  
  
 *bNoScroll*  
 캐럿을 보기로 스크롤할 수 있는지 여부를 나타냅니다. 경우 **FALSE**, 캐럿 스크롤해서 표시 합니다. 경우 **TRUE**, 캐럿 하지 스크롤될 합니다.  
  
 `nStartChar`  
 시작 위치를 지정합니다. 경우 `nStartChar` 0 및 `nEndChar` 은-1로 모든 편집 컨트롤에 텍스트를 선택 합니다. 경우 `nStartChar` 은-1, 현재 선택에서 제거 됩니다.  
  
 `nEndChar`  
 끝 위치를 지정합니다.  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEdit::GetSel](#getsel)합니다.  
  
##  <a name="settabstops"></a>  CEdit::SetTabStops  
 여러 줄 편집 컨트롤의 탭 정지를 설정 하려면이 함수를 호출 합니다.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>매개 변수  
 `cxEachStop`  
 탭 정지를 설정할 수 지정 모든 `cxEachStop` 대화 상자 단위입니다.  
  
 `nTabStops`  
 에 포함 된 탭 정지의 수를 지정 `rgTabStops`합니다. 이 번호는 1 보다 커야 합니다.  
  
 `rgTabStops`  
 대화 상자 단위에 있는 탭을 지정 하는 부호 없는 정수의 배열 가리킵니다 중지 합니다. 대화 상자 단위는 가로 또는 세로 거리. 하나의 가로 대화 상자 단위 현재 대화 기본 두께 단위의 1 / 4 고 세로 대화 단위를 1 1 / 8까지 현재 대화 기본 높이 단위의 같습니다. 대화 상자 기본 단위는 현재 시스템 글꼴의 너비와 높이에 따라 계산 됩니다. **GetDialogBaseUnits** Windows 함수 현재 대화 상자 기본 단위 픽셀 단위로 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 탭 설정 되었습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 여러 줄 편집 컨트롤에 텍스트를 복사 하는 텍스트에 있는 탭 문자는 다음 탭 정지까지 생성 되는 공간을 발생 합니다.  
  
 탭 정지 32 대화 상자 단위의 기본 크기를 설정 하려면이 멤버 함수의 버전은 매개 변수가 없는 호출 합니다. 탭 정지 32가 아닌 다른 크기를 설정 하려면 호출 하 여 버전으로는 `cxEachStop` 매개 변수입니다. 탭 정지 배열 크기를 설정 하려면 두 개의 매개 변수가 있는 버전을 사용 합니다.  
  
 이 멤버 함수는 여러 줄 편집 컨트롤에서만 처리 됩니다.  
  
 `SetTabStops` 편집 창이 자동으로 그려지지 않습니다. 텍스트 편집 컨트롤에 이미 있는 탭 정지를 변경 하면 호출 [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) 편집 창 다시 그리게 합니다.  
  
 자세한 내용은 참조 [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663) 및 [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CEditView::SetTabStops](ceditview-class.md#settabstops)합니다.  
  
##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip  
 현재 편집 컨트롤과 연결 된 풍선 팁에 표시 됩니다.  
  
```  
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

 
BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,   
    LPCWSTR lpszText,   
    INT ttiIcon = TTI_NONE);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pEditBalloonTip`|에 대 한 포인터는 [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) 풍선 팁을 설명 하는 구조입니다.|  
|[in] `lpszTitle`|풍선 설명의 제목을 포함 하는 유니코드 문자열에 대 한 포인터입니다.|  
|[in] `lpszText`|풍선 팁 텍스트를 포함 하는 유니코드 문자열에 대 한 포인터입니다.|  
|[in] `ttiIcon`|`INT` 풍선 팁과 연결할 아이콘의 유형을 지정 하는 합니다. 기본값은 `TTI_NONE`입니다. 자세한 내용은 참조는 `ttiIcon` 의 멤버는 [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) 메시지는 Windows SDK에 설명 되어 있습니다. 자세한 내용은 참조는 [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707) 매크로입니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_cedit`, 즉 현재 편집 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 edit 컨트롤에 대 한 풍선 설명을 표시합니다. [CEdit::ShowBalloonTip](#showballoontip) 메서드 제목과 풍선 팁 텍스트를 지정 합니다.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>  CEdit::Undo  
 마지막 편집 컨트롤 작업을 취소 하려면이 함수를 호출 합니다.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>반환 값  
 단일 행 편집 컨트롤에 대 한 반환 값은 0이 아닌 항상 합니다. 여러 줄 편집 컨트롤에 대 한 반환 값은 실행 취소 작업이 성공 하면 0이 아니고 또는 실행 취소 작업이 실패 한 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 실행 취소 작업 또한 취소할 수 없습니다. 예를 들어 첫 번째 호출로 삭제 된 텍스트를 복원할 수 있습니다 **실행 취소**합니다. 두 번째 호출으로 다시 사용 하 여 텍스트를 제거할 수 중간 편집 작업이 없는 상태로 **실행 취소**합니다.  
  
 자세한 내용은 참조 [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) Windows sdk에서입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CALCDRIV MFC 샘플](../../visual-cpp-samples.md)   
 [MFC 샘플 CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](cwnd-class.md)   
 [CButton 클래스](cbutton-class.md)   
 [CComboBox 클래스](ccombobox-class.md)   
 [CListBox 클래스](clistbox-class.md)   
 [CScrollBar 클래스](cscrollbar-class.md)   
 [CStatic 클래스](cstatic-class.md)   
 [CDialog 클래스](cdialog-class.md)
