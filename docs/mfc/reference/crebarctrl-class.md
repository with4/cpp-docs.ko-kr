---
title: CReBarCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CReBarCtrl
- AFXCMN/CReBarCtrl
- AFXCMN/CReBarCtrl::CReBarCtrl
- AFXCMN/CReBarCtrl::BeginDrag
- AFXCMN/CReBarCtrl::Create
- AFXCMN/CReBarCtrl::CreateEx
- AFXCMN/CReBarCtrl::DeleteBand
- AFXCMN/CReBarCtrl::DragMove
- AFXCMN/CReBarCtrl::EndDrag
- AFXCMN/CReBarCtrl::GetBandBorders
- AFXCMN/CReBarCtrl::GetBandCount
- AFXCMN/CReBarCtrl::GetBandInfo
- AFXCMN/CReBarCtrl::GetBandMargins
- AFXCMN/CReBarCtrl::GetBarHeight
- AFXCMN/CReBarCtrl::GetBarInfo
- AFXCMN/CReBarCtrl::GetBkColor
- AFXCMN/CReBarCtrl::GetColorScheme
- AFXCMN/CReBarCtrl::GetDropTarget
- AFXCMN/CReBarCtrl::GetExtendedStyle
- AFXCMN/CReBarCtrl::GetImageList
- AFXCMN/CReBarCtrl::GetPalette
- AFXCMN/CReBarCtrl::GetRect
- AFXCMN/CReBarCtrl::GetRowCount
- AFXCMN/CReBarCtrl::GetRowHeight
- AFXCMN/CReBarCtrl::GetTextColor
- AFXCMN/CReBarCtrl::GetToolTips
- AFXCMN/CReBarCtrl::HitTest
- AFXCMN/CReBarCtrl::IDToIndex
- AFXCMN/CReBarCtrl::InsertBand
- AFXCMN/CReBarCtrl::MaximizeBand
- AFXCMN/CReBarCtrl::MinimizeBand
- AFXCMN/CReBarCtrl::MoveBand
- AFXCMN/CReBarCtrl::PushChevron
- AFXCMN/CReBarCtrl::RestoreBand
- AFXCMN/CReBarCtrl::SetBandInfo
- AFXCMN/CReBarCtrl::SetBandWidth
- AFXCMN/CReBarCtrl::SetBarInfo
- AFXCMN/CReBarCtrl::SetBkColor
- AFXCMN/CReBarCtrl::SetColorScheme
- AFXCMN/CReBarCtrl::SetExtendedStyle
- AFXCMN/CReBarCtrl::SetImageList
- AFXCMN/CReBarCtrl::SetOwner
- AFXCMN/CReBarCtrl::SetPalette
- AFXCMN/CReBarCtrl::SetTextColor
- AFXCMN/CReBarCtrl::SetToolTips
- AFXCMN/CReBarCtrl::SetWindowTheme
- AFXCMN/CReBarCtrl::ShowBand
- AFXCMN/CReBarCtrl::SizeToRect
dev_langs:
- C++
helpviewer_keywords:
- CReBarCtrl [MFC], CReBarCtrl
- CReBarCtrl [MFC], BeginDrag
- CReBarCtrl [MFC], Create
- CReBarCtrl [MFC], CreateEx
- CReBarCtrl [MFC], DeleteBand
- CReBarCtrl [MFC], DragMove
- CReBarCtrl [MFC], EndDrag
- CReBarCtrl [MFC], GetBandBorders
- CReBarCtrl [MFC], GetBandCount
- CReBarCtrl [MFC], GetBandInfo
- CReBarCtrl [MFC], GetBandMargins
- CReBarCtrl [MFC], GetBarHeight
- CReBarCtrl [MFC], GetBarInfo
- CReBarCtrl [MFC], GetBkColor
- CReBarCtrl [MFC], GetColorScheme
- CReBarCtrl [MFC], GetDropTarget
- CReBarCtrl [MFC], GetExtendedStyle
- CReBarCtrl [MFC], GetImageList
- CReBarCtrl [MFC], GetPalette
- CReBarCtrl [MFC], GetRect
- CReBarCtrl [MFC], GetRowCount
- CReBarCtrl [MFC], GetRowHeight
- CReBarCtrl [MFC], GetTextColor
- CReBarCtrl [MFC], GetToolTips
- CReBarCtrl [MFC], HitTest
- CReBarCtrl [MFC], IDToIndex
- CReBarCtrl [MFC], InsertBand
- CReBarCtrl [MFC], MaximizeBand
- CReBarCtrl [MFC], MinimizeBand
- CReBarCtrl [MFC], MoveBand
- CReBarCtrl [MFC], PushChevron
- CReBarCtrl [MFC], RestoreBand
- CReBarCtrl [MFC], SetBandInfo
- CReBarCtrl [MFC], SetBandWidth
- CReBarCtrl [MFC], SetBarInfo
- CReBarCtrl [MFC], SetBkColor
- CReBarCtrl [MFC], SetColorScheme
- CReBarCtrl [MFC], SetExtendedStyle
- CReBarCtrl [MFC], SetImageList
- CReBarCtrl [MFC], SetOwner
- CReBarCtrl [MFC], SetPalette
- CReBarCtrl [MFC], SetTextColor
- CReBarCtrl [MFC], SetToolTips
- CReBarCtrl [MFC], SetWindowTheme
- CReBarCtrl [MFC], ShowBand
- CReBarCtrl [MFC], SizeToRect
ms.assetid: 154570d7-e48c-425d-8c7e-c64542bcb4cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e595db4e194744ce5d1f1d644a55423c1022fc2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="crebarctrl-class"></a>CReBarCtrl 클래스
자식 창의 컨테이너인 rebar 컨트롤의 기능을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CReBarCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CReBarCtrl::CReBarCtrl](#crebarctrl)|`CReBarCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CReBarCtrl::BeginDrag](#begindrag)|끌어서 놓기 모드로 rebar 컨트롤을 배치합니다.|  
|[CReBarCtrl::Create](#create)|Rebar 컨트롤을 만들고에 연결 된 `CReBarCtrl` 개체입니다.|  
|[CReBarCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 rebar 컨트롤을 만들고에 연결 된 `CReBarCtrl` 개체입니다.|  
|[CReBarCtrl::DeleteBand](#deleteband)|Rebar 컨트롤에서 밴드를 삭제합니다.|  
|[CReBarCtrl::DragMove](#dragmove)|Rebar 컨트롤에서 끌어서 위치에 대 한 호출 후 업데이트 `BeginDrag`합니다.|  
|[CReBarCtrl::EndDrag](#enddrag)|Rebar 컨트롤의 끌어서 놓기 작업을 종료합니다.|  
|[CReBarCtrl::GetBandBorders](#getbandborders)|밴드의 테두리를 검색합니다.|  
|[CReBarCtrl::GetBandCount](#getbandcount)|Rebar 컨트롤의 현재 밴드의 수를 검색 합니다.|  
|[CReBarCtrl::GetBandInfo](#getbandinfo)|Rebar 컨트롤에서 지정된 된 밴드에 대 한 정보를 검색합니다.|  
|[CReBarCtrl::GetBandMargins](#getbandmargins)|밴드의 여백을 검색합니다.|  
|[CReBarCtrl::GetBarHeight](#getbarheight)|Rebar 컨트롤의 높이 검색합니다.|  
|[CReBarCtrl::GetBarInfo](#getbarinfo)|사용 하 여 이미지 목록과 rebar 컨트롤에 대 한 정보를 검색 합니다.|  
|[CReBarCtrl::GetBkColor](#getbkcolor)|Rebar 컨트롤의 기본 배경색을 검색합니다.|  
|[CReBarCtrl::GetColorScheme](#getcolorscheme)|검색 된 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) rebar 컨트롤와 연결 된 구조입니다.|  
|[CReBarCtrl::GetDropTarget](#getdroptarget)|Rebar 컨트롤의 검색 `IDropTarget` 인터페이스 포인터입니다.|  
|[CReBarCtrl::GetExtendedStyle](#getextendedstyle)|현재 rebar 컨트롤의 확장된 스타일을 가져옵니다.|  
|[CReBarCtrl::GetImageList](#getimagelist)|Rebar 컨트롤에 연결 된 이미지 목록을 검색 합니다.|  
|[CReBarCtrl::GetPalette](#getpalette)|Rebar 컨트롤의 현재 팔레트를 검색합니다.|  
|[CReBarCtrl::GetRect](#getrect)|Rebar 컨트롤에서 특정된 밴드에 대 한 경계 사각형을 검색 합니다.|  
|[CReBarCtrl::GetRowCount](#getrowcount)|Rebar 컨트롤의 밴드 행 수를 검색합니다.|  
|[CReBarCtrl::GetRowHeight](#getrowheight)|Rebar 컨트롤의 지정된 된 행의 높이 검색합니다.|  
|[CReBarCtrl::GetTextColor](#gettextcolor)|Rebar 컨트롤의 기본 텍스트 색을 검색합니다.|  
|[CReBarCtrl::GetToolTips](#gettooltips)|Rebar 컨트롤에 연결 된 모든 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|  
|[CReBarCtrl::HitTest](#hittest)|Rebar 밴드는 해당 시점에 존재 하는 경우 화면에 지정 된 시점 rebar 밴드의 부분 인지 확인 합니다.|  
|[CReBarCtrl::IDToIndex](#idtoindex)|Rebar 컨트롤에서 밴드 인덱스 밴드 식별자 (ID)으로 변환합니다.|  
|[CReBarCtrl::InsertBand](#insertband)|Rebar 컨트롤에서 새 밴드를 삽입합니다.|  
|[CReBarCtrl::MaximizeBand](#maximizeband)|최대 크기로 rebar 컨트롤에서 밴드를 조정합니다.|  
|[CReBarCtrl::MinimizeBand](#minimizeband)|가장 작은 크기로 rebar 컨트롤에서 밴드를 조정합니다.|  
|[CReBarCtrl::MoveBand](#moveband)|인덱스 한 개에서 밴드를 다른 위치로 이동 합니다.|  
|[CReBarCtrl::PushChevron](#pushchevron)|프로그래밍 방식으로 갈매기형을 푸시합니다.|  
|[CReBarCtrl::RestoreBand](#restoreband)|이상적인 크기를 rebar 컨트롤에서 밴드를 조정합니다.|  
|[CReBarCtrl::SetBandInfo](#setbandinfo)|Rebar 컨트롤에서 기존 밴드의 특성을 설정합니다.|  
|[CReBarCtrl::SetBandWidth](#setbandwidth)|현재는 rebar 컨트롤에서 지정 된 도킹된 대역의 너비를 설정합니다.|  
|[CReBarCtrl::SetBarInfo](#setbarinfo)|Rebar 컨트롤의 특성을 설정합니다.|  
|[CReBarCtrl::SetBkColor](#setbkcolor)|Rebar 컨트롤의 기본 배경색을 설정합니다.|  
|[CReBarCtrl::SetColorScheme](#setcolorscheme)|Rebar 컨트롤에 단추에 대 한 색 구성표를 설정합니다.|  
|[CReBarCtrl::SetExtendedStyle](#setextendedstyle)|현재 rebar 컨트롤에 대 한 확장된 스타일을 설정합니다.|  
|[CReBarCtrl::SetImageList](#setimagelist)|Rebar 컨트롤의 이미지 목록을 설정합니다.|  
|[CReBarCtrl::SetOwner](#setowner)|Rebar 컨트롤의 소유자 창이 설정합니다.|  
|[CReBarCtrl::SetPalette](#setpalette)|Rebar 컨트롤의 현재 색상표를 설정합니다.|  
|[CReBarCtrl::SetTextColor](#settextcolor)|Rebar 컨트롤의 기본 텍스트 색을 설정합니다.|  
|[CReBarCtrl::SetToolTips](#settooltips)|Rebar 컨트롤 도구 설명 컨트롤에 연결합니다.|  
|[CReBarCtrl::SetWindowTheme](#setwindowtheme)|Rebar 컨트롤의 비주얼 스타일을 설정합니다.|  
|[CReBarCtrl::ShowBand](#showband)|표시 하거나 rebar 컨트롤에서 주어진된 밴드를 숨깁니다.|  
|[CReBarCtrl::SizeToRect](#sizetorect)|지정된 된 사각형을 rebar 컨트롤에 맞춥니다.|  
  
## <a name="remarks"></a>설명  
 Rebar 컨트롤 상주 하는 응용 프로그램을 rebar 밴드 rebar 컨트롤에 포함 된 자식 창에 할당 합니다. 자식 창에는 일반적으로 다른 일반적인 컨트롤입니다.  
  
 Rebar 컨트롤 하나 이상의 밴드를 포함합니다. 각 밴드에는 그리퍼 막대, 비트맵, 텍스트 레이블 및 자식 창의 조합을 포함할 수 있습니다. 밴드에는 이러한 각 항목 중 하나만 포함할 수 있습니다.  
  
 Rebar 컨트롤을 통해 지정 된 배경 비트맵 자식이 창을 표시할 수 있습니다. 모든 rebar 컨트롤 밴드 크기를 조정할 수를 사용 하는 제외 하 고는 **RBBS_FIXEDSIZE** 스타일입니다. Rebar 컨트롤 밴드의 크기를 조정 하거나 위치를 변경할 때는 rebar 컨트롤 크기와 해당 밴드에 할당 된 자식 창의 위치를 관리 합니다. 을 크기를 조정 하거나 컨트롤 내에서 밴드의 순서를 변경 하려면 누르고 밴드의 그리퍼 막대를 끌어 옵니다.  
  
 다음 그림은 3 개의 밴드가 있는 rebar 컨트롤을 보여 줍니다.  
  
-   0 대역 외 플랫, 투명 한 도구 모음 컨트롤을 포함합니다.  
  
-   대역 외 1 모두 투명 하 게 표준 및 투명 드롭다운 단추가 있습니다.  
  
-   대역 외 2 콤보 상자 및 표준 단추 4 개를 포함합니다.  
  
     ![Rebar 메뉴의 예제](../../mfc/reference/media/vc4scc1.gif "vc4scc1")  
  
## <a name="rebar-control"></a>Rebar 컨트롤  
 Rebar 컨트롤 지원:  
  
-   이미지를 나열합니다.  
  
-   메시지 처리 합니다.  
  
-   사용자 지정 그리기 기능입니다.  
  
-   다양 한 표준 창 스타일 이외에도 컨트롤 스타일입니다. 이러한 스타일의 목록을 보려면 참조 [Rebar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774377) Windows sdk에서입니다.  
  
 자세한 내용은 참조 [CReBarCtrl 사용 하 여](../../mfc/using-crebarctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CReBarCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="begindrag"></a>  CReBarCtrl::BeginDrag  
 Win32 메시지의 동작을 구현 [RB_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774429)Windows SDK에 설명 된 대로 합니다.  
  
```  
void BeginDrag(
    UINT uBand,  
    DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 끌어서 놓기 작업이 영향을 주는 밴드의 0부터 시작 인덱스입니다.  
  
 `dwPos`  
 A `DWORD` 시작 마우스 좌표를 포함 하는 값입니다. 세로 좌표는 HIWORD에 포함 된 및 가로 좌표는 LOWORD에 포함 되어 있습니다. 전달 하는 경우 `(DWORD)-1`, rebar 컨트롤은 마지막으로 호출 하는 컨트롤의 스레드에 마우스의 상대 위치를 사용 하는 **GetMessage** 또는 **PeekMessage**합니다.  
  
##  <a name="create"></a>  CReBarCtrl::Create  
 Rebar 컨트롤을 만들고에 연결 된 `CReBarCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 컨트롤에 적용 되는 rebar 컨트롤 스타일의 조합을 지정 합니다. 참조 [Rebar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774377) 지원 되는 스타일 목록을 Windows sdk입니다.  
  
 `rect`  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) rebar 컨트롤의 크기와 위치는 구조입니다.  
  
 `pParentWnd`  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 개체 rebar 컨트롤의 부모 창입니다. 않아야 **NULL**합니다.  
  
 `nID`  
 Rebar 컨트롤의 컨트롤 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 성공적으로 만들어진 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 Rebar 컨트롤을 두 단계로 만듭니다.  
  
1.  호출 [CReBarCtrl](#crebarctrl) 생성 하는 `CReBarCtrl` 개체입니다.  
  
2.  Windows rebar 컨트롤을 만들고에 연결 하는이 멤버 함수 호출의 `CReBarCtrl` 개체입니다.  
  
 호출 하는 경우 **만들기**, 공용 컨트롤은 초기화 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#3](../../mfc/reference/codesnippet/cpp/crebarctrl-class_1.cpp)]  
  
##  <a name="createex"></a>  CReBarCtrl::CreateEx  
 에 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CReBarCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 `dwStyle`  
 컨트롤에 적용 되는 rebar 컨트롤 스타일의 조합을 지정 합니다. 지원 되는 스타일의 목록이 참조 [Rebar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774377) Windows sdk에서입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_** 합니다.  
  
##  <a name="crebarctrl"></a>  CReBarCtrl::CReBarCtrl  
 
          `CReBarCtrl` 개체를 만듭니다.  
  
```  
CReBarCtrl();
```  
  
### <a name="example"></a>예제  
  예를 참조 [CReBarCtrl::Create](#create)합니다.  
  
##  <a name="deleteband"></a>  CReBarCtrl::DeleteBand  
 Win32 메시지의 동작을 구현 [RB_DELETEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774431)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL DeleteBand(UINT uBand);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 삭제할 밴드의 0부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 밴드 성공적으로 삭제 한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#4](../../mfc/reference/codesnippet/cpp/crebarctrl-class_2.cpp)]  
  
##  <a name="dragmove"></a>  CReBarCtrl::DragMove  
 Win32 메시지의 동작을 구현 [RB_DRAGMOVE](https://msdn.microsoft.com/library/bb774433.aspx)Windows SDK에 설명 된 대로 합니다.  
  
```  
void DragMove(DWORD dwPos = (DWORD)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwPos`  
 A `DWORD` 새 마우스 좌표를 포함 하는 값입니다. 세로 좌표는 HIWORD에 포함 된 및 가로 좌표는 LOWORD에 포함 되어 있습니다. 전달 하는 경우 `(DWORD)-1`, rebar 컨트롤은 마지막으로 호출 하는 컨트롤의 스레드에 마우스의 상대 위치를 사용 하는 **GetMessage** 또는 **PeekMessage**합니다.  
  
##  <a name="enddrag"></a>  CReBarCtrl::EndDrag  
 Win32 메시지의 동작을 구현 [RB_ENDDRAG](http://msdn.microsoft.com/library/windows/desktop/bb774435)Windows SDK에 설명 된 대로 합니다.  
  
```  
void EndDrag();
```  
  
##  <a name="getbandborders"></a>  CReBarCtrl::GetBandBorders  
 Win32 메시지의 동작을 구현 [RB_GETBANDBORDERS](http://msdn.microsoft.com/library/windows/desktop/bb774437)Windows SDK에 설명 된 대로 합니다.  
  
```  
void GetBandBorders(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 테두리 검색할 수는 밴드의 0부터 시작 인덱스입니다.  
  
 `prc`  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 대역 외 테두리를 받게 됩니다. Rebar 컨트롤에 있는 경우는 **RBS_BANDBORDERS** 스타일을이 구조체의 각 멤버의 픽셀의 밴드를 해당 측에 테두리를 구성 하는 수를 받게 됩니다. Rebar 컨트롤에 없는 경우는 **RBS_BANDBORDERS** 스타일에이 구조체의 왼쪽된 멤버 유효한 정보를 받습니다. Rebar 컨트롤 스타일에 대 한 참조 [Rebar 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774377) Windows sdk에서입니다.  
  
##  <a name="getbandcount"></a>  CReBarCtrl::GetBandCount  
 Win32 메시지의 동작을 구현 [RB_GETBANDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774439)Windows SDK에 설명 된 대로 합니다.  
  
```  
UINT GetBandCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤에 할당 되는 밴드의 수입니다.  
  
##  <a name="getbandinfo"></a>  CReBarCtrl::GetBandInfo  
 Win32 메시지의 동작을 구현 [RB_GETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774451) Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL GetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 정보 검색할 수는 밴드의 0부터 시작 인덱스입니다.  
  
 `prbbi`  
 에 대 한 포인터는 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) 구조 밴드 정보를 얻습니다. 설정 해야 합니다는 `cbSize` 이 구조체의 멤버 `sizeof(REBARBANDINFO)` 설정 하 고는 **fMask** 이 메시지를 보내기 전에 검색 하려는 항목에는 멤버입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="getbandmargins"></a>  CReBarCtrl::GetBandMargins  
 밴드의 여백을 검색합니다.  
  
```  
void GetBandMargins(PMARGINS pMargins);
```  
  
### <a name="parameters"></a>매개 변수  
 *pMargins*  
 에 대 한 포인터는 [여백](http://msdn.microsoft.com/library/windows/desktop/bb773244)구조 정보를 받을입니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 [RB_GETBANDMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb774453) Windows SDK에 설명 된 대로 메시지입니다.  
  
##  <a name="getbarheight"></a>  CReBarCtrl::GetBarHeight  
 Rebar 막대의 높이 검색합니다.  
  
```  
UINT GetBarHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 높이 컨트롤의 픽셀 단위로 나타내는 값입니다.  
  
##  <a name="getbarinfo"></a>  CReBarCtrl::GetBarInfo  
 Win32 메시지의 동작을 구현 [RB_GETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774457)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL GetBarInfo(REBARINFO* prbi) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `prbi`  
 에 대 한 포인터는 [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) 구조 rebar 컨트롤 정보를 받을 수입니다. 설정 해야 합니다는 `cbSize` 이 구조의 소속 `sizeof(REBARINFO)` 이 메시지를 보내기 전에 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="getbkcolor"></a>  CReBarCtrl::GetBkColor  
 Win32 메시지의 동작을 구현 [RB_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774459)Windows SDK에 설명 된 대로 합니다.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 현재 기본 배경색을 나타내는 값입니다.  
  
##  <a name="getcolorscheme"></a>  CReBarCtrl::GetColorScheme  
 검색 된 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) rebar 컨트롤에 대 한 구조입니다.  
  
```  
BOOL GetColorScheme(COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpcs`  
 에 대 한 포인터는 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Windows SDK에 설명 된 대로 구성 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 **COLORSCHEME** 단추 강조 색 및 단추 그림자 색 구조에 포함 됩니다.  
  
##  <a name="getdroptarget"></a>  CReBarCtrl::GetDropTarget  
 Win32 메시지의 동작을 구현 [RB_GETDROPTARGET](http://msdn.microsoft.com/library/windows/desktop/bb774463)Windows SDK에 설명 된 대로 합니다.  
  
```  
IDropTarget* GetDropTarget() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679) 인터페이스입니다.  
  
##  <a name="getextendedstyle"></a>  CReBarCtrl::GetExtendedStyle  
 현재 rebar 컨트롤의 확장된 스타일을 가져옵니다.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 확장된 스타일을 나타내는 플래그의 비트 조합 (OR)입니다. 가능한 플래그는 `RBS_EX_SPLITTER` 및 `RBS_EX_TRANSPARENT`합니다. 자세한 내용은 참조는 `dwMask` 의 매개 변수는 [CReBarCtrl::SetExtendedStyle](#setextendedstyle) 메서드.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [RB_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774433) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getimagelist"></a>  CReBarCtrl::GetImageList  
 가져옵니다는 `CImageList` rebar 컨트롤에 연결 된 개체입니다.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다. 반환 **NULL** 이미지 목록이 없는 컨트롤에 대해 설정 된 경우.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수에 저장 된 크기와 마스크 정보를 사용 하는 [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) Windows SDK에 설명 된 대로 구성 합니다.  
  
##  <a name="getpalette"></a>  CReBarCtrl::GetPalette  
 Rebar 컨트롤의 현재 팔레트를 검색합니다.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CPalette](../../mfc/reference/cpalette-class.md) rebar 컨트롤의 현재 색상표를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 사용 하는 `CPalette` 개체의 반환 값으로 아닌 `HPALETTE`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#5](../../mfc/reference/codesnippet/cpp/crebarctrl-class_3.cpp)]  
  
##  <a name="getrect"></a>  CReBarCtrl::GetRect  
 Win32 메시지의 동작을 구현 [RB_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb774469)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL GetRect(
    UINT uBand,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 Rebar 컨트롤에서 밴드의 0부터 시작 인덱스입니다.  
  
 `prc`  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 rebar 밴드의 경계를 받게 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#6](../../mfc/reference/codesnippet/cpp/crebarctrl-class_4.cpp)]  
  
##  <a name="getrowcount"></a>  CReBarCtrl::GetRowCount  
 Win32 메시지의 동작을 구현 [RB_GETROWCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774471)Windows SDK에 설명 된 대로 합니다.  
  
```  
UINT GetRowCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **UINT** 컨트롤의 밴드 행의 수를 나타내는 값입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#7](../../mfc/reference/codesnippet/cpp/crebarctrl-class_5.cpp)]  
  
##  <a name="getrowheight"></a>  CReBarCtrl::GetRowHeight  
 Win32 메시지의 동작을 구현 [RB_GETROWHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb774473)Windows SDK에 설명 된 대로 합니다.  
  
```  
UINT GetRowHeight(UINT uRow) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *uRow*  
 검색 된 높이 대 한 대역 외의 0부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 A **UINT** 행 높이 픽셀 단위로 나타내는 값입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#8](../../mfc/reference/codesnippet/cpp/crebarctrl-class_6.cpp)]  
  
##  <a name="gettextcolor"></a>  CReBarCtrl::GetTextColor  
 Win32 메시지의 동작을 구현 [RB_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774475)Windows SDK에 설명 된 대로 합니다.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 현재 기본 텍스트 색을 나타내는 값입니다.  
  
##  <a name="gettooltips"></a>  CReBarCtrl::GetToolTips  
 Win32 메시지의 동작을 구현 [RB_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb774477)Windows SDK에 설명 된 대로 합니다.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체입니다.  
  
### <a name="remarks"></a>설명  
 MFC 구현 `GetToolTips` 반환에 대 한 포인터는 `CToolTipCtrl`, 아닌 `HWND`합니다.  
  
##  <a name="hittest"></a>  CReBarCtrl::HitTest  
 Win32 메시지의 동작을 구현 [RB_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb774494)Windows SDK에 설명 된 대로 합니다.  
  
```  
int HitTest(RBHITTESTINFO* prbht);
```  
  
### <a name="parameters"></a>매개 변수  
 *prbht*  
 에 대 한 포인터는 [RBHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774391) 구조입니다. 메시지를 보내기 전에 **pt** 클라이언트 좌표에서 테스트는 지점으로이 구조체의 멤버를 초기화 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 점을 또는 지점에 없는 rebar 밴드 되었으면-1에서 대역 외의 0부터 시작 하는 인덱스입니다.  
  
##  <a name="idtoindex"></a>  CReBarCtrl::IDToIndex  
 Win32 메시지의 동작을 구현 [RB_IDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774496)Windows SDK에 설명 된 대로 합니다.  
  
```  
int IDToIndex(UINT uBandID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *uBandID*  
 전달 된 지정된 된 밴드의 응용 프로그램 정의 식별자는 **wID** 의 멤버는 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) 밴드를 삽입할 때 구성 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0부터 시작 밴드 인덱스 또는 그렇지 않으면-1입니다. 중복 된 대역 외 인덱스가 존재 하는 경우 첫 번째 반환 됩니다.  
  
##  <a name="insertband"></a>  CReBarCtrl::InsertBand  
 Win32 메시지의 동작을 구현 [RB_INSERTBAND](http://msdn.microsoft.com/library/windows/desktop/bb774498)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL InsertBand(
    UINT uIndex,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>매개 변수  
 *uIndex*  
 밴드를 삽입할 위치의 0부터 시작 인덱스입니다. 이 매개 변수를-1로 설정 하면 컨트롤이 마지막 위치에 새 밴드를 추가 합니다.  
  
 `prbbi`  
 에 대 한 포인터는 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) 삽입할 밴드를 정의 하는 구조입니다. 설정 해야 합니다는 `cbSize` 이 구조의 소속 `sizeof(REBARBANDINFO)` 이 함수를 호출 하기 전에.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#9](../../mfc/reference/codesnippet/cpp/crebarctrl-class_7.cpp)]  
  
##  <a name="maximizeband"></a>  CReBarCtrl::MaximizeBand  
 최대 크기로 rebar 컨트롤에서 밴드를 조정합니다.  
  
```  
void MaximizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 최대화 밴드의 0부터 시작 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 Win32 메시지의 동작을 구현 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) 와 `fIdeal` Windows SDK에 설명 된 대로 0으로 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#10](../../mfc/reference/codesnippet/cpp/crebarctrl-class_8.cpp)]  
  
##  <a name="minimizeband"></a>  CReBarCtrl::MinimizeBand  
 가장 작은 크기로 rebar 컨트롤에서 밴드를 조정합니다.  
  
```  
void MinimizeBand(UINT uBand);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 최소화할 수 밴드의 0부터 시작 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 Win32 메시지의 동작을 구현 [RB_MINIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774502)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#11](../../mfc/reference/codesnippet/cpp/crebarctrl-class_9.cpp)]  
  
##  <a name="moveband"></a>  CReBarCtrl::MoveBand  
 Win32 메시지의 동작을 구현 [RB_MOVEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774504)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL MoveBand(
    UINT uFrom,  
    UINT uTo);
```  
  
### <a name="parameters"></a>매개 변수  
 *uFrom*  
 이동할 밴드의 0부터 시작 인덱스입니다.  
  
 *자동*  
 새 밴드 위치의 0부터 시작 인덱스입니다. 이 매개 변수 값에서 1을 뺀 밴드 수 보다 크면 안 해야 합니다. 밴드의 수를 가져오려면 호출 [GetBandCount](#getbandcount)합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="pushchevron"></a>  CReBarCtrl::PushChevron  
 Win32 메시지의 동작을 구현 [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506)Windows SDK에 설명 된 대로 합니다.  
  
```  
void PushChevron(
    UINT uBand,  
    LPARAM lAppValue);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 밀어넣을 수 있는 펼침 단추는 밴드의 0부터 시작 인덱스입니다.  
  
 `lAppValue`  
 응용 프로그램 정의 32 비트 값입니다. 참조 `lAppValue` 에 [RB_PUSHCHEVRON](http://msdn.microsoft.com/library/windows/desktop/bb774506) in the Windows SDK입니다.  
  
##  <a name="restoreband"></a>  CReBarCtrl::RestoreBand  
 이상적인 크기를 rebar 컨트롤에서 밴드를 조정합니다.  
  
```  
void RestoreBand(UINT uBand);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 최대화 밴드의 0부터 시작 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 Win32 메시지의 동작을 구현 [RB_MAXIMIZEBAND](http://msdn.microsoft.com/library/windows/desktop/bb774500) 와 `fIdeal` Windows SDK에 설명 된 대로 1로 설정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#12](../../mfc/reference/codesnippet/cpp/crebarctrl-class_10.cpp)]  
  
##  <a name="setbandinfo"></a>  CReBarCtrl::SetBandInfo  
 Win32 메시지의 동작을 구현 [RB_SETBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774508)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL SetBandInfo(
    UINT uBand,  
    REBARBANDINFO* prbbi);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 새 설정을 받으려면 대역의 0부터 시작 인덱스입니다.  
  
 `prbbi`  
 에 대 한 포인터는 [REBARBANDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774393) 삽입할 밴드를 정의 하는 구조입니다. 설정 해야 합니다는 `cbSize` 이 구조의 소속 `sizeof(REBARBANDINFO)` 이 메시지를 보내기 전에 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#13](../../mfc/reference/codesnippet/cpp/crebarctrl-class_11.cpp)]  
  
##  <a name="setbandwidth"></a>  CReBarCtrl::SetBandWidth  
 현재는 rebar 컨트롤에서 지정 된 도킹된 대역의 너비를 설정합니다.  
  
```  
BOOL SetBandWidth(
    UINT uBand,   
    int cxWidth);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `uBand`|Rebar 밴드의 0부터 시작 인덱스입니다.|  
|[in] `cxWidth`|Rebar 밴드 (픽셀)에서의 새로운 너비입니다.|  
  
### <a name="return-value"></a>반환 값  
 해당 메서드에 성공하면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [RB_SETBANDWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb774511) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_rebar`, 즉 현재 rebar 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#1](../../mfc/reference/codesnippet/cpp/crebarctrl-class_12.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 각 rebar 밴드 너비를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CReBarCtrl_s1#2](../../mfc/reference/codesnippet/cpp/crebarctrl-class_13.cpp)]  
  
##  <a name="setbarinfo"></a>  CReBarCtrl::SetBarInfo  
 Win32 메시지의 동작을 구현 [RB_SETBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774513)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL SetBarInfo(REBARINFO* prbi);
```  
  
### <a name="parameters"></a>매개 변수  
 `prbi`  
 에 대 한 포인터는 [REBARINFO](http://msdn.microsoft.com/library/windows/desktop/bb774395) 설정 정보가 포함 된 구조체입니다. 설정 해야 합니다는 `cbSize` 이 구조의 소속 `sizeof(REBARINFO)` 이 메시지를 보내기 전에  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CReBarCtrl#14](../../mfc/reference/codesnippet/cpp/crebarctrl-class_14.cpp)]  
  
##  <a name="setbkcolor"></a>  CReBarCtrl::SetBkColor  
 Win32 메시지의 동작을 구현 [RB_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774515)Windows SDK에 설명 된 대로 합니다.  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>매개 변수  
 `clr`  
 **COLORREF** 새 기본 배경색을 나타내는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 이전 기본 배경색을 나타내는 값입니다.  
  
### <a name="remarks"></a>설명  
 배경 색을 설정 하는 시기 및 기본값을 설정 하는 방법에 대 한 자세한 내용은이 항목을 참조 하십시오.  
  
##  <a name="setcolorscheme"></a>  CReBarCtrl::SetColorScheme  
 Rebar 컨트롤에 단추에 대 한 색 구성표를 설정합니다.  
  
```  
void SetColorScheme(const COLORSCHEME* lpcs);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpcs`  
 에 대 한 포인터는 [COLORSCHEME](http://msdn.microsoft.com/library/windows/desktop/bb775502) Windows SDK에 설명 된 대로 구성 합니다.  
  
### <a name="remarks"></a>설명  
 **COLORSCHEME** 단추 강조 색과 단추 그림자 색 구조에 포함 됩니다.  
  
##  <a name="setextendedstyle"></a>  CReBarCtrl::SetExtendedStyle  
 현재 rebar 컨트롤에 대 한 확장된 스타일을 설정합니다.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwMask,   
    DWORD dwStyleEx);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `dwMask`|플래그를 지정 하는 플래그의 비트 조합 (OR)는 `dwStyleEx` 매개 변수가 적용 됩니다. 다음 값 중 하나 이상을 사용 합니다.<br /><br /> RBS_EX_SPLITTER: 기본적으로 표시 하는 분할 아래쪽에 가로 모드에서 마우스 오른쪽 세로 모드에서.<br /><br /> RBS_EX_TRANSPARENT: 전달 된 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) 메시지를 부모 창입니다.|  
|[in] `dwStyleEx`|적용할 스타일을 지정 하는 플래그의 비트 조합 (OR)입니다. 에 사용 되는 동일한 플래그를 지정 된 스타일을 설정 하려면는 `dwMask` 매개 변수입니다. 스타일을 다시 설정 하려면 이진 0을 지정 합니다.|  
  
### <a name="return-value"></a>반환 값  
 이전 확장된 스타일입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [RB_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb774519) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="setimagelist"></a>  CReBarCtrl::SetImageList  
 이미지 목록을 rebar 컨트롤에 할당합니다.  
  
```  
BOOL SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 `pImageList`  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 이미지 목록을 rebar 컨트롤에 할당할 수를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="setowner"></a>  CReBarCtrl::SetOwner  
 Win32 메시지의 동작을 구현 [RB_SETPARENT](http://msdn.microsoft.com/library/windows/desktop/bb774522)Windows SDK에 설명 된 대로 합니다.  
  
```  
CWnd* SetOwner(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 에 대 한 포인터는 `CWnd` rebar 컨트롤의 소유자로 설정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) rebar 컨트롤의 현재 소유자가 있는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수에 대 한 포인터를 사용 한다는 점에 유의 `CWnd` windows로 처리 하는 것이 아니라 rebar 컨트롤의 선택 하 고 현재 소유자에 대 한 개체입니다.  
  
> [!NOTE]
>  이 멤버 함수는 실제 부모 컨트롤이 만들어진; 때 설정한를 변경 하지 않습니다. 대신 지정한 창에 알림 메시지를 보냅니다.  
  
##  <a name="setpalette"></a>  CReBarCtrl::SetPalette  
 Win32 메시지의 동작을 구현 [RB_SETPALETTE](http://msdn.microsoft.com/library/windows/desktop/bb774520)Windows SDK에 설명 된 대로 합니다.  
  
```  
CPalette* SetPalette(HPALETTE hPal);
```  
  
### <a name="parameters"></a>매개 변수  
 *hPal*  
 `HPALETTE` rebar 컨트롤에서 사용할 새 색상표를 지정 하는 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CPalette](../../mfc/reference/cpalette-class.md) rebar 컨트롤의 이전 색상표를 지정 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 사용 하는 `CPalette` 개체의 반환 값으로 아닌 `HPALETTE`합니다.  
  
##  <a name="settextcolor"></a>  CReBarCtrl::SetTextColor  
 Win32 메시지의 동작을 구현 [RB_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774524)Windows SDK에 설명 된 대로 합니다.  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>매개 변수  
 `clr`  
 A **COLORREF** 에 새 텍스트를 나타내는 값 색은 `CReBarCtrl` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 관련 된 이전 텍스트 색을 나타내는 값의 `CReBarCtrl` 개체입니다.  
  
### <a name="remarks"></a>설명  
 Rebar 컨트롤에서 텍스트 색을 유연 하 게 제공 됩니다.  
  
##  <a name="settooltips"></a>  CReBarCtrl::SetToolTips  
 Rebar 컨트롤 도구 설명 컨트롤에 연결합니다.  
  
```  
void SetToolTips(CToolTipCtrl* pToolTip);
```  
  
### <a name="parameters"></a>매개 변수  
 *pToolTip*  
 에 대 한 포인터는 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 개체  
  
### <a name="remarks"></a>설명  
 삭제 해야 합니다는 `CToolTipCtrl` 을 마쳤을 때 개체입니다.  
  
##  <a name="setwindowtheme"></a>  CReBarCtrl::SetWindowTheme  
 Rebar 컨트롤의 비주얼 스타일을 설정합니다.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszSubAppName`  
 설정 하는 rebar 비주얼 스타일을 포함 하는 유니코드 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 [RB_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb774530) Windows SDK에 설명 된 대로 메시지입니다.  
  
##  <a name="showband"></a>  CReBarCtrl::ShowBand  
 Win32 메시지의 동작을 구현 [RB_SHOWBAND](http://msdn.microsoft.com/library/windows/desktop/bb774532)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL ShowBand(
    UINT uBand,  
    BOOL fShow = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `uBand`  
 Rebar 컨트롤에서 밴드의 0부터 시작 인덱스입니다.  
  
 *fShow*  
 밴드를 표시 하거나 숨길 해야 하는 경우를 나타냅니다. 이 값이 **TRUE**, 밴드를 표시 합니다. 그렇지 않으면 밴드는 표시 되지 것입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="sizetorect"></a>  CReBarCtrl::SizeToRect  
 Win32 메시지의 동작을 구현 [RB_SIZETORECT](http://msdn.microsoft.com/library/windows/desktop/bb774534)Windows SDK에 설명 된 대로 합니다.  
  
```  
BOOL SizeToRect(CRect& rect);
```  
  
### <a name="parameters"></a>매개 변수  
 `rect`  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 를 rebar 컨트롤 크기를 조정 하는 사각형을 지정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 사용 하는 `CRect` 개체를 매개 변수로 아닌 `RECT` 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)


