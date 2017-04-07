---
title: "CStatusBar 클래스 | Microsoft Docs"
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
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
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
ms.sourcegitcommit: b790beb88de009e1c7161f3c9af6b3e21c22fd8e
ms.openlocfilehash: a2358d31bd87b2cc540dd9a5ce182b9340764522
ms.lasthandoff: 03/29/2017

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
|[CStatusBar::CommandToIndex](#commandtoindex)|지정 된 표시기 ID에 대해 인덱스를 가져옵니다.|  
|[CStatusBar::Create](#create)|에 연결, 상태 표시줄을 만듭니다는 `CStatusBar` 개체를 초기 글꼴과 막대 높이 설정 합니다.|  
|[CStatusBar::CreateEx](#createex)|만듭니다는 `CStatusBar` 개체는 포함 된 항목에 대 한 추가 스타일으로 `CStatusBarCtrl` 개체입니다.|  
|[CStatusBar::DrawItem](#drawitem)|소유자 그리기 상태 표시줄 컨트롤의 시각적 측면이 때 호출 됩니다.|  
|[CStatusBar::GetItemID](#getitemid)|지정된 된 인덱스에 대 한 표시기 ID를 가져옵니다.|  
|[CStatusBar::GetItemRect](#getitemrect)|지정된 된 인덱스에 대 한 사각형을 표시 하는 가져옵니다.|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|지정된 된 인덱스에 대 한 표시기 ID, 스타일 및 두께 가져옵니다.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|지정된 된 인덱스에 대 한 표시기 스타일을 가져옵니다.|  
|[CStatusBar::GetPaneText](#getpanetext)|지정된 된 인덱스에 대 한 표시기 텍스트를 가져옵니다.|  
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|기본 공용 컨트롤에 직접 액세스할을 수 있습니다.|  
|[CStatusBar::SetIndicators](#setindicators)|표시기 Id를 설정합니다.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|표시기 ID, 스타일 및 두께 지정 된 인덱스를 설정합니다.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|지정된 된 인덱스에 대 한 표시기 스타일을 설정합니다.|  
|[CStatusBar::SetPaneText](#setpanetext)|지정된 된 인덱스에 대 한 표시기 텍스트를 설정합니다.|  
  
## <a name="remarks"></a>설명  
 일반적으로 출력 창이 상태 표시기와 메시지 줄으로 사용 됩니다. 선택 된 메뉴 명령을 간략하게 설명 하는 메뉴 도움말 메시지 줄 및 SCROLL LOCK, NUM LOCK 및 다른 키의 상태를 나타내는 표시기를 예로 들 수 있습니다.  
  
 [CStatusBar::GetStatusBarCtrl](#getstatusbarctrl), 멤버 함수 새 MFC 4.0 허용 상태 표시줄 사용자 지정 및 추가 기능에 대 한 Windows 공용 컨트롤 지원 기능을 사용할 수 있습니다. `CStatusBar`멤버 함수는 대부분의 Windows 공용 컨트롤; 기능 제공. 그러나 호출 하는 경우 `GetStatusBarCtrl`, 상태 표시줄을 Windows 95/98 상태 표시줄의 특징 중 이상용으로 지정할 수 있습니다. 호출 하는 경우 `GetStatusBarCtrl`에 대 한 참조를 반환 합니다는 `CStatusBarCtrl` 개체입니다. 참조 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Windows 공용 컨트롤을 사용 하 여 도구 모음을 디자인 하는 방법에 대 한 자세한 내용은 합니다. 공용 컨트롤에 대 한 자세한 내용은 참조 하십시오. [공용 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775493) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 프레임 워크 위치 0에 가장 왼쪽에 있는 표시기 배열 표시기 정보를 저장합니다. 상태 표시줄을 만들 때 해당 표시기와 함께 프레임 워크를 연결 하는 Id 문자열의 배열을 사용 합니다. 다음 표시기를 액세스 하는 문자열 ID 또는 인덱스를 사용할 수 있습니다.  
  
 기본적으로 첫 번째 표시기가 "탄력적": 다른 표시기 창에서 사용 하지 않는 상태 표시줄 길이을 차지 하는 다른 창의 오른쪽 맞춤 됩니다.  
  
 상태 표시줄을 만들려면 다음이 단계를 수행 합니다.  
  
1.  `CStatusBar` 개체를 생성합니다.  
  
2.  호출 된 [만들기](#create) (또는 [CreateEx](#createex)) 상태 표시줄 창 만들고에 연결 하는 함수는 `CStatusBar` 개체입니다.  
  
3.  호출 [SetIndicators](#setindicators) 각 표시기로 문자열 ID를 연결 합니다.  
  
 상태 표시줄 창의 텍스트를 업데이트 하는 방법은 세 가지가 있습니다.  
  
1.  호출 [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) 창 0에에서 있는 텍스트를 업데이트 합니다.  
  
2.  호출 [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) 상태 표시줄에 `ON_UPDATE_COMMAND_UI` 처리기입니다.  
  
3.  호출 [SetPaneText](#setpanetext) 모든 창에 대 한 텍스트를 업데이트 합니다.  
  
 호출 [SetPaneStyle](#setpanestyle) 상태 표시줄 창의 스타일을 업데이트 합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CStatusBar`, 문서를 참조 [MFC의 상태 표시줄 구현](../../mfc/status-bar-implementation-in-mfc.md) 및 [Technical Note 31: 컨트롤 막대](../../mfc/tn031-control-bars.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxext.h  
  
##  <a name="commandtoindex"></a>CStatusBar::CommandToIndex  
 Id가 지정 된 ID에 대 한 표시기 인덱스를 가져옵니다.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIDFind`  
 해당 인덱스가 검색 되는 표시기의 문자열 ID입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 표시기의 인덱스 그렇지 않으면-1.  
  
### <a name="remarks"></a>주의  
 첫 번째 표시기의 인덱스는 0입니다.  
  
##  <a name="create"></a>CStatusBar::Create  
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
 상태 표시줄 스타일입니다. 표준 Windows 뿐 아니라 [스타일](../../mfc/reference/window-styles.md), 이러한 스타일은 지원 됩니다.  
  
- `CBRS_TOP`컨트롤 막대 프레임 창의 위쪽에입니다.  
  
- `CBRS_BOTTOM`컨트롤 막대 프레임 창 맨 아래에입니다.  
  
- `CBRS_NOALIGN`부모 크기를 조정할 때 컨트롤 막대 위치가 변경 되지 않습니다.  
  
 `nID`  
 도구 모음의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 또한 초기 글꼴을 설정 하 고 설정 하는 상태 막대의 높이 기본값으로 합니다.  
  
##  <a name="createex"></a>CStatusBar::CreateEx  
 상태 표시줄 (자식 창)을 만들어 사용 하 여 연결 하려면이 함수 호출의 `CStatusBar` 개체입니다.  
  
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
 포함된 된 생성에 대 한 추가 스타일 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) 개체입니다. 크기 조정 그립 또는 도구 설명 없이 상태 표시줄을 지정 하는 기본값을 지원 합니다. 지원 되는 상태 막대 스타일은  
  
- **SBARS_SIZEGRIP** 상태 표시줄 컨트롤 크기 조정 그립 상태 표시줄의 오른쪽 끝에 포함 됩니다. 크기 조정 그립 크기 조정 테두리;에 대해 비슷합니다. 해당 사용자를 클릭 하 고 끌어 부모 창의 크기를 조정할 수 있는 사각형 영역입니다.  
  
- **SBT_TOOLTIPS** 상태 표시줄에서 도구 설명을 지원 합니다.  
  
 이러한 스타일에 대 한 세부 정보를 참조 하십시오. [CStatusBarCtrl에 대 한 설정을](../../mfc/settings-for-the-cstatusbarctrl.md)합니다.  
  
 `dwStyle`  
 상태 표시줄 스타일입니다. 기본 표시 상태 표시줄 프레임 창의 맨 아래에 생성 되도록 지정 합니다. 상태 표시줄에 나열 된 컨트롤 스타일의 조합을 적용 [창 스타일](../../mfc/reference/window-styles.md) 및 [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create)합니다. 그러나이 매개 변수 WS_CHILD 및 WS_VISIBLE 스타일을 항상 포함 되어야 합니다.  
  
 `nID`  
 상태 표시줄의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 함수에서 또한 초기 글꼴을 설정 하 고 상태를 설정에 기본값을 막대의 높이입니다.  
  
 사용 하 여 `CreateEx`, 대신 [만들기](#create)포함 된 상태 표시줄 컨트롤을 만들 때 특정 스타일 있어야 하는 경우. 예를 들어 설정 `dwCtrlStyle` 를 **SBT_TOOLTIPS** 상태 표시줄 개체에서 도구 설명을 표시 하도록 합니다.  
  
##  <a name="cstatusbar"></a>CStatusBar::CStatusBar  
 생성 된 `CStatusBar` 개체, 필요한 경우 기본 상태 표시줄 글꼴 만들고 글꼴 특성을 기본값으로 설정 합니다.  
  
```  
CStatusBar();
```  
  
##  <a name="drawitem"></a>CStatusBar::DrawItem  
 이 멤버 함수는 소유자가 그린 상태 표시줄이 변경의 시각적 측면이 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) 드로잉 필요한의 종류에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>주의  
 **itemAction** 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업을 수행 하는 것입니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CStatusBar` 개체입니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 `lpDrawItemStruct` 이 멤버 함수 종료 전에 합니다.  
  
##  <a name="getitemid"></a>CStatusBar::GetItemID  
 로 지정 된 표시기의 ID를 반환 `nIndex`합니다.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 검색할 ID가 있는 표시기의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 ID에서 지정한 표시기의 `nIndex`합니다.  
  
##  <a name="getitemrect"></a>CStatusBar::GetItemRect  
 복사로 지정 된 표시기의 좌표 `nIndex` 에서 가리키는 구조에 `lpRect`합니다.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스를 검색할 수 있는 사각형 좌표는 표시기입니다.  
  
 `lpRect`  
 가리키는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 표시기로 지정 된 좌표를 받게 될 개체입니다 `nIndex`합니다.  
  
### <a name="remarks"></a>설명  
 좌표는 픽셀 상태 표시줄의 왼쪽 위 모퉁이가 기준입니다.  
  
##  <a name="getpaneinfo"></a>CStatusBar::GetPaneInfo  
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
 인덱스를 검색할 수 있는 정보는 창입니다.  
  
 `nID`  
 에 대 한 참조는 **UINT** 창의 ID로 설정 된 합니다.  
  
 `nStyle`  
 에 대 한 참조는 **UINT** 창 스타일으로 설정 되어 있는 합니다.  
  
 `cxWidth`  
 창의 너비를 설정 하는 정수에 대 한 참조입니다.  
  
##  <a name="getpanestyle"></a>CStatusBar::GetPaneStyle  
 상태 표시줄의 창 스타일을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스를 검색할 수 있는 스타일은 창입니다.  
  
### <a name="return-value"></a>반환 값  
 로 지정 된 상태 표시줄 창 스타일 `nIndex`합니다.  
  
### <a name="remarks"></a>설명  
 창의 스타일 창에서 표시 되는 방식을 결정 합니다.  
  
 상태 표시줄에서 사용할 수 있는 스타일의 목록이 참조 [만들기](#create)합니다.  
  
##  <a name="getpanetext"></a>CStatusBar::GetPaneText  
 상태 표시줄 창에 나타나는 텍스트를 검색 하려면이 함수를 호출 합니다.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스를 검색할 수 있는 텍스트는 창입니다.  
  
 `rString`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 검색할 텍스트를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CString` 창의 텍스트를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버에 두 번째 형태 채우기 함수는 `CString` 문자열 텍스트와 함께 개체입니다.  
  
##  <a name="getstatusbarctrl"></a>CStatusBar::GetStatusBarCtrl  
 이 멤버 함수에는 기본 공용 컨트롤에 직접 액세스할을 수 있습니다.  
  
```  
CStatusBarCtrl& GetStatusBarCtrl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조를 포함 한 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `GetStatusBarCtrl` Windows 상태 표시줄 공통 컨트롤의 기능을 활용 하 고는 지원의 이용 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) 상태 표시줄의 사용자 지정에 대 한 제공 합니다. 예를 들어, 공용 컨트롤을 사용 하 여 상태 표시줄에 크기 조정 그립을 포함 하는 스타일을 지정할 수 있습니다 또는 부모 창의 클라이언트 영역의 맨 위에 표시 상태 표시줄을 스타일을 지정할 수 있습니다.  
  
 공용 컨트롤에 대 한 자세한 내용은 참조 하십시오. [공용 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775493) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setindicators"></a>CStatusBar::SetIndicators  
 각 표시기의 ID를 배열의 해당 요소에 지정 된 값으로 설정 `lpIDArray`, 각 ID에 의해 지정 된 문자열 리소스를 로드 하 고 표시기의 텍스트를 문자열로 설정 합니다.  
  
```  
BOOL SetIndicators(
    const UINT* lpIDArray,  
    int nIDCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpIDArray`  
 Id의 배열에 대 한 포인터입니다.  
  
 `nIDCount`  
 가 가리키는 배열의 요소 수가 `lpIDArray`합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="setpaneinfo"></a>CStatusBar::SetPaneInfo  
 새 ID, 스타일 및 두께를 지정 된 표시기 창의 설정합니다.  
  
```  
void SetPaneInfo(
    int nIndex,  
    UINT nID,  
    UINT nStyle,  
    int cxWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 설정할 스타일은 표시기 창의의 인덱스입니다.  
  
 `nID`  
 표시기 창에 대 한 새 ID입니다.  
  
 `nStyle`  
 표시기 창에 대 한 새 스타일입니다.  
  
 `cxWidth`  
 표시기 창에 대 한 새 너비입니다.  
  
### <a name="remarks"></a>주의  
 다음과 같은 표시기 스타일 지원 됩니다.  
  
- **SBPS_NOBORDERS** 창 주위에 3 차원 테두리 없음.  
  
- **SBPS_POPOUT** 역방향 테두리를 텍스트 "나옵니다."  
  
- **SBPS_DISABLED** 텍스트를 그리지 않습니다.  
  
- **SBPS_STRETCH** 스트레치 창 사용 하지 않는 공간을 채웁니다. 상태 표시줄 당 하나의 창에는이 스타일이 있을 수 있습니다.  
  
- **SBPS_NORMAL** 없거나 스트레치, 테두리, 팝아웃 합니다.  
  
##  <a name="setpanestyle"></a>CStatusBar::SetPaneStyle  
 상태 표시줄의 창 스타일을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
void SetPaneStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 창 스타일 설정 되어야 하는 인덱스입니다.  
  
 `nStyle`  
 스타일 스타일 설정 되어야 하는 창입니다.  
  
### <a name="remarks"></a>주의  
 창의 스타일 창에서 표시 되는 방식을 결정 합니다.  
  
 상태 표시줄에서 사용할 수 있는 스타일의 목록이 참조 [SetPaneInfo](#setpaneinfo)합니다.  
  
##  <a name="setpanetext"></a>CStatusBar::SetPaneText  
 가 가리키는 문자열에 창 텍스트를 설정 하려면이 함수를 호출 `lpszNewText`합니다.  
  
```  
BOOL SetPaneText(
    int nIndex,  
    LPCTSTR lpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스 설정 되어야 하는 텍스트가 있는 창입니다.  
  
 `lpszNewText`  
 새 창 텍스트에 대 한 포인터입니다.  
  
 *b 업데이트*  
 경우 **TRUE**, 창에서 텍스트 설정 된 후 무효화 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 호출한 후 `SetPaneText`, 상태 표시줄에 새 텍스트를 표시 하려면 UI 업데이트 처리기를 추가 해야 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView # 176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView # 177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView # 178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CTRLBARS](../../visual-cpp-samples.md)   
 [MFC 샘플 DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl 클래스](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar 클래스](../../mfc/reference/ccontrolbar-class.md)

