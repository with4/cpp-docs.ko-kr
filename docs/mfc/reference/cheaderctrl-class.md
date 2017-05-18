---
title: "CHeaderCtrl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
dev_langs:
- C++
helpviewer_keywords:
- CHeaderCtrl class
- Windows common controls [C++], CHeaderCtrl
- header controls, CHeaderCtrl class
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: faa23ea6f28c2643c9bee090ea150e37d0add97c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="cheaderctrl-class"></a>CHeaderCtrl 클래스
Windows의 공용 헤더 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|`CHeaderCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|헤더 컨트롤에 대 한 모든 필터를 지웁니다.|  
|[CHeaderCtrl::ClearFilter](#clearfilter)|헤더 컨트롤에 대 한 필터를 지웁니다.|  
|[CHeaderCtrl::Create](#create)|헤더 컨트롤을 만들고에 연결 된 `CHeaderCtrl` 개체입니다.|  
|[CHeaderCtrl::CreateDragImage](#createdragimage)|헤더 컨트롤 내에서 항목의 이미지의 투명 한 버전을 만듭니다.|  
|[CHeaderCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 헤더 컨트롤을 만들고에 연결 된 `CListCtrl` 개체입니다.|  
|[CHeaderCtrl::DeleteItem](#deleteitem)|헤더 컨트롤에서 항목을 삭제 합니다.|  
|[CHeaderCtrl::DrawItem](#drawitem)|헤더 컨트롤의 지정된 된 항목을 그립니다.|  
|[CHeaderCtrl::EditFilter](#editfilter)|헤더 컨트롤의 지정된 된 필터를 편집을 시작 합니다.|  
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|헤더 컨트롤에서 비트맵의 여백 너비를 검색합니다.|  
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|포커스가 있는 현재 헤더 컨트롤에서 항목의 식별자를 가져옵니다.|  
|[CHeaderCtrl::GetImageList](#getimagelist)|헤더 컨트롤에서 그리기 헤더 항목에 사용할 이미지 목록의 처리를 검색 합니다.|  
|[CHeaderCtrl::GetItem](#getitem)|헤더 컨트롤의 항목에 대 한 정보를 검색합니다.|  
|[CHeaderCtrl::GetItemCount](#getitemcount)|헤더 컨트롤의 항목 수를 검색합니다.|  
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|헤더 컨트롤의 지정한 드롭 다운 단추에 대 한 경계 사각형 정보를 가져옵니다.|  
|[CHeaderCtrl::GetItemRect](#getitemrect)|헤더 컨트롤의 지정된 된 항목에 대 한 경계 사각형을 검색 합니다.|  
|[CHeaderCtrl::GetOrderArray](#getorderarray)|헤더 컨트롤에서 항목의 왼쪽-오른쪽 순서를 검색합니다.|  
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|현재 헤더 컨트롤에 대 한 오버플로 단추인의 경계 사각형을 가져옵니다.|  
|[CHeaderCtrl::HitTest](#hittest)|헤더, 있는 경우 있는 항목을 지정 된 기간의 결정 합니다.|  
|[CHeaderCtrl::InsertItem](#insertitem)|헤더 컨트롤에 새 항목을 삽입합니다.|  
|[CHeaderCtrl::Layout](#layout)|지정 된 사각형 내에서 헤더 컨트롤의 위치와 크기를 검색합니다.|  
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|헤더 컨트롤에서 해당 순서에 따라 항목에 대 한 인덱스 값을 검색 합니다.|  
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|헤더 컨트롤의 여백 비트맵의 너비를 설정합니다.|  
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|필터 특성에서 변경이 수행 때와 게시의 제한 시간 간격으로 설정 된 `HDN_FILTERCHANGE` 알림입니다.|  
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|현재 헤더 컨트롤에서 지정 된 헤더 항목에 포커스를 설정합니다.|  
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|헤더 항목을 나타내는 수동 사이의 구분선 끌어 변경 및 헤더 항목의 삭제가 합니다.|  
|[CHeaderCtrl::SetImageList](#setimagelist)|헤더 컨트롤에는 이미지 목록에 할당합니다.|  
|[CHeaderCtrl::SetItem](#setitem)|헤더 컨트롤의 지정된 된 항목의 특성을 설정합니다.|  
|[CHeaderCtrl::SetOrderArray](#setorderarray)|헤더 컨트롤에서 항목의 왼쪽-오른쪽 순서를 설정합니다.|  
  
## <a name="remarks"></a>주의  
 헤더 컨트롤에는 일반적으로 텍스트 또는 숫자 열 집합이 위에 배치 되는 창입니다. 각 열에 대 한 제목을 포함 하 고 부분으로 나눌 수 있습니다. 각 열의 너비를 설정 하려면 각 부분을 구분 하는 분할자를 끌 수 있습니다. 헤더 컨트롤의 예시의 경우에 대 한 참조 [헤더 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775238)합니다.  
  
 이 컨트롤 (및 따라서는 `CHeaderCtrl` 클래스)은 이상 버전과 Windows 95/98 및 Windows NT 버전 3.51에서 실행 되는 프로그램 에서만 사용할 수 있습니다.  
  
 Windows 95/Internet Explorer 4.0 공용 컨트롤에 대 한 추가 기능에는 다음이 포함 되어 있습니다.  
  
-   헤더 항목 사용자 지정 정렬 합니다.  
  
-   헤더 항목 끌어서 놓기, 헤더 항목 다시 정렬에 대 한 합니다. 사용 하 여는 `HDS_DRAGDROP` 스타일을 만들 때는 `CHeaderCtrl` 개체입니다.  
  
-   머리글 열 텍스트 열 크기 조정 하는 동안 지속적으로 볼 수 있습니다. 사용 하 여는 `HDS_FULLDRAG` 스타일을 만들 때 한 `CHeaderCtrl` 개체입니다.  
  
-   헤더 핫 추적을 포인터 가리킬 때에 머리글 항목을 강조 표시 합니다. 사용 하 여는 `HDS_HOTTRACK` 스타일을 만들 때는 `CHeaderCtrl` 개체입니다.  
  
-   이미지 목록 지원입니다. 헤더 항목에 저장 된 이미지를 포함할 수 있습니다는 `CImageList` 개체 또는 텍스트입니다.  
  
 사용에 대 한 자세한 내용은 `CHeaderCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CHeaderCtrl 사용 하 여](../../mfc/using-cheaderctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="cheaderctrl"></a>CHeaderCtrl::CHeaderCtrl  
 `CHeaderCtrl` 개체를 생성합니다.  
  
```  
CHeaderCtrl();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]  
  
##  <a name="clearallfilters"></a>CHeaderCtrl::ClearAllFilters  
 헤더 컨트롤에 대 한 모든 필터를 지웁니다.  
  
```  
BOOL ClearAllFilters();
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 Win32 메시지의 동작을 구현 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306) 에 설명 된 대로-1의 열 값이 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]  
  
