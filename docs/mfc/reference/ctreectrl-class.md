---
title: "CTreeCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTreeCtrl
dev_langs:
- C++
helpviewer_keywords:
- directory lists
- tree view controls
- file lists [C++]
- CTreeCtrl class
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
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
ms.openlocfilehash: 5341367b44540e2d0991fd61e52611826bbdcda1
ms.lasthandoff: 02/24/2017

---
# <a name="ctreectrl-class"></a>CTreeCtrl Class
Windows의 공용 트리 뷰 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CTreeCtrl::CTreeCtrl](#ctreectrl)|`CTreeCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTreeCtrl::Create](#create)|트리 뷰 컨트롤을 만들고 연결 하는 `CTreeCtrl` 개체입니다.|  
|[CTreeCtrl::CreateDragImage](#createdragimage)|지정 된 트리 뷰 항목에 대 한 끌기 비트맵을 만듭니다.|  
|[CTreeCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 트리 컨트롤을 만들고에 연결 된 `CTreeCtrl` 개체입니다.|  
|[CTreeCtrl::DeleteAllItems](#deleteallitems)|트리 뷰 컨트롤의 모든 항목을 삭제합니다.|  
|[CTreeCtrl::DeleteItem](#deleteitem)|트리 뷰 컨트롤에 새 항목을 삭제합니다.|  
|[CTreeCtrl::EditLabel](#editlabel)|지정 된 트리 뷰 항목 위치에서 편집합니다.|  
|[CTreeCtrl::EndEditLabelNow](#endeditlabelnow)|현재 트리 뷰 컨트롤의 트리 보기 항목의 레이블에 대 한 편집 작업을 취소합니다.|  
|[CTreeCtrl::EnsureVisible](#ensurevisible)|트리 뷰 항목의 트리 뷰 컨트롤에 표시 되는지 확인 합니다.|  
|[CTreeCtrl::Expand](#expand)|확장 되거나 지정 된 트리 뷰 항목의 자식 항목을 축소 합니다.|  
|[CTreeCtrl::GetBkColor](#getbkcolor)|컨트롤의 현재 배경색을 검색합니다.|  
|[CTreeCtrl::GetCheck](#getcheck)|트리 컨트롤 항목의 선택 상태를 검색합니다.|  
|[CTreeCtrl::GetChildItem](#getchilditem)|지정 된 트리 보기 항목의 자식을 검색합니다.|  
|[CTreeCtrl::GetCount](#getcount)|트리 뷰 컨트롤에 연결 된 트리 항목의 수를 검색 합니다.|  
|[CTreeCtrl::GetDropHilightItem](#getdrophilightitem)|끌어서 놓기 작업의 대상을 검색합니다.|  
|[CTreeCtrl::GetEditControl](#geteditcontrol)|지정 된 트리 뷰 항목을 편집 하는 데 사용 하는 편집 컨트롤의 핸들을 검색 합니다.|  
|[CTreeCtrl::GetExtendedStyle](#getextendedstyle)|현재 트리 뷰 컨트롤을 사용 하는 확장된 스타일을 검색 합니다.|  
|[CTreeCtrl::GetFirstVisibleItem](#getfirstvisibleitem)|지정 된 트리 뷰 항목의 표시 되는 첫 번째 항목을 검색합니다.|  
|[CTreeCtrl::GetImageList](#getimagelist)|트리 뷰 컨트롤에 연결 된 이미지 목록의 처리를 검색 합니다.|  
|[CTreeCtrl::GetIndent](#getindent)|부모에서 오프셋 (픽셀 단위)의 트리 뷰 항목을 검색합니다.|  
|[CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor)|트리 보기에 대 한 삽입 표시를 그리는 데 사용 되는 색을 검색 합니다.|  
|[CTreeCtrl::GetItem](#getitem)|지정 된 트리 뷰 항목의 특성을 검색 합니다.|  
|[CTreeCtrl::GetItemData](#getitemdata)|항목에 연결 된 32 비트 응용 프로그램 특정 값을 반환 합니다.|  
|[CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex)|현재 트리 뷰 컨트롤의 지정된 된 항목 확장된 상태에 있을 때 표시할 이미지의 인덱스를 검색 합니다.|  
|[CTreeCtrl::GetItemHeight](#getitemheight)|트리 뷰 항목의 현재 높이 검색합니다.|  
|[CTreeCtrl::GetItemImage](#getitemimage)|항목에 연결 된 이미지를 검색 합니다.|  
|[CTreeCtrl::GetItemPartRect](#getitempartrect)|현재 트리 뷰 컨트롤에서 지정된 된 항목의 지정된 된 부분에 대 한 경계 사각형을 검색 합니다.|  
|[CTreeCtrl::GetItemRect](#getitemrect)|트리 뷰 항목의 경계 사각형을 검색합니다.|  
|[CTreeCtrl::GetItemState](#getitemstate)|항목의 상태를 반환합니다.|  
|[CTreeCtrl::GetItemStateEx](#getitemstateex)|현재 트리 뷰 컨트롤에서 지정된 된 항목의 확장 된 상태를 검색합니다.|  
|[CTreeCtrl::GetItemText](#getitemtext)|항목의 텍스트를 반환합니다.|  
|[CTreeCtrl::GetLastVisibleItem](#getlastvisibleitem)|현재 트리 뷰 컨트롤의 확장 된 마지막 항목을 검색합니다.|  
|[CTreeCtrl::GetLineColor](#getlinecolor)|트리 뷰 컨트롤에 대 한 현재 선 색을 검색합니다.|  
|[CTreeCtrl::GetNextItem](#getnextitem)|지정 된 관계와 일치 하는 다음 트리 뷰 항목을 검색 합니다.|  
|[CTreeCtrl::GetNextSiblingItem](#getnextsiblingitem)|지정 된 트리 뷰 항목의 다음 형제를 검색합니다.|  
|[CTreeCtrl::GetNextVisibleItem](#getnextvisibleitem)|지정 된 트리 뷰 항목의 표시 되는 다음 항목을 검색합니다.|  
|[CTreeCtrl::GetParentItem](#getparentitem)|지정 된 트리 뷰 항목의 부모를 검색합니다.|  
|[CTreeCtrl::GetPrevSiblingItem](#getprevsiblingitem)|지정 된 트리 뷰 항목의 이전 형제를 검색합니다.|  
|[CTreeCtrl::GetPrevVisibleItem](#getprevvisibleitem)|지정 된 트리 뷰 항목의 표시 되는 이전 항목을 검색합니다.|  
|[CTreeCtrl::GetRootItem](#getrootitem)|지정 된 트리 뷰 항목의 루트를 검색합니다.|  
|[CTreeCtrl::GetScrollTime](#getscrolltime)|트리 뷰 컨트롤에 대 한 최대 스크롤 시간을 검색 합니다.|  
|[CTreeCtrl::GetSelectedCount](#getselectedcount)|현재 트리 뷰 컨트롤에서 선택한 항목의 수를 가져옵니다.|  
|[CTreeCtrl::GetSelectedItem](#getselecteditem)|현재 선택 된 트리 뷰 항목을 검색합니다.|  
|[CTreeCtrl::GetTextColor](#gettextcolor)|컨트롤의 현재 텍스트 색을 검색합니다.|  
|[CTreeCtrl::GetToolTips](#gettooltips)|자식 트리 뷰 컨트롤에서 사용 하는 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|  
|[CTreeCtrl::GetVisibleCount](#getvisiblecount)|트리 뷰 컨트롤에 연결 된 표시 되는 트리 항목의 수를 검색 합니다.|  
|[CTreeCtrl::HitTest](#hittest)|와 관련 된 커서의 현재 위치를 반환 하는 `CTreeCtrl` 개체입니다.|  
|[CTreeCtrl::InsertItem](#insertitem)|트리 뷰 컨트롤에 새 항목을 삽입합니다.|  
|[CTreeCtrl::ItemHasChildren](#itemhaschildren)|지정된 된 항목에 자식 항목이 있으면&0;이 아닌 값을 반환 합니다.|  
|[CTreeCtrl::MapAccIdToItem](#mapaccidtoitem)|현재 트리 뷰 컨트롤의 트리 보기 항목에 대 한 핸들을 지정 된 내게 필요한 옵션 식별자를 매핑합니다.|  
|[CTreeCtrl::MapItemToAccID](#mapitemtoaccid)|내게 필요한 옵션 식별자에 현재 트리 뷰 컨트롤의 트리 보기 항목을 지정된 된 핸들을 매핑합니다.|  
|[CTreeCtrl::Select](#select)|선택 하 고, 스크롤되어 또는 지정 된 트리 뷰 항목을 다시 그립니다.|  
|[CTreeCtrl::SelectDropTarget](#selectdroptarget)|끌어서 놓기 작업의 대상으로 트리 항목을 다시 그립니다.|  
|[CTreeCtrl::SelectItem](#selectitem)|지정 된 트리 뷰 항목을 선택합니다.|  
|[CTreeCtrl::SelectSetFirstVisible](#selectsetfirstvisible)|표시 되는 첫 번째 항목으로 지정 된 트리 뷰 항목을 선택합니다.|  
|[CTreeCtrl::SetAutoscrollInfo](#setautoscrollinfo)|현재 트리 뷰 컨트롤의 자동 스크롤 속도 설정합니다.|  
|[CTreeCtrl::SetBkColor](#setbkcolor)|컨트롤의 배경색을 설정합니다.|  
|[CTreeCtrl::SetCheck](#setcheck)|트리 컨트롤 항목의 선택 상태를 설정 합니다.|  
|[CTreeCtrl::SetExtendedStyle](#setextendedstyle)|현재 트리 뷰 컨트롤에 대 한 확장된 스타일을 설정합니다.|  
|[CTreeCtrl::SetImageList](#setimagelist)|트리 뷰 컨트롤에 연결 된 이미지 목록의 처리를 설정 합니다.|  
|[CTreeCtrl::SetIndent](#setindent)|부모에서 오프셋 (픽셀 단위)의 트리 뷰 항목을 설정합니다.|  
|[CTreeCtrl::SetInsertMark](#setinsertmark)|트리 뷰 컨트롤에 삽입 표시를 설정합니다.|  
|[CTreeCtrl::SetInsertMarkColor](#setinsertmarkcolor)|트리 보기에 대 한 삽입 표시를 그리는 데 사용 되는 색을 설정 합니다.|  
|[CTreeCtrl::SetItem](#setitem)|지정 된 트리 보기 항목의 특성을 설정합니다.|  
|[CTreeCtrl::SetItemData](#setitemdata)|항목에 연결 된 32 비트 응용 프로그램 특정 값을 설정 합니다.|  
|[CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex)|현재 트리 뷰 컨트롤의 지정된 된 항목 확장된 상태에 있을 때 표시할 이미지의 인덱스를 설정 합니다.|  
|[CTreeCtrl::SetItemHeight](#setitemheight)|항목 보기 트리의 높이 설정합니다.|  
|[CTreeCtrl::SetItemImage](#setitemimage)|항목 이미지에 연결합니다.|  
|[CTreeCtrl::SetItemState](#setitemstate)|항목의 상태를 설정합니다.|  
|[CTreeCtrl::SetItemStateEx](#setitemstateex)|현재 트리 뷰 컨트롤에서 지정된 된 항목의 확장 된 상태를 설정합니다.|  
|[CTreeCtrl::SetItemText](#setitemtext)|항목의 텍스트를 설정합니다.|  
|[CTreeCtrl::SetLineColor](#setlinecolor)|트리 뷰 컨트롤에 대 한 현재 선 색을 설정합니다.|  
|[CTreeCtrl::SetScrollTime](#setscrolltime)|트리 뷰 컨트롤에 대 한 최대 스크롤 시간을 설정 합니다.|  
|[CTreeCtrl::SetTextColor](#settextcolor)|컨트롤의 텍스트 색을 설정합니다.|  
|[CTreeCtrl::SetToolTips](#settooltips)|트리 뷰 컨트롤의 자식 도구 설명 컨트롤을 설정합니다.|  
|[CTreeCtrl::ShowInfoTip](#showinfotip)|현재 트리 뷰 컨트롤에 지정된 된 항목에 대 한 정보 팁을 표시합니다.|  
|[CTreeCtrl::SortChildren](#sortchildren)|지정 된 부모 항목의 자식으로 정렬 합니다.|  
|[CTreeCtrl::SortChildrenCB](#sortchildrencb)|응용 프로그램 정의 정렬 함수를 사용 하 여 지정 된 부모 항목의 자식으로 정렬 합니다.|  
  
## <a name="remarks"></a>주의  
 "트리 뷰 컨트롤"는 디스크에 인덱스 또는 파일 및 디렉터리의 항목 머리글 문서를 같은 항목의 계층적 목록을 표시 하는 창입니다. 각 항목에 연결 된 하위 항목의 목록을 얻을 수와 각 항목 레이블 및 선택적 비트맵 이미지로 구성 됩니다. 항목을 클릭 하 여 사용자를 확장 하 고 목록을 축소 하 여 연결 된 하위 항목의 수 있습니다.  
  
 이 컨트롤 (및 따라서는 `CTreeCtrl` 클래스)은 이상 Windows 98 및 Windows NT 버전 4에서 실행 중인 프로그램에만 사용할 수 있습니다.  
  
 사용 하 여 대 한 자세한 내용은 `CTreeCtrl`를 참조 하십시오.  
  
- [컨트롤](../../mfc/controls-mfc.md)  
  
- [CTreeCtrl 사용](../../mfc/using-ctreectrl.md)  
  
- [트리 뷰 컨트롤 참조](http://msdn.microsoft.com/library/windows/desktop/bb759988) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
-   기술 자료 문서 Q222905: 방법: CTreeCtrl에 대 한 상황에 맞는 메뉴 표시  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTreeCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="a-namecreatea--ctreectrlcreate"></a><a name="create"></a>CTreeCtrl::Create  
 트리 컨트롤을 대화 상자 템플릿에 지정 하는 경우 또는 사용 중인 경우 [CTreeView](../../mfc/reference/ctreeview-class.md), 대화 상자 또는 보기를 만들 때 트리 컨트롤이 자동으로 만들어집니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 트리 뷰 컨트롤의 스타일을 지정합니다. 에 설명 된 창 스타일을 적용 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679), 및의 조합이 [트리 뷰 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760013) 에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 트리 뷰 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
 `pParentWnd`  
 일반적으로 부모 창의 트리 뷰 컨트롤의 지정 된 `CDialog`합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 트리 뷰 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 다른 창의 자식 창으로 트리 컨트롤을 만들려는 경우 사용 하 여는 **만들기** 멤버 함수입니다. 사용 하 여 트리 컨트롤을 만드는 경우 **만들기**를 전달 하면 **WS_VISIBLE**, 다른 트리 뷰 스타일 외에도 합니다.  
  
 생성 한 `CTreeCtrl` 두 단계에서입니다. 첫 번째 호출 생성자는 다음 호출 **만들기**, 트리 뷰 컨트롤을 만들고에 연결 하는 `CTreeCtrl` 개체입니다.  
  
 호출 트리 컨트롤이 확장된 창 스타일을 만들려면 [CreateEx](#createex) 대신 **만들기**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_1.cpp)]  
  
##  <a name="a-namecreateexa--ctreectrlcreateex"></a><a name="createex"></a>CTreeCtrl::CreateEx  
 컨트롤 (자식 창)을 만들고 사용 하 여 연결 하려면이 함수를 호출 하 여 `CTreeCtrl` 개체입니다.  
  
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
 생성 되는 컨트롤의 확장된 스타일을 지정 합니다. 확장된 창 스타일의 목록에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 트리 뷰 컨트롤의 스타일을 지정합니다. 에 설명 된 창 스타일을 적용 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679), 및의 조합이 [트리 뷰 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760013) 에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에서 만든 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 앞에 지정 된 Windows 확장된 스타일을 적용 하려면 **WS_EX_**합니다.  
  
##  <a name="a-namecreatedragimagea--ctreectrlcreatedragimage"></a><a name="createdragimage"></a>CTreeCtrl::CreateDragImage  
 지정된 된 항목에 대 한 끌기 비트맵을 트리 뷰 컨트롤에는 비트맵에 대 한 이미지 목록 및 만든 비트맵 이미지 목록에 추가 하려면이 함수를 호출 합니다.  
  
```  
CImageList* CreateDragImage(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 핸들을 끌어 놓을 수 트리 항목입니다.  
  
### <a name="return-value"></a>반환 값  
 끌기 비트맵 추가 된, 성공 하면 이미지 목록에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 항목을 끌어올 때 이미지를 표시 하려면 이미지 목록 기능을 사용 하는 응용 프로그램입니다.  
  
 `CImageList` 개체, 영구 적용 되며 완료 되 면 삭제 해야 합니다. 예:  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #&2;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_2.cpp)]  
  
##  <a name="a-namectreectrla--ctreectrlctreectrl"></a><a name="ctreectrl"></a>CTreeCtrl::CTreeCtrl  
 `CTreeCtrl` 개체를 생성합니다.  
  
```  
CTreeCtrl();
```  
  
##  <a name="a-namedeleteallitemsa--ctreectrldeleteallitems"></a><a name="deleteallitems"></a>CTreeCtrl::DeleteAllItems  
 트리 뷰 컨트롤에서 모든 항목을 삭제 하려면이 함수를 호출 합니다.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&3;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_3.cpp)]  
  
##  <a name="a-namedeleteitema--ctreectrldeleteitem"></a><a name="deleteitem"></a>CTreeCtrl::DeleteItem  
 트리 뷰 컨트롤에서 항목을 삭제 하려면이 함수를 호출 합니다.  
  
```  
BOOL DeleteItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 삭제할 트리 항목의 핸들입니다. 경우 *hitem* 에 **TVI_ROOT** 값, 트리 뷰 컨트롤에서 모든 항목이 삭제 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&4;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_4.cpp)]  
  
##  <a name="a-nameeditlabela--ctreectrleditlabel"></a><a name="editlabel"></a>CTreeCtrl::EditLabel  
 지정된 된 항목 텍스트의 내부 편집을 시작 하려면이 함수를 호출 합니다.  
  
```  
CEdit* EditLabel(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목을 편집할 수의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우에 대 한 포인터는 `CEdit` 항목 텍스트를 편집 하는 데 사용 하 고, 그렇지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 편집 된 텍스트를 포함 하는 한 줄 편집 컨트롤 항목의 텍스트를 대체 하 여 수행 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_5.cpp)]  
  
##  <a name="a-nameendeditlabelnowa--ctreectrlendeditlabelnow"></a><a name="endeditlabelnow"></a>CTreeCtrl::EndEditLabelNow  
 현재 트리 뷰 컨트롤의 트리 보기 항목의 레이블에 대 한 편집 작업을 완료 했습니다.  
  
```  
BOOL EndEditLabelNow(BOOL fCancelWithoutSave);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `fCancelWithoutSave`|`true`편집 작업을 마치기 전에 트리 보기 항목의 변경 내용을 취소 하려면 또는 `false` 트리 뷰 항목 작업을 마치기 전에 변경 내용을 저장 하려면.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_ENDEDITLABELNOW](http://msdn.microsoft.com/library/windows/desktop/bb773564) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameensurevisiblea--ctreectrlensurevisible"></a><a name="ensurevisible"></a>CTreeCtrl::EnsureVisible  
 트리 뷰 항목을 표시 되어 있는지 확인 하려면이 함수를 호출 합니다.  
  
```  
BOOL EnsureVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 되 고 표시 된 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 시스템이 지정된 된 항목 표시 되어 있는지 확인 하려면 트리 뷰 컨트롤의 항목 스크롤됩니다. 그렇지 않으면 반환 값은 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 필요한 경우 함수 부모 항목을 확장 하거나 항목을 볼 수 있도록 트리 뷰 컨트롤을 스크롤합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_6.cpp)]  
  
##  <a name="a-nameexpanda--ctreectrlexpand"></a><a name="expand"></a>CTreeCtrl::Expand  
 지정 된 부모 항목과 연결 하는 경우 자식 항목의 목록을 확장 하거나 축소 하려면이 함수를 호출 합니다.  
  
```  
BOOL Expand(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 확장 하 고 트리 항목의 핸들입니다.  
  
 `nCode`  
 수행할 동작의 유형을 나타내는 플래그입니다. 이 플래그는 다음 값 중 하나일 수 있습니다.  
  
- `TVE_COLLAPSE`목록을 축소합니다.  
  
- `TVE_COLLAPSERESET`목록을 축소 하 고 자식 항목을 제거 합니다. **TVIS_EXPANDEDONCE** 상태 플래그를 다시 설정 합니다. 이 플래그를 함께 사용 해야는 `TVE_COLLAPSE` 플래그입니다.  
  
- `TVE_EXPAND`목록을 확장 합니다.  
  
- `TVE_TOGGLE`현재 확장 되어 있거나 현재 축소 되어 있으면 확장 목록을 축소 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::EnsureVisible](#ensurevisible)합니다.  
  
##  <a name="a-namegetbkcolora--ctreectrlgetbkcolor"></a><a name="getbkcolor"></a>CTreeCtrl::GetBkColor  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_GETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773570)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 컨트롤에 대 한 현재 창 배경색을 나타내는 값입니다. 이 값이-1 인 경우는 컨트롤이 사용 하 고 시스템 창 색입니다. 이 경우에 사용할 수 있습니다 `::GetSysColor(COLOR_WINDOW)` 컨트롤을 사용 하 여 현재 시스템 색상을 얻으려고 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::SetTextColor](#settextcolor)합니다.  
  
##  <a name="a-namegetchecka--ctreectrlgetcheck"></a><a name="getcheck"></a>CTreeCtrl::GetCheck  
 항목의 선택 상태를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL GetCheck(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 **HTREEITEM** 대 한 상태 정보를 얻습니다.  
  
### <a name="return-value"></a>반환 값  
 트리 컨트롤 항목 선택 되는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::SetCheck](#setcheck)합니다.  
  
##  <a name="a-namegetchilditema--ctreectrlgetchilditem"></a><a name="getchilditem"></a>CTreeCtrl::GetChildItem  
 호출 트리를 검색 하려면이 함수는 항목 보기에 지정 된 항목의 자식인 `hItem`합니다.  
  
```  
HTREEITEM GetChildItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 자식 항목의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&7;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_7.cpp)]  
  
##  <a name="a-namegetcounta--ctreectrlgetcount"></a><a name="getcount"></a>CTreeCtrl::GetCount  
 트리 뷰 컨트롤에 있는 항목의 개수를 검색 하려면이 함수를 호출 합니다.  
  
```  
UINT GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 트리 뷰 컨트롤의 항목 수를 지정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&8;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_8.cpp)]  
  
##  <a name="a-namegetdrophilightitema--ctreectrlgetdrophilightitem"></a><a name="getdrophilightitem"></a>CTreeCtrl::GetDropHilightItem  
 끌어서 놓기 작업의 대상이 되는 항목을 검색 하려면이 함수를 호출 합니다.  
  
```  
HTREEITEM GetDropHilightItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 삭제 된 항목의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="a-namegeteditcontrola--ctreectrlgeteditcontrol"></a><a name="geteditcontrol"></a>CTreeCtrl::GetEditControl  
 트리 보기 항목의 텍스트를 편집 하는 데 사용 되는 편집 컨트롤의 핸들을 검색 하려면이 함수를 호출 합니다.  
  
```  
CEdit* GetEditControl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 항목 텍스트를 편집 하는 데 편집 컨트롤에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&10;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_10.cpp)]  
  
##  <a name="a-namegetextendedstylea--ctreectrlgetextendedstyle"></a><a name="getextendedstyle"></a>CTreeCtrl::GetExtendedStyle  
 현재 트리 뷰 컨트롤을 사용 하는 확장된 스타일을 검색 합니다.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 트리 뷰 컨트롤의 비트 조합 (OR)을 포함 하는 값의 스타일을 연장 합니다. 자세한 내용은 참조 [트리 뷰 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759981)합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_GETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773580) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetfirstvisibleitema--ctreectrlgetfirstvisibleitem"></a><a name="getfirstvisibleitem"></a>CTreeCtrl::GetFirstVisibleItem  
 트리 뷰 컨트롤의 표시 되는 첫 번째 항목을 검색 하려면이 함수를 호출 합니다.  
  
```  
HTREEITEM GetFirstVisibleItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 첫 번째 표시 되는 항목;의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::SetCheck](#setcheck)합니다.  
  
##  <a name="a-namegetimagelista--ctreectrlgetimagelist"></a><a name="getimagelist"></a>CTreeCtrl::GetImageList  
 트리 뷰 컨트롤과 연결 된 상태 이미지 목록 또는 보통의 핸들을 검색 하려면이 함수를 호출 합니다.  
  
```  
CImageList* GetImageList(UINT nImageList) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nImageList`  
 이미지 목록 검색 하려면의 형식입니다. 이미지 목록의 다음 값 중 하나일 수 있습니다.  
  
- `TVSIL_NORMAL`트리 뷰 항목에 대 한 선택 되 고 선택 되지 않은 이미지를 포함 하는 일반 이미지 목록을 검색 합니다.  
  
- `TVSIL_STATE`사용자 정의 상태에 있는 트리 뷰 항목에 대 한 이미지를 포함 하는 상태 이미지 목록을 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 컨트롤의 이미지 목록에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 트리 뷰 컨트롤의 각 항목에는 한 쌍의 관련 된 비트맵 이미지 있을 수 있습니다. 항목을 선택 하 고 항목을 선택 하지 않은 경우 표시 되 면 다른 이미지 표시 됩니다. 예를 들어, 선택 하지 않은 경우 선택 된 폴더를 열어와 닫힌된 폴더 항목 표시 될 수 있습니다.  
  
 이미지 목록에 대 한 자세한 내용은 참조는 [CImageList](../../mfc/reference/cimagelist-class.md) 클래스입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&11;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_11.cpp)]  
  
##  <a name="a-namegetindenta--ctreectrlgetindent"></a><a name="getindent"></a>CTreeCtrl::GetIndent  
 크기를 픽셀 단위로 해당 자식 항목에 부모 항목을 기준으로 들여쓰기 됩니다를 검색 하려면이 함수를 호출 합니다.  
  
```  
UINT GetIndent() const;  
```  
  
### <a name="return-value"></a>반환 값  
 들여쓰기의 크기를 픽셀 단위로 지정 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&12;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_12.cpp)]  
  
##  <a name="a-namegetinsertmarkcolora--ctreectrlgetinsertmarkcolor"></a><a name="getinsertmarkcolor"></a>CTreeCtrl::GetInsertMarkColor  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773590)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 현재 삽입 표시 색을 포함 하는 값입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&13;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_13.cpp)]  
  
##  <a name="a-namegetitema--ctreectrlgetitem"></a><a name="getitem"></a>CTreeCtrl::GetItem  
 지정 된 트리 뷰 항목의 특성을 검색 하려면이 함수를 호출 합니다.  
  
```  
BOOL GetItem(TVITEM* pItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 에 대 한 포인터는 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 구조체에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::DeleteItem](#deleteitem)합니다.  
  
##  <a name="a-namegetitemdataa--ctreectrlgetitemdata"></a><a name="getitemdata"></a>CTreeCtrl::GetItemData  
 지정 된 항목과 연결 된 32 비트 응용 프로그램 특정 값을 검색 하려면이 함수를 호출 합니다.  
  
```  
DWORD_PTR GetItemData(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 데이터가 검색 된 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 32 비트 응용 프로그램 관련 값으로 지정 된 항목과 연결 된 `hItem`합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&14;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_14.cpp)]  
  
##  <a name="a-namegetitemexpandedimageindexa--ctreectrlgetitemexpandedimageindex"></a><a name="getitemexpandedimageindex"></a>CTreeCtrl::GetItemExpandedImageIndex  
 현재 트리 뷰 컨트롤의 지정된 된 항목 확장된 상태에 있을 때 표시할 이미지의 인덱스를 검색 합니다.  
  
```  
int GetItemExpandedImageIndex(HTREEITEM hItem)const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `hItem`|트리 뷰 컨트롤 항목에 대 한 핸들입니다.|  
  
### <a name="return-value"></a>반환 값  
 지정 된 항목이 확장 된 상태에 있을 때 표시할 이미지의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 반환 하는 메시지는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조는 트리 뷰 컨트롤 항목 및이 메서드를 설명 하는 검색에서 `iExpandedImage` 해당 구조에서 멤버입니다.  
  
##  <a name="a-namegetitemheighta--ctreectrlgetitemheight"></a><a name="getitemheight"></a>CTreeCtrl::GetItemHeight  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_GETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773599)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
SHORT GetItemHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위로 항목의 높이입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&15;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_15.cpp)]  
  
##  <a name="a-namegetitemimagea--ctreectrlgetitemimage"></a><a name="getitemimage"></a>CTreeCtrl::GetItemImage  
 트리 뷰 컨트롤의 각 항목에는 한 쌍의 관련 된 비트맵 이미지 있을 수 있습니다.  
  
```  
BOOL GetItemImage(
    HTREEITEM hItem,  
    int& nImage,  
    int& nSelectedImage) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 핸들을 검색할 수 있는 이미지는 항목입니다.  
  
 `nImage`  
 트리 뷰 컨트롤의 이미지 목록 내에서 항목의 이미지의 인덱스를 수신 하는 정수입니다.  
  
 `nSelectedImage`  
 트리 뷰 컨트롤의 이미지 목록 내에서 항목의 선택 된 이미지의 인덱스를 수신 하는 정수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이미지 항목의 레이블 왼쪽에 나타납니다. 항목을 선택 하 고 항목을 선택 하지 않은 경우 표시 되 면 다른 이미지 표시 됩니다. 예를 들어, 선택 하지 않은 경우 선택 된 폴더를 열어와 닫힌된 폴더 항목 표시 될 수 있습니다.  
  
 항목의 이미지 및 트리 뷰 컨트롤의 이미지 목록 내에서 선택 된 이미지의 인덱스를 검색 하려면이 함수를 호출 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&16;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_16.cpp)]  
  
##  <a name="a-namegetitempartrecta--ctreectrlgetitempartrect"></a><a name="getitempartrect"></a>CTreeCtrl::GetItemPartRect  
 현재 트리 뷰 컨트롤에서 지정된 된 항목의 지정된 된 부분에 대 한 경계 사각형을 검색 합니다.  
  
```  
BOOL GetItemPartRect(
    HTREEITEM hItem,   
    int nPart,   
    LPRECT lpRect)const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `hItem`|트리 뷰 컨트롤 항목에 대 한 핸들입니다.|  
|[in] `nPart`|파트에 대 한 식별자입니다. 로 설정 해야 `TVGIPR_BUTTON`합니다.|  
|[out] `lpRect`|에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다. 이 메서드가 성공적 이면 구조 좌표가 사각형으로 지정 된 파트의 `hItem` 및 `nPart`합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 각 트리 컨트롤 항목 그래픽 사각형에 의해 제한 됩니다. 특정 시점으로, 해당 사각형을 클릭할 때마다 항목 이라고 *적중*합니다. 이 메서드는 사각형에 포인트를 클릭할 때, 식별 되는 항목 가장 큰 사각형을 반환 된 `hItem` 매개 변수는 적중 합니다.  
  
 이 메서드는 전송 된 `TVM_GETITEMPARTRECT` 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 자세한 내용은 참조는 [TreeView_GetItemPartRect](http://msdn.microsoft.com/library/windows/desktop/bb773847) 매크로입니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 이러한 변수는 다음 예제에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 내게 필요한 옵션 식별자를 사용 하 고 [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) 루트 트리 보기 항목에 대 한 핸들을 검색 하는 메서드입니다. 다음 예제에서는 핸들을 사용 및 [CTreeCtrl::GetItemPartRect](#getitempartrect) 메서드를 해당 항목 주위 3D 사각형을 그립니다. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다. 사용 된 [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) 내게 필요한 옵션 식별자를 가진 루트 트리 보기 항목을 연결 하는 방법이 있습니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="a-namegetitemrecta--ctreectrlgetitemrect"></a><a name="getitemrect"></a>CTreeCtrl::GetItemRect  
 에 대 한 경계 사각형을 검색 하려면이 함수를 호출 `hItem` 인지 확인 표시 여부 및 합니다.  
  
```  
BOOL GetItemRect(
    HTREEITEM hItem,  
    LPRECT lpRect,  
    BOOL bTextOnly) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 뷰 컨트롤 항목의 핸들입니다.  
  
 `lpRect`  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조체는 경계 사각형입니다. 좌표는 트리 뷰 컨트롤의 왼쪽 위 모퉁이 기준으로 합니다.  
  
 *bTextOnly*  
 이 매개 변수가&0;이 아닌 경우에 경계 사각형 항목의 텍스트에만 포함 되어 있습니다. 그렇지 않으면 트리 뷰 컨트롤에 항목을 차지 하는 줄 전체를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 포함 된 경계 사각형에 항목을 표시할지,&0;이 아닌 `lpRect`합니다. 그렇지 않으면 0을 `lpRect` 초기화 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&17;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_19.cpp)]  
  
##  <a name="a-namegetitemstatea--ctreectrlgetitemstate"></a><a name="getitemstate"></a>CTreeCtrl::GetItemState  
 지정 된 항목의 상태를 반환 `hItem`합니다.  
  
```  
UINT GetItemState(
    HTREEITEM hItem,  
    UINT nStateMask) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 상태가 검색할 항목의 핸들입니다.  
  
 `nStateMask`  
 검색할 하나 이상의 상태를 나타내는 마스크입니다. 에 대 한 가능한 값에 대 한 자세한 내용은 `nStateMask`의 설명을 참조는 **상태** 및 **stateMask** 의 멤버는 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 A **UINT** nStateMask 하 여 지정 된 값의 비트 OR를 보유 하는 합니다. 가능한 값에 대 한 자세한 내용은 참조 [CTreeCtrl::GetItem](#getitem)합니다. 특정 상태에 대 한 값을 찾으려면 다음 예와에서 같이 상태 값 및 반환 값의 비트 AND 연산을 수행 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&18;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_20.cpp)]  
  
##  <a name="a-namegetitemstateexa--ctreectrlgetitemstateex"></a><a name="getitemstateex"></a>CTreeCtrl::GetItemStateEx  
 현재 트리 뷰 컨트롤에서 지정된 된 항목의 확장 된 상태를 검색합니다.  
  
```  
UINT GetItemStateEx(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `hItem`|트리 뷰 컨트롤 항목에 대 한 핸들입니다.|  
  
### <a name="return-value"></a>반환 값  
 항목의 확장 된 상태입니다. 자세한 내용은 참조는 `uStateEx` 의 멤버는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773596) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 반환 하는 메시지는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조는 트리 뷰 컨트롤 항목 및이 메서드를 설명 하는 검색에서 `uStateEx` 해당 구조에서 멤버입니다.  
  
##  <a name="a-namegetitemtexta--ctreectrlgetitemtext"></a><a name="getitemtext"></a>CTreeCtrl::GetItemText  
 지정 된 항목의 텍스트를 반환 `hItem`합니다.  
  
```  
CString GetItemText(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 핸들을 검색할 수 있는 텍스트는 항목입니다.  
  
### <a name="return-value"></a>반환 값  
 A `CString` 항목의 텍스트를 포함 하는 개체입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetNextItem](#getnextitem)합니다.  
  
##  <a name="a-namegetlastvisibleitema--ctreectrlgetlastvisibleitem"></a><a name="getlastvisibleitem"></a>CTreeCtrl::GetLastVisibleItem  
 현재 트리 뷰 컨트롤에서 마지막 노드를 확장 되지 않은 항목을 검색합니다.  
  
```  
HTREEITEM GetLastVisibleItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 마지막 노드를 확장 되지 않은 항목에 대 한 핸들 그렇지 않으면 `NULL`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_GETNEXTITEM](http://msdn.microsoft.com/library/windows/desktop/bb773622) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 자세한 내용은 참조는 `TVGN_LASTVISIBLE` 플래그는 `flag` 해당 메시지의 매개 변수입니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 다음 예제에는 이러한 변수 중 하나 이상이 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 마지막 확장 되지 않은 트리 뷰 노드 항목에 대 한 핸들을 검색 하 고 해당 항목 주위에 3D 사각형을 그립니다. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&6;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_21.cpp)]  
  
##  <a name="a-namegetlinecolora--ctreectrlgetlinecolor"></a><a name="getlinecolor"></a>CTreeCtrl::GetLineColor  
 이 멤버 함수는 win32 메시지의 동작을 구현 [TVM_GETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773619)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
COLORREF GetLineColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선 색입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&19;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_22.cpp)]  
  
##  <a name="a-namegetnextitema--ctreectrlgetnextitem"></a><a name="getnextitem"></a>CTreeCtrl::GetNextItem  
 호출 트리를 검색 하려면이 함수는 항목 보기에 표시 하 여 지정된 된 관계는 `nCode` 매개 변수를 `hItem`합니다.  
  
```  
HTREEITEM GetNextItem(
    HTREEITEM hItem,  
    UINT nCode) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
 `nCode`  
 관계의 종류를 나타내는 플래그 `hItem`합니다. 이 플래그는 다음 값 중 하나일 수 있습니다.  
  
- `TVGN_CARET`현재 선택한 항목을 검색합니다.  
  
- `TVGN_CHILD`지정 된 항목의 첫 번째 자식 항목을 검색 된 `hItem` 매개 변수입니다.  
  
- `TVGN_DROPHILITE`끌어서 놓기 작업의 대상이 되는 항목을 검색 합니다.  
  
- `TVGN_FIRSTVISIBLE`표시 되는 첫 번째 항목을 검색합니다.  
  
- `TVGN_LASTVISIBLE`트리에서 확장 된 마지막 항목을 검색합니다. 이 트리 보기 창에 보이는 마지막 항목을 검색 하지 않습니다.  
  
- `TVGN_NEXT`다음 형제 항목을 검색합니다.  
  
- `TVGN_NEXTVISIBLE`지정된 된 항목 다음에 나오는 다음 표시 항목을 검색 합니다.  
  
- `TVGN_PARENT`지정된 된 항목의 부모를 검색합니다.  
  
- `TVGN_PREVIOUS`이전 형제 항목을 검색합니다.  
  
- `TVGN_PREVIOUSVISIBLE`지정된 된 항목을 앞에 오는 첫 번째 표시 항목을 검색 합니다.  
  
- `TVGN_ROOT`지정된 된 항목은 일부 루트 항목의 첫 번째 자식 항목을 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 다음 항목의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 반환 **NULL** 검색 되는 항목 트리의 루트 노드인 경우. 예를 들어,이 메시지를 사용 하는 경우는 `TVGN_PARENT` 메시지가 반환 됩니다 트리 뷰의 루트 노드의 첫 번째 수준 자식에 플래그 **NULL**합니다.  
  
### <a name="example"></a>예제  
 사용 하는 예제에 대 한 `GetNextItem` 루프에서 참조 [CTreeCtrl::DeleteItem](#deleteitem)합니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #&20;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_23.cpp)]  
  
##  <a name="a-namegetnextsiblingitema--ctreectrlgetnextsiblingitem"></a><a name="getnextsiblingitem"></a>CTreeCtrl::GetNextSiblingItem  
 다음 형제를 검색 하려면이 함수를 호출 `hItem`합니다.  
  
```  
HTREEITEM GetNextSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 다음 형제 항목;의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&21;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_24.cpp)]  
  
##  <a name="a-namegetnextvisibleitema--ctreectrlgetnextvisibleitem"></a><a name="getnextvisibleitem"></a>CTreeCtrl::GetNextVisibleItem  
 표시 되는 다음 항목을 검색 하려면이 함수를 호출 `hItem`합니다.  
  
```  
HTREEITEM GetNextVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 핸들을 다음 표시 되는 항목입니다. 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::SetCheck](#setcheck)합니다.  
  
##  <a name="a-namegetparentitema--ctreectrlgetparentitem"></a><a name="getparentitem"></a>CTreeCtrl::GetParentItem  
 부모를 검색 하려면이 함수를 호출 `hItem`합니다.  
  
```  
HTREEITEM GetParentItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 핸들을 부모 항목입니다. 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 반환 **NULL** 지정된 된 항목의 부모는 트리의 루트 노드인 경우.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::EnsureVisible](#ensurevisible)합니다.  
  
##  <a name="a-namegetprevsiblingitema--ctreectrlgetprevsiblingitem"></a><a name="getprevsiblingitem"></a>CTreeCtrl::GetPrevSiblingItem  
 이전 형제를 검색 하려면이 함수를 호출 `hItem`합니다.  
  
```  
HTREEITEM GetPrevSiblingItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 형제; 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&22;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_25.cpp)]  
  
##  <a name="a-namegetprevvisibleitema--ctreectrlgetprevvisibleitem"></a><a name="getprevvisibleitem"></a>CTreeCtrl::GetPrevVisibleItem  
 표시 되는 이전 항목을 검색 하려면이 함수를 호출 `hItem`합니다.  
  
```  
HTREEITEM GetPrevVisibleItem(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 핸들을 이전 표시 되는 항목입니다. 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl&23;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_26.cpp)]  
  
##  <a name="a-namegetrootitema--ctreectrlgetrootitem"></a><a name="getrootitem"></a>CTreeCtrl::GetRootItem  
 트리 뷰 컨트롤의 루트 항목을 검색 하려면이 함수를 호출 합니다.  
  
```  
HTREEITEM GetRootItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 루트 항목;의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::EditLabel](#editlabel)합니다.  
  
##  <a name="a-namegetscrolltimea--ctreectrlgetscrolltime"></a><a name="getscrolltime"></a>CTreeCtrl::GetScrollTime  
 트리 뷰 컨트롤에 대 한 최대 스크롤 시간을 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
UINT GetScrollTime() const;  
```  
  
### <a name="return-value"></a>반환 값  
 스크롤 최대 시간 (밀리초)입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 win32 메시지의 동작을 구현 [TVM_GETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773625)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetselectedcounta--ctreectrlgetselectedcount"></a><a name="getselectedcount"></a>CTreeCtrl::GetSelectedCount  
 현재 트리 뷰 컨트롤에서 선택한 항목의 수를 가져옵니다.  
  
```  
UINT GetSelectedCount();
```  
  
### <a name="return-value"></a>반환 값  
 선택한 항목의 수입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_GETSELECTEDCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb773629) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetselecteditema--ctreectrlgetselecteditem"></a><a name="getselecteditem"></a>CTreeCtrl::GetSelectedItem  
 트리 뷰 컨트롤의 현재 선택 된 항목을 검색 하려면이 함수를 호출 합니다.  
  
```  
HTREEITEM GetSelectedItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 항목;의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&24;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_27.cpp)]  
  
##  <a name="a-namegettextcolora--ctreectrlgettextcolor"></a><a name="gettextcolor"></a>CTreeCtrl::GetTextColor  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_GETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773633)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 현재 텍스트 색을 나타내는 값입니다. 이 값이-1 이면 컨트롤 텍스트 색에 대 한 시스템 색 사용 중인.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::SetTextColor](#settextcolor)합니다.  
  
##  <a name="a-namegettooltipsa--ctreectrlgettooltips"></a><a name="gettooltips"></a>CTreeCtrl::GetToolTips  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773729)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 트리 컨트롤에서 사용할 개체입니다. 경우는 [만들기](#create) 스타일을 사용 하는 멤버 함수 **TVS_NOTOOLTIPS**, 도구 설명 없음 사용 되 고 **NULL** 반환 됩니다.  
  
### <a name="remarks"></a>주의  
 MFC 구현 `GetToolTips` 반환는 `CToolTipCtrl` 도구 설명 컨트롤에 대 한 핸들 보다는 트리 컨트롤에서 사용 되는 개체입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&25;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_28.cpp)]  
  
##  <a name="a-namegetvisiblecounta--ctreectrlgetvisiblecount"></a><a name="getvisiblecount"></a>CTreeCtrl::GetVisibleCount  
 트리 뷰 컨트롤에 표시 되는 항목의 개수를 검색 하려면이 함수를 호출 합니다.  
  
```  
UINT GetVisibleCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 트리 뷰 컨트롤에서 표시 된 항목의 수 그렇지 않으면-1입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::SetCheck](#setcheck)합니다.  
  
##  <a name="a-namehittesta--ctreectrlhittest"></a><a name="hittest"></a>CTreeCtrl::HitTest  
 트리 뷰 컨트롤의 클라이언트 영역을 기준으로 지정된 된 지점의 위치를 확인 하려면이 함수를 호출 합니다.  
  
```  
HTREEITEM HitTest(
    CPoint pt,  
    UINT* pFlags = NULL) const;  
  
HTREEITEM HitTest(TVHITTESTINFO* pHitTestInfo) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 테스트할 점의 좌표를 클라이언트입니다.  
  
 `pFlags`  
 적중된 테스트의 결과 대 한 정보를 수신 하는 정수에 대 한 포인터입니다. 아래에 나열 된 값 이나 하나 할 수는 **플래그** 주의 섹션에는 멤버입니다.  
  
 `pHitTestInfo`  
 주소에 [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) 적중된 테스트의 결과 대 한 정보를 수신 하는 적중 테스트에 위치를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 위치를 차지 하는 트리 뷰 항목의 핸들 또는 **NULL** 시점을 차지 하는 항목이 없는 경우.  
  
### <a name="remarks"></a>주의  
 이 함수를 호출 하는 경우는 `pt` 매개 변수는 테스트할 점의 좌표를 지정 합니다. 지정된 된 지점에 있는 항목의 핸들을 반환 하는 함수 또는 **NULL** 시점을 차지 하는 항목이 없는 경우. 또한는 `pFlags` 매개 변수에 지정 된 지점의 위치를 나타내는 값을 포함 합니다. 가능한 값은 다음과 같습니다.  
  
|||  
|-|-|  
|값|의미|  
|TVHT_ABOVE|클라이언트 영역 위쪽에 있습니다.|  
|TVHT_BELOW|아래 클라이언트 영역입니다.|  
|TVHT_NOWHERE|클라이언트 영역에서 하지만 마지막 항목 아래에 있습니다.|  
|TVHT_ONITEM|비트맵 또는 항목에 연결 된 레이블 합니다.|  
|TVHT_ONITEMBUTTON|항목에 연결 된 단추입니다.|  
|TVHT_ONITEMICON|항목에 연결 된 비트맵입니다.|  
|TVHT_ONITEMINDENT|항목에 연결 된 들여쓰기입니다.|  
|TVHT_ONITEMLABEL|항목에 연결 된의 레이블 (string).|  
|TVHT_ONITEMRIGHT|항목의 오른쪽 영역입니다.|  
|TVHT_ONITEMSTATEICON|사용자 정의 상태에 있는 트리 뷰 항목에 대 한 상태 아이콘입니다.|  
|TVHT_TOLEFT|클라이언트 영역의 왼쪽입니다.|  
|TVHT_TORIGHT|클라이언트 영역을 합니다.|  
|||  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="a-nameinsertitema--ctreectrlinsertitem"></a><a name="insertitem"></a>CTreeCtrl::InsertItem  
 트리 뷰 컨트롤에 새 항목을 삽입 하려면이 함수를 호출 합니다.  
  
```  
HTREEITEM InsertItem(LPTVINSERTSTRUCT lpInsertStruct);

 
HTREEITEM InsertItem(
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam,  
    HTREEITEM hParent,  
    HTREEITEM hInsertAfter);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);

 
HTREEITEM InsertItem(
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    HTREEITEM hParent = TVI_ROOT,  
    HTREEITEM hInsertAfter = TVI_LAST);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpInsertStruct*  
 에 대 한 포인터는 `TVINSERTSTRUCT` 트리 보기 항목을 삽입할 수의 특성을 지정 하는 합니다.  
  
 `nMask`  
 설정 하는 특성을 지정 하는 정수입니다. 참조는 `TVITEM` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `lpszItem`  
 항목의 텍스트를 포함 하는 문자열의 주소입니다.  
  
 `nImage`  
 트리 뷰 컨트롤의 이미지 목록에서 항목의 이미지의 인덱스입니다.  
  
 `nSelectedImage`  
 트리 뷰 컨트롤의 이미지 목록에서 항목의 선택 된 이미지의 인덱스입니다.  
  
 `nState`  
 항목의 상태에 대 한 값을 지정합니다. 참조 트리 뷰 컨트롤 항목 상태에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 목록은 적절 한 상태입니다.  
  
 `nStateMask`  
 설정할 수 있는 상태 지정 합니다. 참조는 `TVITEM` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `lParam`  
 항목에 연결 된 32 비트 응용 프로그램 관련 값입니다.  
  
 `hParent`  
 삽입된 된 항목의 부모의 핸들입니다.  
  
 *hInsertAfter*  
 이후에 새 항목이 삽입 되는 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 새 항목의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 이 예제에서는 트리 컨트롤 항목을 삽입 하는 경우 각 버전의 함수를 사용 하 여 할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&27;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_30.cpp)]  
  
##  <a name="a-nameitemhaschildrena--ctreectrlitemhaschildren"></a><a name="itemhaschildren"></a>CTreeCtrl::ItemHasChildren  
 이 함수를 사용 하 여 트리 항목으로 지정 되었는지 여부를 확인 하려면 `hItem` 이 하위 항목입니다.  
  
```  
BOOL ItemHasChildren(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 트리 항목으로 지정 된 경우 0이 아닌 `hItem` 에 자식 항목이 고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 따라서 사용할 수 있는 경우 다음 [CTreeCtrl::GetChildItem](#getchilditem) 해당 자식 항목을 검색 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetSelectedItem](#getselecteditem)합니다.  
  
##  <a name="a-namemapaccidtoitema--ctreectrlmapaccidtoitem"></a><a name="mapaccidtoitem"></a>CTreeCtrl::MapAccIdToItem  
 현재 트리 뷰 컨트롤의 트리 보기 항목의 핸들을 지정 된 내게 필요한 옵션 식별자를 매핑합니다.  
  
```  
HTREEITEM MapAccIdToItem(UINT uAccId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `uAccId`|트리 뷰 항목에 있는 요소에 대 한 내게 필요한 옵션 식별자입니다.|  
  
### <a name="return-value"></a>반환 값  
 트리 보기 항목에 대 한 핸들 ( `HTREEITEM`)에 해당 하는 `uAccId` 매개 변수입니다. 자세한 내용은 참조는 `hItem` 의 멤버는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조입니다.  
  
### <a name="remarks"></a>주의  
 내게 필요한 옵션 도구는 장애가 있는 사용자는 데 도움이 되는 응용 프로그램 컴퓨터를 사용 합니다. 내게 필요한 옵션 식별자에서 사용 되는 `IAccessible` 창에서 요소를 고유 하 게 지정 하는 인터페이스입니다. 내게 필요한 옵션 식별자에 대 한 자세한 내용은 "에 대 한 활성 내게 필요한 옵션 지원" 항목에 대 한 검색 [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322)합니다.  
  
 이 메서드는 전송 된 [TVM_MAPACCIDTOHTREEITEM](http://msdn.microsoft.com/library/windows/desktop/bb773734) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 이러한 변수는 다음 예제에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 내게 필요한 옵션 식별자를 사용 하 고 [CTreeCtrl::MapAccIdToItem](#mapaccidtoitem) 루트 트리 보기 항목에 대 한 핸들을 검색 하는 메서드입니다. 이 예제에서는 핸들을 사용 및 [CTreeCtrl::GetItemPartRect](#getitempartrect) 해당 항목 둘레 3D 사각형을 그리는 메서드. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다. 사용 된 [CTreeCtrl::MapItemToAccID](#mapitemtoaccid) 내게 필요한 옵션 식별자를 가진 루트 트리 보기 항목을 연결 하는 방법이 있습니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&5;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_18.cpp)]  
  
##  <a name="a-namemapitemtoaccida--ctreectrlmapitemtoaccid"></a><a name="mapitemtoaccid"></a>CTreeCtrl::MapItemToAccID  
 현재 트리 뷰 컨트롤의 트리 보기 항목의 지정된 된 핸들을 내게 필요한 옵션 식별자에 매핑합니다.  
  
```  
UINT MapItemToAccID(HTREEITEM hItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `hItem`|컨트롤의 트리 보기 항목의 핸들입니다. 자세한 내용은 참조는 `hItem` 의 멤버는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 에 해당 하는 내게 필요한 옵션 식별자는 `hItem` 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 내게 필요한 옵션 도구는 장애가 있는 사용자는 데 도움이 되는 응용 프로그램 컴퓨터를 사용 합니다. 내게 필요한 옵션 식별자에서 사용 되는 `IAccessible` 창에서 요소를 고유 하 게 지정 하는 인터페이스입니다. 내게 필요한 옵션 식별자에 대 한 자세한 내용은 "에 대 한 활성 내게 필요한 옵션 지원" 항목에 대 한 검색 [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322)합니다.  
  
 이 메서드는 전송 된 [TVM_MAPHTREEITEMTOACCID](http://msdn.microsoft.com/library/windows/desktop/bb773735) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 이러한 변수는 다음 예제에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 트리 뷰 컨트롤 항목에 대 한 id 번호를 가져옵니다. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다. 이 코드 예제에서는 루트 국가/지역 노드에 대 한 고유 식별 번호를 가져옵니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&2;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_31.cpp)]  
  
##  <a name="a-nameselecta--ctreectrlselect"></a><a name="select"></a>CTreeCtrl::Select  
 지정 된 트리 뷰 항목 선택, 항목 보기를 스크롤하여 하거나 끌어서 놓기 작업의 대상을 나타내는 데 사용 되는 스타일에 항목을 다시 그리게이 함수를 호출 합니다.  
  
```  
BOOL Select(
    HTREEITEM hItem,  
    UINT nCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
 `nCode`  
 수행할 작업의 형식입니다. 이 매개 변수는 다음 값 중 하나일 수 있습니다.  
  
- `TVGN_CARET`지정된 된 항목을 선택 영역을 설정합니다.  
  
- `TVGN_DROPHILITE`끌어서 놓기 작업의 대상을 나타내는 데 사용 되는 스타일에 지정된 된 항목을 다시 그립니다.  
  
- `TVGN_FIRSTVISIBLE`지정된 된 항목이 표시 되는 첫 번째 항목은 되도록 트리 뷰를 세로 방향으로 스크롤합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 경우 `nCode` 값이 포함 된 `TVGN_CARET`, 부모 창은 수신 하는 **TVN_SELCHANGING** 및 **TVN_SELCHANGED** 알림 메시지입니다. 또한 지정된 된 항목은 축소 된 부모 항목의 자식 이면 지정 된 항목을 표시 부모의 자식 항목 목록이 확장 됩니다. 부모 창은 수신 하는 경우에 **TVN_ITEMEXPANDING** 및 **TVN_ITEMEXPANDED** 알림 메시지입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::HitTest](#hittest)합니다.  
  
##  <a name="a-nameselectdroptargeta--ctreectrlselectdroptarget"></a><a name="selectdroptarget"></a>CTreeCtrl::SelectDropTarget  
 끌어서 놓기 작업의 대상을 나타내는 데 사용 되는 스타일에 항목을 다시 그리도록 하려면이 함수를 호출 합니다.  
  
```  
BOOL SelectDropTarget(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&9;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_9.cpp)]  
  
##  <a name="a-nameselectitema--ctreectrlselectitem"></a><a name="selectitem"></a>CTreeCtrl::SelectItem  
 지정 된 트리 뷰 항목을 선택 하려면이 함수를 호출 합니다.  
  
```  
BOOL SelectItem(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 경우 `hItem` 는 **NULL**, 다음이 함수는 없는 항목을 선택 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&26;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_29.cpp)]  
  
##  <a name="a-nameselectsetfirstvisiblea--ctreectrlselectsetfirstvisible"></a><a name="selectsetfirstvisible"></a>CTreeCtrl::SelectSetFirstVisible  
 이 함수는 지정된 된 항목이 표시 되는 첫 번째 항목 트리 뷰를 세로로 스크롤할를 호출 합니다.  
  
```  
BOOL SelectSetFirstVisible(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 표시 되는 첫 번째 항목으로 설정 하도록 트리 항목의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 함수는 사용 하 여 창에 메시지를 보냅니다는 `TVM_SELECTITEM` 및 `TVGN_FIRSTVISIBLE` 메시지 매개 변수입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&28;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_32.cpp)]  
  
##  <a name="a-namesetautoscrollinfoa--ctreectrlsetautoscrollinfo"></a><a name="setautoscrollinfo"></a>CTreeCtrl::SetAutoscrollInfo  
 현재 트리 뷰 컨트롤의 자동 스크롤 속도 설정합니다.  
  
```  
BOOL SetAutoscrollInfo(
    UINT uPixelsPerSec,   
    UINT uUpdateTime);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `uPixelsPerSec`|스크롤할 수 있는 초당 픽셀 수입니다.|  
|[in] `uUpdateTime`|컨트롤의 업데이트 사이의 시간 간격입니다.|  
  
### <a name="return-value"></a>반환 값  
 항상 `true`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 자동 스크롤 매개 변수는 현재 표시 되지 않는 항목 보기로 스크롤할 하는 데 사용 됩니다. 트리 뷰 컨트롤 있어야는 `TVS_EX_AUTOHSCROLL` 확장 스타일에 설명 된 [트리 뷰 컨트롤에 대 한 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759981)합니다.  
  
 이 메서드는 전송 된 [하지만 TVM_SETAUTOSCROLLINFO](http://msdn.microsoft.com/library/windows/desktop/bb773738) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 이러한 변수는 다음 예제에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 현재 트리 뷰 컨트롤의 자동 스크롤 동작을 설정 합니다. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다. 우리 일부러 트리 뷰 컨트롤 좁은 포커스가 있는 트리 항목을 표시 하도록 자동으로 스크롤해야 합니다. 이 코드 예제에서는 트리 항목이 표시 될 때까지 5 초 마다 초당 30 픽셀을 자동으로 스크롤하려면 트리 뷰 컨트롤을 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&4;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_33.cpp)]  
  
##  <a name="a-namesetbkcolora--ctreectrlsetbkcolor"></a><a name="setbkcolor"></a>CTreeCtrl::SetBkColor  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_SETBKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773741)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
COLORREF SetBkColor(COLORREF clr);
```  
  
### <a name="parameters"></a>매개 변수  
 `clr`  
 A **COLORREF** 새 배경 색을 포함 하는 값입니다. 이 값이-1 인 경우 컨트롤의 배경색에 대 한 시스템 색을 사용 하 여 되돌아갑니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 현재 텍스트 색을 나타내는 값입니다. 이 값이-1 이면 컨트롤 텍스트 색에 대 한 시스템 색 사용 중인.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::SetTextColor](#settextcolor)합니다.  
  
##  <a name="a-namesetchecka--ctreectrlsetcheck"></a><a name="setcheck"></a>CTreeCtrl::SetCheck  
 트리 컨트롤 항목의 선택 상태를 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
BOOL SetCheck(
    HTREEITEM hItem,  
    BOOL fCheck = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 **HTREEITEM** 확인 상태 변경을 받을 수 있습니다.  
  
 `fCheck`  
 트리 컨트롤 항목 선택 하거나 선택을 취소할 수 있는지 여부를 나타냅니다. 기본적으로 `SetCheck` 검사할 항목을 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 트리 컨트롤 항목 체크 될 때 ( `fCheck` 로 설정 **TRUE**), 인접 한 확인 표시와 함께 표시 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&29;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_34.cpp)]  
  
### <a name="example"></a>예제  
 확인란을 사용 하려면 트리 컨트롤을 채우기 전에 TVS_CHECKBOXES를 설정 합니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #&30;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_35.cpp)]  
  
##  <a name="a-namesetextendedstylea--ctreectrlsetextendedstyle"></a><a name="setextendedstyle"></a>CTreeCtrl::SetExtendedStyle  
 현재 트리 뷰 컨트롤에 대 한 확장된 스타일을 설정합니다.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,   
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `dwExMask`|이 메서드에 의해 영향을 받는 현재 트리 뷰 컨트롤의 스타일을 지정 하는 비트 마스크입니다. 이 매개 변수가&0; 인 경우 무시 됩니다의 값은 `dwExStyles` 매개 변수는 트리 뷰 컨트롤에 할당 됩니다.<br /><br /> 0 또는에 설명 된 스타일의 비트 조합 (OR) 지정 [트리 뷰 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759981)합니다.|  
|[in] `dwExStyles`|설정 하거나 선택을 취소 제어 현재 트리 보기에는 스타일을 지정 하는 비트 마스크입니다.<br /><br /> 혼합 스타일을 설정 하려면에 설명 된 스타일의 비트 조합 (OR)을 지정 [트리 뷰 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb759981)합니다. 스타일의 집합을 해제 하려면&0;을 지정 합니다.|  
  
### <a name="return-value"></a>반환 값  
 확장 컨트롤 스타일 이전 포함 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지정 된 스타일을 지웁니다는 `dwExMask` 매개 변수를 다음에 지정 된 스타일을 설정 된 `dwExStyles` 매개 변수입니다. 확장된 스타일의 비트에 해당 하는 `dwExMask` 변경 합니다.  
  
 이 메서드는 전송 된 [TVM_SETEXTENDEDSTYLE](http://msdn.microsoft.com/library/windows/desktop/bb773744) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 이러한 변수는 다음 예제에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 추가 `TVS_EX_AUTOHSCROLL` 스타일 현재 트리 뷰 컨트롤을 확장 합니다. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다. 우리 일부러 트리 뷰 컨트롤 좁은 포커스가 있는 트리 항목을 표시 하도록 자동으로 스크롤해야 합니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&3;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_36.cpp)]  
  
##  <a name="a-namesetimagelista--ctreectrlsetimagelist"></a><a name="setimagelist"></a>CTreeCtrl::SetImageList  
 일반 설정 하려면이 함수를 호출 하거나 트리에 대 한 상태 이미지 목록 컨트롤을 보기 및 새 이미지를 사용 하 여 컨트롤을 다시 그리도록 합니다.  
  
```  
CImageList* SetImageList(
    CImageList* pImageList,  
    int nImageListType);
```  
  
### <a name="parameters"></a>매개 변수  
 `pImageList`  
 할당할 이미지 목록에 대 한 포인터입니다. 경우 `pImageList` 는 **NULL**, 트리 뷰 컨트롤에서 모든 이미지 제거 됩니다.  
  
 `nImageListType`  
 이미지 목록 종류를 설정 합니다. 이미지 목록의 다음 값 중 하나일 수 있습니다.  
  
- `TVSIL_NORMAL`트리 뷰 항목에 대 한 선택 되 고 선택 되지 않은 이미지를 포함 하는 일반 이미지 목록을 설정 합니다. 이미지 오버레이 대 한이 상태를 사용 해야 합니다.  
  
- `TVSIL_STATE`사용자 정의 상태에 있는 트리 뷰 항목에 대 한 이미지를 포함 하는 상태 이미지 목록을 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 있으면 이전 이미지 목록에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetImageList](#getimagelist)합니다.  
  
##  <a name="a-namesetindenta--ctreectrlsetindent"></a><a name="setindent"></a>CTreeCtrl::SetIndent  
 트리 뷰 컨트롤에 대 한 들여쓰기의 너비를 설정 하 고 새 너비에 맞게 컨트롤을 다시 그리도록 하려면이 함수를 호출 합니다.  
  
```  
void SetIndent(UINT nIndent);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndent`  
 들여쓰기를 픽셀 단위로 너비입니다. 경우 `nIndent` 작으면 시스템에 정의 된 최소 너비 보다으로 새 너비 시스템에 정의 된 최소한으로 설정 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetIndent](#getindent)합니다.  
  
##  <a name="a-namesetinsertmarka--ctreectrlsetinsertmark"></a><a name="setinsertmark"></a>CTreeCtrl::SetInsertMark  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb773753)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
BOOL SetInsertMark(
    HTREEITEM hItem,  
    BOOL fAfter = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 **HTREEITEM** 항목 삽입 표시가 배치할 수를 지정 하는 합니다. 이 인수가 **NULL**, 삽입 표시가 제거 됩니다.  
  
 *fAfter*  
 **BOOL** 삽입 표시가 지정된 된 항목 앞뒤 배치 하는 경우 지정 하는 값입니다. 이 인수를&0;이 아닌 경우 삽입 표시가 항목 뒤에 배치 됩니다. 이 인수는&0; 인 경우 삽입 표시가 항목 전에 배치 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&31;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_37.cpp)]  
  
##  <a name="a-namesetinsertmarkcolora--ctreectrlsetinsertmarkcolor"></a><a name="setinsertmarkcolor"></a>CTreeCtrl::SetInsertMarkColor  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773755)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
COLORREF SetInsertMarkColor(COLORREF clrNew);
```  
  
### <a name="parameters"></a>매개 변수  
 `clrNew`  
 A **COLORREF** 새로운 삽입 표시 색을 포함 하는 값입니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 이전 삽입 표시 색을 포함 하는 값입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetInsertMarkColor](#getinsertmarkcolor)합니다.  
  
##  <a name="a-namesetitema--ctreectrlsetitem"></a><a name="setitem"></a>CTreeCtrl::SetItem  
 지정 된 트리 뷰 항목의 특성을 설정 하려면이 함수를 호출 합니다.  
  
```  
BOOL SetItem(TVITEM* pItem);

 
BOOL SetItem(
    HTREEITEM hItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    int nSelectedImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 에 대 한 포인터는 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 에 설명 된 대로 새 항목을 포함 하는 구조 특성은 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `hItem`  
 설정 된 특성을 가진 항목의 핸들입니다. 참조는 **hItem** 의 멤버는 `TVITEM` 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `nMask`  
 설정 하는 특성을 지정 하는 정수입니다. 참조는 **마스크** 의 멤버는 `TVITEM` 구조입니다.  
  
 `lpszItem`  
 항목의 텍스트를 포함 하는 문자열의 주소입니다.  
  
 `nImage`  
 트리 뷰 컨트롤의 이미지 목록에서 항목의 이미지의 인덱스입니다. 참조는 `iImage` 의 멤버는 `TVITEM` 구조입니다.  
  
 `nSelectedImage`  
 트리 뷰 컨트롤의 이미지 목록에서 항목의 선택 된 이미지의 인덱스입니다. 참조는 **iSelectedImage** 의 멤버는 `TVITEM` 구조입니다.  
  
 `nState`  
 항목의 상태에 대 한 값을 지정합니다. 참조는 **상태** 의 멤버는 `TVITEM` 구조입니다.  
  
 `nStateMask`  
 설정할 수 있는 상태 지정 합니다. 참조는 **stateMask** 의 멤버는 `TVITEM` 구조입니다.  
  
 `lParam`  
 항목에 연결 된 32 비트 응용 프로그램 관련 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 에 `TVITEM` 구조를는 **hItem** 멤버에는 항목을 식별 하 고 **마스크** 멤버 특성 집합을 지정 합니다.  
  
 경우는 **마스크** 멤버 또는 `nMask` 매개 변수 지정는 `TVIF_TEXT` 값은 **pszText** 멤버 또는 `lpszItem` 는 null로 끝나는 문자열의 주소 및 **cchTextMax** 멤버가 무시 됩니다. 경우 **마스크** (또는 `nMask`) 지정는 `TVIF_STATE` 값을는 **stateMask** 멤버 또는 `nStateMask` 매개 변수를 변경 하는 항목 상태 지정 및 **상태** 멤버 또는 `nState` 매개 변수는 해당 상태에 대 한 값을 포함 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&32;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_38.cpp)]  
  
##  <a name="a-namesetitemdataa--ctreectrlsetitemdata"></a><a name="setitemdata"></a>CTreeCtrl::SetItemData  
 지정 된 항목과 연결 된 32 비트 응용 프로그램 특정 값을 설정 하려면이 함수를 호출 합니다.  
  
```  
BOOL SetItemData(
    HTREEITEM hItem,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 데이터가 검색 된 항목의 핸들입니다.  
  
 `dwData`  
 32 비트 응용 프로그램 관련 값으로 지정 된 항목과 연결 된 `hItem`합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&33;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_39.cpp)]  
  
##  <a name="a-namesetitemexpandedimageindexa--ctreectrlsetitemexpandedimageindex"></a><a name="setitemexpandedimageindex"></a>CTreeCtrl::SetItemExpandedImageIndex  
 현재 트리 뷰 컨트롤의 지정된 된 항목 확장된 상태에 있을 때 표시할 이미지의 인덱스를 설정 합니다.  
  
```  
BOOL SetItemExpandedImageIndex(
    HTREEITEM hItem,   
    int iExpandedImage);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `hItem`|트리 뷰 컨트롤 항목에 대 한 핸들입니다.|  
|[in] `iExpandedImage`|지정 된 항목이 확장 된 상태에 있을 때 표시할 이미지의 인덱스입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 이 메서드 할당는 `iExpandedImage` 매개 변수를는 `iExpandedImage` 의 멤버는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조를 사용 하 여 다음 메시지에 적용 되도록 합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 이러한 변수는 다음 예제에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제는 확인 하는 간단한 테스트 여부는 [CTreeCtrl::GetItemExpandedImageIndex](#getitemexpandedimageindex) 의해 설정 된 값을 반환 하는 메서드는 [CTreeCtrl::SetItemExpandedImageIndex](#setitemexpandedimageindex) 메서드. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&8;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_40.cpp)]  
  
##  <a name="a-namesetitemheighta--ctreectrlsetitemheight"></a><a name="setitemheight"></a>CTreeCtrl::SetItemHeight  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_SETITEMHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb773761)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
SHORT SetItemHeight(SHORT cyHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 `cyHeight`  
 픽셀 단위로 트리 뷰에 모든 항목의 새 높이 지정합니다. 이 인수는 이미지의 높이 보다 작은 경우 다음 설정 됩니다 이미지의 높이입니다. 반올림으로이 인수를 없는 경우도 가장 가까운 짝수 값입니다. 이 인수가-1 인 경우 컨트롤의 기본 항목 높이 사용 하 여 되돌아갑니다.  
  
### <a name="return-value"></a>반환 값  
 이전 높이 (픽셀)에 있는 항목입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetItemHeight](#getitemheight)합니다.  
  
##  <a name="a-namesetitemimagea--ctreectrlsetitemimage"></a><a name="setitemimage"></a>CTreeCtrl::SetItemImage  
 항목 이미지에 연결합니다.  
  
```  
BOOL SetItemImage(
    HTREEITEM hItem,  
    int nImage,  
    int nSelectedImage);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 해당 이미지를 설정할 항목의 핸들입니다.  
  
 `nImage`  
 트리 뷰 컨트롤의 이미지 목록에서 항목의 이미지의 인덱스입니다.  
  
 `nSelectedImage`  
 트리 뷰 컨트롤의 이미지 목록에서 항목의 선택 된 이미지의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 트리 뷰 컨트롤의 각 항목에는 한 쌍의 관련 된 비트맵 이미지 있을 수 있습니다. 이미지 항목의 레이블 왼쪽에 나타납니다. 항목을 선택 하 고 항목을 선택 하지 않은 경우 표시 되 면 다른 이미지 표시 됩니다. 예를 들어, 선택 하지 않은 경우 선택 된 폴더를 열어와 닫힌된 폴더 항목 표시 될 수 있습니다.  
  
 항목의 이미지 및 트리 뷰 컨트롤의 이미지 목록 내에서 선택 된 이미지의 인덱스를 설정 하려면이 함수를 호출 합니다.  
  
 이미지에 대 한 자세한 내용은 참조 하십시오. [CImageList](../../mfc/reference/cimagelist-class.md)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetItemImage](#getitemimage)합니다.  
  
##  <a name="a-namesetitemstatea--ctreectrlsetitemstate"></a><a name="setitemstate"></a>CTreeCtrl::SetItemState  
 지정 된 항목의 상태를 설정 `hItem`합니다.  
  
```  
BOOL SetItemState(
    HTREEITEM hItem,  
    UINT nState,  
    UINT nStateMask);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 상태가 설정할 항목의 핸들입니다.  
  
 `nState`  
 항목에 대해 새 상태를 지정합니다.  
  
 `nStateMask`  
 변경할 수 있는 상태 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 상태에 대 한 자세한 내용은 참조 [CTreeCtrl::GetItem](#getitem)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetItemState](#getitemstate)합니다.  
  
##  <a name="a-namesetitemstateexa--ctreectrlsetitemstateex"></a><a name="setitemstateex"></a>CTreeCtrl::SetItemStateEx  
 현재 트리 뷰 컨트롤에서 지정된 된 항목의 확장 된 상태를 설정합니다.  
  
```  
BOOL SetItemStateEx(
    HTREEITEM hItem,   
    UINT uStateEx);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `hItem`|트리 뷰 컨트롤 항목에 대 한 핸들입니다.|  
|[in] `uStateEx`|항목의 확장 된 상태입니다. 자세한 내용은 참조는 `uStateEx` 의 멤버는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [TVM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb773758) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 이 메서드 할당는 `uStateEx` 매개 변수를는 `uStateEx` 의 멤버는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조를 사용 하 여 다음 메시지에 적용 되도록 합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_treeCtrl`, 즉 현재 트리 뷰 컨트롤에 액세스 하는 데 사용 합니다. 또한이 코드 예제에서는 부호 없는 정수 및 여러 HTREEITEM 변수를 정의합니다. 이러한 변수는 다음 예제에 사용 됩니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_17.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 트리 뷰 항목을 사용할 수 없는 상태로 설정합니다. 표시 되지 않는 코드 예제에서는 이전 단원에서 미국에 대 한 루트 국가/지역 노드, 알기로 펜실베이니아 및 워싱턴 주에 대 한 하위 및 도시 상태에 대 한 트리 항목으로 구성 된 트리 뷰를 만들었습니다. 이 코드 예제에서는 비활성화 된 상태로 알기로 펜실베이니아 노드를 설정합니다.  
  
 [!code-cpp[NVC_MFC_CTreeCtrl_s&#1;&7;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_41.cpp)]  
  
##  <a name="a-namesetitemtexta--ctreectrlsetitemtext"></a><a name="setitemtext"></a>CTreeCtrl::SetItemText  
 지정 된 항목의 텍스트를 설정 `hItem`합니다.  
  
```  
BOOL SetItemText(
    HTREEITEM hItem,  
    LPCTSTR lpszItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 설정 되어야 하는 텍스트가 포함 된 항목의 핸들입니다.  
  
 `lpszItem`  
 항목에 대 한 새 텍스트를 포함 하는 문자열의 주소  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&34;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_42.cpp)]  
  
##  <a name="a-namesetlinecolora--ctreectrlsetlinecolor"></a><a name="setlinecolor"></a>CTreeCtrl::SetLineColor  
 트리 뷰 컨트롤에 대 한 현재 선 색을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
COLORREF SetLineColor(COLORREF clrNew = CLR_DEFAULT);
```  
  
### <a name="parameters"></a>매개 변수  
 `clrNew`  
 새 선 색입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 선 색입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 win32 메시지의 동작을 구현 [TVM_SETLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773764)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&35;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_43.cpp)]  
  
##  <a name="a-namesetscrolltimea--ctreectrlsetscrolltime"></a><a name="setscrolltime"></a>CTreeCtrl::SetScrollTime  
 트리 뷰 컨트롤에 대 한 최대 스크롤 시간을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
UINT SetScrollTime(UINT uScrollTime);
```  
  
### <a name="parameters"></a>매개 변수  
 *uScrollTime*  
 새 스크롤 최대 시간을 시간 (밀리초)입니다. 이 값이 100 보다 작은 인 경우 최대 100 개까지 반올림 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전 스크롤 최대 시간 (밀리초)입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 win32 메시지의 동작을 구현 [TVM_SETSCROLLTIME](http://msdn.microsoft.com/library/windows/desktop/bb773767)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesettextcolora--ctreectrlsettextcolor"></a><a name="settextcolor"></a>CTreeCtrl::SetTextColor  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_SETTEXTCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb773769)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
COLORREF SetTextColor(COLORREF clr);
```  
  
### <a name="parameters"></a>매개 변수  
 `clr`  
 A **COLORREF** 새 텍스트 색을 포함 하는 값입니다. 이 인수가-1 인 경우 컨트롤의 텍스트 색에 대 한 시스템 색을 사용 하 여 되돌아갑니다.  
  
### <a name="return-value"></a>반환 값  
 A **COLORREF** 이전 텍스트 색을 나타내는 값입니다. 이 값이-1 인 경우 컨트롤의 시스템 색을 사용 하 여 텍스트 색을 했습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&36;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_44.cpp)]  
  
##  <a name="a-namesettooltipsa--ctreectrlsettooltips"></a><a name="settooltips"></a>CTreeCtrl::SetToolTips  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [TVM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb773772)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
```  
CToolTipCtrl* SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWndTip`  
 에 대 한 포인터는 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 트리 컨트롤에서 사용할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md) 컨트롤에 의해 이전에 사용 되는 도구 설명이 포함 된 개체 또는 **NULL** 도구 설명 없음 이전에 사용 되는 경우.  
  
### <a name="remarks"></a>주의  
 도구를 사용 하려면 지정 된 **TVS_NOTOOLTIPS** 스타일을 만들 때는 `CTreeCtrl` 개체입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CTreeCtrl::GetToolTips](#gettooltips)합니다.  
  
##  <a name="a-nameshowinfotipa--ctreectrlshowinfotip"></a><a name="showinfotip"></a>CTreeCtrl::ShowInfoTip  
 현재 트리 뷰 컨트롤에 지정된 된 항목에 대 한 정보 팁을 표시합니다.  
  
```  
void ShowInfoTip(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `hItem`|컨트롤의 트리 보기 항목에 대 한 핸들입니다. 자세한 내용은 참조는 `hItem` 의 멤버는 [TVITEMEX](http://msdn.microsoft.com/library/windows/desktop/bb773459) 구조입니다.|  
  
### <a name="remarks"></a>주의  
 도구 설명 및 정보 팁 차이점에 대 한 자세한 내용은에서 "도구 설명 및 정보 팁" 항목에 대 한 검색 [Microsoft Developer Network](http://go.microsoft.com/fwlink/linkid=56322)합니다.  
  
 이 메서드는 전송 된 [TVM_SHOWINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb773779) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesortchildrena--ctreectrlsortchildren"></a><a name="sortchildren"></a>CTreeCtrl::SortChildren  
 트리 뷰 컨트롤에서 지정 된 부모 항목의 자식 항목을 사전순으로 정렬 하려면이 함수를 호출 합니다.  
  
```  
BOOL SortChildren(HTREEITEM hItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `hItem`  
 정렬 된 자식 항목을 부모 항목의 핸들입니다. 경우 `hItem` 는 **NULL**, 정렬 트리의 루트에서 진행 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 `SortChildren`재귀적으로; 트리를 검색 하지 않습니다. 직계 자식만 `hItem` 정렬 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&37;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_45.cpp)]  
  
##  <a name="a-namesortchildrencba--ctreectrlsortchildrencb"></a><a name="sortchildrencb"></a>CTreeCtrl::SortChildrenCB  
 항목을 비교 하는 응용 프로그램에서 정의 된 콜백 함수를 사용 하 여 트리 뷰 항목을 정렬 하려면이 함수를 호출 합니다.  
  
```  
BOOL SortChildrenCB(LPTVSORTCB pSort);
```  
  
### <a name="parameters"></a>매개 변수  
 *pSort*  
 에 대 한 포인터는 [TVSORTCB](http://msdn.microsoft.com/library/windows/desktop/bb773462) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 구조체의 비교 함수 **lpfnCompare**, 음수 값을 반환 해야 첫 번째 항목 두 번째 따라야 합니다. 또는 경우에는&0;이 두 항목은 해당 하는 경우 양수 값 경우 첫 번째 항목 두 번째 앞에 야 합니다.  
  
 `lParam1` 및 `lParam2` 에 해당 하는 매개 변수는 **lParam** 의 멤버는 [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) 비교할 두 개의 항목을 하기 위한 구조체입니다. `lParamSort` 에 해당 하는 매개 변수는 **lParam** 의 멤버는 `TV_SORTCB` 구조입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CTreeCtrl #&38;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_46.cpp)]  
  
 [!code-cpp[NVC_MFC_CTreeCtrl #&39;](../../mfc/reference/codesnippet/cpp/ctreectrl-class_47.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CMNCTRL1](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CImageList 클래스](../../mfc/reference/cimagelist-class.md)

