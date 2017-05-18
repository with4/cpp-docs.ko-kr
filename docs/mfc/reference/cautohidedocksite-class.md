---
title: "CAutoHideDockSite 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::CanAcceptPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::DockPane
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::GetAlignRect
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::RepositionPanes
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetLeft
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::SetOffsetRight
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::UnSetAutoHideMode
- AFXAUTOHIDEDOCKSITE/CAutoHideDockSite::m_nExtraSpace
dev_langs:
- C++
helpviewer_keywords:
- AllowShowOnPaneMenu method
- CAutoHideDockSite class
ms.assetid: 2a0f6bec-c369-4ab7-977d-564e7946ebad
caps.latest.revision: 32
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 58beaa382a2ef04cfaee0fbcf63b9eef36831472
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cautohidedocksite-class"></a>CAutoHideDockSite 클래스
`CAutoHideDockSite` 확장은 [CDockSite 클래스](../../mfc/reference/cdocksite-class.md) 자동 숨김 도킹 창을 구현 하 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAutoHideDockSite : public CDockSite  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|`CAutoHideDockSite::CAutoHideDockSite`|
          `CAutoHideDockSite` 개체를 생성합니다.|  
|`CAutoHideDockSite::~CAutoHideDockSite`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|`CAutoHideDockSite::AllowShowOnPaneMenu`|나타냅니다 여부는 `CAutoHideDockSite` 메뉴에 표시 됩니다.|  
|[CAutoHideDockSite::CanAcceptPane](#canacceptpane)|기본 창 개체에서 파생 되었는지 여부를 결정은 [CMFCAutoHideBar 클래스](../../mfc/reference/cmfcautohidebar-class.md)합니다.|  
|[CAutoHideDockSite::DockPane](#dockpane)|이 창을 도킹 `CAuotHideDockSite` 개체입니다.|  
|[CAutoHideDockSite::GetAlignRect](#getalignrect)|화면 좌표에서 도크 사이트의 크기를 검색합니다.|  
|[CAutoHideDockSite::RepositionPanes](#repositionpanes)|창에서 다시 그리면는 `CAutoHideDockSite` 전역 여백 및 단추 간격입니다.|  
|[CAutoHideDockSite::SetOffsetLeft](#setoffsetleft)|도킹 모음의 왼쪽 여백을 설정합니다.|  
|[CAutoHideDockSite::SetOffsetRight](#setoffsetright)|도킹 막대의 오른쪽 여백을 설정합니다.|  
|[CAutoHideDockSite::UnSetAutoHideMode](#unsetautohidemode)|호출 [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) 개체에 대 한는 `CAutoHideDockSite`합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|이름|설명|  
|[CAutoHideDockSite::m_nExtraSpace](#m_nextraspace)|도구 모음 도킹 막대의 가장자리 사이의 공간 크기를 정의합니다. 이 공간은 왼쪽된 가장자리 또는 도킹 공간에 대 한 맞춤에 따라 위쪽 가장자리에서 측정 됩니다.|  
  
## <a name="remarks"></a>주의  
 호출 하는 경우 [CFrameWndEx::EnableAutoHidePanes](../../mfc/reference/cframewndex-class.md#enableautohidepanes), 프레임 워크는 자동으로 만들고는 `CAutoHideDockSite` 개체입니다. 대부분의 경우에서 있습니다 없어야를 인스턴스화하거나이 클래스를 직접 사용 합니다.  
  
 도킹 막대는 왼쪽 도킹 창와 왼쪽 간의 차이 [CMFCAutoHideButton 클래스](../../mfc/reference/cmfcautohidebutton-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 검색 하는 방법을 한 `CAutoHideDockSite` 에서 개체는 `CMFCAutoHideBar` 개체 및 도킹 창의 왼쪽 및 오른쪽 여백을 설정 하는 방법입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&29;](../../mfc/reference/codesnippet/cpp/cautohidedocksite-class_1.cpp)]  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxautohidedocksite.h  
  
##  <a name="canacceptpane"></a>CAutoHideDockSite::CanAcceptPane  
 기본 창 인지를 확인 한 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 또는 개체에서 파생 된 `CMFCAutoHideBar`합니다.  
  
```  
virtual BOOL CanAcceptPane(const CBasePane* pBar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pBar`|프레임 워크를 테스트 하는 기본 창입니다.|  
  
### <a name="return-value"></a>반환 값  
 `TRUE`경우 `pBar` 에서 파생 된 `CMFCAutoHideBar`; `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 기본 창 개체에서 파생 된 경우 `CMFCAutoHideBar`, 포함할 수는 `CAutoHideDockSite`합니다.  
  
##  <a name="dockpane"></a>CAutoHideDockSite::DockPane  
 이 창을 도킹 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) 개체입니다.  
  
```  
virtual void DockPane(
    CPane* pWnd,  
    AFX_DOCK_METHOD dockMethod,  
    LPRECT lpRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pWnd`|프레임 워크 도킹 된 창입니다.|  
|[in] `dockMethod`|창에 대 한 옵션을 도킹 합니다.|  
|[in] `lpRect`|도킹 된 창에 대 한 경계를 지정 하는 사각형입니다.|  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 매개 변수를 사용 하지 않습니다 `dockMethod`를 제공 하는 나중에 사용할 수 있습니다.  
  
 경우 `lpRect` 는 `NULL`, 프레임 워크 도크 사이트의 기본 위치에 있는 창을 넣습니다. 도킹 사이트 가로 이면 왼쪽에 도킹 사이트의 기본 위치는 합니다. 그렇지 않은 경우 기본 위치는 도크 사이트의 위쪽에 있습니다.  
  
##  <a name="getalignrect"></a>CAutoHideDockSite::GetAlignRect  
 화면 좌표에서 도크 사이트의 크기를 검색합니다.  
  
```  
void GetAlignRect(CRect& rect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `rect`|사각형에 대 한 참조입니다. 메서드는이 사각형에 도크 사이트의 크기를 저장합니다.|  
  
### <a name="remarks"></a>주의  
 사각형은 포함 되지 않도록 오프셋된 여백에 대해 조정 됩니다.  
  
##  <a name="m_nextraspace"></a>CAutoHideDockSite::m_nExtraSpace  
 가장자리 사이의 공간 크기는 [CAutoHideDockSite 클래스](../../mfc/reference/cautohidedocksite-class.md) 및 [CMFCAutoHideBar 클래스](../../mfc/reference/cmfcautohidebar-class.md) 개체입니다.  
  
```  
static int m_nExtraSpace;  
```  
  
### <a name="remarks"></a>주의  
 때는 `CMFCAutoHideBar` 에 도킹 한 `CAutoHideDockSite`, 전체 도크 사이트를 차지 하지 해야 합니다. 왼쪽 가장자리나 위쪽 테두리 사이의 공간을 제어 하는이 전역 변수는 `CMFCAutoHideBar` 해당 `CAutoHideDockSite` 가장자리입니다. 위쪽 또는 왼쪽 가장자리에서 사용 되는지 여부는 현재 맞춤에 따라 달라 집니다.  
  
##  <a name="setoffsetleft"></a>CAutoHideDockSite::SetOffsetLeft  
 도킹 모음의 왼쪽 여백을 설정합니다.  
  
```  
void SetOffsetLeft(int nOffset);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nOffset`  
 새 오프셋입니다.  
  
### <a name="remarks"></a>주의  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체에 정적으로 배치 되는 `CAutoHideDockSite` 개체입니다. 즉, 사용자의 위치를 변경할 수 없는 수동으로 `CMFCAutoHideBar` 개체입니다. `SetOffsetLeft` 가장 왼쪽의 왼쪽 사이의 간격을 제어 하는 메서드 `CMFCAutoHideBar` 및 왼쪽에는 `CAutoHideDockSite`합니다.  
  
##  <a name="setoffsetright"></a>CAutoHideDockSite::SetOffsetRight  
 도킹 막대의 오른쪽 여백을 설정합니다.  
  
```  
void SetOffsetRight(int nOffset);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nOffset`  
 새 오프셋입니다.  
  
### <a name="remarks"></a>주의  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체에 정적으로 배치 되는 `CAutoHideDockSite` 개체입니다. 즉, 사용자의 위치를 변경할 수 없는 수동으로 `CMFCAutoHideBar` 개체입니다. `SetOffsetRight` 맨 오른쪽의 오른쪽 사이의 간격을 제어 하는 메서드 `CMFCAutoHideBar` 및 오른쪽에는 `CAutoHideDockSite`합니다.  
  
##  <a name="repositionpanes"></a>CAutoHideDockSite::RepositionPanes  
 에 창이 다시 그리면는 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)합니다.  
  
```  
virtual void RepositionPanes(CRect& rectNewClientArea);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `rectNewClientArea`|예약 된 값입니다.|  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 사용 하지 않는 `rectNewClientArea`합니다. 일반 도구 모음 여백 및 단추 간격입니다. 창을 다시 그립니다.  
  
##  <a name="unsetautohidemode"></a>CAutoHideDockSite::UnSetAutoHideMode  
 호출 [CMFCAutoHideBar::UnSetAutoHideMode](../../mfc/reference/cmfcautohidebar-class.md#unsetautohidemode) 개체 도킹 사이트에 대 한 합니다.  
  
```  
void UnSetAutoHideMode(CMFCAutoHideBar* pAutoHideToolbar);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pAutoHideToolbar`|에 대 한 포인터는 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md) 개체 창에 있는 `CAutoHideDockSite`합니다.|  
  
### <a name="remarks"></a>주의  
 이 메서드를 포함 하는 행에 대 한 검색 `pAutoHideToolbar`합니다. 호출 `CMFCAutoHideBar.UnSetAutoHideMode` 모든는 `CMFCAutoHideBar` 해당 행에는 개체입니다. 경우 `pAutoHideToolbar` 파일이 아니거나 `NULL`,이 메서드를 호출 `CMFCAutoHideBar.UnSetAutoHideMode` 모든는 `CMFCAutoHideBar` 에 있는 개체는 `CAutoHideDockSite`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockSite 클래스](../../mfc/reference/cdocksite-class.md)