##  <a name="clearfilter"></a>CHeaderCtrl::ClearFilter  
 헤더 컨트롤에 대 한 필터를 지웁니다.  
  
```  
BOOL ClearFilter(int nColumn);
```  
  
### <a name="parameters"></a>매개 변수  
 `nColumn`  
 나타내는 선택을 필터링 하는 열 값입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 Win32 메시지의 동작을 구현 [HDM_CLEARFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775306)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]  
  
##  <a name="create"></a>CHeaderCtrl::Create  
 헤더 컨트롤을 만들고에 연결 된 `CHeaderCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 헤더 컨트롤의 스타일을 지정합니다. 헤더 컨트롤 스타일에 대 한 참조 [헤더 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775241) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 헤더 컨트롤의 크기와 위치를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
 `pParentWnd`  
 헤더 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 헤더 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CHeaderCtrl` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출 하 고 호출 **만들기**, 헤더 컨트롤 만들고에 연결 하는 `CHeaderCtrl` 개체입니다.  
  
 헤더 컨트롤 스타일 아니라 헤더 컨트롤 배치 하 고 크기를 조정 하는 방법을 결정 하는 다음과 같은 일반적인 컨트롤 스타일을 사용할 수 있습니다 (참조 [공통 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 에 대 한 자세한 내용은):  
  
- `CCS_BOTTOM`부모 창의 클라이언트 영역의 맨 아래에 배치 하 고 컨트롤 창의 너비 부모와 동일한 너비를 설정 하는 합니다.  
  
- `CCS_NODIVIDER`컨트롤의 위쪽에 그려지는에서 두 픽셀 강조 표시 되지 않도록 합니다.  
  
- `CCS_NOMOVEY`컨트롤이 크기 조정 및에 대 한 응답에서 가로로 하지만 하지을 세로로 자체 이동 하는 `WM_SIZE` 메시지입니다. 경우는 `CCS_NORESIZE` 스타일은 사용,이 스타일 적용 되지 않습니다. 헤더 컨트롤 기본적으로이 스타일을 갖습니다.  
  
- `CCS_NOPARENTALIGN`컨트롤을 위쪽 또는 아래쪽 부모 창의 자동으로 이동할 수 없습니다. 대신, 컨트롤은 부모 창의 크기를 변경 되더라도 부모 창 내에서 위치를 유지합니다. 경우는 `CCS_TOP` 또는 `CCS_BOTTOM` 스타일도 사용 되는, 높이 기본적으로 조정 됩니다 있지만 위치와 폭 변경 되지 않습니다.  
  
- `CCS_NORESIZE`초기 크기 또는 새 크기를 설정할 때 기본 너비와 높이 사용 하 여 컨트롤을 방지 합니다. 대신 컨트롤의 너비와 높이 생성 또는 크기 조정에 대 한 요청에 지정 된 사용 합니다.  
  
- `CCS_TOP`컨트롤이 부모 창의 클라이언트 영역 위쪽에 배치 하 부모와 동일 하 게 너비 창의 너비를 설정 하는 합니다.  
  
 헤더 컨트롤에 다음 창 스타일을 적용할 수 있습니다 (참조 [창 스타일](../../mfc/reference/window-styles.md) 에 대 한 자세한 내용은):  
  
- **WS_CHILD** 자식 창을 만듭니다. 함께 사용할 수 없습니다는 `WS_POPUP` 스타일입니다.  
  
- **WS_VISIBLE** 처음에 표시 되는 창을 만듭니다.  
  
- **WS_DISABLED** 처음부터 사용할 창을 만듭니다.  
  
- **WS_GROUP** 를 이동할 수 한 컨트롤에서 다음 화살표 키를 가진 컨트롤 그룹의 첫 번째 컨트롤을 지정 합니다. 정의 된 모든 컨트롤은 **WS_GROUP** 후 동일한 그룹에 속하는 첫 번째 컨트롤에 스타일입니다. 다음 컨트롤은 **WS_GROUP** 스타일 스타일 그룹을 종료 하 고 다음 그룹 (즉, 한 그룹 끝 다음 시작 하는 위치)를 시작 합니다.  
  
- **WS_TABSTOP** 사용자 TAB 키를 사용 하 여 이동할 수 있는 컨트롤의 모든 숫자 중 하나를 지정 합니다. TAB 키를 누를 사용자로 지정 된 다음 컨트롤로 이동는 **WS_TABSTOP** 스타일입니다.  
  
 컨트롤 확장된 창 스타일을 사용 하려면 호출 [CreateEx](#createex) 대신 **만들기**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]  
  
##  <a name="createex"></a>CHeaderCtrl::CreateEx  
 와 연결 하 고 컨트롤 (자식 창)을 만듭니다.는 `CHeaderCtrl` 개체입니다.  
  
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
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 헤더 컨트롤의 스타일입니다. 헤더 컨트롤 스타일에 대 한 참조 [헤더 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775241) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 참조 [만들기](#create) 목록은 한 추가 스타일입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 **만들기** Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_**합니다.  
  
##  <a name="createdragimage"></a>CHeaderCtrl::CreateDragImage  
 헤더 컨트롤 내에서 항목의 이미지의 투명 한 버전을 만듭니다.  
  
```  
CImageList* CreateDragImage(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 헤더 컨트롤에서 항목의 0부터 시작 하는 인덱스입니다. 이 항목에 할당 된 이미지는 투명 한 이미지의 기반입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 성공 되지 않으면 개체 **NULL**합니다. 반환된 된 목록에는 하나의 이미지만 포함 되어 있습니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_CREATEDRAGIMAGE](http://msdn.microsoft.com/library/windows/desktop/bb775308)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 헤더 항목 끌어서 놓기 지원 하기 위해 제공 됩니다.  
  
 `CImageList` 개체를 반환 된 포인터가 가리키는 임시 개체 이며 다음 유휴 시간 처리에서 삭제 됩니다.  
  
##  <a name="deleteitem"></a>CHeaderCtrl::DeleteItem  
 헤더 컨트롤에서 항목을 삭제 합니다.  
  
```  
BOOL DeleteItem(int nPos);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 삭제할 항목의 0부터 시작 하는 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]  
  
##  <a name="drawitem"></a>CHeaderCtrl::DrawItem  
 소유자 그리기 헤더 컨트롤 변경 내용의 시각적 측면이 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) 그려야 하는 항목을 설명 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 **itemAction** 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업을 수행 하는 것입니다.  
  
 기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CHeaderCtrl` 개체입니다.  
  
 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야 `lpDrawItemStruct` 함수 종료 전에이 멤버입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]  
  
##  <a name="editfilter"></a>CHeaderCtrl::EditFilter  
 헤더 컨트롤의 지정된 된 필터를 편집 하기 시작 합니다.  
  
```  
BOOL EditFilter(
    int nColumn,  
    BOOL bDiscardChanges);
```  
  
### <a name="parameters"></a>매개 변수  
 `nColumn`  
 열 편집입니다.  
  
 `bDiscardChanges`  
 사용자를 처리 하는 방법을 지정 하는 값의 필터를 편집 하는 중 사용자가 변경 내용을 편집 때는 [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312) 메시지가 전송 됩니다.  
  
 지정 `true` 사용자가 변경한 내용을 무시 하려면 또는 `false` 사용자가 수행한 변경 내용을 적용 합니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 Win32 메시지의 동작을 구현 [HDM_EDITFILTER](http://msdn.microsoft.com/library/windows/desktop/bb775312)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]  
  
##  <a name="getbitmapmargin"></a>CHeaderCtrl::GetBitmapMargin  
 헤더 컨트롤에서 비트맵의 여백 너비를 검색합니다.  
  
```  
int GetBitmapMargin() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀에서 비트맵 여백의 너비입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_GETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775314)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]  
  
