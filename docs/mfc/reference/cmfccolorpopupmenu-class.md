---
title: "CMFCColorPopupMenu 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu class
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 14076d78eaf86ef01e68656685dd2fd102d96311
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu 클래스
문서 또는 응용 프로그램에서 색을 선택 하는 데 사용할 팝업 메뉴를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|`CMFCColorPopupMenu` 개체를 생성합니다.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|||  
|-|-|  
|이름|설명|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|도킹 가능한 분리 색 막대를 만듭니다. (재정의 [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|반환 된 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 팝업 메뉴에 포함 된입니다. (재정의 [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|에 대 한 포인터를 가져오는 데 프레임 워크에 의해는 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식으로 연결 된 개체입니다.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|속성 표 컨트롤 개체의 포함 된 설정 `CMFCColorBar` 개체입니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|이름|설명|  
|`m_bEnabledInCustomizeMode`|색 막대를 표시할지 여부를 결정 하는 부울 값입니다.|  
|`m_wndColorBar`|`CMFCColorBar` 색 선택을 제공 하는 개체입니다.|  
  
### <a name="remarks"></a>설명  
 이 클래스의 팝업 메뉴 기능을 상속 된 `CMFCPopupMenu` 클래스 및 관리 하는 `CMFCColorBar` 색 선택을 제공 하는 개체입니다. 도구 모음 프레임 워크가 사용자 지정 모드에 있을 때와 `m_bEnabledInCustomizeMode` 멤버가로 설정 된 `FALSE`, 색 막대 개체는 표시 되지 않습니다. 사용자 지정 모드에 대 한 자세한 내용은 참조 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 에 대 한 자세한 내용은 `CMFCColorBar`, 참조 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu"></a>CMFCColorPopupMenu::CMFCColorPopupMenu  
 `CMFCColorPopupMenu` 개체를 생성합니다.  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `colors`  
 배열 프레임 워크의 팝업 메뉴에 표시 하는 색입니다.  
  
 [in] `color`  
 색을 선택합니다.  
  
 [in] `lpszAutoColor`  
 텍스트 레이블을 *자동* (기본값) 색 단추 또는 `NULL`합니다.  
  
 자동 단추에 대 한 표준 레이블은 **자동**합니다.  
  
 [in] `lpszOtherColor`  
 텍스트 레이블을 *다른* 단추를 다른 색 선택 표시, 또는 `NULL`합니다.  
  
 다른 단추에 대 한 표준 레이블은 **다른 색... **.  
  
 [in] `lpszDocColors`  
 문서 색 단추의 텍스트 레이블입니다. 색상표를 문서는 현재 문서에 사용 된 모든 색을 나열 합니다.  
  
 [in] `lstDocColors`  
 현재 문서에 사용 된 색의 목록이 됩니다.  
  
 [in] `nColumns`  
 색의 배열에 있는 열의 수입니다.  
  
 [in] `nHorzDockRows`  
 가로 방향으로 도킹 한 경우 색 막대에 있는 행의 수입니다.  
  
 [in] `nVertDockColumns`  
 세로로 도킹 한 경우 색 막대에 있는 열의 수입니다.  
  
 [in] `colorAutomatic`  
 자동 단추를 클릭할 때 프레임 워크 적용 되는 기본 색입니다.  
  
 [in] `uiCommandID`  
 색 막대 제어 명령 id입니다.  
  
 [in] `bStdColorDlg`  
 표준 시스템 색 대화 상자를 표시할지 여부를 나타내는 부울 값 또는 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 대화 상자입니다.  
  
 [in] `pParentBtn`  
 부모 단추에 대 한 포인터입니다.  
  
 [in] `nID`  
 명령 ID입니다.  
  
### <a name="remarks"></a>주의  
 생성자 오버 로드 된 각는 `m_bEnabledInCustomizeMode` 멤버를 `FALSE`합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 생성 하는 방법을 한 `CMFCColorPopupMenu` 개체입니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp #&34;](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>CMFCColorPopupMenu::CreateTearOffBar  
 도킹 가능한 분리 색 막대를 만듭니다.  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>매개 변수  
  
|||  
|-|-|  
|매개 변수|설명|  
|[in] `pWndMain`|분리 막대의 부모 창에 대 한 포인터입니다.|  
|[in] `uiID`|분리 막대의 명령 ID입니다.|  
|[in] `lpszName`|분리 표시줄 창의 텍스트입니다.|  
  
### <a name="return-value"></a>반환 값  
 새 분리 컨트롤 모음 개체에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드가 만드는 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 개체와 캐스팅 한 [CPane 클래스](../../mfc/reference/cpane-class.md) 포인터입니다. 이 값을 캐스팅할 수 다시는 [CMFCColorBar 클래스](../../mfc/reference/cmfccolorbar-class.md) 에 설명 된 캐스팅 매크로 중 하나를 사용 하 여 포인터 [MFC 클래스 개체의 형식 캐스팅의](../../mfc/reference/type-casting-of-mfc-class-objects.md)합니다.  
  
##  <a name="getmenubar"></a>CMFCColorPopupMenu::GetMenuBar  
 반환 된 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 팝업 메뉴에 포함 된입니다.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>반환 값  
 포함 된 작업에 대 한 포인터 `CMFCPopupMenuBar`합니다.  
  
### <a name="remarks"></a>주의  
 색 팝업 메뉴에는 포함 된 [CMFCPopupMenuBar 클래스](../../mfc/reference/cmfcpopupmenubar-class.md) 개체입니다. 응용 프로그램에 포함 된 다른 형식을 사용 하는 경우 파생된 클래스에서이 메서드를 재정의 합니다.  
  
##  <a name="setproplist"></a>CMFCColorPopupMenu::SetPropList  
 속성 표 컨트롤 개체의 포함 된 설정 `CMFCColorBar` 개체입니다.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pWndList`  
 속성 표 컨트롤 개체에 대 한 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

