---
title: "CStatusBar 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBar
dev_langs:
- C++
helpviewer_keywords:
- indicators, status bar
- CStatusBar class
- status bars
- indicators
- status indicators
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: 24
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e96070041ef5bcee0865991a14b6484082d8fc91
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbar-class"></a>CStatusBar 클래스
텍스트 출력 창의 행 또는 "지표"가 있는 컨트롤 막대입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|`CStatusBar` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|지정 된 표시기 ID에 대 한 인덱스를 가져옵니다.|  
|[CStatusBar::Create](#create)|상태 표시줄을 만들고, 연결 하는 `CStatusBar` 개체를 초기 글꼴과 막대 높이 설정 합니다.|  
|[CStatusBar::CreateEx](#createex)|만듭니다는 `CStatusBar` 개체에 포함 된 스타일을 추가 하 여 `CStatusBarCtrl` 개체입니다.|  
|[CStatusBar::DrawItem](#drawitem)|소유자 그리기 상태 표시줄 컨트롤의 시각적 측면이 때 호출 됩니다.|  
|[CStatusBar::GetItemID](#getitemid)|지정된 된 인덱스에 대 한 표시기 ID를 가져옵니다.|  
|[CStatusBar::GetItemRect](#getitemrect)|지정된 된 인덱스에 대 한 사각형을 표시 하는 가져옵니다.|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|지정된 된 인덱스에 대 한 표시기 ID, 스타일 및 두께 가져옵니다.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|지정된 된 인덱스에 대 한 표시기 스타일을 가져옵니다.|  
|[CStatusBar::GetPaneText](#getpanetext)|지정된 된 인덱스에 대 한 표시기 텍스트를 가져옵니다.|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|내부 공용 컨트롤에 직접 액세스할 수 있습니다.|  
|[CStatusBar::SetIndicators](#setindicators)|표시기 Id를 설정합니다.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|표시기 ID, 스타일 및 두께 지정 된 인덱스를 설정합니다.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|지정된 된 인덱스에 대 한 표시기 스타일을 설정합니다.|  
|[CStatusBar::SetPaneText](#setpanetext)|지정된 된 인덱스에 대 한 표시기 텍스트를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 일반적으로 출력 창은 상태 표시기와 메시지 줄으로 사용 됩니다. SCROLL LOCK, NUM LOCK 및 다른 키의 상태를 나타내는 표시기 및 선택 된 메뉴 명령에 간략히 설명 하는 메뉴 도움말 메시지 줄을 예로 들 수 있습니다.  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), 멤버 함수 새로운 MFC 4.0 허용 상태 표시줄 사용자 지정 및 추가 기능에 대 한 Windows 공용 컨트롤 지원 기능을 사용할 수 있습니다. `CStatusBar`멤버 함수를 사용 하면 대부분의 Windows 공용 컨트롤;의 기능 그러나 호출 하면 `GetStatusBarCtrl`, Windows 95/98 상태 표시줄의 특징 중 훨씬 더 많은 상태 표시줄을 제공할 수 있습니다. 호출 하는 경우 `GetStatusBarCtrl`에 대 한 참조를 반환 합니다는 `CStatusBarCtrl` 개체입니다. 참조 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Windows 공용 컨트롤을 사용 하 여 도구 모음을 디자인 하는 방법에 대 한 자세한 내용은 합니다. 공용 컨트롤에 대 한 자세한 내용은 참조 하십시오. [공용 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775493) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 표시기 정보 위치 0의 가장 왼쪽에 있는 표시기를 배열에 보관 하는 프레임 워크입니다. 상태 표시줄을 만들 때 해당 표시기가 있는 프레임 워크를 연결 하는 Id 문자열의 배열을 사용 합니다. 그런 다음 표시기에 액세스 하는 문자열 ID 또는 인덱스를 사용할 수 있습니다.  
  
 기본적으로 첫 번째 표시기가 "탄력적인": 차지 다른 표시기 창에서 사용 하지 않는 상태 표시줄 길이 다른 창 오른쪽 맞춤 합니다.  
  
 상태 표시줄을 만들려면 다음이 단계를 따르십시오.  
  
1.  `CStatusBar` 개체를 생성합니다.  
  
2.  호출 된 [만들기](#create) (또는 [CreateEx](#createex)) 상태 표시줄 창을 만들고에 연결 하는 함수는 `CStatusBar` 개체입니다.  
  
3.  호출 [SetIndicators](#setindicators) 각 표시기로 문자열 ID를 연결할 수 있습니다.  
  
 상태 표시줄 창의 텍스트를 업데이트 하는 방법은 세 가지가 있습니다.  
  
1.  호출 [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) 0 창에서 텍스트를 업데이트 합니다.  
  
2.  호출 [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) 상태 표시줄에 `ON_UPDATE_COMMAND_UI` 처리기입니다.  
  
3.  호출 [SetPaneText](#setpanetext) 모든 창에 대 한 텍스트를 업데이트 합니다.  
  
 호출 [SetPaneStyle](#setpanestyle) 상태 표시줄 창의 스타일을 업데이트 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CStatusBar`, 문서를 참조 하십시오 [MFC의 상태 표시줄 구현](../../mfc/status-bar-implementation-in-mfc.md) 및 [기술 Note 31: 컨트롤 막대](../../mfc/tn031-control-bars.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="a-namecommandtoindexa--cstatusbarcommandtoindex"></a><a name="commandtoindex"></a>CStatusBar::CommandToIndex  
 지정 된 ID에 대 한 표시기 인덱스를 가져옵니다.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDFind`  
 인덱스가 범위를 검색할 표시기의 문자열 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 표시기의 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 첫 번째 표시기의 인덱스는 0입니다.  
  
##  <a name="a-namecreatea--cstatusbarcreate"></a><a name="create"></a>CStatusBar::Create  
 상태 표시줄 (자식 창)을 만들고 사용 하 여 연결 된 `CStatusBar` 개체입니다.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentWnd`  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 인 Windows 창 상태 표시줄의 부모인 개체입니다.  
  
 `dwStyle`  
 상태 표시줄 스타일입니다. 표준 Windows 외에도 [스타일](../../mfc/reference/window-styles.md), 이러한 스타일은 지원 됩니다.  
  
- `CBRS_TOP`컨트롤 막대는 프레임 창 위쪽에 있습니다.  
  
- `CBRS_BOTTOM`컨트롤 막대는 프레임 창 아래쪽에 있습니다.  
  
- `CBRS_NOALIGN`컨트롤 막대 부모 크기가 조정 될 때 변경 되지 됩니다.  
  
 `nID`  
 도구 모음의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 또한 초기 글꼴을 설정 하 고 상태를 설정 기본값으로 막대의 높이입니다.  
  
##  <a name="a-namecreateexa--cstatusbarcreateex"></a><a name="createex"></a>CStatusBar::CreateEx  
 상태 표시줄 (자식 창)을 만들어 사용 하 여 연결 하려면이 함수를 호출 하 여 `CStatusBar` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>매개 변수  
 `pParentWnd`  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 인 Windows 창 상태 표시줄의 부모인 개체입니다.  
  
 `dwCtrlStyle`  
 포함된 된 생성에 대 한 추가 스타일 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) 개체입니다. 기본적으로는 상태 표시줄 크기 조정 그립 또는 도구 설명 없이 지정을 지원 합니다. 지원 되는 상태 표시줄 스타일은  
  
- **SBARS_SIZEGRIP** 상태 표시줄 컨트롤 크기 조정 그립 상태 표시줄의 오른쪽 끝에 포함 됩니다. 크기 조정 그립 크기 조정 테두리;에 대해 비슷합니다. 그 사용자를 클릭 하 고 끌어서 크기를 부모 창 조정 수 있는 사각형 영역입니다.  
  
- **SBT_TOOLTIPS** 상태 표시줄에 도구 설명 지원 합니다.  
  
 이러한 스타일에 대 한 세부 정보를 참조 하십시오. [CStatusBarCtrl에 대 한 설정을](../../mfc/settings-for-the-cstatusbarctrl.md)합니다.  
  
 `dwStyle`  
 상태 표시줄 스타일입니다. 기본 표시 상태 표시줄 프레임 창의 맨 아래에 생성 되도록 지정 합니다. 상태 표시줄에 나열 된 컨트롤 스타일의 조합이 적용 [창 스타일](../../mfc/reference/window-styles.md) 및 [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create)합니다. 그러나이 매개 변수 WS_CHILD 및 WS_VISIBLE 스타일을 항상 포함 해야 합니다.  
  
 `nID`  
 상태 표시줄의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 또한 초기 글꼴을 설정 하 고 상태를 설정 기본값으로 막대의 높이입니다.  
  
 사용 하 여 `CreateEx`, 대신 [만들기](#create)특정 스타일을 포함 된 상태 표시줄 컨트롤을 만드는 동안 존재 해야 하는 경우. 예를 들어 설정 `dwCtrlStyle` 를 **SBT_TOOLTIPS** 상태 표시줄 개체에서 도구 설명을 표시 하려면.  
  
##  <a name="a-namecstatusbara--cstatusbarcstatusbar"></a><a name="cstatusbar"></a>CStatusBar::CStatusBar  
 생성 된 `CStatusBar` 개체 만듭니다 필요한 경우 기본 상태 표시줄 글꼴 및 글꼴 특성 값을 기본값으로 설정 합니다.  
  
```  
CStatusBar();
```  
  
##  <a name="a-namedrawitema--cstatusbardrawitem"></a><a name="drawitem"></a>CStatusBar::DrawItem  
 이 멤버 함수는 소유자가 그린 상태 표시줄 변경의 시각적 측면이 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) 필요한 드로잉의 종류에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>주의  
 **itemAction** 의 멤버는 `DRAWITEMSTRUCT` 구조 수행 되는 그리기 작업을 정의 합니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CStatusBar` 개체입니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 인터페이스 (GDI) 개체를 복원 해야 `lpDrawItemStruct` 이 멤버 함수를 종료 하기 전에 합니다.  
  
##  <a name="a-namegetitemida--cstatusbargetitemid"></a><a name="getitemid"></a>CStatusBar::GetItemID  
 지정 된 표시기의 ID를 반환 `nIndex`합니다.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 검색할 ID가 있는 표시기의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 표시기의 ID `nIndex`합니다.  
  
##  <a name="a-namegetitemrecta--cstatusbargetitemrect"></a><a name="getitemrect"></a>CStatusBar::GetItemRect  
 복사 하 여 지정 된 표시기의 좌표 `nIndex` 구조를 가리키는 `lpRect`합니다.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 검색할 수 있는 사각형 좌표는 표시기의 인덱스입니다.  
  
 `lpRect`  
 가리키는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 로 지정 된 표시기의 좌표를 받게 될 개체입니다 `nIndex`합니다.  
  
### <a name="remarks"></a>주의  
 좌표는 상태 표시줄의 왼쪽 위 모퉁이 기준으로 하는 픽셀입니다.  
  
##  <a name="a-namegetpaneinfoa--cstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>CStatusBar::GetPaneInfo  
 집합 `nID`, `nStyle`, 및 `cxWidth` ID, 스타일 및 지정 된 위치에서 표시기 창의 너비를 `nIndex`합니다.  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스 인 정보를 검색 하는 창입니다.  
  
 `nID`  
 에 대 한 참조는 **UINT** 창에서의 ID로 설정 된 합니다.  
  
 `nStyle`  
 에 대 한 참조는 **UINT** 창의 스타일으로 설정 되어 있는 합니다.  
  
 `cxWidth`  
 창의 너비를 설정 하는 정수에 대 한 참조입니다.  
  
##  <a name="a-namegetpanestylea--cstatusbargetpanestyle"></a><a name="getpanestyle"></a>CStatusBar::GetPaneStyle  
 상태 표시줄의 창 스타일을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 창 스타일을 검색할 수는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 상태 표시줄 창의 스타일 `nIndex`합니다.  
  
### <a name="remarks"></a>주의  
 창 스타일 창에서 표시 되는 방식을 결정 합니다.  
  
 상태 표시줄에 사용할 수 있는 스타일의 목록은 참조 하십시오. [만들기](#create)합니다.  
  
##  <a name="a-namegetpanetexta--cstatusbargetpanetext"></a><a name="getpanetext"></a>CStatusBar::GetPaneText  
 상태 표시줄 창에 표시 되는 텍스트를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  ```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be retrieved.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that contains the text to be retrieved.  
  
### Return Value  
 A `CString` object containing the pane's text.  
  
### Remarks  
 The second form of this member function fills a `CString` object with the string text.  
  
##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl  
 This member function allows direct access to the underlying common control.  
  
```  
CStatusBarCtrl / / GetStatusBarCtrl() const;  
```  
  
### Return Value  
 Contains a reference to a [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) object.  
  
### Remarks  
 Use `GetStatusBarCtrl` to take advantage of the functionality of the Windows status-bar common control, and to take advantage of the support [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) provides for status-bar customization. For example, by using the common control, you can specify a style that includes a sizing grip on the status bar, or you can specify a style to have the status bar appear at the top of the parent window's client area.  
  
 For more general information about common controls, See [Common Controls](http://msdn.microsoft.com/library/windows/desktop/bb775493) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setindicators"></a>  CStatusBar::SetIndicators  
 Sets each indicator's ID to the value specified by the corresponding element of the array `lpIDArray`, loads the string resource specified by each ID, and sets the indicator's text to the string.  
  
```  
BOOL SetIndicators (const UINT * lpIDArray,  
    int nIDCount);
```  
  
### Parameters  
 `lpIDArray`  
 Pointer to an array of IDs.  
  
 `nIDCount`  
 Number of elements in the array pointed to by `lpIDArray`.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 Sets the specified indicator pane to a new ID, style, and width.  
  
```  
void SetPaneInfo (int nIndex,  
    UINT nID  
    UINT nStyle  
    int cxWidth);
```  
  
### Parameters  
 `nIndex`  
 Index of the indicator pane whose style is to be set.  
  
 `nID`  
 New ID for the indicator pane.  
  
 `nStyle`  
 New style for the indicator pane.  
  
 `cxWidth`  
 New width for the indicator pane.  
  
### Remarks  
 The following indicator styles are supported:  
  
- **SBPS_NOBORDERS** No 3-D border around the pane.  
  
- **SBPS_POPOUT** Reverse border so that text "pops out."  
  
- **SBPS_DISABLED** Do not draw text.  
  
- **SBPS_STRETCH** Stretch pane to fill unused space. Only one pane per status bar can have this style.  
  
- **SBPS_NORMAL** No stretch, borders, or pop-out.  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 Call this member function to set the style of a status bar's pane.  
  
```  
void SetPaneStyle (int nIndex,  
    UINT nStyle);
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose style is to be set.  
  
 `nStyle`  
 Style of the pane whose style is to be set.  
  
### Remarks  
 A pane's style determines how the pane appears.  
  
 For a list of styles available for status bars, see [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 Call this member function to set the pane text to the string pointed to by `lpszNewText`.  
  
```  
BOOL SetPaneText (int nIndex,  
    LPCTSTR lpszNewText  
    BOOL b 업데이트 = TRUE);
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be set.  
  
 `lpszNewText`  
 Pointer to the new pane text.  
  
 *bUpdate*  
 If **TRUE**, the pane is invalidated after the text is set.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 After you call `SetPaneText`, you must add a UI update handler to display the new text in the status bar.  
  
### Example  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## See Also  
 [MFC Sample CTRLBARS](../../visual-cpp-samples.md)   
 [MFC Sample DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)