##  <a name="getfocuseditem"></a>CHeaderCtrl::GetFocusedItem  
 현재 헤더 컨트롤에 포커스가 있는 항목의 인덱스를 가져옵니다.  
  
```  
int GetFocusedItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 포커스가 있는 머리글 항목의 0부터 시작 하는 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [HDM_GETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775330) 에 설명 되어 있는 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제는 `SetFocusedItem` 및 `GetFocusedItem` 메서드. 코드의 이전 단원에서 5 개의 열이 있는 헤더 컨트롤을 생성 합니다. 그러나 열이 표시 되도록 열 구분 기호를 끌 수 있습니다. 다음 예제에서는 설정 하 고 마지막 열 머리글의 포커스 항목으로 확인 합니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="getimagelist"></a>CHeaderCtrl::GetImageList  
 헤더 컨트롤에서 그리기 헤더 항목에 사용할 이미지 목록의 처리를 검색 합니다.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_GETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775332)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. `CImageList` 개체를 반환 된 포인터가 가리키는 임시 개체 이며 다음 유휴 시간 처리에서 삭제 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]  
  
##  <a name="getitem"></a>CHeaderCtrl::GetItem  
 헤더 컨트롤 항목에 대 한 정보를 검색합니다.  
  
```  
BOOL GetItem(
    int nPos,  
    HDITEM* pHeaderItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 검색할 항목의 0부터 시작 하는 인덱스를 지정 합니다.  
  
 `pHeaderItem`  
 에 대 한 포인터는 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) 구조체 새 항목입니다. 이 구조체를 사용는 `InsertItem` 및 `SetItem` 멤버 함수입니다. 모든 플래그 설정 된 **마스크** 요소 값의 해당 요소에 제대로 채워졌는지 반환 되 면 확인 합니다. 경우는 **마스크** 요소는 0으로 설정 되어, 다른 구조 요소에는 값은 의미가 없습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]  
  
