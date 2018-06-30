---
title: CSplitterWnd 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSplitterWnd
- AFXEXT/CSplitterWnd
- AFXEXT/CSplitterWnd::CSplitterWnd
- AFXEXT/CSplitterWnd::ActivateNext
- AFXEXT/CSplitterWnd::CanActivateNext
- AFXEXT/CSplitterWnd::Create
- AFXEXT/CSplitterWnd::CreateScrollBarCtrl
- AFXEXT/CSplitterWnd::CreateStatic
- AFXEXT/CSplitterWnd::CreateView
- AFXEXT/CSplitterWnd::DeleteColumn
- AFXEXT/CSplitterWnd::DeleteRow
- AFXEXT/CSplitterWnd::DeleteView
- AFXEXT/CSplitterWnd::DoKeyboardSplit
- AFXEXT/CSplitterWnd::DoScroll
- AFXEXT/CSplitterWnd::DoScrollBy
- AFXEXT/CSplitterWnd::GetActivePane
- AFXEXT/CSplitterWnd::GetColumnCount
- AFXEXT/CSplitterWnd::GetColumnInfo
- AFXEXT/CSplitterWnd::GetPane
- AFXEXT/CSplitterWnd::GetRowCount
- AFXEXT/CSplitterWnd::GetRowInfo
- AFXEXT/CSplitterWnd::GetScrollStyle
- AFXEXT/CSplitterWnd::IdFromRowCol
- AFXEXT/CSplitterWnd::IsChildPane
- AFXEXT/CSplitterWnd::IsTracking
- AFXEXT/CSplitterWnd::RecalcLayout
- AFXEXT/CSplitterWnd::SetActivePane
- AFXEXT/CSplitterWnd::SetColumnInfo
- AFXEXT/CSplitterWnd::SetRowInfo
- AFXEXT/CSplitterWnd::SetScrollStyle
- AFXEXT/CSplitterWnd::SplitColumn
- AFXEXT/CSplitterWnd::SplitRow
- AFXEXT/CSplitterWnd::OnDraw
- AFXEXT/CSplitterWnd::OnDrawSplitter
- AFXEXT/CSplitterWnd::OnInvertTracker
dev_langs:
- C++
helpviewer_keywords:
- CSplitterWnd [MFC], CSplitterWnd
- CSplitterWnd [MFC], ActivateNext
- CSplitterWnd [MFC], CanActivateNext
- CSplitterWnd [MFC], Create
- CSplitterWnd [MFC], CreateScrollBarCtrl
- CSplitterWnd [MFC], CreateStatic
- CSplitterWnd [MFC], CreateView
- CSplitterWnd [MFC], DeleteColumn
- CSplitterWnd [MFC], DeleteRow
- CSplitterWnd [MFC], DeleteView
- CSplitterWnd [MFC], DoKeyboardSplit
- CSplitterWnd [MFC], DoScroll
- CSplitterWnd [MFC], DoScrollBy
- CSplitterWnd [MFC], GetActivePane
- CSplitterWnd [MFC], GetColumnCount
- CSplitterWnd [MFC], GetColumnInfo
- CSplitterWnd [MFC], GetPane
- CSplitterWnd [MFC], GetRowCount
- CSplitterWnd [MFC], GetRowInfo
- CSplitterWnd [MFC], GetScrollStyle
- CSplitterWnd [MFC], IdFromRowCol
- CSplitterWnd [MFC], IsChildPane
- CSplitterWnd [MFC], IsTracking
- CSplitterWnd [MFC], RecalcLayout
- CSplitterWnd [MFC], SetActivePane
- CSplitterWnd [MFC], SetColumnInfo
- CSplitterWnd [MFC], SetRowInfo
- CSplitterWnd [MFC], SetScrollStyle
- CSplitterWnd [MFC], SplitColumn
- CSplitterWnd [MFC], SplitRow
- CSplitterWnd [MFC], OnDraw
- CSplitterWnd [MFC], OnDrawSplitter
- CSplitterWnd [MFC], OnInvertTracker
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3d2b44c4e854a27bcc753c1403ea058b03906a8
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123151"
---
# <a name="csplitterwnd-class"></a>CSplitterWnd 클래스
여러 개의 창이 포함된 창인 분할자 창 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSplitterWnd::CSplitterWnd](#csplitterwnd)|생성 하는 호출을 `CSplitterWnd` 개체입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSplitterWnd::ActivateNext](#activatenext)|다음 창] 또는 [이전 창 명령을 수행합니다.|  
|[CSplitterWnd::CanActivateNext](#canactivatenext)|다음 창] 또는 [이전 창 명령을 현재 수 있는지를 확인 합니다.|  
|[CSplitterWnd::Create](#create)|동적 분할 창을 만들고에 연결 하는 호출 된 `CSplitterWnd` 개체입니다.|  
|[CSplitterWnd::CreateScrollBarCtrl](#createscrollbarctrl)|공유 scroll bar 컨트롤을 만듭니다.|  
|[CSplitterWnd::CreateStatic](#createstatic)|정적 분할 창은 만들고에 연결 하는 호출 된 `CSplitterWnd` 개체입니다.|  
|[CSplitterWnd::CreateView](#createview)|분할 창에서 창을 만드는 호출 합니다.|  
|[CSplitterWnd::DeleteColumn](#deletecolumn)|분할 창에서 열을 삭제합니다.|  
|[CSplitterWnd::DeleteRow](#deleterow)|분할 창에서 행을 삭제 합니다.|  
|[CSplitterWnd::DeleteView](#deleteview)|분할 창에서 뷰를 삭제합니다.|  
|[CSplitterWnd::DoKeyboardSplit](#dokeyboardsplit)|키보드 분할 명령을, 일반적으로 "창 분할 합니다."를 수행 합니다.|  
|[CSplitterWnd::DoScroll](#doscroll)|분할 창을 동기화 된 스크롤을 수행 합니다.|  
|[CSplitterWnd::DoScrollBy](#doscrollby)|지정 된 픽셀 수 만큼 분할 창을 스크롤합니다.|  
|[CSplitterWnd::GetActivePane](#getactivepane)|포커스 또는 프레임에서 활성 뷰에서 활성 창을 결정합니다.|  
|[CSplitterWnd::GetColumnCount](#getcolumncount)|현재 창 열 개수를 반환합니다.|  
|[CSplitterWnd::GetColumnInfo](#getcolumninfo)|지정한 열에 정보를 반환합니다.|  
|[CSplitterWnd::GetPane](#getpane)|지정 된 행과 열에 창을 반환합니다.|  
|[CSplitterWnd::GetRowCount](#getrowcount)|현재 창 행 개수를 반환합니다.|  
|[CSplitterWnd::GetRowInfo](#getrowinfo)|지정된 된 행에 정보를 반환 합니다.|  
|[CSplitterWnd::GetScrollStyle](#getscrollstyle)|공유 스크롤 막대 스타일을 반환합니다.|  
|[CSplitterWnd::IdFromRowCol](#idfromrowcol)|자식 창의 지정 된 행과 열에 창 ID를 반환합니다.|  
|[CSplitterWnd::IsChildPane](#ischildpane)|현재 창이이 분할 창의 자식 창 되는지 확인 하 여 호출입니다.|  
|[CSplitterWnd::IsTracking](#istracking)|분할 막대는 현재 이동 중인 경우를 결정 합니다.|  
|[CSplitterWnd::RecalcLayout](#recalclayout)|분할 창 행 또는 열 크기를 조정한 후 다시 표시 하려면 여기를 호출 합니다.|  
|[CSplitterWnd::SetActivePane](#setactivepane)|창을 설정 합니다. 프레임에서 활성 상태 여야 합니다.|  
|[CSplitterWnd::SetColumnInfo](#setcolumninfo)|지정 된 열 정보를 설정 하려면 여기를 호출 합니다.|  
|[CSplitterWnd::SetRowInfo](#setrowinfo)|지정 된 행 정보를 설정 하려면 여기를 호출 합니다.|  
|[CSplitterWnd::SetScrollStyle](#setscrollstyle)|분할 창에 대 한 새 스크롤 막대 스타일 스크롤 막대 지원 공유를 지정 합니다.|  
|[CSplitterWnd::SplitColumn](#splitcolumn)|프레임 창이 세로로 분할 하는 지점을 나타냅니다.|  
|[CSplitterWnd::SplitRow](#splitrow)|프레임 창이 가로로 분할 하는 지점을 나타냅니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CSplitterWnd::OnDraw](#ondraw)|분할 창 그리기 위해 프레임 워크에서 호출 됩니다.|  
|[CSplitterWnd::OnDrawSplitter](#ondrawsplitter)|분할 창의 이미지를 렌더링합니다.|  
|[CSplitterWnd::OnInvertTracker](#oninverttracker)|동일한 크기와 셰이프 프레임 창으로 되도록 분할 창의 이미지를 렌더링 합니다.|  
  
## <a name="remarks"></a>설명  
 하나의 창에서 파생 된 응용 프로그램 관련 개체는 일반적으로 [CView](../../mfc/reference/cview-class.md), 하나일 수 있습니다 하지만 [CWnd](../../mfc/reference/cwnd-class.md) 적절 한 자식 창 ID를 가진 개체를  
  
 A `CSplitterWnd` 개체가 부모에 일반적으로 포함 된 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 또는 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 개체입니다. 만들기는 `CSplitterWnd` 개체는 다음 단계를 사용 하 여:  
  
1.  포함 된 `CSplitterWnd` 부모 프레임에서 멤버 변수입니다.  
  
2.  부모 프레임의 재정의 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) 멤버 함수입니다.  
  
3.  재정의 된 내의 `OnCreateClient`, 호출의 [만들기](#create) 또는 [CreateStatic](#createstatic) 의 멤버 함수 `CSplitterWnd`합니다.  
  
 호출 된 `Create` 멤버 함수는 동적 분할 창을 만들 수 있습니다. 일반적으로 만들고 한 수의 개별 창 또는 같은 문서 보기를 스크롤 하는 동적 분할 창 사용 됩니다. 프레임 워크에 분할자;에 대 한 초기가 창을 자동으로 만듭니다. 다음 프레임 워크 만듭니다가 고 분할 창 컨트롤을 작동 하는 사용자 처럼 추가 창 삭제 합니다.  
  
 호출 하는 경우 `Create`는 창이 너무 작아서 표시할 수 있는 경우를 결정 하는 최소 행 높이 및 열 너비를 지정 합니다. 호출한 후 `Create`를 호출 하 여 이러한 최소값을 조정할 수 있습니다는 [SetColumnInfo](#setcolumninfo) 및 [SetRowInfo](#setrowinfo) 멤버 함수입니다.  
  
 또한 사용 하 여는 `SetColumnInfo` 및 `SetRowInfo` 열에 대 한 "이상적인" 너비와 행에 대 한 "이상적인" 높이 설정 하는 멤버 함수입니다. 창에 표시 하는 프레임 워크, 경우 먼저 분할 창 다음 부모 프레임을 표시 합니다. 다음 프레임 워크의 열과 행 분할 창의 클라이언트 영역 오른쪽 아래 모서리에 왼쪽 위에서 작동 하 여 이상적인 차원에 따른 창을 배치 합니다.  
  
 동적 분할 창에서 모든 창은 동일한 클래스 여야 합니다. 동적 분할 창을 지원 되는 친숙 한 응용 프로그램에는 Microsoft Word 및 Microsoft Excel 포함 됩니다.  
  
 사용 하 여는 `CreateStatic` 멤버 함수는 정적 분할 창을 만들 수 있습니다. 창, 하지는 번호 또는 주문 정적 분할 창 크기에만 변경할 수 있습니다.  
  
 정적 분할을 만들 때 고정 된 분할자의 모든 창 구체적으로 만들어야 합니다. 부모 프레임의 하기 전에 모든 창 만들어야 `OnCreateClient` 멤버 함수가 반환 그렇지 창을 제대로 표시 되지 않으면 framework 합니다.  
  
 `CreateStatic` 멤버 함수 자동 0의 최소 행 높이 및 열 너비와 정적 분할을 초기화 합니다. 호출한 후 `Create`를 호출 하 여 이러한 최소값을 조정는 [SetColumnInfo](#setcolumninfo) 및 [SetRowInfo](#setrowinfo) 멤버 함수입니다. 또한 사용 하 여 `SetColumnInfo` 및 `SetRowInfo` 호출한 후 `CreateStatic` 원하는 이상적인 창 크기를 나타내는입니다.  
  
 정적 분할의 개별 창은 종종 서로 다른 클래스에 속해 있습니다. 정적 분할 창은의 예는 그래픽 편집기 및 Windows 파일 관리자를 참조 합니다.  
  
 분할 창 (창 있을 수 있는 스크롤 막대)와 별도로 특수 스크롤 막대를 지원 합니다. 이러한 스크롤 막대의 자식인는 `CSplitterWnd` 개체를 공유 하는 창이 있습니다.  
  
 분할 창을 만들 때에 이러한 특수 스크롤 막대를 만듭니다. 예를 들어 한 `CSplitterWnd` 행이 하나씩, 두 개의 열 있고 WS_VSCROLL 스타일에는 두 개의 창에서 공유 된 세로 스크롤 막대가 표시 됩니다. 사용자가 스크롤 막대를 움직이면 WM_VSCROLL 메시지 창의 두 창으로 전송 됩니다. 스크롤 막대 위치를 설정 하는 창, 공유 스크롤 막대 설정 됩니다.  
  
 분할 창에 자세한 내용은 다음을 참조 합니다.  
  
- [기술적으로 설명 29](../../mfc/tn029-splitter-windows.md)  
  
-   기술 자료 문서 Q262024: 방법: CSplitterWnd 자식으로 사용 하 여 CPropertySheet  
  
 동적 분할 창을 만드는 방법에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   MFC 샘플 [Scribble](../../visual-cpp-samples.md)  
  
-   MFC 샘플 [VIEWEX](../../visual-cpp-samples.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="activatenext"></a>  CSplitterWnd::ActivateNext  
 다음 창] 또는 [이전 창 명령을 수행 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void ActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bPrev*  
 활성화 하는 창을 나타냅니다. **True 이면** 에 대 한 이전; **FALSE** 다음에 대 한 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 높은 수준의 명령에서 사용 되는 [CView](../../mfc/reference/cview-class.md) 에 위임 하기 위해 클래스는 `CSplitterWnd` 구현 합니다.  
  
##  <a name="canactivatenext"></a>  CSplitterWnd::CanActivateNext  
 다음 창] 또는 [이전 창 명령을 현재 지원 되는지 확인 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL CanActivateNext(BOOL bPrev = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bPrev*  
 활성화 하는 창을 나타냅니다. **True 이면** 에 대 한 이전; **FALSE** 다음에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 높은 수준의 명령에서 사용 되는 [CView](../../mfc/reference/cview-class.md) 에 위임 하기 위해 클래스는 `CSplitterWnd` 구현 합니다.  
  
##  <a name="create"></a>  CSplitterWnd::Create  
 동적 분할 창을 만들기 위해 호출 된 **만들기** 멤버 함수입니다.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    int nMaxRows,  
    int nMaxCols,  
    SIZE sizeMin,  
    CCreateContext* pContext,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_HSCROLL | WS_VSCROLL | SPLS_DYNAMIC_SPLIT,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>매개 변수  
 *pParentWnd*  
 분할 창의 부모 프레임 창입니다.  
  
 *nMaxRows*  
 분할 창에 있는 행의 최대 수입니다. 이 값 2를 넘지 않아야 합니다.  
  
 *nMaxCols*  
 분할 창에 있는 열의 최대 수입니다. 이 값 2를 넘지 않아야 합니다.  
  
 *sizeMin*  
 창을 표시 될 수 있습니다 최소 크기를 지정 합니다.  
  
 *pContext*  
 에 대 한 포인터는 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조입니다. 대부분의 경우가 수는 *pContext* 부모 프레임 창에 전달 합니다.  
  
 *dwStyle*  
 창 스타일을 지정합니다.  
  
 *nID*  
 창의 자식 창 ID입니다. ID 분할 창을 다른 분할 창 내에 중첩 된 경우가 아니면 AFX_IDW_PANE_FIRST 될 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 포함할 수는 `CSplitterWnd` 부모의 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 또는 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 다음 단계를 수행 하 여 개체:  
  
1.  포함 된 `CSplitterWnd` 부모 프레임에서 멤버 변수입니다.  
  
2.  부모 프레임의 재정의 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) 멤버 함수입니다.  
  
3.  호출 된 `Create` 재정의 된 내에서 멤버 함수 `OnCreateClient`합니다.  
  
 부모 프레임 내에서 분할자 창을 만들 때 전달 부모 프레임의 *pContext* 분할자 창에 매개 변수입니다. 그렇지 않으면이 매개 변수는 NULL 일 수 있습니다.  
  
 동적 분할 창 초기 최소 행 높이 및 열 너비 설정한는 *sizeMin* 매개 변수입니다. 이러한 최소값은 창이 너무 작아 전체에 표시 되는지 여부를 결정을 변경할 수 있습니다는 [SetRowInfo](#setrowinfo) 및 [SetColumnInfo](#setcolumninfo) 멤버 함수입니다.  
  
 에 대 한 자세한 동적 분할 창, 문서에서 "분할 창"을 참조 [여러 문서 형식, 뷰 및 프레임 창](../../mfc/multiple-document-types-views-and-frame-windows.md), [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 클래스 개요입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#125](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_1.cpp)]  
  
##  <a name="createscrollbarctrl"></a>  CSplitterWnd::CreateScrollBarCtrl  
 공유 scroll bar 컨트롤을 만들기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL CreateScrollBarCtrl(
    DWORD dwStyle,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwStyle*  
 창 스타일을 지정합니다.  
  
 *nID*  
 창의 자식 창 ID입니다. ID 분할 창을 다른 분할 창 내에 중첩 된 경우가 아니면 AFX_IDW_PANE_FIRST 될 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 재정의 `CreateScrollBarCtrl` 스크롤 막대 옆에 있는 여러 추가 컨트롤을 포함 하도록 합니다. 기본 동작은 일반 Windows 스크롤 막대 컨트롤을 만드는 것입니다.  
  
##  <a name="createstatic"></a>  CSplitterWnd::CreateStatic  
 정적 분할 창을 만들기 위해 호출 된 `CreateStatic` 멤버 함수입니다.  
  
```  
virtual BOOL CreateStatic(
    CWnd* pParentWnd,  
    int nRows,  
    int nCols,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE,  
    UINT nID = AFX_IDW_PANE_FIRST);
```  
  
### <a name="parameters"></a>매개 변수  
 *pParentWnd*  
 분할 창의 부모 프레임 창입니다.  
  
 *nRows*  
 행의 수입니다. 이 값은 16을 초과할 수 없습니다.  
  
 *nCols*  
 열의 수입니다. 이 값은 16을 초과할 수 없습니다.  
  
 *dwStyle*  
 창 스타일을 지정합니다.  
  
 *nID*  
 창의 자식 창 ID입니다. ID 분할 창을 다른 분할 창 내에 중첩 된 경우가 아니면 AFX_IDW_PANE_FIRST 될 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 A `CSplitterWnd` 은 일반적으로 부모에 포함 `CFrameWnd` 또는 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) 다음 단계를 수행 하 여 개체:  
  
1.  포함 된 `CSplitterWnd` 부모 프레임에서 멤버 변수입니다.  
  
2.  부모 프레임의 재정의 `OnCreateClient` 멤버 함수입니다.  
  
3.  호출 된 `CreateStatic` 재정의 된 내에서 멤버 함수 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient)합니다.  
  
 정적 분할 창은 고정된 된 수의 서로 다른 클래스에서 종종 창 포함합니다.  
  
 정적 분할 창은 만들 때 동시에 만들어야 모든 창. [CreateView](#createview) 멤버 함수는 대개이 목적을 위해 사용 되지만 다른 nonview 클래스를 만들 수 있습니다.  
  
 정적 분할 창에 대 한 초기 최소 행 높이 및 열 너비는 0입니다. 이러한 최소값 창을 너무 작아서 전체에 표시 될 때 작업을 결정 하는 변경할 수 있습니다는 [SetRowInfo](#setrowinfo) 및 [SetColumnInfo](#setcolumninfo) 멤버 함수입니다.  
  
 정적 분할 창에 스크롤 막대를 추가 하려면 WS_HSCROLL 및 WS_VSCROLL 스타일을 추가 *dwStyle*합니다.  
  
 문서에서 "분할 창"을 참조 하십시오. [여러 문서 형식, 뷰 및 프레임 창](../../mfc/multiple-document-types-views-and-frame-windows.md), [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 정적 분할 창에 대 한 자세한 클래스 개요입니다.  
  
##  <a name="createview"></a>  CSplitterWnd::CreateView  
 정적 분할 창에 대 한 창을 만듭니다.  
  
```  
virtual BOOL CreateView(
    int row,  
    int col,  
    CRuntimeClass* pViewClass,  
    SIZE sizeInit,  
    CCreateContext* pContext);
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 새 보기를 배치 하는 분할자 창 행을 지정 합니다.  
  
 *열*  
 새 보기를 배치 하는 분할자 창을 열을 지정 합니다.  
  
 *pViewClass*  
 지정 된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 새 보기의 합니다.  
  
 *sizeInit*  
 새 보기의 초기 크기를 지정합니다.  
  
 *pContext*  
 뷰를 생성 하는 데 사용 되는 생성 컨텍스트에 대 한 포인터 (일반적으로 *pContext* 재정의 된 부모 프레임으로 전달 [CFrameWnd::OnCreateClient](../../mfc/reference/cframewnd-class.md#oncreateclient) 분할 창 인 멤버 함수 만드는 중).  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 정적 분할 창은의 모든 창 프레임 워크가 표시 하는 분할 전에 만들어야 합니다.  
  
 프레임 워크는 또한 동적 분할 창 사용자 창, 행 또는 열을 분할 하는 경우 새 창을 만들려면이 멤버 함수를 호출 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#4](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_2.cpp)]  
  
##  <a name="csplitterwnd"></a>  CSplitterWnd::CSplitterWnd  
 생성 하는 호출을 `CSplitterWnd` 개체입니다.  
  
```  
CSplitterWnd();
```  
  
### <a name="remarks"></a>설명  
 생성 된 `CSplitterWnd` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출을 만드는 `CSplitterWnd` 개체를 호출 합니다는 [만들기](#create) 분할 창을 만들고에 연결 하는 멤버 함수는 `CSplitterWnd` 개체입니다.  
  
##  <a name="deletecolumn"></a>  CSplitterWnd::DeleteColumn  
 분할 창에서 열을 삭제합니다.  
  
```  
virtual void DeleteColumn(int colDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 *colDelete*  
 삭제할 열을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수 (즉, 분할자 창에 있으면 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 해당 사용자 지정할 수 있습니다, 가상 함수를 함께 [CreateView](#createview)고급 동적 분할 창을 구현 합니다.  
  
##  <a name="deleterow"></a>  CSplitterWnd::DeleteRow  
 분할 창에서 행을 삭제 합니다.  
  
```  
virtual void DeleteRow(int rowDelete);
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 삭제할 행을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수 (즉, 분할자 창에 있으면 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 해당 사용자 지정할 수 있습니다, 가상 함수를 함께 [CreateView](#createview)고급 동적 분할 창을 구현 합니다.  
  
##  <a name="deleteview"></a>  CSplitterWnd::DeleteView  
 분할 창에서 뷰를 삭제합니다.  
  
```  
virtual void DeleteView(
    int row,  
    int col);
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 보기를 삭제 하는 분할자 창 행을 지정 합니다.  
  
 *열*  
 보기를 삭제 하는 분할자 창을 열을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 현재 보기를 삭제 하는 경우에 다음 보기로 활성화 됩니다. 기본 구현은 보기 자동 가정에서 삭제할 [PostNcDestroy](../../mfc/reference/cwnd-class.md#postncdestroy)합니다.  
  
 이 멤버 함수 (즉, 분할자 창에 있으면 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 해당 사용자 지정할 수 있습니다, 가상 함수를 함께 [CreateView](#createview)고급 동적 분할 창을 구현 합니다.  
  
##  <a name="dokeyboardsplit"></a>  CSplitterWnd::DoKeyboardSplit  
 키보드 분할 명령을, 일반적으로 "창 분할 합니다."를 수행 합니다.  
  
```  
virtual BOOL DoKeyboardSplit();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 높은 수준의 명령에서 사용 되는 [CView](../../mfc/reference/cview-class.md) 에 위임 하기 위해 클래스는 `CSplitterWnd` 구현 합니다.  
  
##  <a name="doscroll"></a>  CSplitterWnd::DoScroll  
 분할 창을 동기화 된 스크롤을 수행 합니다.  
  
```  
virtual BOOL DoScroll(
    CView* pViewFrom,  
    UINT nScrollCode,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pViewFrom*  
 스크롤 메시지의 원본 보기에 대 한 포인터입니다.  
  
 *nScrollCode*  
 사용자 지정 하는 스크롤 막대 코드 요청을 스크롤의입니다. 이 매개 변수는 두 부분으로 구성 됩니다: 가로 스크롤 발생 유형의 결정 하는 낮은 순서 바이트 및 세로 스크롤 발생의 유형을 결정 하는 상위 바이트:  
  
- SB_BOTTOM를 아래쪽으로 스크롤.  
  
- 한 줄 아래로 SB_LINEDOWN 스크롤합니다.  
  
- 한 줄 위로 SB_LINEUP 스크롤합니다.  
  
- 한 페이지 아래로 SB_PAGEDOWN 스크롤합니다.  
  
- 한 페이지 위로 SB_PAGEUP 스크롤합니다.  
  
- 맨 위로 이동 SB_TOP 스크롤입니다.  
  
 *bDoScroll*  
 지정 된 스크롤 동작이 발생 하는지 여부를 결정 합니다. 경우 *bDoScroll* 가 TRUE (즉, 있으면 자식 창 및 분할 창을 스크롤 범위에 있으면), 지정된 된 스크롤 작업을 수행할 수 있습니다; 다음 경우 *bDoScroll* FALSE 이면 (즉, 없는 자식 창 있는 경우 분할 뷰 스크롤 범위가 수도 있고), 다음 스크롤 발생 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 동기화 하는 경우 0이 아닌 스크롤하면 발생 합니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 뷰의 스크롤 메시지를 받을 때 분할 창을 동기화 된 스크롤 수행 하기 위해 프레임 워크에 의해 호출 됩니다. 동기화 된 스크롤링이 허용 되기 전에 사용자가 작업을 요구 하도록 재정의 합니다.  
  
##  <a name="doscrollby"></a>  CSplitterWnd::DoScrollBy  
 지정 된 픽셀 수 만큼 분할 창을 스크롤합니다.  
  
```  
virtual BOOL DoScrollBy(
    CView* pViewFrom,  
    CSize sizeScroll,  
    BOOL bDoScroll = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pViewFrom*  
 스크롤 메시지의 원본 보기에 대 한 포인터입니다.  
  
 *sizeScroll*  
 가로 및 세로로 스크롤할 수 픽셀 수입니다.  
  
 *bDoScroll*  
 지정 된 스크롤 동작이 발생 하는지 여부를 결정 합니다. 경우 *bDoScroll* 가 TRUE (즉, 있으면 자식 창 및 분할 창을 스크롤 범위에 있으면), 지정된 된 스크롤 작업을 수행할 수 있습니다; 다음 경우 *bDoScroll* FALSE 이면 (즉, 없는 자식 창 있는 경우 분할 뷰 스크롤 범위가 수도 있고), 다음 스크롤 발생 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 동기화 하는 경우 0이 아닌 스크롤하면 발생 합니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 스크롤 메시지에 대 한 응답으로 프레임 워크에서 호출 되 면 수행 하는 양만큼 (픽셀)를 가리키는 분할 창을 스크롤을 동기화 *sizeScroll*합니다. 양수 값과 오른쪽 아래로 스크롤 나타냅니다. 음수 값을 왼쪽 위로 스크롤 나타냅니다.  
  
 스크롤을 허용 하기 전에 사용자가 작업을 요구 하도록 재정의 합니다.  
  
##  <a name="getactivepane"></a>  CSplitterWnd::GetActivePane  
 포커스 또는 프레임에서 활성 뷰에서 활성 창을 결정합니다.  
  
```  
virtual CWnd* GetActivePane(
    int* pRow = NULL,  
    int* pCol = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pRow*  
 에 대 한 포인터는 **int** 를 활성 창의 행 번호를 검색 합니다.  
  
 *pCol*  
 에 대 한 포인터는 **int** 를 현재 창 열 수를 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 활성 창에 대 한 포인터입니다. 활성 창 없는 경우 NULL입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 창에 현재 창을 확인 하는 프레임 워크에서 호출 됩니다. 활성 창을 가져오기 전에 사용자가 작업을 요구 하도록 재정의 합니다.  
  
##  <a name="getcolumncount"></a>  CSplitterWnd::GetColumnCount  
 현재 창 열 개수를 반환합니다.  
  
```  
int GetColumnCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 분할자의 현재 열 개수를 반환합니다. 정적 분할에 대 한 또한이 됩니다 최대 열 수 있습니다.  
  
##  <a name="getcolumninfo"></a>  CSplitterWnd::GetColumnInfo  
 지정한 열에 정보를 반환합니다.  
  
```  
void GetColumnInfo(
    int col,  
    int& cxCur,  
    int& cxMin) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *열*  
 열을 지정합니다.  
  
 *cxCur*  
 에 대 한 참조는 **int** 열의 현재 너비로 설정 해야 합니다.  
  
 *cxMin*  
 에 대 한 참조는 **int** 열의 현재 최소 너비로 설정 해야 합니다.  
  
##  <a name="getpane"></a>  CSplitterWnd::GetPane  
 지정 된 행과 열에 창을 반환합니다.  
  
```  
CWnd* GetPane(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 행을 지정합니다.  
  
 *열*  
 열을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 행과 열에 창을 반환합니다. 반환 된 창은 일반적으로 [CView](../../mfc/reference/cview-class.md)-클래스를 파생 합니다.  
  
##  <a name="getrowcount"></a>  CSplitterWnd::GetRowCount  
 현재 창 행 개수를 반환합니다.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 분할 창에서 현재 행의 수를 반환합니다. 정적 분할 창에 대 한 또한이 됩니다 최대 행 수입니다.  
  
##  <a name="getrowinfo"></a>  CSplitterWnd::GetRowInfo  
 지정된 된 행에 정보를 반환 합니다.  
  
```  
void GetRowInfo(
    int row,  
    int& cyCur,  
    int& cyMin) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 행을 지정합니다.  
  
 *cyCur*  
 에 대 한 참조 **int** 픽셀에서 행의 현재 높이로 설정 해야 합니다.  
  
 *cyMin*  
 에 대 한 참조 **int** 현재 최소 높이 (픽셀)의 행으로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 행에 대 한 정보를 얻으려면이 멤버 함수를 호출 합니다. *cyCur* 매개 변수는 지정된 된 행의 현재 높이 채워집니다 및 *cyMin* 행의 최소 높이으로 채워집니다.  
  
##  <a name="getscrollstyle"></a>  CSplitterWnd::GetScrollStyle  
 분할 창에 대 한 공유 스크롤 막대 스타일을 반환 합니다.  
  
```  
DWORD GetScrollStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 다음 창 중 하나 이상의 스타일 플래그:  
  
- WS_HSCROLL 분할자 현재 관리 하는 경우 가로 스크롤 막대를 공유 합니다.  
  
- WS_VSCROLL 분할자 현재 관리 하는 경우 세로 스크롤 막대를 공유 합니다.  
  
 0 이면 분할자 창 모든 공유 스크롤 막대를 현재 관리 하지 않습니다.  
  
##  <a name="idfromrowcol"></a>  CSplitterWnd::IdFromRowCol  
 자식 지정한 행 및 열에 있는 창에 대 한 창 ID를 가져옵니다.  
  
```  
int IdFromRowCol(
    int row,  
    int col) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 분할 창 행을 지정합니다.  
  
 *열*  
 분할 창 열을 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 창의 자식 창 ID입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수 nonviews 창으로 만들기 위한 사용 되 고 창 존재 전에 호출 될 수도 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#5](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_3.cpp)]  
  
##  <a name="ischildpane"></a>  CSplitterWnd::IsChildPane  
 결정 여부 *pWnd* 현재이 분할 창의 자식 창입니다.  
  
```  
BOOL IsChildPane(
    CWnd* pWnd,  
    int* pRow,  
    int* pCol);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWnd*  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 테스트할 개체입니다.  
  
 *pRow*  
 에 대 한 포인터는 **int** 를 저장할 행 번호입니다.  
  
 *pCol*  
 에 대 한 포인터는 **int** 저장할 열 번호입니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아니면 *pWnd* 는 현재이 분할 창의 자식 창 및 *pRow* 및 *pCol* 분할 창에서 창의 위치를 사용 하 여 채워집니다. 경우 *pWnd* 자식 창 없는이 분할자 창 0이 반환 됩니다.  
  
### <a name="remarks"></a>설명  
 6.0 이전 버전 Visual c + +에서는이 기능으로 정의 되었습니다.  
  
 `BOOL IsChildPane(CWnd* pWnd, int& row, int& col);`  
  
 이 버전은 이제 사용할 수 및 사용 하지 않아야 합니다.  
  
##  <a name="istracking"></a>  CSplitterWnd::IsTracking  
 이 창에는 분할 막대는 현재 이동 중인 경우를 확인 하려면 함수를 호출 합니다.  
  
```  
BOOL IsTracking();
```  
  
### <a name="return-value"></a>반환 값  
 분할자 작업이 진행 중인 경우 0이 아닌 그렇지 않으면 0입니다.  
  
##  <a name="ondrawsplitter"></a>  CSplitterWnd::OnDrawSplitter  
 분할 창의 이미지를 렌더링합니다.  
  
```  
virtual void OnDrawSplitter(
    CDC* pDC,  
    ESplitType nType,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 그릴 장치 컨텍스트에 대 한 포인터입니다. 경우 *pDC* 가 null 인 경우 다음 [CWnd::RedrawWindow](../../mfc/reference/cwnd-class.md#redrawwindow) 라고 창 프레임 워크 및 분할 없음을 그려집니다.  
  
 *n 유형*  
 값은 `enum ESplitType`, 다음 중 하나일 수 있습니다.  
  
- `splitBox` 분할자 끌어서 상자입니다.  
  
- `splitBar` 두 개의 분할 창을 사이 표시 된 막대입니다.  
  
- `splitIntersection` 분할 창을 교차 합니다. 이 요소는 Windows 95/98에서 실행 중인 경우 호출 되지 않습니다.  
  
- `splitBorder` 분할 창 테두리입니다.  
  
 *rect*  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 크기와 분할 창을 모양을 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 그리고 분할자 창의 정확한 특성을 지정 하는 프레임 워크에서 호출 됩니다. 재정의 `OnDrawSplitter` 창에는 다양 한 그래픽 구성 요소에 대 한 이미지의 고급 사용자 지정에 대 한 합니다. 기본 이미지 분할 막대의 교차점 섞이는 한다는 점에서 Microsoft Windows 95/98 또는 Windows에 대 한 Microsoft works 분할자와 비슷합니다.  
  
 에 대 한 자세한 동적 분할 창, 문서에서 "분할 창"을 참조 [여러 문서 형식, 뷰 및 프레임 창](../../mfc/multiple-document-types-views-and-frame-windows.md), [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 클래스 개요입니다.  
  
##  <a name="oninverttracker"></a>  CSplitterWnd::OnInvertTracker  
 동일한 크기와 셰이프 프레임 창으로 되도록 분할 창의 이미지를 렌더링 합니다.  
  
```  
virtual void OnInvertTracker(const CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 *rect*  
 에 대 한 참조는 `CRect` 추적 사각형을 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 분할 창 크기를 조정 하는 동안 프레임 워크에서 호출 됩니다. 재정의 `OnInvertTracker` 분할 창의 이미지의 고급 사용자 지정에 대 한 합니다. 기본 이미지 분할 막대의 교차점 섞이는 한다는 점에서 Microsoft Windows 95/98 또는 Windows에 대 한 Microsoft works 분할자와 비슷합니다.  
  
 에 대 한 자세한 동적 분할 창, 문서에서 "분할 창"을 참조 [여러 문서 형식, 뷰 및 프레임 창](../../mfc/multiple-document-types-views-and-frame-windows.md), [기술 참고 29](../../mfc/tn029-splitter-windows.md), 및 `CSplitterWnd` 클래스 개요입니다.  
  
##  <a name="recalclayout"></a>  CSplitterWnd::RecalcLayout  
 분할 창 행 또는 열 크기를 조정한 후 다시 표시 하려면 여기를 호출 합니다.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>설명  
 행 및 열 크기를 조정한 후 올바르게 분할 창을 다시 표시 하려면이 멤버 함수 호출의 [SetRowInfo](#setrowinfo) 및 [SetColumnInfo](#setcolumninfo) 멤버 함수입니다. 분할 창 표시 되기 전에 생성 프로세스의 일부로 행 및 열 크기 변경 하면이 멤버 함수를 호출할 필요는 없습니다.  
  
 프레임 워크는 사용자 분할 창 크기를 조정 하거나 분할을 이동 될 때마다이 멤버 함수를 호출 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CSplitterWnd::SetColumnInfo](#setcolumninfo)합니다.  
  
##  <a name="setactivepane"></a>  CSplitterWnd::SetActivePane  
 창을 설정 합니다. 프레임에서 활성 상태 여야 합니다.  
  
```  
virtual void SetActivePane(
    int row,  
    int col,  
    CWnd* pWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 경우 *pWnd* NULL 이면 활성화 될 창에서 행을 지정 합니다.  
  
 *열*  
 경우 *pWnd* NULL 이면 활성화 될 창에서 열을 지정 합니다.  
  
 *pWnd*  
 에 대 한 포인터는 `CWnd` 개체입니다. 창으로 지정 된 값이 null 이면 *행* 및 *col* 활성 설정 되어 있습니다. NULL이 아닌 경우에 활성 설정 되어 있는 창을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 프레임 창 내에서 창으로 포커스를 변경할 때 창을 활성화로 설정 하는 프레임 워크에서 호출 됩니다. 명시적으로 호출할 수 `SetActivePane` 지정된 된 보기에 포커스를 변경할 수 있습니다.  
  
 행 및 열 중 하나를 제공 하 여 창 지정 **또는** 제공 하 여 *pWnd*합니다.  
  
##  <a name="setcolumninfo"></a>  CSplitterWnd::SetColumnInfo  
 지정 된 열 정보를 설정 하려면 여기를 호출 합니다.  
  
```  
void SetColumnInfo(
    int col,  
    int cxIdeal,  
    int cxMin);
```  
  
### <a name="parameters"></a>매개 변수  
 *열*  
 분할 창 열을 지정합니다.  
  
 *cxIdeal*  
 분할자 창 열에 대 한 이상적인 너비를 픽셀 단위로 지정 합니다.  
  
 *cxMin*  
 분할 창 열에 대 한 최소 너비를 픽셀 단위로 지정 합니다.  
  
### <a name="remarks"></a>설명  
 새 최소 너비 및 열에 대 한 이상적인 너비를 설정 하려면이 함수를 호출 합니다. 열 최소 값 너무 작아서 표시할 수 있는 열 시점을 결정 합니다.  
  
 프레임 워크가 표시 분할 창, 분할자 창의 클라이언트 영역 오른쪽 아래 모서리에 왼쪽 위에서 작동 하 여 이상적인 차원에 따른 행과 열에 있는 창 레이아웃 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#6](../../mfc/reference/codesnippet/cpp/csplitterwnd-class_4.cpp)]  
  
##  <a name="setrowinfo"></a>  CSplitterWnd::SetRowInfo  
 지정 된 행 정보를 설정 하려면 여기를 호출 합니다.  
  
```  
void SetRowInfo(
    int row,  
    int cyIdeal,  
    int cyMin);
```  
  
### <a name="parameters"></a>매개 변수  
 *행*  
 분할 창 행을 지정합니다.  
  
 *cyIdeal*  
 분할자 창 행에 대 한 이상적인 높이 픽셀 단위로 지정 합니다.  
  
 *cyMin*  
 분할 창 행에 대 한 최소 높이 픽셀 단위로 지정 합니다.  
  
### <a name="remarks"></a>설명  
 새 최소 높이 및 행의 이상적인 높이 설정 하려면이 함수를 호출 합니다. 행 최소값 행을 수 있는 시기 너무 작아서 표시할 수를 결정 합니다.  
  
 프레임 워크가 표시 분할 창, 분할자 창의 클라이언트 영역 오른쪽 아래 모서리에 왼쪽 위에서 작동 하 여 이상적인 차원에 따른 행과 열에 있는 창 레이아웃 합니다.  
  
##  <a name="setscrollstyle"></a>  CSplitterWnd::SetScrollStyle  
 분할 창에 대 한 새 스크롤 스타일 스크롤 막대 지원 공유를 지정 합니다.  
  
```  
void SetScrollStyle(DWORD dwStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwStyle*  
 분할 창에 대 한 새 스크롤 스타일 공유는 다음 값 중 하나일 수 있는 스크롤 막대 지원:  
  
- WS_HSCROLL 만들기/표시 공유 가로 스크롤 막대입니다.  
  
- WS_VSCROLL 만들기/표시 공유 세로 스크롤 막대입니다.  
  
### <a name="remarks"></a>설명  
 스크롤 막대를 만든 후이 소멸 되지 것입니다 경우에 `SetScrollStyle` 해당 스타일; 하지 않고 호출 되었으며 그 스크롤 막대 대신 숨겨져 있습니다. 이렇게 하면에서 스크롤 막대를 숨겨진 경우에 상태를 유지 합니다. 호출한 후 `SetScrollStyle` 를 호출할 필요는 [RecalcLayout](#recalclayout) 모든 변경 내용을 적용 하려면에 대 한 합니다.  
  
##  <a name="splitcolumn"></a>  CSplitterWnd::SplitColumn  
 프레임 창이 세로로 분할 하는 지점을 나타냅니다.  
  
```  
virtual BOOL SplitColumn(int cxBefore);
```  
  
### <a name="parameters"></a>매개 변수  
 *cxBefore*  
 분할이 발생 하기 전에 픽셀 단위로 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 세로 분할 창을 만들 때 호출 됩니다. `SplitColumn` 분할이 발생 하는 기본 위치를 나타냅니다.  
  
 `SplitColumn` (즉, 분할자 창에 있으면 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 해당 사용자 지정할 수 있습니다, 가상 함수를 함께 [CreateView](#createview)고급 동적 분할 창을 구현 합니다.  
  
##  <a name="splitrow"></a>  CSplitterWnd::SplitRow  
 프레임 창이 가로로 분할 하는 지점을 나타냅니다.  
  
```  
virtual BOOL SplitRow(int cyBefore);
```  
  
### <a name="parameters"></a>매개 변수  
 *cyBefore*  
 분할이 발생 하기 전에 픽셀 단위로 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 가로 분할자 창을 만들 때 호출 됩니다. `SplitRow` 분할이 발생 하는 기본 위치를 나타냅니다.  
  
 `SplitRow` (즉, 분할자 창에 있으면 SPLS_DYNAMIC_SPLIT 스타일) 동적 분할 창의 논리를 구현 하기 위해 프레임 워크에서 호출 됩니다. 해당 사용자 지정할 수 있습니다, 가상 함수를 함께 [CreateView](#createview)고급 동적 분할 창을 구현 합니다.  
  
##  <a name="ondraw"></a>  CSplitterWnd::OnDraw  
 분할 창 그리기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 *pDC*  
 장치 컨텍스트에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 VIEWEX](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)
