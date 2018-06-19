---
title: CDockSite 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockSite
- AFXDOCKSITE/CDockSite
- AFXDOCKSITE/CDockSite::AddRow
- AFXDOCKSITE/CDockSite::AdjustDockingLayout
- AFXDOCKSITE/CDockSite::AdjustLayout
- AFXDOCKSITE/CDockSite::AlignDockSite
- AFXDOCKSITE/CDockSite::CalcFixedLayout
- AFXDOCKSITE/CDockSite::CanAcceptPane
- AFXDOCKSITE/CDockSite::CreateEx
- AFXDOCKSITE/CDockSite::CreateRow
- AFXDOCKSITE/CDockSite::DockPane
- AFXDOCKSITE/CDockSite::DoesAllowDynInsertBefore
- AFXDOCKSITE/CDockSite::FindRowIndex
- AFXDOCKSITE/CDockSite::FixupVirtualRects
- AFXDOCKSITE/CDockSite::GetDockSiteID
- AFXDOCKSITE/CDockSite::GetDockSiteRowsList
- AFXDOCKSITE/CDockSite::IsAccessibilityCompatible
- AFXDOCKSITE/CDockSite::IsDragMode
- AFXDOCKSITE/CDockSite::IsLastRow
- AFXDOCKSITE/CDockSite::IsRectWithinDockSite
- AFXDOCKSITE/CDockSite::IsResizable
- AFXDOCKSITE/CDockSite::MovePane
- AFXDOCKSITE/CDockSite::OnInsertRow
- AFXDOCKSITE/CDockSite::OnRemoveRow
- AFXDOCKSITE/CDockSite::OnResizeRow
- AFXDOCKSITE/CDockSite::OnSetWindowPos
- AFXDOCKSITE/CDockSite::OnShowRow
- AFXDOCKSITE/CDockSite::OnSizeParent
- AFXDOCKSITE/CDockSite::PaneFromPoint
- AFXDOCKSITE/CDockSite::DockPaneLeftOf
- AFXDOCKSITE/CDockSite::FindPaneByID
- AFXDOCKSITE/CDockSite::GetPaneList
- AFXDOCKSITE/CDockSite::RectSideFromPoint
- AFXDOCKSITE/CDockSite::RemovePane
- AFXDOCKSITE/CDockSite::RemoveRow
- AFXDOCKSITE/CDockSite::ReplacePane
- AFXDOCKSITE/CDockSite::RepositionPanes
- AFXDOCKSITE/CDockSite::ResizeDockSite
- AFXDOCKSITE/CDockSite::ResizeRow
- AFXDOCKSITE/CDockSite::ShowPane
- AFXDOCKSITE/CDockSite::ShowRow
- AFXDOCKSITE/CDockSite::SwapRows
dev_langs:
- C++
helpviewer_keywords:
- CDockSite [MFC], AddRow
- CDockSite [MFC], AdjustDockingLayout
- CDockSite [MFC], AdjustLayout
- CDockSite [MFC], AlignDockSite
- CDockSite [MFC], CalcFixedLayout
- CDockSite [MFC], CanAcceptPane
- CDockSite [MFC], CreateEx
- CDockSite [MFC], CreateRow
- CDockSite [MFC], DockPane
- CDockSite [MFC], DoesAllowDynInsertBefore
- CDockSite [MFC], FindRowIndex
- CDockSite [MFC], FixupVirtualRects
- CDockSite [MFC], GetDockSiteID
- CDockSite [MFC], GetDockSiteRowsList
- CDockSite [MFC], IsAccessibilityCompatible
- CDockSite [MFC], IsDragMode
- CDockSite [MFC], IsLastRow
- CDockSite [MFC], IsRectWithinDockSite
- CDockSite [MFC], IsResizable
- CDockSite [MFC], MovePane
- CDockSite [MFC], OnInsertRow
- CDockSite [MFC], OnRemoveRow
- CDockSite [MFC], OnResizeRow
- CDockSite [MFC], OnSetWindowPos
- CDockSite [MFC], OnShowRow
- CDockSite [MFC], OnSizeParent
- CDockSite [MFC], PaneFromPoint
- CDockSite [MFC], DockPaneLeftOf
- CDockSite [MFC], FindPaneByID
- CDockSite [MFC], GetPaneList
- CDockSite [MFC], RectSideFromPoint
- CDockSite [MFC], RemovePane
- CDockSite [MFC], RemoveRow
- CDockSite [MFC], ReplacePane
- CDockSite [MFC], RepositionPanes
- CDockSite [MFC], ResizeDockSite
- CDockSite [MFC], ResizeRow
- CDockSite [MFC], ShowPane
- CDockSite [MFC], ShowRow
- CDockSite [MFC], SwapRows
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a374496c731e33d13de3ece893fe2ff046d38e7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33371379"
---
# <a name="cdocksite-class"></a>CDockSite Class
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 [CPane Class](../../mfc/reference/cpane-class.md) 에서 파생되는 창을 행 집합으로 배열하기 위한 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDockSite: public CBasePane  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDockSite::AddRow](#addrow)||  
|[CDockSite::AdjustDockingLayout](#adjustdockinglayout)|(재정의 [:: Adjustdockinglayout](../../mfc/reference/cbasepane-class.md#adjustdockinglayout).)|  
|[CDockSite::AdjustLayout](#adjustlayout)|(재정의 [cbasepane:: Adjustlayout](../../mfc/reference/cbasepane-class.md#adjustlayout).)|  
|[CDockSite::AlignDockSite](#aligndocksite)||  
|[CDockSite::CalcFixedLayout](#calcfixedlayout)|(재정의 [cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout).)|  
|[CDockSite::CanAcceptPane](#canacceptpane)|(재정의 [cbasepane:: Canacceptpane](../../mfc/reference/cbasepane-class.md#canacceptpane).)|  
|[CDockSite::CreateEx](#createex)|(재정의 [cbasepane:: Createex](../../mfc/reference/cbasepane-class.md#createex).)|  
|[CDockSite::CreateRow](#createrow)||  
|[CDockSite::DockPane](#dockpane)|(재정의 [cbasepane:: Dockpane](../../mfc/reference/cbasepane-class.md#dockpane).)|  
|[CDockSite::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|(재정의 [:: Doesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|  
|[CDockSite::FindRowIndex](#findrowindex)||  
|[CDockSite::FixupVirtualRects](#fixupvirtualrects)||  
|[CDockSite::GetDockSiteID](#getdocksiteid)||  
|[CDockSite::GetDockSiteRowsList](#getdocksiterowslist)||  
|[CDockSite::IsAccessibilityCompatible](#isaccessibilitycompatible)|(`CBasePane::IsAccessibilityCompatible`를 재정의합니다.)|  
|[CDockSite::IsDragMode](#isdragmode)||  
|[CDockSite::IsLastRow](#islastrow)||  
|[CDockSite::IsRectWithinDockSite](#isrectwithindocksite)||  
|[CDockSite::IsResizable](#isresizable)|(재정의 [cbasepane:: Isresizable](../../mfc/reference/cbasepane-class.md#isresizable).)|  
|[CDockSite::MovePane](#movepane)||  
|[CDockSite::OnInsertRow](#oninsertrow)||  
|[CDockSite::OnRemoveRow](#onremoverow)||  
|[CDockSite::OnResizeRow](#onresizerow)||  
|[CDockSite::OnSetWindowPos](#onsetwindowpos)||  
|[CDockSite::OnShowRow](#onshowrow)||  
|[CDockSite::OnSizeParent](#onsizeparent)||  
|[CDockSite::PaneFromPoint](#panefrompoint)|주어진 매개 변수로 지정된 지점에서 도킹 사이트에 도킹된 창을 반환합니다.|  
|[CDockSite::DockPaneLeftOf](#dockpaneleftof)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[CDockSite::FindPaneByID](#findpanebyid)|지정된 ID로 식별되는 창을 반환합니다.|  
|[CDockSite::GetPaneList](#getpanelist)|도킹 사이트에 도킹된 창 목록을 반환합니다.|  
|[CDockSite::RectSideFromPoint](#rectsidefrompoint)||  
|[CDockSite::RemovePane](#removepane)||  
|[CDockSite::RemoveRow](#removerow)||  
|[CDockSite::ReplacePane](#replacepane)||  
|[CDockSite::RepositionPanes](#repositionpanes)||  
|[CDockSite::ResizeDockSite](#resizedocksite)||  
|[CDockSite::ResizeRow](#resizerow)||  
|[CDockSite::ShowPane](#showpane)|창을 표시합니다.|  
|[CDockSite::ShowRow](#showrow)||  
|[CDockSite::SwapRows](#swaprows)||  
  
## <a name="remarks"></a>설명  
 프레임 워크 만듭니다 `CDockSite` 개체를 호출 하는 경우 자동으로 [CFrameWndEx::EnableDocking](../../mfc/reference/cframewndex-class.md#enabledocking)합니다. 도킹 사이트 창은 주 프레임 창에서 클라이언트 영역의 가장자리에 배치됩니다.  
  
 일반적으로 않아도 때문에 도킹 사이트에서 제공 하는 서비스를 호출 하려면 [CFrameWndEx 클래스](../../mfc/reference/cframewndex-class.md) 이러한 서비스를 처리 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CDockSite` 클래스의 개체를 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/cpp/cdocksite-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxDockSite.h  
  
##  <a name="addrow"></a>  CDockSite::AddRow  

  
```  
CDockingPanesRow* AddRow(
    POSITION pos,  
    int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pos`  
 [in] `nHeight`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="adjustdockinglayout"></a>  CDockSite::AdjustDockingLayout  

  
```  
virtual void AdjustDockingLayout();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="adjustlayout"></a>  CDockSite::AdjustLayout  

  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="aligndocksite"></a>  CDockSite::AlignDockSite  

  
```  
void AlignDockSite(
    const CRect& rectToAlignBy,  
    CRect& rectResult,  
    BOOL bMoveImmediately);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectToAlignBy`  
 [in] `rectResult`  
 [in] `bMoveImmediately`  
  
### <a name="remarks"></a>설명  
  
##  <a name="calcfixedlayout"></a>  CDockSite::CalcFixedLayout  

  
```  
virtual CSize CalcFixedLayout(
    BOOL bStretch,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bStretch`  
 [in] `bHorz`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="canacceptpane"></a>  CDockSite::CanAcceptPane  

  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pBar`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="createex"></a>  CDockSite::CreateEx  

  
```  
virtual BOOL CreateEx(
    DWORD dwStyleEx,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    DWORD dwControlBarStyle,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `dwStyleEx`  
 [in] `dwStyle`  
 [in] `rect`  
 [in] `pParentWnd`  
 [in] `dwControlBarStyle`  
 [in] `pContext`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="createrow"></a>  CDockSite::CreateRow  

  
```  
virtual CDockingPanesRow* CreateRow(
    CDockSite* pParentDockBar,  
    int nOffset,  
    int nRowHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pParentDockBar`  
 [in] `nOffset`  
 [in] `nRowHeight`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="dockpane"></a>  CDockSite::DockPane  

  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPCRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 [in] `dockMethod`  
 [in] `lpRect`  
  
### <a name="remarks"></a>설명  
  
##  <a name="dockpaneleftof"></a>  CDockSite::DockPaneLeftOf  
 창을 다른 창의 왼쪽에 도킹합니다.  
  
```  
virtual BOOL DockPaneLeftOf(
    CPane* pBarToDock,  
    CPane* pTargetBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out] `pBarToDock`  
 왼쪽에 도킹 창에 대 한 포인터 `pTargetBar`합니다.  
  
 [in] [out] `pTargetBar`  
 대상 창에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창이 도킹 되어 있는 성공적으로 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="doesallowdyninsertbefore"></a>  CDockSite::DoesAllowDynInsertBefore  

  
```  
virtual BOOL DoesAllowDynInsertBefore() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="findpanebyid"></a>  CDockSite::FindPaneByID  
 창에 지정 된 id를 반환합니다.  
  
```  
CPane* FindPaneByID(UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nID`  
 찾을 창의 명령 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 창에는 지정한 명령 ID에 대 한 포인터 또는 `NULL` 창에서을 찾을 수 없는 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="findrowindex"></a>  CDockSite::FindRowIndex  

  
```  
int FindRowIndex(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRow`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="fixupvirtualrects"></a>  CDockSite::FixupVirtualRects  

  
```  
virtual void FixupVirtualRects();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="getdocksiteid"></a>  CDockSite::GetDockSiteID  

  
```  
virtual UINT GetDockSiteID() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getdocksiterowslist"></a>  CDockSite::GetDockSiteRowsList  

  
```  
const CObList& GetDockSiteRowsList() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="getpanelist"></a>  CDockSite::GetPaneList  
 도킹 사이트에 도킹 된 창 목록을 반환 합니다.  
  
```  
const CObList& GetPaneList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 읽기 전용 참조 창의 목록은 현재 도킹 막대에 도킹 합니다.  
  
##  <a name="isaccessibilitycompatible"></a>  CDockSite::IsAccessibilityCompatible  

  
```  
virtual BOOL IsAccessibilityCompatible();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="isdragmode"></a>  CDockSite::IsDragMode  

  
```  
virtual BOOL IsDragMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="islastrow"></a>  CDockSite::IsLastRow  

  
```  
bool IsLastRow(CDockingPanesRow* pRow) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRow`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="isrectwithindocksite"></a>  CDockSite::IsRectWithinDockSite  

  
```  
BOOL IsRectWithinDockSite(
    CRect rect,  
    CPoint& ptDelta);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 [in] `ptDelta`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="isresizable"></a>  CDockSite::IsResizable  

  
```  
virtual BOOL IsResizable() const;  
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="movepane"></a>  CDockSite::MovePane  

  
```  
virtual BOOL MovePane(
    CPane* pWnd,  
    UINT nFlags,  
    CPoint ptOffset);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 [in] `nFlags`  
 [in] `ptOffset`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="oninsertrow"></a>  CDockSite::OnInsertRow  

  
```  
virtual void OnInsertRow(POSITION pos);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pos`  
  
### <a name="remarks"></a>설명  
  
##  <a name="onremoverow"></a>  CDockSite::OnRemoveRow  

  
```  
virtual void OnRemoveRow(
    POSITION pos,  
    BOOL bByShow = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pos`  
 [in] `bByShow`  
  
### <a name="remarks"></a>설명  
  
##  <a name="onresizerow"></a>  CDockSite::OnResizeRow  

  
```  
virtual int OnResizeRow(
    CDockingPanesRow* pRowToResize,  
    int nOffset);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRowToResize`  
 [in] `nOffset`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="onsizeparent"></a>  CDockSite::OnSizeParent  

  
```  
virtual void OnSizeParent(
    CRect& rectAvailable,  
    UINT nSide,  
    BOOL bExpand,  
    int nOffset);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectAvailable`  
 [in] `nSide`  
 [in] `bExpand`  
 [in] `nOffset`  
  
### <a name="remarks"></a>설명  
  
##  <a name="onsetwindowpos"></a>  CDockSite::OnSetWindowPos  

  
```  
virtual BOOL OnSetWindowPos(
    const CWnd* pWndInsertAfter,  
    const CRect& rectWnd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndInsertAfter`  
 [in] `rectWnd`  
 [in] `nFlags`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="onshowrow"></a>  CDockSite::OnShowRow  

  
```  
virtual void OnShowRow(
    POSITION pos,  
    BOOL bShow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pos`  
 [in] `bShow`  
  
### <a name="remarks"></a>설명  
  
##  <a name="panefrompoint"></a>  CDockSite::PaneFromPoint  
 주어진 매개 변수로 지정된 지점에서 도킹 사이트에 도킹된 창을 반환합니다.  
  
```  
virtual CPane* PaneFromPoint(CPoint pt);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pt`  
 한 요소를 화면 좌표를 검색 창에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 지점에 있는 창에 대 한 포인터 또는 `NULL` 없는 창이 지정된 된 지점에 있는 경우.  
  
### <a name="remarks"></a>설명  
  
##  <a name="rectsidefrompoint"></a>  CDockSite::RectSideFromPoint  

  
```  
static int __stdcall RectSideFromPoint(
    const CRect& rect,  
    const CPoint& point);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rect`  
 [in] `point`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="removepane"></a>  CDockSite::RemovePane  

  
```  
virtual void RemovePane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 [in] `dockMethod`  
  
### <a name="remarks"></a>설명  
  
##  <a name="removerow"></a>  CDockSite::RemoveRow  

  
```  
void RemoveRow(CDockingPanesRow* pRow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRow`  
  
### <a name="remarks"></a>설명  
  
##  <a name="replacepane"></a>  CDockSite::ReplacePane  

  
```  
BOOL ReplacePane(
    CPane* pOldBar,  
    CPane* pNewBar);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pOldBar`  
 [in] `pNewBar`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="repositionpanes"></a>  CDockSite::RepositionPanes  

  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `rectNewClientArea`  
  
### <a name="remarks"></a>설명  
  
##  <a name="resizedocksite"></a>  CDockSite::ResizeDockSite  

  
```  
void ResizeDockSite(
    int nNewWidth,  
    int nNewHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nNewWidth`  
 [in] `nNewHeight`  
  
### <a name="remarks"></a>설명  
  
##  <a name="resizerow"></a>  CDockSite::ResizeRow  

  
```  
int ResizeRow(
    CDockingPanesRow* pRow,  
    int nNewSize,  
    BOOL bAdjustLayout = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRow`  
 [in] `nNewSize`  
 [in] `bAdjustLayout`  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>설명  
  
##  <a name="showpane"></a>  CDockSite::ShowPane  
 창을 표시합니다.  
  
```  
virtual BOOL ShowPane(
    CBasePane* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] [out] `pBar`  
 에 표시 하거나 숨길 수 있는 창에 대 한 포인터입니다.  
  
 [in] `bShow`  
 `TRUE` 창에서 표시할; 임을 지정 하려면 `FALSE` 창이 숨겨져야 되는지 지정 하려면.  
  
 [in] `bDelay`  
 `TRUE` 창 레이아웃 창이 표시 되 고; 후까지 지연 될 해야 지정 하려면 그렇지 않으면 `FALSE`합니다.  
  
 [in] `bActivate`  
 이 매개 변수는 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 창에서 성공적으로 숨기 거 나 표시할지 되었습니다. `FALSE` 지정 된 창이 도킹 사이트에 속해 있지 않으면입니다.  
  
### <a name="remarks"></a>설명  
 표시 하거나 숨기려면 도킹 된 창에이 메서드를 호출 합니다. 호출할 필요가 없습니다 일반적으로 `CDockSite::ShowPane` 를 직접 부모 프레임 창에서 또는 기본 창에서 호출 되어 합니다.  
  
##  <a name="showrow"></a>  CDockSite::ShowRow  

  
```  
void ShowRow(
    CDockingPanesRow* pRow,  
    BOOL bShow,  
    BOOL bAdjustLayout);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pRow`  
 [in] `bShow`  
 [in] `bAdjustLayout`  
  
### <a name="remarks"></a>설명  
  
##  <a name="swaprows"></a>  CDockSite::SwapRows  

  
```  
void SwapRows(
    CDockingPanesRow* pFirstRow,  
    CDockingPanesRow* pSecondRow);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pFirstRow`  
 [in] `pSecondRow`  
  
### <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CBasePane 클래스](../../mfc/reference/cbasepane-class.md)