##  <a name="getitemcount"></a>CHeaderCtrl::GetItemCount  
 헤더 컨트롤의 항목 수를 검색합니다.  
  
```  
int GetItemCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 헤더 컨트롤 항목의 수 그렇지 않으면-1입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CHeaderCtrl::DeleteItem](#deleteitem)합니다.  
  
##  <a name="getitemdropdownrect"></a>CHeaderCtrl::GetItemDropDownRect  
 현재 헤더 컨트롤의 헤더 항목을 드롭 다운 단추의 경계 사각형을 가져옵니다.  
  
```  
BOOL GetItemDropDownRect(
    int iItem,   
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iItem`|스타일은 헤더 항목의 0부터 시작 인덱스 `HDF_SPLITBUTTON`합니다. 자세한 내용은 참조는 `fmt` 의 멤버는 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) 구조입니다.|  
|[out] `lpRect`|에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조 경계 사각형 정보를 얻습니다.|  
  
### <a name="return-value"></a>반환 값  
 `true`이 함수는 성공 하는 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [HDM_GETITEMDROPDOWNRECT](http://msdn.microsoft.com/library/windows/desktop/bb775339) 에 설명 되어 있는 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제는 `GetItemDropDownRect` 메서드. 코드의 이전 단원에서 5 개의 열이 있는 헤더 컨트롤을 생성 합니다. 다음 코드 예제에서는 머리글 드롭 다운 단추에 대 한 예약 된 첫 번째 열에 위치 주변 3 차원 사각형을 그립니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]  
  
##  <a name="getitemrect"></a>CHeaderCtrl::GetItemRect  
 헤더 컨트롤의 지정된 된 항목에 대 한 경계 사각형을 검색 합니다.  
  
```  
BOOL GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 헤더 컨트롤 항목의 0부터 시작 하는 인덱스입니다.  
  
 `lpRect`  
 주소에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조체는 경계 사각형 정보입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 Win32 메시지의 동작을 구현 [HDM_GETITEMRECT](http://msdn.microsoft.com/library/windows/desktop/bb775341)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getorderarray"></a>CHeaderCtrl::GetOrderArray  
 헤더 컨트롤에서 항목의 왼쪽-오른쪽 순서를 검색합니다.  
  
```  
BOOL GetOrderArray(
    LPINT piArray,  
    int iCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `piArray`  
 표시 된 왼쪽에서 오른쪽 순서로 헤더 컨트롤에서 항목의 인덱스 값을 받는 버퍼의 주소에 대 한 포인터입니다.  
  
 `iCount`  
 헤더 컨트롤 항목의 수입니다. 음수가 아닌 이어야 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_GETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775343)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 헤더 항목 순서 지정을 지원 하기 위해 제공 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]  
  
##  <a name="getoverflowrect"></a>CHeaderCtrl::GetOverflowRect  
 현재 헤더 컨트롤의 오버플로 단추의 경계 사각형을 가져옵니다.  
  
```  
BOOL GetOverflowRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `lpRect`|에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조체는 경계 사각형 정보입니다.|  
  
### <a name="return-value"></a>반환 값  
 `true`이 함수는 성공 하는 경우 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 헤더 컨트롤에 동시에 표시할 수 있는 것 보다 더 많은 항목이 포함 된 경우 컨트롤을 사용 하 여 스크롤 하는 오버플로 단추가 표시 되지 않는 항목에 표시 됩니다. 헤더 컨트롤에 있어야는 `HDS_OVERFLOW` 및 `HDF_SPLITBUTTON` 스타일 오버플로 단추를 표시 합니다. 경계 사각형 오버플로 단추를 포함 하 고 오버플로 단추가 표시 된 경우에 존재 합니다. 자세한 내용은 참조 [헤더 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775241)합니다.  
  
 이 메서드는 전송 된 [HDM_GETOVERFLOWRECT](http://msdn.microsoft.com/library/windows/desktop/bb775345) 에 설명 되어 있는 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제는 `GetOverflowRect` 메서드. 코드의 이전 단원에서 5 개의 열이 있는 헤더 컨트롤을 생성 합니다. 그러나 열이 표시 되도록 열 구분 기호를 끌 수 있습니다. 일부 열이 표시 되지 않는 헤더 컨트롤 오버플로 단추를 그립니다. 다음 코드 예제에서는 오버플로 단추의 위치 주위 3D 사각형을 그립니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]  
  
##  <a name="hittest"></a>CHeaderCtrl::HitTest  
 헤더, 있는 경우 있는 항목을 지정 된 기간의 결정 합니다.  
  
```  
int HitTest(LPHDHITTESTINFO* phdhti);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in, out] `phdhti`|에 대 한 포인터는 [HDHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb775245) 구조를 테스트 하는 시점을 지정 하 고 테스트의 결과 받습니다.|  
  
### <a name="return-value"></a>반환 값  
 지정된 된 위치;에 있는 경우에 머리글 항목의 0부터 시작 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [HDM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb775349) 에 설명 되어 있는 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제는 `HitTest` 메서드. 이 코드 예제는 이전 섹션에서 5 개의 열이 있는 헤더 컨트롤을 생성 합니다. 그러나 열이 표시 되도록 열 구분 기호를 끌 수 있습니다. 이 예제에서는 표시 되는 경우는 열의 인덱스를 보고 하 고 해당 열이 표시 되지 않으면-1입니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]  
  
##  <a name="insertitem"></a>CHeaderCtrl::InsertItem  
 지정된 된 인덱스에 헤더 컨트롤에 새 항목을 삽입합니다.  
  
```  
int InsertItem(
    int nPos,  
    HDITEM* phdi);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 삽입할 항목의 인덱스(0부터 시작)입니다. 값이 0 이면 해당 항목의 헤더 컨트롤의 시작 부분에 삽입 됩니다. 값의 최 댓 값 보다 큰 경우 해당 항목의 헤더 컨트롤의 끝에 삽입 됩니다.  
  
 *phdi*  
 에 대 한 포인터는 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) 삽입할 항목에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 새 항목의 인덱스 그렇지 않으면-1입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]  
  
##  <a name="layout"></a>CHeaderCtrl::Layout  
 지정 된 사각형 내에서 헤더 컨트롤의 위치와 크기를 검색합니다.  
  
```  
BOOL Layout(HDLAYOUT* pHeaderLayout);
```  
  
### <a name="parameters"></a>매개 변수  
 *pHeaderLayout*  
 에 대 한 포인터는 [HDLAYOUT](http://msdn.microsoft.com/library/windows/desktop/bb775249) 크기와 헤더 컨트롤의 위치를 설정 하는 데 사용 되는 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 함수를 사용 하도록 지정된 된 사각형에 있는 새 헤더 컨트롤에 대 한 적절 한 크기를 결정 하려면 사용 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]  
  
##  <a name="ordertoindex"></a>CHeaderCtrl::OrderToIndex  
 헤더 컨트롤에서 해당 순서에 따라 항목에 대 한 인덱스 값을 검색 합니다.  
  
```  
int OrderToIndex(int nOrder) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *nOrder*  
 항목이 나타나는 헤더 컨트롤에서 왼쪽에서 오른쪽의 0부터 시작 순서.  
  
### <a name="return-value"></a>반환 값  
 헤더 컨트롤에서 해당 순서에 따라 항목의 인덱스입니다. 왼쪽에서 오른쪽으로 0으로 시작 인덱스를 계산 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [HDM_ORDERTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb775355)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 헤더 항목 순서 지정을 지원 하기 위해 제공 됩니다.  
  
##  <a name="setbitmapmargin"></a>CHeaderCtrl::SetBitmapMargin  
 헤더 컨트롤의 여백 비트맵의 너비를 설정합니다.  
  
```  
int SetBitmapMargin(int nWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 `nWidth`  
 너비 (픽셀) 기존 헤더 컨트롤 내에서 비트맵 주위의 여백입니다.  
  
### <a name="return-value"></a>반환 값  
 픽셀에서 비트맵 여백의 너비입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETBITMAPMARGIN](http://msdn.microsoft.com/library/windows/desktop/bb775357)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]  
  
##  <a name="setfilterchangetimeout"></a>CHeaderCtrl::SetFilterChangeTimeout  
 필터 특성에서 변경이 수행 때와 게시의 제한 시간 간격으로 설정 된 [HDN_FILTERCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb775277) 알림입니다.  
  
```  
int SetFilterChangeTimeout(DWORD dwTimeOut);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwTimeOut*  
 제한 시간 값 (밀리초)에서입니다.  
  
### <a name="return-value"></a>반환 값  
 수정 중인 필터 컨트롤의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETFILTERCHANGETIMEOUT](http://msdn.microsoft.com/library/windows/desktop/bb775359)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]  
  
##  <a name="setfocuseditem"></a>CHeaderCtrl::SetFocusedItem  
 현재 헤더 컨트롤에서 지정 된 헤더 항목에 포커스를 설정합니다.  
  
```  
BOOL SetFocusedItem(int iItem);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iItem`|헤더 항목의 0부터 시작 인덱스입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [HDM_SETFOCUSEDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775361) 에 설명 되어 있는 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 변수를 정의 `m_headerCtrl`, 즉 현재 헤더 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제는 `SetFocusedItem` 및 `GetFocusedItem` 메서드. 코드의 이전 단원에서 5 개의 열이 있는 헤더 컨트롤을 생성 합니다. 그러나 열이 표시 되도록 열 구분 기호를 끌 수 있습니다. 다음 예제에서는 설정 하 고 마지막 열 머리글의 포커스 항목으로 확인 합니다.  
  
 [!code-cpp[NVC_MFC_CHeaderCtrl_s&#4; 4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]  
  
##  <a name="sethotdivider"></a>CHeaderCtrl::SetHotDivider  
 헤더 항목을 나타내는 수동 사이의 구분선 끌어 변경 및 헤더 항목의 삭제가 합니다.  
  
```  
int SetHotDivider(CPoint pt);  
int SetHotDivider(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 포인터의 위치입니다. 헤더 컨트롤에는 포인터의 위치에 따라 적절 한 구분선 강조 표시 합니다.  
  
 `nIndex`  
 강조 표시 된 구분선의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 강조 표시 된 구분선의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETHOTDIVIDER](http://msdn.microsoft.com/library/windows/desktop/bb775363)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 헤더 항목 끌어서 놓기 지원 하기 위해 제공 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CHeaderCtrl # 16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]  
  
##  <a name="setimagelist"></a>CHeaderCtrl::SetImageList  
 헤더 컨트롤에는 이미지 목록에 할당합니다.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 `pImageList`  
 에 대 한 포인터는 `CImageList` 헤더 컨트롤에 할당할 이미지 목록을 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 헤더 컨트롤에 이전에 할당 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [HDM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775365)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. `CImageList` 개체를 반환 된 포인터가 가리키는 임시 개체 이며 다음 유휴 시간 처리에서 삭제 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CHeaderCtrl::GetImageList](#getimagelist)합니다.  
  
##  <a name="setitem"></a>CHeaderCtrl::SetItem  
 헤더 컨트롤의 지정된 된 항목의 특성을 설정합니다.  
  
```  
BOOL SetItem(
    int nPos,  
    HDITEM* pHeaderItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPos`  
 조작할 수 항목의 0부터 시작 하는 인덱스입니다.  
  
 `pHeaderItem`  
 에 대 한 포인터는 [HDITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) 새 항목에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CHeaderCtrl::GetItem](#getitem)합니다.  
  
##  <a name="setorderarray"></a>CHeaderCtrl::SetOrderArray  
 헤더 컨트롤에서 항목의 왼쪽-오른쪽 순서를 설정합니다.  
  
```  
BOOL SetOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `iCount`  
 헤더 컨트롤 항목의 수입니다.  
  
 `piArray`  
 표시 된 왼쪽에서 오른쪽 순서로 헤더 컨트롤에서 항목의 인덱스 값을 받는 버퍼의 주소에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [HDM_SETORDERARRAY](http://msdn.microsoft.com/library/windows/desktop/bb775369)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 헤더 항목 순서 지정을 지원 하기 위해 제공 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CHeaderCtrl::GetOrderArray](#getorderarray)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CTabCtrl 클래스](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)   
 [CImageList 클래스](../../mfc/reference/cimagelist-class.md)

