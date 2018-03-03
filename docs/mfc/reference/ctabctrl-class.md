---
title: "CTabCtrl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabCtrl
- AFXCMN/CTabCtrl
- AFXCMN/CTabCtrl::CTabCtrl
- AFXCMN/CTabCtrl::AdjustRect
- AFXCMN/CTabCtrl::Create
- AFXCMN/CTabCtrl::CreateEx
- AFXCMN/CTabCtrl::DeleteAllItems
- AFXCMN/CTabCtrl::DeleteItem
- AFXCMN/CTabCtrl::DeselectAll
- AFXCMN/CTabCtrl::DrawItem
- AFXCMN/CTabCtrl::GetCurFocus
- AFXCMN/CTabCtrl::GetCurSel
- AFXCMN/CTabCtrl::GetExtendedStyle
- AFXCMN/CTabCtrl::GetImageList
- AFXCMN/CTabCtrl::GetItem
- AFXCMN/CTabCtrl::GetItemCount
- AFXCMN/CTabCtrl::GetItemRect
- AFXCMN/CTabCtrl::GetItemState
- AFXCMN/CTabCtrl::GetRowCount
- AFXCMN/CTabCtrl::GetToolTips
- AFXCMN/CTabCtrl::HighlightItem
- AFXCMN/CTabCtrl::HitTest
- AFXCMN/CTabCtrl::InsertItem
- AFXCMN/CTabCtrl::RemoveImage
- AFXCMN/CTabCtrl::SetCurFocus
- AFXCMN/CTabCtrl::SetCurSel
- AFXCMN/CTabCtrl::SetExtendedStyle
- AFXCMN/CTabCtrl::SetImageList
- AFXCMN/CTabCtrl::SetItem
- AFXCMN/CTabCtrl::SetItemExtra
- AFXCMN/CTabCtrl::SetItemSize
- AFXCMN/CTabCtrl::SetItemState
- AFXCMN/CTabCtrl::SetMinTabWidth
- AFXCMN/CTabCtrl::SetPadding
- AFXCMN/CTabCtrl::SetToolTips
dev_langs:
- C++
helpviewer_keywords:
- CTabCtrl [MFC], CTabCtrl
- CTabCtrl [MFC], AdjustRect
- CTabCtrl [MFC], Create
- CTabCtrl [MFC], CreateEx
- CTabCtrl [MFC], DeleteAllItems
- CTabCtrl [MFC], DeleteItem
- CTabCtrl [MFC], DeselectAll
- CTabCtrl [MFC], DrawItem
- CTabCtrl [MFC], GetCurFocus
- CTabCtrl [MFC], GetCurSel
- CTabCtrl [MFC], GetExtendedStyle
- CTabCtrl [MFC], GetImageList
- CTabCtrl [MFC], GetItem
- CTabCtrl [MFC], GetItemCount
- CTabCtrl [MFC], GetItemRect
- CTabCtrl [MFC], GetItemState
- CTabCtrl [MFC], GetRowCount
- CTabCtrl [MFC], GetToolTips
- CTabCtrl [MFC], HighlightItem
- CTabCtrl [MFC], HitTest
- CTabCtrl [MFC], InsertItem
- CTabCtrl [MFC], RemoveImage
- CTabCtrl [MFC], SetCurFocus
- CTabCtrl [MFC], SetCurSel
- CTabCtrl [MFC], SetExtendedStyle
- CTabCtrl [MFC], SetImageList
- CTabCtrl [MFC], SetItem
- CTabCtrl [MFC], SetItemExtra
- CTabCtrl [MFC], SetItemSize
- CTabCtrl [MFC], SetItemState
- CTabCtrl [MFC], SetMinTabWidth
- CTabCtrl [MFC], SetPadding
- CTabCtrl [MFC], SetToolTips
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ed981a2f7345a59f3df479bcd82b9326fd84de12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ctabctrl-class"></a>CTabCtrl 클래스
Windows의 공용 탭 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CTabCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CTabCtrl::CTabCtrl](#ctabctrl)|`CTabCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTabCtrl::AdjustRect](#adjustrect)|창 사각형을 지정 하는 탭 컨트롤의 표시 영역을 계산 하거나 축의 특정된 디스플레이 영역에 해당 하는 창 사각형을 계산 합니다.|  
|[CTabCtrl::Create](#create)|탭 컨트롤을 만들고의 인스턴스에 연결 된 `CTabCtrl` 개체입니다.|  
|[CTabCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 탭 컨트롤을 만들고의 인스턴스에 연결 된 `CTabCtrl` 개체입니다.|  
|[CTabCtrl::DeleteAllItems](#deleteallitems)|탭 컨트롤에서 모든 항목을 제거합니다.|  
|[CTabCtrl::DeleteItem](#deleteitem)|탭 컨트롤에서 항목을 제거 합니다.|  
|[CTabCtrl::DeselectAll](#deselectall)|탭 컨트롤을 누르는 된 선택 취소의 항목을 다시 설정 합니다.|  
|[CTabCtrl::DrawItem](#drawitem)|탭 컨트롤의 지정된 된 항목을 그립니다.|  
|[CTabCtrl::GetCurFocus](#getcurfocus)|탭 컨트롤의 현재 포커스가 있는 탭을 검색합니다.|  
|[CTabCtrl::GetCurSel](#getcursel)|탭 컨트롤의 현재 선택 된 탭을 결정합니다.|  
|[CTabCtrl::GetExtendedStyle](#getextendedstyle)|현재 사용 중인 탭 컨트롤에 대 한 확장된 스타일을 검색 합니다.|  
|[CTabCtrl::GetImageList](#getimagelist)|탭 컨트롤에 연결 된 이미지 목록을 검색 합니다.|  
|[CTabCtrl::GetItem](#getitem)|탭 컨트롤의 탭에 대 한 정보를 검색 합니다.|  
|[CTabCtrl::GetItemCount](#getitemcount)|탭 컨트롤의 탭 수를 검색합니다.|  
|[CTabCtrl::GetItemRect](#getitemrect)|탭 컨트롤의 탭에 대 한 경계 사각형을 검색 합니다.|  
|[CTabCtrl::GetItemState](#getitemstate)|표시 된 탭 제어 항목의 상태를 검색합니다.|  
|[CTabCtrl::GetRowCount](#getrowcount)|탭 컨트롤의 탭 행의 현재 수를 검색합니다.|  
|[CTabCtrl::GetToolTips](#gettooltips)|탭 컨트롤에 연결 된 도구 설명 컨트롤의 핸들을 검색 합니다.|  
|[CTabCtrl::HighlightItem](#highlightitem)|탭 항목 강조 표시 상태를 설정합니다.|  
|[CTabCtrl::HitTest](#hittest)|지정 된 화면 위치에는 있는 경우 탭을 결정 합니다.|  
|[CTabCtrl::InsertItem](#insertitem)|탭 컨트롤에 새 탭을 삽입합니다.|  
|[CTabCtrl::RemoveImage](#removeimage)|탭 컨트롤의 이미지 목록에서 이미지를 제거합니다.|  
|[CTabCtrl::SetCurFocus](#setcurfocus)|탭 컨트롤의 지정된 된 탭에 포커스를 설정 합니다.|  
|[CTabCtrl::SetCurSel](#setcursel)|탭 컨트롤의 탭을 선택합니다.|  
|[CTabCtrl::SetExtendedStyle](#setextendedstyle)|탭 컨트롤에 대 한 확장된 스타일을 설정합니다.|  
|[CTabCtrl::SetImageList](#setimagelist)|탭 컨트롤에는 이미지 목록에 할당합니다.|  
|[CTabCtrl::SetItem](#setitem)|탭의 속성의 일부나 전부를 설정합니다.|  
|[CTabCtrl::SetItemExtra](#setitemextra)|응용 프로그램 정의 데이터 탭 컨트롤에 대 한 예약 탭 당 바이트 수를 설정 합니다.|  
|[CTabCtrl::SetItemSize](#setitemsize)|항목의 높이 및 너비를 설정 합니다.|  
|[CTabCtrl::SetItemState](#setitemstate)|표시 된 탭 제어 항목의 상태를 설정합니다.|  
|[CTabCtrl::SetMinTabWidth](#setmintabwidth)|탭 컨트롤에서 항목의 최소 너비를 설정합니다.|  
|[CTabCtrl::SetPadding](#setpadding)|각 탭의 아이콘 및 탭 컨트롤의 레이블 (패딩) 하는 공간의 크기를 설정 합니다.|  
|[CTabCtrl::SetToolTips](#settooltips)|탭 컨트롤에 도구 설명 컨트롤을 할당합니다.|  
  
## <a name="remarks"></a>설명  
 "탭 컨트롤"은 노트북의 구분선 또는 파일 캐비닛의 레이블을 비슷합니다. 응용 프로그램은 탭 컨트롤을 사용하여 창 또는 대화 상자의 동일한 영역에 대해 여러 페이지를 정의할 수 있습니다. 각 페이지 정보 또는 사용자가 해당 탭을 선택 하면 응용 프로그램에서 표시 하는 컨트롤의 그룹 집합으로 구성 됩니다. 특수 한 유형의 탭 컨트롤 단추 처럼 보이는 탭이 표시 됩니다. 단추를 클릭 하면 페이지를 표시 하는 대신 명령 바로 수행 해야 합니다.  
  
 이 컨트롤 (및 따라서는 `CTabCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수는 있습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CTabCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CTabCtrl 사용 하 여](../../mfc/using-ctabctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="adjustrect"></a>CTabCtrl::AdjustRect  
 창 사각형을 지정 하는 탭 컨트롤의 표시 영역을 계산 하거나 축의 특정된 디스플레이 영역에 해당 하는 창 사각형을 계산 합니다.  
  
```  
void AdjustRect(BOOL bLarger,   LPRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `bLarger`  
 어떤 작업을 수행할지를 나타냅니다. 이 매개 변수가 **TRUE**, `lpRect` 표시 사각형을 지정 하 고 해당 창 사각형을 받습니다. 이 매개 변수가 **FALSE**, `lpRect` 창 사각형을 지정 하 고 해당 표시 사각형을 받습니다.  
  
 `lpRect`  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조를 지정된 된 사각형을 지정 하 고 계산 된 사각형을 받습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CTabCtrl#1](../../mfc/reference/codesnippet/cpp/ctabctrl-class_1.cpp)]  
  
##  <a name="create"></a>CTabCtrl::Create  
 탭 컨트롤을 만들고의 인스턴스에 연결 된 `CTabCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 탭 컨트롤의 스타일을 지정합니다. 어떠한 조합의 적용 [컨트롤 스타일 탭](http://msdn.microsoft.com/library/windows/desktop/bb760549)Windows SDK에 설명 된 대로 합니다. 참조 **주의** 목록은 한 창 스타일을 컨트롤에 적용할 수 있습니다.  
  
 `rect`  
 탭 컨트롤의 크기와 위치를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
 `pParentWnd`  
 탭 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 탭 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 개체의 초기화 했으면 성공 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CTabCtrl` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출 하 고 호출 **만들기**, 탭 컨트롤 만들고에 연결 하는 `CTabCtrl` 개체입니다.  
  
 탭 컨트롤 스타일 이외에도 다음 창 스타일 탭 컨트롤에 적용할 수 있습니다.  
  
- **WS_CHILD** 탭 컨트롤을 표시 하는 자식 창을 만듭니다. 함께 사용할 수 없습니다는 `WS_POPUP` 스타일입니다.  
  
- **WS_VISIBLE** 처음 표시 되는 탭 컨트롤을 만듭니다.  
  
- **WS_DISABLED** 처음부터 사용할 창을 만듭니다.  
  
- **WS_GROUP** 를 이동할 수 한 컨트롤에서 다음 화살표 키를 가진 컨트롤 그룹의 첫 번째 컨트롤을 지정 합니다. 정의 된 모든 컨트롤은 **WS_GROUP** 후 동일한 그룹에 속하는 첫 번째 컨트롤에 스타일입니다. 다음 컨트롤은 **WS_GROUP** 스타일 스타일 그룹을 종료 하 고 다음 그룹 (즉, 한 그룹 끝 다음 시작 하는 위치)를 시작 합니다.  
  
- **WS_TABSTOP** 사용자 TAB 키를 사용 하 여 이동할 수 있는 컨트롤의 모든 숫자 중 하나를 지정 합니다. TAB 키를 누를 사용자로 지정 된 다음 컨트롤로 이동는 **WS_TABSTOP** 스타일입니다.  
  
 확장된 창 스타일을 사용 하 여 탭 컨트롤을 만들려면 호출 [CTabCtrl::CreateEx](#createex) 대신 **만들기**합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CTabCtrl#2](../../mfc/reference/codesnippet/cpp/ctabctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CTabCtrl::CreateEx  
 에 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CTabCtrl` 개체입니다.  
  
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
 탭 컨트롤의 스타일을 지정합니다. 어떠한 조합의 적용 [컨트롤 스타일 탭](http://msdn.microsoft.com/library/windows/desktop/bb760549)Windows SDK에 설명 된 대로 합니다. 참조 **주의** 에 [만들기](#create) 목록은 한 창 스타일을 컨트롤에 적용할 수 있습니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_**합니다.  
  
 `CreateEx`로 지정 된 확장된 창 스타일와 컨트롤을 만듭니다 `dwExStyle`합니다. 스타일을 사용 하 여 컨트롤에만 확장 집합 [SetExtendedStyle](#setextendedstyle)합니다. 사용 예를 들어 `CreateEx` 으로 이러한 스타일을 설정 하려면 **WS_EX_CONTEXTHELP**를 사용 하지만 `SetExtendedStyle` 으로 이러한 스타일을 설정 하려면 **TCS_EX_FLATSEPARATORS**합니다. 자세한 내용은 뒷부분에 있는 스타일을 참조 하십시오. [탭 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760546) Windows sdk에서입니다.  
  
##  <a name="ctabctrl"></a>CTabCtrl::CTabCtrl  
 `CTabCtrl` 개체를 생성합니다.  
  
```  
CTabCtrl();
```  
  
##  <a name="deleteallitems"></a>CTabCtrl::DeleteAllItems  
 탭 컨트롤에서 모든 항목을 제거합니다.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="deleteitem"></a>CTabCtrl::DeleteItem  
 탭 컨트롤에서 지정된 된 항목을 제거합니다.  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 삭제할 항목의 0부터 시작 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CTabCtrl#3](../../mfc/reference/codesnippet/cpp/ctabctrl-class_3.cpp)]  
  
##  <a name="deselectall"></a>CTabCtrl::DeselectAll  
 탭 컨트롤을 누르는 된 선택 취소의 항목을 다시 설정 합니다.  
  
```  
void DeselectAll(BOOL fExcludeFocus);
```  
  
### <a name="parameters"></a>매개 변수  
 *fExcludeFocus*  
 항목 선택 취소의 범위를 지정 하는 플래그입니다. 이 매개 변수 설정 하는 경우 **FALSE**, 모든 탭 단추를 다시 설정 됩니다. 로 설정 되어 있으면 **TRUE**, 현재 선택한을 제외한 모든 탭 항목을 다시 설정 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TCM_DESELECTALL](http://msdn.microsoft.com/library/windows/desktop/bb760579)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="drawitem"></a>CTabCtrl::DrawItem  
 소유자 그리기 탭 컨트롤 변경의 시각적 측면이 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) 그려야 하는 항목을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>설명  
 **itemAction** 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업을 수행 하는 것입니다.  
  
 기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CTabCtrl` 개체입니다.  
  
 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 `lpDrawItemStruct` 함수 종료 전에이 멤버입니다.  
  
##  <a name="getcurfocus"></a>CTabCtrl::GetCurFocus  
 현재 포커스가 있는 탭의 인덱스를 검색합니다.  
  
```  
int GetCurFocus() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 포커스가 있는 탭의 0부터 시작 하는 인덱스입니다.  
  
##  <a name="getcursel"></a>CTabCtrl::GetCurSel  
 탭 컨트롤의 현재 선택 된 탭을 검색합니다.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 선택한 탭 이나-1 없는 탭이 선택의 0부터 시작 인덱스입니다.  
  
##  <a name="getextendedstyle"></a>CTabCtrl::GetExtendedStyle  
 현재 사용 중인 탭 컨트롤에 대 한 확장된 스타일을 검색 합니다.  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>반환 값  
 탭 컨트롤에 대 한 사용 중인 확장된 스타일을 나타냅니다. 이 값은의 조합 [탭 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760546)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TCM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760585)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="getimagelist"></a>CTabCtrl::GetImageList  
 탭 컨트롤에 연관된 이미지 목록을 검색합니다.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 컨트롤의 탭의 이미지 목록에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
##  <a name="getitem"></a>CTabCtrl::GetItem  
 탭 컨트롤의 탭에 대 한 정보를 검색 합니다.  
  
```  
BOOL GetItem(int nItem,   TCITEM* pTabCtrlItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 탭의 인덱스 0부터 시작 합니다.  
  
 `pTabCtrlItem`  
 에 대 한 포인터는 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) 구조를 검색할 정보를 지정 하는 데 사용 합니다. 또한 탭에 대 한 정보를 수신 하는 데 사용 합니다. 이 구조체를 사용는 `InsertItem`, `GetItem`, 및 `SetItem` 멤버 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 하면 **FALSE** 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 메시지를 보낼 때의 **마스크** 멤버 반환 될 특성을 지정 합니다. 경우는 **마스크** 멤버 지정는 `TCIF_TEXT` 값은 **pszText** 멤버 항목 텍스트를 수신 하는 버퍼의 주소를 포함 해야 및 **cchTextMax** 멤버는 버퍼의 크기를 지정 해야 합니다.  
  
 **마스크**  
 지정 하는 값 `TCITEM` 구조체 멤버를 검색 하거나 설정 합니다. 이 멤버는 0 이거나 조합 다음 값 중 하나일 수 있습니다.  
  
- `TCIF_TEXT`**pszText** 멤버는 사용할 수 있습니다.  
  
- `TCIF_IMAGE``iImage` 멤버는 사용할 수 있습니다.  
  
- `TCIF_PARAM`**lParam** 멤버는 사용할 수 있습니다.  
  
- `TCIF_RTLREADING`텍스트 **pszText** 오른쪽에서 왼쪽 읽기 순서를 사용 하 여 히브리어 또는 아랍어 시스템에 표시 됩니다.  
  
- `TCIF_STATE`**dwState** 멤버는 사용할 수 있습니다.  
  
 **pszText**  
 구조는 탭에 대 한 정보를 포함 하는 경우에 탭 텍스트를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다. 구조 정보를 받는 경우이 멤버는 탭 텍스트를 수신 하는 버퍼의 주소를 지정 합니다.  
  
 **cchTextMax**  
 버퍼의 크기를 가리키고 **pszText**합니다. 구조 정보를 받고 있지 않습니다 하는 경우이 멤버는 무시 됩니다.  
  
 `iImage`  
 탭에 대 한 이미지가 없는 경우 탭 컨트롤의 이미지 목록 또는-1을 인덱싱하십시오.  
  
 **lParam**  
 키와 연결 된 응용 프로그램 정의 데이터입니다. 응용 프로그램 구조를 정의 하 고 대신 사용 해야 4 바이트 이상 탭당 응용 프로그램 정의 데이터의 경우는 `TCITEM` 구조입니다. 응용 프로그램 정의 된 구조체의 첫 번째 멤버 이어야 합니다는 [TCITEMHEADER](http://msdn.microsoft.com/library/windows/desktop/bb760556)구조입니다. **TCITEMHEADER** 구조는 동일는 `TCITEM` 구조, 없이 **lParam** 멤버입니다. 크기의 구조와의 크기의 차이 **TCITEMHEADER** 구조 탭당 추가 바이트의 수와 같아야 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CTabCtrl#4](../../mfc/reference/codesnippet/cpp/ctabctrl-class_4.cpp)]  
  
##  <a name="getitemcount"></a>CTabCtrl::GetItemCount  
 탭 컨트롤의 탭 수를 검색합니다.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 탭 컨트롤의 항목 수입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.  
  
##  <a name="getitemrect"></a>CTabCtrl::GetItemRect  
 탭 컨트롤의 지정된 된 탭에 대 한 경계 사각형을 검색 합니다.  
  
```  
BOOL GetItemRect(int nItem,   LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 탭 항목의 0부터 시작 인덱스입니다.  
  
 `lpRect`  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조체 탭의 경계 사각형입니다. 이러한 좌표는 뷰포트의 현재 매핑 모드를 사용합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.  
  
##  <a name="getitemstate"></a>CTabCtrl::GetItemState  
 로 식별 되는 탭 컨트롤 항목의 상태를 검색 `nItem`합니다.  
  
```  
DWORD GetItemState(
    int nItem,  
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 상태 정보를 검색 하려는 항목의 0부터 시작 인덱스 번호를 지정 합니다.  
  
 `dwMask`  
 항목의 상태를 반환 하는 플래그를 지정 하는 마스크입니다. 값의 목록이 참조의 마스크 멤버는 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK에 설명 된 대로 구성 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 참조는 `DWORD` 상태 정보를 수신 하는 값입니다. 다음 값 중 하나입니다.  
  
|값|설명|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|탭 제어 항목을 선택 합니다.|  
|**TCIS_HIGHLIGHTED**|탭 제어 항목 강조 표시 되어 및 탭과 텍스트가 현재 강조 색을 사용 하 여을 그려집니다. 강조 색을 사용 하는 true 보간 디더링된 색이 아니라이 됩니다.|  
  
### <a name="remarks"></a>설명  
 항목의 상태를 지정 하 여는 **dwState** 의 멤버는 `TCITEM` 구조입니다.  
  
##  <a name="getrowcount"></a>CTabCtrl::GetRowCount  
 탭 컨트롤에서 행의 현재 수를 검색 합니다.  
  
```  
int GetRowCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 탭 컨트롤의 탭 행의 수입니다.  
  
### <a name="remarks"></a>설명  
 만 있는 컨트롤 탭은 **TCS_MULTILINE** 스타일 탭의 여러 행을 가질 수 있습니다.  
  
##  <a name="gettooltips"></a>CTabCtrl::GetToolTips  
 탭 컨트롤에 연결 된 도구 설명 컨트롤의 핸들을 검색 합니다.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 도구 설명 컨트롤의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 탭 컨트롤에 있는 경우 도구 설명 컨트롤을 만듭니다는 **TCS_TOOLTIPS** 스타일입니다. 사용 하 여 탭 컨트롤에 도구 설명 컨트롤을 할당할 수도 있습니다는 `SetToolTips` 멤버 함수입니다.  
  
##  <a name="highlightitem"></a>CTabCtrl::HighlightItem  
 탭 항목 강조 표시 상태를 설정합니다.  
  
```  
BOOL HighlightItem(int idItem,   BOOL fHighlight = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `idItem`  
 탭 제어 항목의 0부터 시작 인덱스입니다.  
  
 `fHighlight`  
 설정할 강조 표시 상태를 지정 하는 값입니다. 이 값이 **TRUE**, 탭이 강조 표시; 경우 **FALSE**, 탭의 기본 상태로 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수 구현 Win32 메시지 [TCM_HIGHLIGHTITEM](http://msdn.microsoft.com/library/windows/desktop/bb760602)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="hittest"></a>CTabCtrl::HitTest  
 지정 된 화면 위치에는 있는 경우 탭을 결정 합니다.  
  
```  
int HitTest(TCHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pHitTestInfo`  
 에 대 한 포인터는 [TCHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb760553) 테스트할 화면 위치를 지정 하는 Windows SDK에 설명 된 대로 구성 합니다.  
  
### <a name="return-value"></a>반환 값  
 탭이 않을 경우 지정된 된 위치에 탭 또는-1의 0부터 시작 하는 인덱스를 반환 합니다.  
  
##  <a name="insertitem"></a>CTabCtrl::InsertItem  
 기존 탭 컨트롤에 새 탭을 삽입합니다.  
  
```  
LONG InsertItem(
    int nItem,
    TCITEM* pTabCtrlItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem);

 
LONG InsertItem(
    int nItem,
    LPCTSTR lpszItem,
    int nImage);

 
LONG InsertItem(
    UINT nMask,
    int nItem,
    LPCTSTR lpszItem,
    int nImage,
    LPARAM lParam);

 
LONG InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage,  
    LPARAM lParam,  
    DWORD dwState,  
    DWORD dwStateMask);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 새 탭의 인덱스 0부터 시작 합니다.  
  
 `pTabCtrlItem`  
 에 대 한 포인터는 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) 탭의 특성을 지정 하는 구조입니다.  
  
 `lpszItem`  
 탭의 텍스트를 포함 하는 null로 끝나는 문자열의 주소입니다.  
  
 `nImage`  
 이미지 목록에서 삽입할 이미지를의 0부터 시작 하는 인덱스입니다.  
  
 `nMask`  
 지정 `TCITEM` 설정할 특성을 구성 합니다. 0 또는 다음 값의 조합 될 수 있습니다.  
  
- `TCIF_TEXT`**pszText** 멤버는 사용할 수 있습니다.  
  
- `TCIF_IMAGE``iImage` 멤버는 사용할 수 있습니다.  
  
- `TCIF_PARAM`**lParam** 멤버는 사용할 수 있습니다.  
  
- `TCIF_RTLREADING`텍스트 **pszText** 오른쪽에서 왼쪽 읽기 순서를 사용 하 여 히브리어 또는 아랍어 시스템에 표시 됩니다.  
  
- `TCIF_STATE`**dwState** 멤버는 사용할 수 있습니다.  
  
 `lParam`  
 키와 연결 된 응용 프로그램 정의 데이터입니다.  
  
 `dwState`  
 항목의 상태에 대 한 값을 지정합니다. 자세한 내용은 참조 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows sdk에서입니다.  
  
 *dwStateMask*  
 설정할을 어떤 상태로 지정 합니다. 자세한 내용은 참조 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows sdk에서입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 새 탭의 0부터 시작 인덱스 그렇지 않으면-1입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CTabCtrl#5](../../mfc/reference/codesnippet/cpp/ctabctrl-class_5.cpp)]  
  
##  <a name="removeimage"></a>CTabCtrl::RemoveImage  
 탭 컨트롤의 이미지 목록에서 지정된 된 이미지를 제거합니다.  
  
```  
void RemoveImage(int nImage);
```  
  
### <a name="parameters"></a>매개 변수  
 `nImage`  
 제거할 이미지의 인덱스 0부터 시작 합니다.  
  
### <a name="remarks"></a>설명  
 탭 컨트롤 각 탭에 같은 이미지와 연결 되어 있도록 각 탭의 이미지 인덱스를 업데이트 합니다.  
  
##  <a name="setcurfocus"></a>CTabCtrl::SetCurFocus  
 탭 컨트롤의 지정된 된 탭에 포커스를 설정 합니다.  
  
```  
void SetCurFocus(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 포커스를 탭의 인덱스를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TCM_SETCURFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb760610)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="setcursel"></a>CTabCtrl::SetCurSel  
 탭 컨트롤의 탭을 선택합니다.  
  
```  
int SetCurSel(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 선택 항목의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 이전에 선택한 탭의 0부터 시작 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>설명  
 탭 컨트롤을 전송 하지 않습니다는 **TCN_SELCHANGING** 또는 **TCN_SELCHANGE** 알림 메시지를이 함수를 사용 하는 탭을 선택 합니다. 사용 하 여 이러한 알림을 보내기 **WM_NOTIFY**, 사용자가 클릭 또는 키보드를 사용 하 여 탭을 변경 합니다.  
  
##  <a name="setextendedstyle"></a>CTabCtrl::SetExtendedStyle  
 탭 컨트롤에 대 한 확장된 스타일을 설정합니다.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle,   DWORD dwExMask = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwNewStyle`  
 탭의 조합을 지정 하는 값 확장된 스타일을 제어 합니다.  
  
 `dwExMask`  
 A `DWORD` 에 스타일을 나타내는 값 `dwNewStyle` 영향을 줄 수입니다. 에 확장된 스타일 `dwExMask` 변경 됩니다. 다른 모든 스타일 그대로 유지 됩니다. 이 매개 변수가 0 이면 다음 모든 스타일의 경우 `dwNewStyle` 영향을 받게 됩니다.  
  
### <a name="return-value"></a>반환 값  
 A `DWORD` 이전 포함 된 값 [탭 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760546)Windows SDK에 설명 된 대로 합니다.  
  
### <a name="return-value"></a>반환 값  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TCM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb760627)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="setimagelist"></a>CTabCtrl::SetImageList  
 탭 컨트롤에는 이미지 목록에 할당합니다.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 `pImageList`  
 탭 컨트롤에 할당할 이미지 목록에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 이미지 목록에 대 한 포인터를 반환 하거나 **NULL** 이전 이미지 목록이 없는 경우.  
  
##  <a name="setitem"></a>CTabCtrl::SetItem  
 탭의 속성의 일부나 전부를 설정합니다.  
  
```  
BOOL SetItem(int nItem,   TCITEM* pTabCtrlItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 항목의 0부터 시작 인덱스입니다.  
  
 `pTabCtrlItem`  
 에 대 한 포인터는 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) 새 항목 특성이 포함 된 구조입니다. **마스크** 멤버는 특성을 설정 하려면을 지정 합니다. 경우는 **마스크** 멤버 지정는 `TCIF_TEXT` 값의 **pszText** 멤버는 null로 끝나는 문자열의 주소 및 **cchTextMax** 멤버가 무시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
  예를 참조 [GetItem](#getitem)합니다.  
  
##  <a name="setitemextra"></a>CTabCtrl::SetItemExtra  
 응용 프로그램 정의 데이터 탭 컨트롤에 대 한 예약 탭 당 바이트 수를 설정 합니다.  
  
```  
BOOL SetItemExtra(int nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `nBytes`  
 설정에 추가 바이트의 수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TCM_SETITEMEXTRA](http://msdn.microsoft.com/library/windows/desktop/bb760633)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="setitemsize"></a>CTabCtrl::SetItemSize  
 탭 컨트롤 항목의 높이 및 너비를 설정합니다.  
  
```  
CSize SetItemSize(CSize size);
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 탭 제어 항목의 새로운 너비 및 높이입니다(픽셀).  
  
### <a name="return-value"></a>반환 값  
 탭 제어 항목의 이전 높이 및 너비를 반환합니다.  
  
##  <a name="setitemstate"></a>CTabCtrl::SetItemState  
 로 식별 되는 탭 컨트롤 항목의 상태를 설정 `nItem`합니다.  
  
```  
BOOL SetItemState(
    int nItem,
    DWORD dwMask,
    DWORD dwState);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 상태 정보를 설정할 항목의 0부터 시작 인덱스 번호를 지정 합니다.  
  
 `dwMask`  
 항목의 상태를 설정 하는 플래그를 지정 하는 마스크입니다. 값의 목록이 참조의 마스크 멤버는 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) Windows SDK에 설명 된 대로 구성 합니다.  
  
 `dwState`  
 에 대 한 참조는 `DWORD` 상태 정보를 포함 하는 값입니다. 다음 값 중 하나입니다.  
  
|값|설명|  
|-----------|-----------------|  
|**TCIS_BUTTONPRESSED**|탭 제어 항목을 선택 합니다.|  
|**TCIS_HIGHLIGHTED**|탭 제어 항목 강조 표시 되어 및 탭과 텍스트가 현재 강조 색을 사용 하 여을 그려집니다. 강조 색을 사용 하는 true 보간 디더링된 색이 아니라이 됩니다.|  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
##  <a name="setmintabwidth"></a>CTabCtrl::SetMinTabWidth  
 탭 컨트롤에서 항목의 최소 너비를 설정합니다.  
  
```  
int SetMinTabWidth(int cx);
```  
  
### <a name="parameters"></a>매개 변수  
 `cx`  
 탭 제어 항목에 설정 해야 하는 최소 너비입니다. 이 매개 변수는-1로 설정 하는 경우 컨트롤이 기본 탭 너비를 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전 탭 최소 너비입니다.  
  
### <a name="return-value"></a>반환 값  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TCM_SETMINTABWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb760637)Windows SDK에 설명 된 대로 합니다.  
  
##  <a name="setpadding"></a>CTabCtrl::SetPadding  
 각 탭의 아이콘 및 탭 컨트롤의 레이블 (패딩) 하는 공간의 크기를 설정 합니다.  
  
```  
void SetPadding(CSize size);
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 각 탭의 아이콘 및 탭 컨트롤의 레이블 (패딩) 하는 공간의 크기를 설정 합니다.  
  
##  <a name="settooltips"></a>CTabCtrl::SetToolTips  
 탭 컨트롤에 도구 설명 컨트롤을 할당합니다.  
  
```  
void SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWndTip`  
 도구 설명 컨트롤의 핸들입니다.  
  
### <a name="remarks"></a>설명  
 탭 컨트롤을 호출 하 여 연결 된 도구 설명 컨트롤을 가져올 수 있습니다 `GetToolTips`합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CPropertySheet::GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl 클래스](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)
