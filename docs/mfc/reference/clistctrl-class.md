---
title: "CListCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CListCtrl
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class
- LVS_REPORT
- LVS_LIST
- LVS_ICON
- list view controls
- list view controls, CListCtrl class
- Windows common controls [C++], CListCtrl
- LVS_SMALLICON
ms.assetid: fe08a1ca-4b05-4ff7-a12a-ee4c765a2197
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: fb82dd194d59bff9e0a3fe8f047686a8bcc4d927
ms.lasthandoff: 02/24/2017

---
# <a name="clistctrl-class"></a>CListCtrl 클래스
각각 이미지 목록의 아이콘과 레이블로 구성되는 항목 컬렉션을 표시하는 "목록 뷰 컨트롤"의 기능을 캡슐화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CListCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CListCtrl::CListCtrl](#clistctrl)|`CListCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CListCtrl::ApproximateViewRect](#approximateviewrect)|너비와 높이 목록 뷰 컨트롤의 항목을 표시 하는 데 필요한 결정 합니다.|  
|[CListCtrl::Arrange](#arrange)|눈금에 항목을 정렬합니다.|  
|[CListCtrl::CancelEditLabel](#canceleditlabel)|항목 텍스트 편집 작업을 취소 합니다.|  
|[CListCtrl::Create](#create)|목록 컨트롤을 만들고에 연결 된 `CListCtrl` 개체입니다.|  
|[CListCtrl::CreateDragImage](#createdragimage)|지정된 된 항목에 대 한 끌기 이미지 목록을 만듭니다.|  
|[CListCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 목록 컨트롤을 만들고에 연결 된 `CListCtrl` 개체입니다.|  
|[CListCtrl::DeleteAllItems](#deleteallitems)|컨트롤에서 모든 항목을 삭제합니다.|  
|[CListCtrl::DeleteColumn](#deletecolumn)|List view 컨트롤에서 열을 삭제합니다.|  
|[CListCtrl::DeleteItem](#deleteitem)|컨트롤에서 항목을 삭제합니다.|  
|[CListCtrl::DrawItem](#drawitem)|소유자 그리기 컨트롤의 시각적 측면이 때 호출 됩니다.|  
|[CListCtrl::EditLabel](#editlabel)|항목의 텍스트의 내부 편집을 시작 합니다.|  
|[CListCtrl::EnableGroupView](#enablegroupview)|목록 뷰 컨트롤의 항목을 그룹으로 표시할지 여부를 사용 하지 않도록 설정 하거나 사용 합니다.|  
|[CListCtrl::EnsureVisible](#ensurevisible)|항목이 표시 되는지 확인 합니다.|  
|[CListCtrl::FindItem](#finditem)|지정 된 특징을 가진 목록 보기 항목을 검색 합니다.|  
|[CListCtrl::GetBkColor](#getbkcolor)|목록 뷰 컨트롤의 배경색을 검색합니다.|  
|[CListCtrl::GetBkImage](#getbkimage)|목록 뷰 컨트롤의 현재 배경 이미지를 검색합니다.|  
|[CListCtrl::GetCallbackMask](#getcallbackmask)|목록 뷰 컨트롤에 대 한 콜백 마스크를 검색합니다.|  
|[CListCtrl::GetCheck](#getcheck)|항목에 연결 된 상태 이미지의 현재 상태 표시를 검색 합니다.|  
|[CListCtrl::GetColumn](#getcolumn)|컨트롤의 열 특성을 검색 합니다.|  
|[CListCtrl::GetColumnOrderArray](#getcolumnorderarray)|목록 뷰 컨트롤의 열 순서 (왼쪽에서 오른쪽)를 검색 합니다.|  
|[CListCtrl::GetColumnWidth](#getcolumnwidth)|보고서 보기 또는 목록 보기에서 열 너비를 검색합니다.|  
|[CListCtrl::GetCountPerPage](#getcountperpage)|목록 뷰 컨트롤에 세로로 들어갈 수 있는 항목의 수를 계산 합니다.|  
|[CListCtrl::GetEditControl](#geteditcontrol)|항목의 텍스트를 편집 하는 데 사용 하는 편집 컨트롤의 핸들을 검색 합니다.|  
|[CListCtrl::GetEmptyText](#getemptytext)|현재 목록 뷰 컨트롤이 비어 있으면 표시할 문자열을 검색 합니다.|  
|[CListCtrl::GetExtendedStyle](#getextendedstyle)|목록 뷰 컨트롤의 현재 확장된 스타일을 검색합니다.|  
|[CListCtrl::GetFirstSelectedItemPosition](#getfirstselecteditemposition)|목록 뷰 컨트롤에서 첫 번째 선택한 목록 보기 항목의 위치를 검색합니다.|  
|[CListCtrl::GetFocusedGroup](#getfocusedgroup)|현재 목록 뷰 컨트롤에 키보드 포커스가 있는 그룹을 검색 합니다.|  
|[CListCtrl::GetGroupCount](#getgroupcount)|현재 목록 뷰 컨트롤의 그룹 수를 검색합니다.|  
|[CListCtrl::GetGroupInfo](#getgroupinfo)|지정된 된 그룹 목록 뷰 컨트롤에 대 한 정보를 가져옵니다.|  
|[CListCtrl::GetGroupInfoByIndex](#getgroupinfobyindex)|현재 목록 뷰 컨트롤에서 지정된 된 그룹에 대 한 정보를 검색합니다.|  
|[CListCtrl::GetGroupMetrics](#getgroupmetrics)|그룹의 메트릭을 검색합니다.|  
|[CListCtrl::GetGroupRect](#getgrouprect)|현재 목록 뷰 컨트롤에서 지정된 된 그룹에 대 한 경계 사각형을 검색 합니다.|  
|[CListCtrl::GetGroupState](#getgroupstate)|현재 목록 뷰 컨트롤에서 지정된 된 그룹에 대 한 상태를 검색합니다.|  
|[CListCtrl::GetHeaderCtrl](#getheaderctrl)|목록 뷰 컨트롤의 헤더 컨트롤을 검색합니다.|  
|[CListCtrl::GetHotCursor](#gethotcursor)|목록 뷰 컨트롤에 대해 핫 트래킹을 때 사용 되는 커서를 검색 합니다.|  
|[CListCtrl::GetHotItem](#gethotitem)|커서에서 현재 목록 보기 항목을 검색합니다.|  
|[CListCtrl::GetHoverTime](#gethovertime)|목록 뷰 컨트롤의 현재 호버 시간을 검색합니다.|  
|[CListCtrl::GetImageList](#getimagelist)|그리기 항목 목록 보기에 사용 되는 이미지 목록의 핸들을 검색 합니다.|  
|[CListCtrl::GetInsertMark](#getinsertmark)|삽입 표시의 현재 위치를 검색합니다.|  
|[CListCtrl::GetInsertMarkColor](#getinsertmarkcolor)|삽입 표시의 현재 색을 검색 합니다.|  
|[CListCtrl::GetInsertMarkRect](#getinsertmarkrect)|삽입점을 제한 하는 사각형을 검색 합니다.|  
|[CListCtrl::GetItem](#getitem)|특성 목록 보기 항목을 검색합니다.|  
|[CListCtrl::GetItemCount](#getitemcount)|목록 뷰 컨트롤의 항목 수를 검색합니다.|  
|[CListCtrl::GetItemData](#getitemdata)|항목에 연결 된 응용 프로그램 특정 값을 검색 합니다.|  
|[CListCtrl::GetItemIndexRect](#getitemindexrect)|현재 목록 뷰 컨트롤의 하위 항목의 전체 또는 일부에 대 한 경계 사각형을 검색 합니다.|  
|[CListCtrl::GetItemPosition](#getitemposition)|목록 보기 항목의 위치를 검색 합니다.|  
|[CListCtrl::GetItemRect](#getitemrect)|항목에 대 한 경계 사각형을 검색 합니다.|  
|[CListCtrl::GetItemSpacing](#getitemspacing)|현재 목록 뷰 컨트롤의 항목 사이의 간격을 계산합니다.|  
|[CListCtrl::GetItemState](#getitemstate)|목록 보기 항목의 상태를 검색합니다.|  
|[CListCtrl::GetItemText](#getitemtext)|목록 보기 항목 또는 하위 항목의 텍스트를 검색합니다.|  
|[CListCtrl::GetNextItem](#getnextitem)|속성을 지정 하 고 지정된 된 항목에 지정 된 관계로 목록 보기 항목을 검색 합니다.|  
|[CListCtrl::GetNextItemIndex](#getnextitemindex)|지정된 된 속성 집합이 있는 현재 목록 뷰 컨트롤에서 항목의 인덱스를 검색 합니다.|  
|[CListCtrl::GetNextSelectedItem](#getnextselecteditem)|인덱스 목록 보기 항목 위치 및 반복에 대 한 다음 선택한 목록 보기 항목의 위치를 검색합니다.|  
|[CListCtrl::GetNumberOfWorkAreas](#getnumberofworkareas)|현재는 목록 뷰 컨트롤에 대 한 작업 영역 수를 검색합니다.|  
|[CListCtrl::GetOrigin](#getorigin)|목록 뷰 컨트롤에 대 한 현재 보기 원점을 검색합니다.|  
|[CListCtrl::GetOutlineColor](#getoutlinecolor)|목록 뷰 컨트롤의 테두리 색을 검색 합니다.|  
|[CListCtrl::GetSelectedColumn](#getselectedcolumn)|목록 컨트롤에서 현재 선택 된 열의 인덱스를 검색합니다.|  
|[CListCtrl::GetSelectedCount](#getselectedcount)|List view 컨트롤에서 선택한 항목의 수를 가져옵니다.|  
|[CListCtrl::GetSelectionMark](#getselectionmark)|목록 뷰 컨트롤의 선택 표시를 검색합니다.|  
|[CListCtrl::GetStringWidth](#getstringwidth)|지정된 된 문자열의 모든 표시 하는 데 필요한 최소 열 너비를 결정 합니다.|  
|[CListCtrl::GetSubItemRect](#getsubitemrect)|목록 뷰 컨트롤에 있는 항목의 경계 사각형을 검색 합니다.|  
|[CListCtrl::GetTextBkColor](#gettextbkcolor)|목록 뷰 컨트롤의 텍스트 배경 색을 검색합니다.|  
|[CListCtrl::GetTextColor](#gettextcolor)|목록 뷰 컨트롤의 텍스트 색을 검색합니다.|  
|[CListCtrl::GetTileInfo](#gettileinfo)|목록 뷰 컨트롤에서 타일에 대 한 정보를 검색합니다.|  
|[CListCtrl::GetTileViewInfo](#gettileviewinfo)|Tile 보기에는 목록 뷰 컨트롤에 대 한 정보를 검색합니다.|  
|[CListCtrl::GetToolTips](#gettooltips)|목록 뷰 컨트롤에서 사용 하 여 도구 설명을 표시 하는 도구 설명 컨트롤을 검색 합니다.|  
|[CListCtrl::GetTopIndex](#gettopindex)|표시 되는 맨 위에 있는 항목의 인덱스를 검색 합니다.|  
|[CListCtrl::GetView](#getview)|목록 뷰 컨트롤의 뷰를 가져옵니다.|  
|[CListCtrl::GetViewRect](#getviewrect)|목록 뷰 컨트롤의 모든 항목의 경계 사각형을 검색합니다.|  
|[CListCtrl::GetWorkAreas](#getworkareas)|목록 뷰 컨트롤의 현재 작업 영역을 검색합니다.|  
|[CListCtrl::HasGroup](#hasgroup)|목록 뷰 컨트롤에서 지정된 된 그룹에 있는지 확인 합니다.|  
|[CListCtrl::HitTest](#hittest)|결정 목록 보기 항목은 지정된 된 위치에 있습니다.|  
|[CListCtrl::InsertColumn](#insertcolumn)|목록 뷰 컨트롤에 새 열을 삽입합니다.|  
|[CListCtrl::InsertGroup](#insertgroup)|그룹 목록 뷰 컨트롤에 삽입합니다.|  
|[CListCtrl::InsertGroupSorted](#insertgroupsorted)|그룹의 정렬 된 목록에 지정된 된 그룹을 삽입합니다.|  
|[CListCtrl::InsertItem](#insertitem)|목록 뷰 컨트롤에 새 항목을 삽입합니다.|  
|[CListCtrl::InsertMarkHitTest](#insertmarkhittest)|지정된 된 지점에 가장 가까운 삽입 포인터를 검색합니다.|  
|[CListCtrl::IsGroupViewEnabled](#isgroupviewenabled)|그룹 보기는 목록 뷰 컨트롤에 대 한 사용 되는지 여부를 결정 합니다.|  
|[CListCtrl::IsItemVisible](#isitemvisible)|현재 목록 뷰 컨트롤에서 지정된 된 항목 표시 여부를 나타냅니다.|  
|[CListCtrl::MapIDToIndex](#mapidtoindex)|인덱스를 현재 목록 뷰 컨트롤에 있는 항목의 고유 ID를 매핑합니다.|  
|[CListCtrl::MapIndexToID](#mapindextoid)|고유 ID를 현재 목록 뷰 컨트롤에 있는 항목의 인덱스를 매핑합니다.|  
|[CListCtrl::MoveGroup](#movegroup)|지정된 된 그룹을 이동합니다.|  
|[CListCtrl::MoveItemToGroup](#moveitemtogroup)|지정 된 그룹에 지정 된 목록 뷰 컨트롤의&0; 기반된 인덱스를 이동 합니다.|  
|[CListCtrl::RedrawItems](#redrawitems)|항목의 범위를 다시 그려야 하는 목록 뷰 컨트롤을 강제로 수행 합니다.|  
|[CListCtrl::RemoveAllGroups](#removeallgroups)|목록 뷰 컨트롤에서 모든 그룹을 제거합니다.|  
|[CListCtrl::RemoveGroup](#removegroup)|List view 컨트롤에서 지정된 된 그룹을 제거합니다.|  
|[CListCtrl::Scroll](#scroll)|목록 뷰 컨트롤의 내용을 스크롤합니다.|  
|[CListCtrl::SetBkColor](#setbkcolor)|목록 뷰 컨트롤의 배경색을 설정합니다.|  
|[CListCtrl::SetBkImage](#setbkimage)|목록 뷰 컨트롤의 현재 배경 이미지를 설정합니다.|  
|[CListCtrl::SetCallbackMask](#setcallbackmask)|목록 뷰 컨트롤에 대 한 콜백 마스크를 설정합니다.|  
|[CListCtrl::SetCheck](#setcheck)|현재 표시 항목에 연결 된 상태 이미지의 상태를 설정 합니다.|  
|[CListCtrl::SetColumn](#setcolumn)|목록 뷰 열 특성을 설정합니다.|  
|[CListCtrl::SetColumnOrderArray](#setcolumnorderarray)|목록 뷰 컨트롤의 열 순서 (왼쪽에서 오른쪽)를 설정 합니다.|  
|[CListCtrl::SetColumnWidth](#setcolumnwidth)|보고서 보기 또는 목록 보기에서 열 너비를 변경합니다.|  
|[CListCtrl::SetExtendedStyle](#setextendedstyle)|목록 뷰 컨트롤의 현재 확장된 스타일을 설정합니다.|  
|[CListCtrl::SetGroupInfo](#setgroupinfo)|목록 뷰 컨트롤의 지정된 된 그룹에 대 한 정보를 설정합니다.|  
|[CListCtrl::SetGroupMetrics](#setgroupmetrics)|목록 뷰 컨트롤의 그룹 메트릭을 설정합니다.|  
|[CListCtrl::SetHotCursor](#sethotcursor)|목록 뷰 컨트롤에 대해 핫 트래킹을 때 사용 되는 커서를 설정 합니다.|  
|[CListCtrl::SetHotItem](#sethotitem)|목록 뷰 컨트롤의 현재 활성 항목을 설정합니다.|  
|[CListCtrl::SetHoverTime](#sethovertime)|목록 뷰 컨트롤의 현재 호버 시간을 설정합니다.|  
|[CListCtrl::SetIconSpacing](#seticonspacing)|목록 뷰 컨트롤의 아이콘 사이의 간격을 설정 합니다.|  
|[CListCtrl::SetImageList](#setimagelist)|이미지 목록을 목록 뷰 컨트롤에 할당합니다.|  
|[CListCtrl::SetInfoTip](#setinfotip)|도구 설명 텍스트를 설정합니다.|  
|[CListCtrl::SetInsertMark](#setinsertmark)|정의 된 위치에 삽입 포인터를 설정합니다.|  
|[CListCtrl::SetInsertMarkColor](#setinsertmarkcolor)|삽입 포인터의 색을 설정 합니다.|  
|[CListCtrl::SetItem](#setitem)|일부 또는 전체 목록 보기 항목의 특성을 설정합니다.|  
|[CListCtrl::SetItemCount](#setitemcount)|많은 수의 항목을 추가 하는 데는 목록 뷰 컨트롤을 준비 합니다.|  
|[CListCtrl::SetItemCountEx](#setitemcountex)|가상 목록 뷰 컨트롤에 대 한 항목 수를 설정합니다.|  
|[CListCtrl::SetItemData](#setitemdata)|항목의 응용 프로그램 특정 값을 설정합니다.|  
|[CListCtrl::SetItemIndexState](#setitemindexstate)|현재 목록 뷰 컨트롤에서 항목의 상태를 설정합니다.|  
|[CListCtrl::SetItemPosition](#setitemposition)|목록 뷰 컨트롤의 지정된 된 위치에 항목을 이동합니다.|  
|[CListCtrl::SetItemState](#setitemstate)|목록 뷰 컨트롤에 있는 항목의 상태를 변경합니다.|  
|[CListCtrl::SetItemText](#setitemtext)|목록 보기 항목 또는 하위 항목의 텍스트를 변경합니다.|  
|[CListCtrl::SetOutlineColor](#setoutlinecolor)|목록 뷰 컨트롤의 테두리 색을 설정합니다.|  
|[CListCtrl::SetSelectedColumn](#setselectedcolumn)|목록 뷰 컨트롤의 선택된 된 열을 설정합니다.|  
|[CListCtrl::SetSelectionMark](#setselectionmark)|목록 뷰 컨트롤의 선택 표시를 설정합니다.|  
|[CListCtrl::SetTextBkColor](#settextbkcolor)|목록 뷰 컨트롤에서 텍스트의 배경색을 설정합니다.|  
|[CListCtrl::SetTextColor](#settextcolor)|목록 뷰 컨트롤의 텍스트 색을 설정합니다.|  
|[CListCtrl::SetTileInfo](#settileinfo)|목록 뷰 컨트롤의 타일에 대 한 정보를 설정합니다.|  
|[CListCtrl::SetTileViewInfo](#settileviewinfo)|Tile 보기에는 목록 뷰 컨트롤을 사용 하는 정보를 설정 합니다.|  
|[CListCtrl::SetToolTips](#settooltips)|List view 컨트롤에서 도구 설명을 표시 하려면 사용할 도구 설명 컨트롤을 설정 합니다.|  
|[CListCtrl::SetView](#setview)|목록 뷰 컨트롤의 뷰를 설정합니다.|  
|[CListCtrl::SetWorkAreas](#setworkareas)|목록 뷰 컨트롤의 아이콘 표시 될 수 있는 영역을 설정 합니다.|  
|[CListCtrl::SortGroups](#sortgroups)|목록의 그룹을 정렬 합니다. 사용자 정의 함수를 사용 하 여 제어를 봅니다.|  
|[CListCtrl::SortItems](#sortitems)|응용 프로그램 정의 된 비교 함수를 사용 하 여 목록 보기 항목을 정렬 합니다.|  
|[CListCtrl::SortItemsEx](#sortitemsex)|응용 프로그램 정의 된 비교 함수를 사용 하 여 목록 보기 항목을 정렬 합니다.|  
|[CListCtrl::SubItemHitTest](#subitemhittest)|지정된 된 위치에 있는 경우 목록 보기 항목을 결정 합니다.|  
|[CListCtrl::Update](#update)|지정된 된 항목 자동으로 그려지도록 강제로 합니다.|  
  
## <a name="remarks"></a>주의  
 프로그램 아이콘 및 레이블 외에도 각 항목 아이콘 및 레이블 오른쪽 열에 표시 되는 정보가 있을 수 있습니다. 이 컨트롤 (및 따라서는 `CListCtrl` 클래스)은 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.  
  
 다음은의 간략 한 개요는 `CListCtrl` 클래스입니다. 개념, 자세한 설명은 [CListCtrl 사용 하 여](../../mfc/using-clistctrl.md) 및 [컨트롤](../../mfc/controls-mfc.md)합니다.  
  
## <a name="views"></a>보기  
 목록 뷰 컨트롤 "views." 라는 네 가지 방법으로 해당 콘텐츠를 표시할 수 있습니다.  
  
-   아이콘 보기  
  
     각 항목 아래에 레이블이 있는 큰 아이콘 (32 x 32 픽셀 단위)으로 표시 됩니다. 목록 보기 창에서 임의의 위치에 항목을 끌 수 있습니다.  
  
-   작은 아이콘 보기  
  
     각 항목의 오른쪽에 레이블이 있는 작은 아이콘 (16 x 16 픽셀)으로 표시 됩니다. 목록 보기 창에서 임의의 위치에 항목을 끌 수 있습니다.  
  
-   목록 보기  
  
     각 항목의 오른쪽에 레이블이 있는 작은 아이콘으로 표시 됩니다. 항목 열에서 정리 되 고 목록 보기 창에서 임의의 위치에 끌어 올 수 없습니다.  
  
-   보고서 보기  
  
     각 항목 오른쪽에 열으로 정렬 하는 추가 정보가 있는 별도 줄에 나타납니다. 작은 아이콘 및 레이블 맨 왼쪽 열 포함 고 후속 열 포함 응용 프로그램에 의해 지정 된 대로 하위 항목입니다. 포함 된 헤더 컨트롤 (클래스 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)) 이러한 열을 구현 합니다. 헤더 컨트롤 및 보고서 보기의 열에 대 한 자세한 내용은 참조 하십시오. [를 사용 하 여 CListCtrl: 제어 (보고서 뷰)에 열 추가](../../mfc/adding-columns-to-the-control-report-view.md)합니다.  
  
 다음 항목도 참조하세요.  
  
-   기술 자료 문서 Q250614: 방법: 보고서 뷰에서 CListCtrl 항목 정렬  
  
-   기술 자료 문서 Q200054: PRB: OnTimer()는 되지 호출 반복적으로 목록 컨트롤에 대 한  
  
 컨트롤의 현재 목록 보기의 스타일을 현재 보기를 결정합니다. 이러한 스타일과 사용법에 대 한 자세한 내용은 참조 하십시오. [를 사용 하 여 CListCtrl: 목록 컨트롤 스타일 변경](../../mfc/changing-list-control-styles.md)합니다.  
  
## <a name="extended-styles"></a>확장된 스타일  
 표준 목록 스타일 외에도 클래스 `CListCtrl` 다양 한 강화 된 기능을 제공 하는 확장된 스타일을 지원 합니다. 이 기능의 몇 가지 예는 다음과 같습니다.  
  
-   호버 선택  
  
     기능을 사용 자동으로 선택 항목의 특정 기간에 대 한 항목 위로 커서를 유지할 때입니다.  
  
-   가상 목록 보기  
  
     기능을 사용을 지원 하도록 컨트롤 `DWORD` 항목입니다. 이것이 가능한 것은 응용 프로그램에 대 한 항목 데이터를 관리 하는 오버 헤드를 배치 하 여입니다. 항목 선택 및 포커스 정보를 제외한 모든 항목 정보는 응용 프로그램에 의해 관리 되어야 합니다. 자세한 내용은 참조 [를 사용 하 여 CListCtrl: 가상 목록 컨트롤](../../mfc/virtual-list-controls.md)합니다.  
  
-   1 및&2; – 클릭 정품 인증  
  
     기능을 사용 (자동 강조 표시 된 항목 텍스트의) 하는 핫 트래킹 및 강조 표시 된 항목의 하나 또는 두 – 클릭 활성화 합니다.  
  
-   끌어서 놓기 열 순서  
  
     사용 하도록 설정 하면 끌어서 놓기는 목록 뷰 컨트롤의 열 순서를 바꿀 수 있습니다. 보고서 보기에서 사용할 수 있습니다.  
  
 확장 스타일을 사용 하 여 이러한 새로운에 대 한 정보, 참조 [를 사용 하 여 CListCtrl: 목록 컨트롤 스타일 변경](../../mfc/changing-list-control-styles.md)합니다.  
  
## <a name="items-and-subitems"></a>항목과 하위 항목  
 각 항목에는 목록 뷰 컨트롤 (이미지 목록)에서 아이콘, 레이블, 현재 상태 및 ("항목 데이터" 라고 함) 하는 응용 프로그램 정의 값으로 구성 됩니다. 하나 이상의 하위 항목 각 항목에 연결할 수도 있습니다. "하위"항목은 보고서 뷰에서 항목의 아이콘 및 레이블 오른쪽에 있는 열에 표시 될 수 있는 문자열입니다. 목록 뷰 컨트롤의 모든 항목에는 동일한 하위 항목 수가 있어야 합니다.  
  
 클래스 **CListCtrl** 삽입, 삭제, 찾기 및 이러한 항목의 수정에 대 한 몇 가지 기능을 제공 합니다. 자세한 내용은 참조 [CListCtrl::GetItem](#getitem), [CListCtrl::InsertItem](#insertitem), 및 [CListCtrl::FindItem](#finditem), [컨트롤에 항목 추가](../adding-items-to-the-control.md), 및 [스크롤, 정렬, 정렬 및 목록 컨트롤에서 찾는](../scrolling-arranging-sorting-and-finding-in-list-controls.md)합니다.  
  
 기본적으로 목록 뷰 컨트롤은 항목의 아이콘 및 텍스트 특성을 저장 합니다. 그러나 이러한 항목 형식은 외에도 클래스 `CListCtrl` 지원 ""콜백 항목입니다. "콜백 항목"가 있는 목록 보기 항목을 응용 프로그램-컨트롤 대신-텍스트, 아이콘 또는 둘 모두를 저장 합니다. 콜백 마스크는 지정 된 항목 특성 (텍스트 및/또는 아이콘)는 응용 프로그램에서 제공 하는 데 사용 됩니다. 콜백 항목을 사용 하는 응용 프로그램 필요에 따라 텍스트 및/또는 아이콘 특성을 제공할 수 있어야 합니다. 콜백 항목은 응용 프로그램이 이미이 정보 중 일부를 유지 관리 하는 경우에 유용 합니다. 자세한 내용은 참조 [를 사용 하 여 CListCtrl: 콜백 항목 및 콜백 마스크](../callback-items-and-the-callback-mask.md)합니다.  
  
## <a name="image-lists"></a>이미지 목록  
 아이콘, 헤더 항목 이미지 및 응용 프로그램 – 상태에 대해 정의 된 여러 이미지 목록에 목록 뷰 항목이 포함 된 (클래스에 의해 구현 [CImageList](cimagelist-class.md))를 만들고 목록 뷰 컨트롤에 할당 합니다. 각 목록 뷰 컨트롤에는 최대&4; 개의 서로 다른 유형의 이미지 목록 가질 수 있습니다.  
  
-   큰 아이콘  
  
     큰 아이콘에 대 한 아이콘 보기에 사용 합니다.  
  
-   작은 아이콘  
  
     더 작은 버전 아이콘 보기에 사용 되는 아이콘의 작은 아이콘, 목록 및 보고서 보기에 사용.  
  
-   응용 프로그램 정의 상태  
  
     응용 프로그램 정의 상태를 표시 하는 항목의 아이콘 옆에 표시 되는 상태 이미지를 포함 합니다.  
  
-   헤더 항목  
  
     각 헤더 컨트롤 항목에 표시 되는 작은 이미지에 대 한 보고서 보기에서 사용 합니다.  
  
 기본적으로는 목록 뷰 컨트롤 소멸; 소멸 될 때 할당 된 이미지 목록 그러나 개발자 응용 프로그램에 의해 결정 된 대로 더 이상 사용 하는 경우 각 이미지 목록 파괴 하 여이 동작을 사용자 지정할 수 없습니다. 자세한 내용은 참조 [를 사용 하 여 CListCtrl: 목록 항목 및 이미지 목록](../list-items-and-image-lists.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CListCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="a-nameapproximateviewrecta--clistctrlapproximateviewrect"></a><a name="approximateviewrect"></a>CListCtrl::ApproximateViewRect  
 너비와 높이 목록 뷰 컨트롤의 항목을 표시 하는 데 필요한 결정 합니다.  
  
```  
CSize ApproximateViewRect(
    CSize sz = CSize(-1,  
 -1),  
    int iCount = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `sz`  
 픽셀 단위의 컨트롤의 제안 된 차원입니다. 차원을 지정 하지 않은 경우 프레임 워크는 컨트롤의 현재 너비 또는 높이 값을 사용 합니다.  
  
 `iCount`  
 컨트롤에 표시할 항목 수입니다. 이 매개 변수가-1 인 경우 프레임 워크 사용 하 여 항목의 총 현재 컨트롤에 있습니다.  
  
### <a name="return-value"></a>반환 값  
 A `CSize` 대략적인 너비 및 높이 (픽셀)은 항목을 표시 하는 데 필요한 포함 된 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_ApproximateViewRect](http://msdn.microsoft.com/library/windows/desktop/bb761231)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namearrangea--clistctrlarrange"></a><a name="arrange"></a>CListCtrl::Arrange  
 눈금에 정렬 되도록 아이콘 보기의 항목 위치를 변경 합니다.  
  
```  
BOOL Arrange(UINT nCode);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCode`  
 항목에 대 한 맞춤 스타일을 지정합니다. 다음 값 중 하나일 수 있습니다.  
  
- `LVA_ALIGNLEFT`창의 왼쪽된 가장자리를 따라 항목을 정렬합니다.  
  
- `LVA_ALIGNTOP`창의 위쪽 가장자리를 따라 항목을 정렬합니다.  
  
- `LVA_DEFAULT`목록 보기의 현재 맞춤 스타일 (기본값)에 따라 항목을 정렬합니다.  
  
- `LVA_SNAPTOGRID`가장 가까운 모눈 위치까지 모든 아이콘을 맞춥니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 `nCode` 맞춤 스타일 매개 변수를 지정 합니다.  
  
### <a name="example"></a>예제    
```cpp  
    // Align all of the list view control items along the top
    // of the window (the list view control must be in icon or
    // small icon mode).
    m_myListCtrl.Arrange(LVA_ALIGNTOP);
```

  
##  <a name="a-namecanceleditlabela--clistctrlcanceleditlabel"></a><a name="canceleditlabel"></a>CListCtrl::CancelEditLabel  
 항목 텍스트 편집 작업을 취소 합니다.  
  
```  
void CancelEditLabel();
```  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_CANCELEDITLABEL](http://msdn.microsoft.com/library/windows/desktop/bb774886) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameclistctrla--clistctrlclistctrl"></a><a name="clistctrl"></a>CListCtrl::CListCtrl  
 `CListCtrl` 개체를 생성합니다.  
  
```  
CListCtrl();
```  
  
##  <a name="a-namecreatea--clistctrlcreate"></a><a name="create"></a>CListCtrl::Create  
 목록 컨트롤을 만들고에 연결 된 `CListCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 목록 컨트롤의 스타일을 지정합니다. 목록 컨트롤 스타일의 조합이 컨트롤에 적용 됩니다. 참조 [목록 보기 창 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774739) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)] 이러한 스타일의 전체 목록은 합니다. 확장 스타일을 사용 하 여 컨트롤에 특정 집합 [SetExtendedStyle](#setextendedstyle)합니다.  
  
 `rect`  
 목록 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 `CRect` 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
 `pParentWnd`  
 목록 컨트롤의 부모 창에 일반적으로 지정 된 `CDialog`합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 목록 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CListCtrl` 두 단계에서입니다. 먼저, 생성자를 호출 하 고 다음 호출 **만들기**, list view 컨트롤을 만들고 연결 하는 `CListCtrl` 개체입니다.  
  
 List 컨트롤 개체에 확장된 창 스타일을 적용할 호출 [CreateEx](#createex) 대신 **만들기**합니다.  
  
### <a name="example"></a>예제  

```cpp  
    m_myListCtrl.Create(
        WS_CHILD|WS_VISIBLE|WS_BORDER|LVS_REPORT|LVS_EDITLABELS,
        CRect(10,10,400,200), pParentWnd, IDD_MYLISTCTRL);   
```

  
##  <a name="a-namecreateexa--clistctrlcreateex"></a><a name="createex"></a>CListCtrl::CreateEx  
 컨트롤 (자식 창)와 연결 된 `CListCtrl` 개체입니다.  
  
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
 생성 되는 컨트롤의 확장된 스타일을 지정 합니다. 확장된 창 스타일의 목록에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 목록 컨트롤의 스타일을 지정합니다. 목록 컨트롤 스타일의 조합이 컨트롤에 적용 됩니다. 이러한 스타일의 전체 목록은 참조 하십시오. [목록 보기 창 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774739) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에서 만든 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 앞에 지정 된 Windows 확장된 스타일을 적용 하려면 **WS_EX_**합니다.  
  
 `CreateEx`지정 된 확장된 창 스타일을 사용 하 여 컨트롤을 만듭니다 `dwExStyle`합니다. 호출을 설정 하려면 확장된 스타일 특정 컨트롤에 [SetExtendedStyle](#setextendedstyle)합니다. 사용 예를 들어 `CreateEx` 으로 이러한 스타일을 설정 하려면 **WS_EX_CONTEXTHELP**를 사용 하지만 `SetExtendedStyle` 으로 이러한 스타일을 설정 하려면 **LVS_EX_FULLROWSELECT**합니다. 자세한 내용은 항목에서 설명 하는 스타일을 참조 하십시오. [확장 목록 뷰 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774732) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namecreatedragimagea--clistctrlcreatedragimage"></a><a name="createdragimage"></a>CListCtrl::CreateDragImage  
 지정 된 항목에 대 한 끌기 이미지 목록을 만듭니다 `nItem`합니다.  
  
```  
CImageList* CreateDragImage(
    int nItem,  
    LPPOINT lpPoint);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 끌기 이미지 목록이 있는 만들 항목의 인덱스입니다.  
  
 `lpPoint`  
 주소에 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 구조, 이미지의 왼쪽 위 모퉁이의 초기 위치를 보기에 조정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우에 끌기 이미지 목록에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 `CImageList` 개체, 영구 적용 되며 완료 되 면 삭제 해야 합니다. 예:  
  

```cpp  
        CImageList* pImageList = m_myListCtrl.CreateDragImage(nItem, &point);

        // do something

        delete pImageList;
```

  
##  <a name="a-namedeleteallitemsa--clistctrldeleteallitems"></a><a name="deleteallitems"></a>CListCtrl::DeleteAllItems  
 List view 컨트롤에서 모든 항목을 삭제합니다.  
  
```  
BOOL DeleteAllItems();
```  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  

```cpp  
    // Delete all of the items from the list view control.
    m_myListCtrl.DeleteAllItems();
    ASSERT(m_myListCtrl.GetItemCount() == 0);
```

  
##  <a name="a-namedeletecolumna--clistctrldeletecolumn"></a><a name="deletecolumn"></a>CListCtrl::DeleteColumn  
 List view 컨트롤에서 열을 삭제합니다.  
  
```  
BOOL DeleteColumn(int nCol);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCol`  
 삭제할 열의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  

```cpp  
        int nColumnCount = m_myListCtrl.GetHeaderCtrl()->GetItemCount();

        // Delete all of the columns.
        for (int i=0; i < nColumnCount; i++)
        {
            m_myListCtrl.DeleteColumn(0);
        }
```

  
##  <a name="a-namedeleteitema--clistctrldeleteitem"></a><a name="deleteitem"></a>CListCtrl::DeleteItem  
 목록 뷰 컨트롤에서 항목을 삭제합니다.  
  
```  
BOOL DeleteItem(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 삭제할 항목의 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  
```cpp  
        int nCount = m_myListCtrl.GetItemCount();

        // Delete all of the items from the list view control.
        for (int i=0; i < nCount; i++)
        {
            m_myListCtrl.DeleteItem(0);
        }
```

  
##  <a name="a-namedrawitema--clistctrldrawitem"></a><a name="drawitem"></a>CListCtrl::DrawItem  
 소유자 그리기 목록 보기 컨트롤의 시각적 측면이 될 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 긴 포인터는 `DRAWITEMSTRUCT` 필요한 드로잉의 종류에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>주의  
 **itemAction** 의 멤버는 [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) 구조 수행 되는 그리기 작업을 정의 합니다.  
  
 이 멤버 함수는 기본적으로 아무 작업도 수행합니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CListCtrl` 개체입니다.  
  
 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 인터페이스 (GDI) 개체를 복원 해야 `lpDrawItemStruct` 전에이 멤버 함수를 종료 합니다.  
  
##  <a name="a-nameeditlabela--clistctrleditlabel"></a><a name="editlabel"></a>CListCtrl::EditLabel  
 항목의 텍스트의 내부 편집을 시작 합니다.  
  
```  
CEdit* EditLabel(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 편집할 수 있는 목록 보기 항목의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우에 대 한 포인터는 `CEdit` 항목 텍스트를 편집 하는 데 사용 하 고, 그렇지 않으면 개체 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 가 있는 목록 보기 컨트롤은 `LVS_EDITLABELS` 창 스타일을 통해 사용자 위치에 항목 레이블을 편집할 수 있습니다. 사용자는 포커스가 있는 항목의 레이블을 클릭 하 여 편집을 시작 합니다.  
  
 지정 된 목록 뷰 항목 텍스트의 내부 편집을 시작 하려면이 함수를 사용 합니다.  
  
### <a name="example"></a>예제  
```cpp  
        // Make sure the focus is set to the list view control.
        m_myListCtrl.SetFocus();

        // Show the edit control on the label of the first
        // item in the list view control.
        CEdit* pmyEdit = m_myListCtrl.EditLabel(1);
        ASSERT(pmyEdit != NULL);
```

  
##  <a name="a-nameenablegroupviewa--clistctrlenablegroupview"></a><a name="enablegroupview"></a>CListCtrl::EnableGroupView  
 목록 뷰 컨트롤의 항목을 그룹으로 표시할지 여부를 사용 하지 않도록 설정 하거나 사용 합니다.  
  
```  
LRESULT EnableGroupView(BOOL fEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 `fEnable`  
 항목 표시 listview 컨트롤 그룹을 사용할 수 있도록 여부를 나타냅니다. **True 이면** 그룹화를 사용 하도록 설정 하려면 **FALSE** 사용 하지 않도록 합니다.  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
- **0** 목록 보기를 표시 하는 기능 항목으로 그룹을 이미 활성화 하거나 비활성화 합니다.  
  
- **1** 컨트롤의 상태가 변경 되었습니다.  
  
- **-1** 작업이 실패 했습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_ENABLEGROUPVIEW](http://msdn.microsoft.com/library/windows/desktop/bb774900) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameensurevisiblea--clistctrlensurevisible"></a><a name="ensurevisible"></a>CListCtrl::EnsureVisible  
 목록 보기 항목을 부분적으로 표시 적어도 중인지 확인 합니다.  
  
```  
BOOL EnsureVisible(
    int nItem,  
    BOOL bPartialOK);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 이 표시 되도록 하는 목록 보기 항목의 인덱스입니다.  
  
 `bPartialOK`  
 부분 가시성을 허용할지 여부를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 필요한 경우 list view 컨트롤이 스크롤됩니다. 하는 경우는 `bPartialOK` 매개 변수는&0;이 아니고, 스크롤이 되지 않는 항목은 부분적으로 표시 하는 경우 발생 합니다.  
  
### <a name="example"></a>예제  
```cpp  
        // Ensure that the last item is visible.
        int nCount = m_myListCtrl.GetItemCount();
        if (nCount > 0)
            m_myListCtrl.EnsureVisible(nCount-1, FALSE);
```

  
##  <a name="a-namefinditema--clistctrlfinditem"></a><a name="finditem"></a>CListCtrl::FindItem  
 지정 된 특징을 가진 목록 보기 항목을 검색 합니다.  
  
```  
int FindItem(
    LVFINDINFO* pFindInfo,  
    int nStart = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pFindInfo`  
 에 대 한 포인터는 [LVFINDINFO](http://msdn.microsoft.com/library/windows/desktop/bb774745) 검색 한 항목에 대 한 정보가 포함 된 구조입니다.  
  
 `nStart`  
 -1을 처음부터 시작, 검색을 시작할 항목의 인덱스입니다. 에 있는 항목 `nStart` 경우 검색에서 제외 `nStart` -1과 같지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면-1 성공 하는 경우 항목의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 `pFindInfo` 매개 변수가 가리키는 **LVFINDINFO** 구조를 검색 하는 데 목록 보기 항목에 대 한 정보를 포함 합니다.  
  
### <a name="example"></a>예제  

```cpp  
        LVFINDINFO info;
        int nIndex;

        info.flags = LVFI_PARTIAL|LVFI_STRING;
        info.psz = _T("item");

        // Delete all of the items that begin with the string.
        while ((nIndex = m_myListCtrl.FindItem(&info)) != -1)
        {
            m_myListCtrl.DeleteItem(nIndex);
        }
```

  
##  <a name="a-namegetbkcolora--clistctrlgetbkcolor"></a><a name="getbkcolor"></a>CListCtrl::GetBkColor  
 목록 뷰 컨트롤의 배경색을 검색합니다.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 색을 지정 하는 데 사용 되는 32 비트 값입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::SetBkColor](#setbkcolor)합니다.  
  
##  <a name="a-namegetbkimagea--clistctrlgetbkimage"></a><a name="getbkimage"></a>CListCtrl::GetBkImage  
 목록 뷰 컨트롤의 현재 배경 이미지를 검색합니다.  
  
```  
BOOL GetBkImage(LVBKIMAGE* plvbkImage) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `plvbkImage`  
 에 대 한 포인터는 **LVBKIMAGE** 목록 보기의 현재 배경 이미지를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면&0; 또는 성공 하면&0;이 아닌 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 Win32 매크로의 동작을 구현 [ListView_GetBkImage](http://msdn.microsoft.com/library/windows/desktop/bb761246)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

```cpp  
        LVBKIMAGE bki;

        // If no background image is set for the list view control use
        // the Microsoft homepage image as the background image.
        if (m_myListCtrl.GetBkImage(&bki) && (bki.ulFlags == LVBKIF_SOURCE_NONE))
        {
            m_myListCtrl.SetBkImage(
                _T("http://www.microsoft.com/library/images/gifs/homepage/microsoft.gif"),
                TRUE);
        }
```

  
##  <a name="a-namegetcallbackmaska--clistctrlgetcallbackmask"></a><a name="getcallbackmask"></a>CListCtrl::GetCallbackMask  
 목록 뷰 컨트롤에 대 한 콜백 마스크를 검색합니다.  
  
```  
UINT GetCallbackMask() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 뷰 컨트롤의 콜백 마스크입니다.  
  
### <a name="remarks"></a>주의  
 "콜백 항목"가 있는 목록 보기 항목을 응용 프로그램-컨트롤 대신-텍스트, 아이콘 또는 둘 모두를 저장 합니다. 목록 뷰 컨트롤을 이러한 특성을 저장할 수, 있지만이 정보 중 일부 응용 프로그램에서 이미 유지 되는 경우 콜백 항목을 사용 하는 것이 좋습니다. 전체 컨트롤에는 대신 특정 항목에 적용 됩니다 및 콜백 마스크 항목 상태 비트는 응용 프로그램에서 유지 관리를 지정 합니다. 콜백 마스크는 기본적으로 컨트롤 모든 항목 상태를 추적 하는&0;입니다. 콜백 항목을 사용 하 여 응용 프로그램 또는&0;이 아니고 콜백 마스크를 지정 하는 경우 필요에 따라 목록 보기 항목 특성을 제공할 수 있어야 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::SetCallbackMask](#setcallbackmask)합니다.  
  
##  <a name="a-namegetchecka--clistctrlgetcheck"></a><a name="getcheck"></a>CListCtrl::GetCheck  
 항목과 연결 되는 상태 이미지의 현재 상태 표시를 검색 합니다.  
  
```  
BOOL GetCheck(int nItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 목록 컨트롤 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 선택 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetCheckState](http://msdn.microsoft.com/library/windows/desktop/bb761250)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::SetCheck](#setcheck)합니다.  
  
##  <a name="a-namegetcolumna--clistctrlgetcolumn"></a><a name="getcolumn"></a>CListCtrl::GetColumn  
 목록 뷰 컨트롤의 열 특성을 검색 합니다.  
  
```  
BOOL GetColumn(
    int nCol,  
    LVCOLUMN* pColumn) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nCol`  
 검색 된 특성을 가진 열의 인덱스입니다.  
  
 `pColumn`  
 주소에 [LVCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) 검색할 정보를 지정 하 고 열에 대 한 정보를 수신 하는 구조입니다. **마스크** 멤버를 검색 하는 열 특성을 지정 합니다. 경우는 **마스크** 멤버 지정는 `LVCF_TEXT` 값은 **pszText** 멤버 항목의 텍스트를 받는 버퍼의 주소를 포함 해야 및 **cchTextMax** 멤버 버퍼의 크기를 지정 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 **LVCOLUMN** 구조는 보고서 보기의 열에 대 한 정보를 포함 합니다.  
  
### <a name="example"></a>예제  

```cpp  
        LVCOLUMN col;

        col.mask = LVCF_WIDTH;

        // Double the column width of the first column.
        if (m_myListCtrl.GetColumn(0, &col))
        {
            col.cx *= 2;
            m_myListCtrl.SetColumn(0, &col);
        }
```

  
##  <a name="a-namegetcolumnorderarraya--clistctrlgetcolumnorderarray"></a><a name="getcolumnorderarray"></a>CListCtrl::GetColumnOrderArray  
 목록 뷰 컨트롤의 열 순서 (왼쪽에서 오른쪽)를 검색 합니다.  
  
```  
BOOL GetColumnOrderArray(
    LPINT piArray,  
    int iCount = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 `piArray`  
 목록 뷰 컨트롤의 열 인덱스 값이 포함 될 버퍼에 대 한 포인터입니다. 버퍼는 목록 뷰 컨트롤에서 열의 총 수를 포함할 수 있는 크기 여야 합니다.  
  
 `iCount`  
 목록 뷰 컨트롤에서 열 수입니다. 이 매개 변수가-1 인 경우 열 수가 프레임 워크에 의해 자동으로 검색 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetColumnOrderArray](http://msdn.microsoft.com/library/windows/desktop/bb761254)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

```cpp  
        // Reverse the order of the columns in the list view control
        // (i.e. make the first column the last, the last column
        // the first, and so on...).
        CHeaderCtrl* pHeaderCtrl = m_myListCtrl.GetHeaderCtrl();

        if (pHeaderCtrl != NULL)
        {
            int  nColumnCount = pHeaderCtrl->GetItemCount();
            LPINT pnOrder = (LPINT) malloc(nColumnCount*sizeof(int));
            ASSERT(pnOrder != NULL);
m_myListCtrl.GetColumnOrderArray(pnOrder, nColumnCount);

            int i, j, nTemp;
            for (i = 0, j = nColumnCount-1; i < j; i++, j--)
            {
                nTemp = pnOrder[i];
                pnOrder[i] = pnOrder[j];
                pnOrder[j] = nTemp;
            }

            m_myListCtrl.SetColumnOrderArray(nColumnCount, pnOrder);
            free(pnOrder);
        }
```

  
##  <a name="a-namegetcolumnwidtha--clistctrlgetcolumnwidth"></a><a name="getcolumnwidth"></a>CListCtrl::GetColumnWidth  
 보고서 보기 또는 목록 보기에서 열 너비를 검색합니다.  
  
```  
int GetColumnWidth(int nCol) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nCol`  
 너비는 검색할 열의 인덱스를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 너비 (픽셀)로 지정 된 열의 `nCol`합니다.  
  
### <a name="example"></a>예제  

```cpp  
        // Increase the column width of the second column by 20.
        int nWidth = m_myListCtrl.GetColumnWidth(1);
        m_myListCtrl.SetColumnWidth(1, 20 + nWidth);
```

  
##  <a name="a-namegetcountperpagea--clistctrlgetcountperpage"></a><a name="getcountperpage"></a>CListCtrl::GetCountPerPage  
 목록 보기 또는 보고서 보기에는 목록 뷰 컨트롤의 표시 영역에 세로로 들어갈 수 있는 항목의 수를 계산 합니다.  
  
```  
int GetCountPerPage() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 보기 또는 보고서 보기에는 목록 뷰 컨트롤의 표시 영역에 세로로 들어갈 수 있는 항목의 수입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetTopIndex](#gettopindex)합니다.  
  
##  <a name="a-namegeteditcontrola--clistctrlgeteditcontrol"></a><a name="geteditcontrol"></a>CListCtrl::GetEditControl  
 목록 보기 항목의 텍스트를 편집 하는 데 사용 하는 편집 컨트롤의 핸들을 검색 합니다.  
  
```  
CEdit* GetEditControl() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우에 대 한 포인터는 [CEdit](cedit-class.md) 항목 텍스트를 편집 하는 데 사용 하 고, 그렇지 않으면 개체 **NULL**합니다.  
  
### <a name="example"></a>예제  

```cpp  
        // The string replacing the text in the edit control.
        LPCTSTR lpszmyString = _T("custom label!");

        // If possible, replace the text in the label edit control.
        CEdit* pEdit = m_myListCtrl.GetEditControl();

        if (pEdit != NULL)
        {
            pEdit->SetWindowText(lpszmyString);
        }
```

  
##  <a name="a-namegetemptytexta--clistctrlgetemptytext"></a><a name="getemptytext"></a>CListCtrl::GetEmptyText  
 현재 목록 뷰 컨트롤이 비어 있으면 표시할 문자열을 검색 합니다.  
  
```  
CString GetEmptyText() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 컨트롤이 빈 경우 표시할 텍스트를 포함 하는 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_GETEMPTYTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774921) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetextendedstylea--clistctrlgetextendedstyle"></a><a name="getextendedstyle"></a>CListCtrl::GetExtendedStyle  
 목록 뷰 컨트롤의 현재 확장된 스타일을 검색합니다.  
  
```  
DWORD GetExtendedStyle();
```  
  
### <a name="return-value"></a>반환 값  
 목록에서 사용 중인 확장된 스타일의 조합 뷰 컨트롤입니다. 이러한 확장된 스타일 목록은 설명이 포함 된 참조는 [확장 목록 뷰 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774732) 항목에는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetExtendedListViewStyle](http://msdn.microsoft.com/library/windows/desktop/bb761264)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::SetExtendedStyle](#setextendedstyle)합니다.  
  
##  <a name="a-namegetfirstselecteditempositiona--clistctrlgetfirstselecteditemposition"></a><a name="getfirstselecteditemposition"></a>CListCtrl::GetFirstSelectedItemPosition  
 목록 뷰 컨트롤에서 선택된 된 첫 번째 항목의 위치를 가져옵니다.  
  
```  
POSITION GetFirstSelectedItemPosition() const;  
```  
  
### <a name="return-value"></a>반환 값  
 A **위치** 반복 또는 개체 포인터 검색;에 사용할 수 있는 값 **NULL** 없는 항목을 선택 합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는이 함수의 사용을 보여 줍니다.  
  

```cpp  
        POSITION pos = m_myListCtrl.GetFirstSelectedItemPosition();
        if (pos == NULL)
        {
            TRACE(_T("No items were selected!\n"));
        }
        else
        {
            while (pos)
            {
                int nItem = m_myListCtrl.GetNextSelectedItem(pos);
                TRACE(_T("Item %d was selected!\n"), nItem);
                // you could do your own processing on nItem here
            }
        }
```

  
##  <a name="a-namegetfocusedgroupa--clistctrlgetfocusedgroup"></a><a name="getfocusedgroup"></a>CListCtrl::GetFocusedGroup  
 현재 목록 뷰 컨트롤에 키보드 포커스가 있는 그룹을 검색 합니다.  
  
```  
int GetFocusedGroup() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상태 그룹의 인덱스 `LVGS_FOCUSED`이러한 그룹; 하는 경우, 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_GETFOCUSEDGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774925) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 자세한 내용은 참조는 `LVGS_FOCUSED` 값은 `state` 의 멤버는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 구조입니다.  
  
##  <a name="a-namegetgroupcounta--clistctrlgetgroupcount"></a><a name="getgroupcount"></a>CListCtrl::GetGroupCount  
 현재 목록 뷰 컨트롤의 그룹 수를 검색합니다.  
  
```  
int GetGroupCount()const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 뷰 컨트롤의 그룹 수를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_GETGROUPCOUNT](http://msdn.microsoft.com/library/windows/desktop/bb774931) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)] --> 합니다.  
  
##  <a name="a-namegetgroupinfoa--clistctrlgetgroupinfo"></a><a name="getgroupinfo"></a>CListCtrl::GetGroupInfo  
 지정된 된 그룹 목록 뷰 컨트롤에 대 한 정보를 가져옵니다.  
  
```  
int GetGroupInfo(
    int iGroupId,  
    PLVGROUP pgrp) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `iGroupId`  
 해당 정보를 검색 하는 그룹의 식별자입니다.  
  
 `pgrp`  
 에 대 한 포인터는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 지정 된 그룹에 대 한 정보를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 성공 하면 그룹 또는-1의 ID를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETGROUPINFO](http://msdn.microsoft.com/library/windows/desktop/bb774932) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetgroupinfobyindexa--clistctrlgetgroupinfobyindex"></a><a name="getgroupinfobyindex"></a>CListCtrl::GetGroupInfoByIndex  
 현재 목록 뷰 컨트롤에서 지정된 된 그룹에 대 한 정보를 검색합니다.  
  
```  
BOOL GetGroupInfoByIndex(
    int iIndex,   
    PLVGROUP pGroup) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iIndex`|그룹의 인덱스&0;부터 시작 합니다.|  
|[out] `pGroup`|에 대 한 포인터는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 구조에서 지정한 그룹에 대 한 정보를 수신 하는 `iIndex` 매개 변수입니다.<br /><br /> 호출자의 멤버를 초기화 하는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 구조입니다. 설정의 `cbSize` 구조체의 크기 및 플래그의 멤버는 `mask` 검색할 정보를 지정 하는 멤버입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_GETGROUPINFOBYINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774933) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)] --> 합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_listCtrl`, 즉 현재 목록 뷰 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  

```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>예제  
 다음 코드 예제는 `GetGroupInfoByIndex` 메서드. 이 코드의 이전 섹션에는 목록 뷰 컨트롤 만든 예제 보고서 보기에서 "ClientID" 및 "등급" 라는 두 개의 열을 표시 합니다. 다음 코드 예제에서는 이러한 그룹이 있으면 해당 인덱스는 0, 그룹에 대 한 정보를 검색 합니다.    
```cpp  
    // GetGroupInfoByIndex
    const int GROUP_HEADER_BUFFER_SIZE = 40;

// Initialize the structure 
    LVGROUP gInfo = {0};
    gInfo.cbSize = sizeof(LVGROUP);
    wchar_t wstrHeadGet[GROUP_HEADER_BUFFER_SIZE] = {0};
    gInfo.cchHeader = GROUP_HEADER_BUFFER_SIZE;
    gInfo.pszHeader = wstrHeadGet;
    gInfo.mask = (LVGF_ALIGN | LVGF_STATE | LVGF_HEADER | LVGF_GROUPID);
    gInfo.state = LVGS_NORMAL;
    gInfo.uAlign  = LVGA_HEADER_LEFT;

    BOOL bRet = m_listCtrl.GetGroupInfoByIndex( 0, &gInfo );
    if (bRet == TRUE) {
        CString strHeader = CString( gInfo.pszHeader );
        CString str;
        str.Format(_T("Header: '%s'"), strHeader);
        AfxMessageBox(str, MB_ICONINFORMATION);
    }
    else
    {
        AfxMessageBox(_T("No group information was retrieved."));
    }
```

  
##  <a name="a-namegetgroupmetricsa--clistctrlgetgroupmetrics"></a><a name="getgroupmetrics"></a>CListCtrl::GetGroupMetrics  
 그룹의 메트릭을 검색합니다.  
  
```  
void GetGroupMetrics(PLVGROUPMETRICS pGroupMetrics) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pGroupMetrics`  
 에 대 한 포인터는 [LVGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb774752) 그룹 메트릭 정보를 포함 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb774934) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetgrouprecta--clistctrlgetgrouprect"></a><a name="getgrouprect"></a>CListCtrl::GetGroupRect  
 현재 목록 뷰 컨트롤에서 지정된 된 그룹에 대 한 경계 사각형을 검색 합니다.  
  
```  
BOOL GetGroupRect(
    int iGroupId,   
    LPRECT lpRect,   
    int iCoords = LVGGR_GROUP) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iGroupId`|그룹을 지정합니다.|  
|[in, out] `lpRect`|에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다. 이 메서드가 성공적 이면 구조 좌표가 사각형으로 지정 된 그룹의 `iGroupId`합니다.|  
|[in] `iCoords`|검색할 사각형 좌표를 지정 합니다. 다음이 값 중 하나를 사용 합니다.<br /><br /> - `LVGGR_GROUP`-전체 확장 된 그룹의 (기본값) 좌표입니다.<br />- `LVGGR_HEADER`좌표 헤더 (축소 된 그룹)입니다.<br />- `LVGGR_SUBSETLINK`좌표 (태그 하위 집합) 하위 집합 링크만입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 호출자가 할당 해야는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 가리키는 구조는 `pRect` 매개 변수입니다.  
  
 이 메서드는 전송 된 [LVM_GETGROUPRECT](http://msdn.microsoft.com/library/windows/desktop/bb774935) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_listCtrl`, 즉 현재 목록 뷰 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.    
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>예제  
 다음 코드 예제는 `GetGroupRect` 메서드. 이 코드 예제에서는 이전 단원에서 "ClientID" 및 "등급"이 보고서 뷰에서 라는 두 개의 열을 표시 하는 목록 뷰 컨트롤을 만들었습니다. 다음 코드 예제에서는 이러한 그룹이 있으면 해당 인덱스는 0, 그룹 주위 3D 사각형을 그립니다.    
  
```cpp  
    // GetGroupRect

    // Get the graphics rectangle that surrounds group 0.
    CRect rect;
    BOOL bRet = m_listCtrl.GetGroupRect( 0, &rect, LVGGR_GROUP); 
    // Draw a blue rectangle around group 0.
    if (bRet == TRUE) {
        m_listCtrl.GetDC()->Draw3dRect( &rect, RGB(0, 0, 255), RGB(0, 0, 255));
    }
    else {
        AfxMessageBox(_T("No group information was retrieved."), MB_ICONINFORMATION);
    }
```

  
##  <a name="a-namegetgroupstatea--clistctrlgetgroupstate"></a><a name="getgroupstate"></a>CListCtrl::GetGroupState  
 현재 목록 뷰 컨트롤에서 지정된 된 그룹에 대 한 상태를 검색합니다.  
  
```  
UINT GetGroupState(
    int iGroupId,   
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iGroupId`|그룹의 인덱스&0;부터 시작 합니다.|  
|[in] `dwMask`|지정된 된 그룹에 대 한 검색 하는 상태 값을 지정 하는 마스크입니다. 자세한 내용은 참조는 `mask` 의 멤버는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 구조입니다.|  
  
### <a name="return-value"></a>반환 값  
 지정된 된 그룹 또는 그룹을 찾을 수 없는 경우 0에 대 한 요청 된 상태입니다.  
  
### <a name="remarks"></a>주의  
 반환 값에 비트 AND 연산의 결과이 `dwMask` 의 값과 매개 변수는 `state` 의 멤버는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 현재 목록 뷰 컨트롤을 나타내는 구조입니다.  
  
 이 메서드는 전송 된 [LVM_GETGROUPSTATE](http://msdn.microsoft.com/library/windows/desktop/bb774936) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 자세한 내용은 참조는 [ListView_GetGroupState](http://msdn.microsoft.com/library/windows/desktop/bb761288) 매크로입니다.  
  
##  <a name="a-namegetheaderctrla--clistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CListCtrl::GetHeaderCtrl  
 목록 뷰 컨트롤의 헤더 컨트롤을 검색합니다.  
  
```  
CHeaderCtrl* GetHeaderCtrl();
```  
  
### <a name="return-value"></a>반환 값  
 List view 컨트롤에서 사용 하는 헤더 컨트롤에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetHeader](http://msdn.microsoft.com/library/windows/desktop/bb761290)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetColumnOrderArray](#getcolumnorderarray)합니다.  
  
##  <a name="a-namegethotcursora--clistctrlgethotcursor"></a><a name="gethotcursor"></a>CListCtrl::GetHotCursor  
 목록 뷰 컨트롤에 대해 핫 트래킹을 때 사용 되는 커서를 검색 합니다.  
  
```  
HCURSOR GetHotCursor();
```  
  
### <a name="return-value"></a>반환 값  
 List view 컨트롤에서 사용 중인 현재 핫 커서 리소스에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetHotCursor](http://msdn.microsoft.com/library/windows/desktop/bb761292)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 핫 커서 호버 선택을 사용 하는 경우에 표시 되는 모든 목록 보기 항목 위로 커서를 이동할 때 나타납니다. 설정 하 여 호버 선택을 사용 하는지는 **LVS_EX_TRACKSELECT** 확장 스타일입니다.  
  
### <a name="example"></a>예제    
  
```cpp  
        // Set the hot cursor to be the system app starting cursor.
        HCURSOR hCursor = ::LoadCursor(NULL, IDC_APPSTARTING);
        m_myListCtrl.SetHotCursor(hCursor);
        ASSERT(m_myListCtrl.GetHotCursor() == hCursor);
```

  
##  <a name="a-namegethotitema--clistctrlgethotitem"></a><a name="gethotitem"></a>CListCtrl::GetHotItem  
 커서에서 현재 목록 보기 항목을 검색합니다.  
  
```  
int GetHotItem();
```  
  
### <a name="return-value"></a>반환 값  
 목록 뷰 컨트롤의 현재 활성 항목의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetHotItem](http://msdn.microsoft.com/library/windows/desktop/bb761294)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 핫 추적 (및 선택 마우스를 이동) 하는 경우 현재 선택 된 항목을 사용할 수 있는 핫 항목 정의 됩니다.  
  
 핫 트래킹을 사용 사용자 목록 보기 항목 위에 놓을 때을 하는 경우 항목 레이블은 마우스 단추를 사용 하지 않고 자동으로 강조 표시 됩니다.  
  
### <a name="example"></a>예제    
  
```cpp  
    // Set the hot item to the first item only if no other item is 
    // highlighted.
    if (m_myListCtrl.GetHotItem() == -1)
        m_myListCtrl.SetHotItem(0);
```

  
##  <a name="a-namegethovertimea--clistctrlgethovertime"></a><a name="gethovertime"></a>CListCtrl::GetHoverTime  
 목록 뷰 컨트롤의 현재 호버 시간을 검색합니다.  
  
```  
DWORD GetHoverTime() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 선택 되기 전에 마우스 커서를 항목 위로 해야 밀리초 지연 시간을 반환 합니다. 반환 값이-1 인 경우 다음 호버 시간은 기본 호버 시간입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetHoverTime](http://msdn.microsoft.com/library/windows/desktop/bb761296)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제    
  
```cpp  
        // If the hover time is the default set to 1 sec.
        DWORD dwTime = m_myListCtrl.GetHoverTime();
        if (dwTime == -1)
            m_myListCtrl.SetHoverTime(1000);
```

  
##  <a name="a-namegetimagelista--clistctrlgetimagelist"></a><a name="getimagelist"></a>CListCtrl::GetImageList  
 그리기 항목 목록 보기에 사용 되는 이미지 목록의 핸들을 검색 합니다.  
  
```  
CImageList* GetImageList(int nImageList) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nImageList`  
 검색 하는 이미지 목록을 지정 하는 값입니다. 다음이 값 중 하나일 수 있습니다.  
  
- `LVSIL_NORMAL`큰 아이콘으로 이미지 목록입니다.  
  
- `LVSIL_SMALL`작은 아이콘에 있는 이미지 목록입니다.  
  
- `LVSIL_STATE`상태 이미지와 이미지 목록입니다.  
  
### <a name="return-value"></a>반환 값  
 목록 보기 항목을 그리는 데 사용 되는 이미지 목록에 대 한 포인터입니다.  
  
### <a name="example"></a>예제    
  
```cpp  
        ASSERT(m_myListCtrl.GetImageList(LVSIL_NORMAL) == NULL);
m_myListCtrl.SetImageList(&m_lcImageList, LVSIL_NORMAL);
        ASSERT(m_myListCtrl.GetImageList(LVSIL_NORMAL) == &m_lcImageList);
```

  
##  <a name="a-namegetinsertmarka--clistctrlgetinsertmark"></a><a name="getinsertmark"></a>CListCtrl::GetInsertMark  
 삽입 표시의 현재 위치를 검색합니다.  
  
```  
BOOL GetInsertMark(LPLVINSERTMARK lvim) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lvim`  
 에 대 한 포인터는 [LVINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774758) 있는 삽입 표시에 대 한 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 하는 경우 또는 **FALSE** 그렇지 않은 경우. **FALSE** 경우 반환 됩니다의 크기는 `cbSize` 의 멤버는 **LVINSERTMARK** 구조 구조체의 실제 크기와 같지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774945) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetinsertmarkcolora--clistctrlgetinsertmarkcolor"></a><a name="getinsertmarkcolor"></a>CListCtrl::GetInsertMarkColor  
 삽입 표시의 현재 색을 검색 합니다.  
  
```  
COLORREF GetInsertMarkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 삽입 지점의 색을 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774947) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetinsertmarkrecta--clistctrlgetinsertmarkrect"></a><a name="getinsertmarkrect"></a>CListCtrl::GetInsertMarkRect  
 삽입점을 제한 하는 사각형을 검색 합니다.  
  
```  
int GetInsertMarkRect(LPRECT pRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pRect`  
 에 대 한 포인터는 `RECT` 삽입 포인터를 제한 하는 사각형의 좌표를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
- **0** 삽입 지점을 찾을 수 없습니다.  
  
- **1** 삽입 지점을 찾을 수 있습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETINSERTMARKRECT](http://msdn.microsoft.com/library/windows/desktop/bb774949) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetitema--clistctrlgetitem"></a><a name="getitem"></a>CListCtrl::GetItem  
 목록 보기 항목을 특성의 일부 또는 전부를 검색합니다.  
  
```  
BOOL GetItem(LVITEM* pItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 에 대 한 포인터는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 구조체 항목의 특성입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 **LVITEM** 구조 지정 하거나 목록 보기 항목의 특성을 받습니다.  
  
##  <a name="a-namegetitemcounta--clistctrlgetitemcount"></a><a name="getitemcount"></a>CListCtrl::GetItemCount  
 목록 뷰 컨트롤의 항목 수를 검색합니다.  
  
```  
int GetItemCount() const; 
```  
  
### <a name="return-value"></a>반환 값  
 목록 뷰 컨트롤의 항목 수를 지정 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::DeleteItem](#deleteitem)합니다.  
  
##  <a name="a-namegetitemdataa--clistctrlgetitemdata"></a><a name="getitemdata"></a>CListCtrl::GetItemData  
 지정 된 항목과 연결 된 32 비트 응용 프로그램 관련 값을 검색 `nItem`합니다.  
  
```  
DWORD_PTR GetItemData(int nItem) const; 
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 데이터가 검색 된 목록 항목의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 항목에 연결 하는 32 비트 응용 프로그램 관련 값입니다.  
  
### <a name="remarks"></a>주의  
 이 값은는 **lParam** 의 멤버는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 에 설명 된 대로 구조는[!INCLUDE[winSDK](./includes/winsdk_md.md)]  
  
### <a name="example"></a>예제  

```cpp  
    // If any item's data is equal to zero then reset it to -1.
    for (int i=0; i < m_myListCtrl.GetItemCount(); i++)
    {
        if (m_myListCtrl.GetItemData(i) == 0)
        {
            m_myListCtrl.SetItemData(i, (DWORD) -1);
        }
    }
```

  
##  <a name="a-namegetitemindexrecta--clistctrlgetitemindexrect"></a><a name="getitemindexrect"></a>CListCtrl::GetItemIndexRect  
 현재 목록 뷰 컨트롤의 하위 항목의 전체 또는 일부에 대 한 경계 사각형을 검색 합니다.  
  
```  
BOOL GetItemIndexRect(
    PLVITEMINDEX pItemIndex,   
    int iColumn,   
    int rectType,   
    LPRECT pRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pItemIndex`|에 대 한 포인터는 [LVITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774762) 하위 항목의 부모 항목에 대 한 구조입니다.<br /><br /> 호출자는 할당의 멤버를 설정 하는 [LVITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774762) 구조입니다. 이 매개 변수 수 없습니다 `NULL`합니다.|  
|[in] `iColumn`|컨트롤에 있는 열의&0;부터 시작 인덱스입니다.|  
|[in] `rectType`|경계 사각형을 검색 되는 목록 뷰 하위 항목의 일부입니다. 다음 값 중 하나를 지정합니다.<br /><br /> `LVIR_BOUNDS`-아이콘 및 레이블을 포함 하 여 전체 하위 항목의 경계 사각형을 반환 합니다.<br /><br /> `LVIR_ICON`-아이콘 또는 작은 아이콘의 하위 항목의 경계 사각형을 반환합니다.<br /><br /> `LVIR_LABEL`-하위 항목 텍스트의 경계 사각형을 반환합니다.|  
|[out] `pRect`|에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 하위 항목의 경계 사각형에 대 한 정보를 수신 하는 구조입니다.<br /><br /> 호출자가 할당 된 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다. 이 매개 변수 수 없습니다 `NULL`합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_GETITEMINDEXRECT](http://msdn.microsoft.com/library/windows/desktop/bb761046) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 자세한 내용은 참조 [ListView_GetItemIndexRect 매크로](http://msdn.microsoft.com/library/windows/desktop/bb774959)합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_listCtrl`, 즉 현재 목록 뷰 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.    
  
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>예제  
 다음 코드 예제는 `GetGroupRect` 메서드. 이 코드를 입력 하기 전에 목록 뷰 컨트롤 만든 예제 보고서 보기에서 "ClientID" 및 "등급" 라는 두 개의 열을 표시 합니다. 다음 코드 예제에서는 두 열 모두에 두 번째 하위 항목 주위 3D 사각형을 그립니다.    
  
```cpp  
    // GetItemIndexRect
    // Get the rectangle that bounds the second item in the first group.
    LVITEMINDEX lvItemIndex;
    lvItemIndex.iGroup = 0;
    lvItemIndex.iItem = 1;
    CRect rect;
    BOOL bRet = m_listCtrl.GetItemIndexRect(
        &lvItemIndex, 0, LVIR_BOUNDS, &rect);

    // Draw a red rectangle around the item.
    m_listCtrl.GetDC()->Draw3dRect( &rect, RGB(255, 0, 0), RGB(255, 0, 0) );
```

  
##  <a name="a-namegetitempositiona--clistctrlgetitemposition"></a><a name="getitemposition"></a>CListCtrl::GetItemPosition  
 목록 보기 항목의 위치를 검색 합니다.  
  
```  
BOOL GetItemPosition(
    int nItem,  
    LPPOINT lpPoint) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 해당 위치를 검색할 항목의 인덱스입니다.  
  
 `lpPoint`  
 주소에 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 항목의 왼쪽 위 모퉁이의 위치를 수신 하는 구조 보기에서 조정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제    
  
```cpp  
        POINT pt;

        // Move all items in the list control 100 pixels to the right.
        UINT i, nCount = m_myListCtrl.GetItemCount();

        for (i=0; i < nCount; i++)
        {
            m_myListCtrl.GetItemPosition(i, &pt);
            pt.x += 100;
            m_myListCtrl.SetItemPosition(i, pt);
        }   
```

  
##  <a name="a-namegetitemrecta--clistctrlgetitemrect"></a><a name="getitemrect"></a>CListCtrl::GetItemRect  
 현재 보기에서 항목의 전체 또는 일부에 대 한 경계 사각형을 검색 합니다.  
  
```  
BOOL GetItemRect(
    int nItem,  
    LPRECT lpRect,  
    UINT nCode) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 해당 위치를 검색할 항목의 인덱스입니다.  
  
 `lpRect`  
 주소에 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조체는 경계 사각형입니다.  
  
 `nCode`  
 목록 보기 항목을 검색할 경계 사각형의 일부입니다. 다음이 값 중 하나일 수 있습니다.  
  
- `LVIR_BOUNDS`아이콘 및 레이블을 포함 하 여 전체 항목의 경계 사각형을 반환 합니다.  
  
- `LVIR_ICON`아이콘 또는 작은 아이콘의 경계 사각형을 반환합니다.  
  
- `LVIR_LABEL`항목 텍스트의 경계 사각형을 반환합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제    
  
```cpp  
// OnClick is the handler for the NM_CLICK notification
void CListCtrlDlg::OnClick(NMHDR* pNMHDR, LRESULT* pResult)
{
    UNREFERENCED_PARAMETER(pResult);
LPNMITEMACTIVATE pia = (LPNMITEMACTIVATE)pNMHDR;

    // Get the current mouse location and convert it to client
    // coordinates.
    CPoint pos( ::GetMessagePos() ); 
    ScreenToClient(&pos);

    // Get indexes of the first and last visible items in 
    // the listview control.
    int index = m_myListCtrl.GetTopIndex();
    int last_visible_index = index + m_myListCtrl.GetCountPerPage();
    if (last_visible_index > m_myListCtrl.GetItemCount())
        last_visible_index = m_myListCtrl.GetItemCount();

    // Loop until number visible items has been reached.
    while (index <= last_visible_index)
    {
        // Get the bounding rectangle of an item. If the mouse
        // location is within the bounding rectangle of the item,
        // you know you have found the item that was being clicked.
        CRect r;
        m_myListCtrl.GetItemRect(index, &r, LVIR_BOUNDS);
        if (r.PtInRect(pia->ptAction))
        {
            UINT flag = LVIS_SELECTED | LVIS_FOCUSED;
            m_myListCtrl.SetItemState(index, flag, flag);
            break;
        }

        // Get the next item in listview control.
        index++;
    }
}
```

  
##  <a name="a-namegetitemspacinga--clistctrlgetitemspacing"></a><a name="getitemspacing"></a>CListCtrl::GetItemSpacing  
 현재 목록 뷰 컨트롤의 항목 사이의 간격을 계산합니다.  
  
```  
BOOL GetItemSpacing(
    BOOL fSmall,   
    int* pnHorzSpacing,   
    int* pnVertSpacing) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `fSmall`|검색할 항목 간격에 대 한 보기입니다. 지정 `true` 작은 아이콘 보기의 경우 또는 `false` 아이콘 보기에 대 한 합니다.|  
|[out] `pnHorzSpacing`|항목 간에 가로 간격을 포함합니다.|  
|[out] `pnVertSpacing`|항목 간 세로 간격을 포함합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_GETITEMSPACING](http://msdn.microsoft.com/library/windows/desktop/bb761051) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetitemstatea--clistctrlgetitemstate"></a><a name="getitemstate"></a>CListCtrl::GetItemState  
 목록 보기 항목의 상태를 검색합니다.  
  
```  
UINT GetItemState(
    int nItem,  
    UINT nMask) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 상태가 검색할 항목의 인덱스입니다.  
  
 `nMask`  
 항목의 상태를 반환 하는 플래그를 지정 하는 마스크입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 목록에 대 한 상태 플래그 항목 보기.  
  
### <a name="remarks"></a>주의  
 항목의 상태를 지정 하 여는 **상태** 의 멤버는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 구조체에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 지정 하거나 항목의 상태를 변경할 때의 **stateMask** 멤버 상태 비트를 변경 하려면 지정 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetTopIndex](#gettopindex)합니다.  
  
##  <a name="a-namegetitemtexta--clistctrlgetitemtext"></a><a name="getitemtext"></a>CListCtrl::GetItemText  
 목록 보기 항목 또는 하위 항목의 텍스트를 검색합니다.  
  
```  
int GetItemText(
    int nItem,  
    int nSubItem,  
    LPTSTR lpszText,  
    int nLen) const; 
 
CString GetItemText(
    int nItem,  
    int nSubItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 검색할 수 있는 텍스트는 항목의 인덱스입니다.  
  
 `nSubItem`  
 검색할 텍스트가 하위 항목을 지정 합니다.  
  
 `lpszText`  
 항목 텍스트를 수신 하는 문자열에 대 한 포인터입니다.  
  
 `nLen`  
 가 가리키는 버퍼의 길이 `lpszText`합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 되는 버전 `int` 검색 된 문자열의 길이 반환 합니다.  
  
 반환 되는 버전을 `CString` 항목 텍스트를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 경우 `nSubItem` 가&0; 인 경우이 함수에 항목 레이블; 검색 `nSubItem` 는&0;이 아닌 경우 텍스트를 검색 하위 항목의 합니다. 하위 항목 인수에 대 한 자세한 내용은 설명 부분을 참조 하십시오.는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 구조에서 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetnextitema--clistctrlgetnextitem"></a><a name="getnextitem"></a>CListCtrl::GetNextItem  
 목록에 대 한 검색 볼 항목 이동 하 고 지정 된 속성이 있는 특정된 항목에 지정된 된 관계를 갖습니다.  
  
```  
int GetNextItem(
    int nItem,  
    int nFlags) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 지정된 된 플래그와 일치 하는 첫 번째 항목을 찾습니다.-1, 검색을 시작할 항목의 인덱스입니다. 지정 된 항목 자체는 검색에서 제외 됩니다.  
  
 `nFlags`  
 요청된 된 항목의 상태와 지정된 된 항목을 요청한 항목의 기하학적 관계입니다. 기하학적 관계는 다음이 값 중 하나일 수 있습니다.  
  
- `LVNI_ABOVE`지정된 된 항목 위쪽에 있는 항목을 검색 합니다.  
  
- `LVNI_ALL`인덱스 (기본값) 별로 다음 항목을 검색 합니다.  
  
- `LVNI_BELOW`지정된 된 항목 아래에 있는 항목을 검색 합니다.  
  
- `LVNI_TOLEFT`지정된 된 항목의 왼쪽에 있는 항목을 검색 합니다.  
  
- `LVNI_TORIGHT`지정된 된 항목의 오른쪽에 있는 항목을 검색 합니다.  
  
 상태는&0; 일 수 또는 이러한 값 중 하나 이상을 사용할 수 있습니다.  
  
- `LVNI_DROPHILITED`항목에는 `LVIS_DROPHILITED` 플래그가 설정 된 상태입니다.  
  
- `LVNI_FOCUSED`항목에는 `LVIS_FOCUSED` 플래그가 설정 된 상태입니다.  
  
- `LVNI_SELECTED`항목에는 `LVIS_SELECTED` 플래그가 설정 된 상태입니다.  
  
 항목에 지정 된 상태 플래그 집합의 일부 없는 경우 다음 항목을 계속 검색 합니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면-1 성공 하는 경우 다음 항목의 인덱스입니다.  
  
##  <a name="a-namegetnextitemindexa--clistctrlgetnextitemindex"></a><a name="getnextitemindex"></a>CListCtrl::GetNextItemIndex  
 지정된 된 속성 집합이 있는 현재 목록 뷰 컨트롤에서 항목의 인덱스를 검색 합니다.  
  
```  
BOOL GetNextItemIndex(
    PLVITEMINDEX pItemIndex,   
    int nFlags) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in, out] `pItemIndex`|에 대 한 포인터는 [LVITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774762) 검색이 시작 되는 항목을 설명 하는 구조 또는-1은 첫 번째 일치 하는 항목에 플래그를 찾기는 `nFlags` 매개 변수입니다.<br /><br /> 이 메서드가 성공적으로 수행 되는 `LVITEMINDEX` 구조 검색 하 여 항목을 설명 합니다.|  
|[in] `nFlags`|검색을 수행 하는 방법을 지정 하는 플래그의 비트 조합 (OR)입니다.<br /><br /> 검색 인덱스, 상태 또는 대상 항목의 모양에 따라 달라질 수 또는으로 지정 된 항목을 기준으로 대상 항목의 실제 위치는 `pItemIndex` 매개 변수입니다. 자세한 내용은 참조는 `flags` 매개 변수는 [LVM_GETNEXTITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761059) 메시지입니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 호출자는 할당의 멤버를 설정 하는 `LVITEMINDEX` 가리키는 구조는 `pItemIndex` 매개 변수입니다.  
  
 이 메서드는 전송 된 [LVM_GETNEXTITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761059) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="a-namegetnextselecteditema--clistctrlgetnextselecteditem"></a><a name="getnextselecteditem"></a>CListCtrl::GetNextSelectedItem  
 식별 되는 목록 항목의 인덱스를 가져옵니다 `pos`를 설정 하는 다음 *pos* 에 **위치** 값입니다.  
  
```  
int GetNextSelectedItem(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pos`  
 에 대 한 참조는 **위치** 에 대 한 이전 호출에서 반환 된 값 `GetNextSelectedItem` 또는 `GetFirstSelectedItemPosition`합니다. 값은 다음 위치에이 호출으로 업데이트 됩니다.  
  
### <a name="return-value"></a>반환 값  
 식별 되는 목록 항목의 인덱스 `pos`합니다.  
  
### <a name="remarks"></a>주의  
 사용할 수 있습니다 `GetNextSelectedItem` 정방향 반복 루프를 호출 하 여 초기 위치를 설정 하는 경우에 `GetFirstSelectedItemPosition`합니다.  
  
 확인 해야 하면 **위치** 값이 유효 합니다. 올바르지 않을 경우 Microsoft Foundation 클래스 라이브러리의 디버그 버전 어설션 합니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는이 함수의 사용을 보여 줍니다.    
  
```cpp  
        POSITION pos = m_myListCtrl.GetFirstSelectedItemPosition();
        if (pos == NULL)
        {
            TRACE(_T("No items were selected!\n"));
        }
        else
        {
            while (pos)
            {
                int nItem = m_myListCtrl.GetNextSelectedItem(pos);
                TRACE(_T("Item %d was selected!\n"), nItem);
                // you could do your own processing on nItem here
            }
        }
```

  
##  <a name="a-namegetnumberofworkareasa--clistctrlgetnumberofworkareas"></a><a name="getnumberofworkareas"></a>CListCtrl::GetNumberOfWorkAreas  
 현재는 목록 뷰 컨트롤에 대 한 작업 영역 수를 검색합니다.  
  
```  
UINT GetNumberOfWorkAreas() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 이번에는 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetNumberOfWorkAreas](http://msdn.microsoft.com/library/windows/desktop/bb774988)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제    
  
```cpp  
        UINT i, uCount = m_myListCtrl.GetNumberOfWorkAreas();
        LPRECT lpRects = (LPRECT) malloc(uCount*sizeof(RECT));

        if (lpRects != NULL)
        {
            // Dump all of the work area dimensions.
            m_myListCtrl.GetWorkAreas(uCount, lpRects);

            for (i=0; i < uCount; i++)
            {
                TRACE(_T("Work area %d; left = %d, top = %d, right = %d, ")
                    _T("bottom = %d\r\n"),
                    i, lpRects[i].left, lpRects[i].top, lpRects[i].right, 
                    lpRects[i].bottom);
            }

            free(lpRects);
        }
        else
        {
            TRACE(_T("Couldn't allocate enough memory!"));   
        }

```

  
##  <a name="a-namegetoutlinecolora--clistctrlgetoutlinecolor"></a><a name="getoutlinecolor"></a>CListCtrl::GetOutlineColor  
 목록 뷰 컨트롤의 테두리 색을 검색 합니다.  
  
```  
COLORREF GetOutlineColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 된 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 윤곽선 색을 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETOUTLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761065) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetorigina--clistctrlgetorigin"></a><a name="getorigin"></a>CListCtrl::GetOrigin  
 목록 뷰 컨트롤에 대 한 현재 보기 원점을 검색합니다.  
  
```  
BOOL GetOrigin(LPPOINT lpPoint) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpPoint`  
 주소에 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 구조체 뷰 원점입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다. 그러나 컨트롤이 보고서 뷰에서 경우 반환 값은 항상&0;입니다.  
  
##  <a name="a-namegetselectedcolumna--clistctrlgetselectedcolumn"></a><a name="getselectedcolumn"></a>CListCtrl::GetSelectedColumn  
 목록 컨트롤에서 현재 선택 된 열의 인덱스를 검색합니다.  
  
```  
UINT GetSelectedColumn() const;  
```  
  
### <a name="return-value"></a>반환 값  
 선택한 열의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETSELECTEDCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb761067) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetselectedcounta--clistctrlgetselectedcount"></a><a name="getselectedcount"></a>CListCtrl::GetSelectedCount  
 List view 컨트롤에서 선택한 항목의 수를 가져옵니다.  
  
```  
UINT GetSelectedCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 List view 컨트롤에서 선택한 항목의 수입니다.  
  
### <a name="example"></a>예제    
  
```cpp  
        UINT i, uSelectedCount = m_myListCtrl.GetSelectedCount();
        int  nItem = -1;

        // Update all of the selected items.
        if (uSelectedCount > 0)
        {
            for (i=0; i < uSelectedCount; i++)
            {
                nItem = m_myListCtrl.GetNextItem(nItem, LVNI_SELECTED);
                ASSERT(nItem != -1);
                m_myListCtrl.Update(nItem); 
            }
        }
```

  
##  <a name="a-namegetselectionmarka--clistctrlgetselectionmark"></a><a name="getselectionmark"></a>CListCtrl::GetSelectionMark  
 목록 뷰 컨트롤의 선택 표시를 검색합니다.  
  
```  
int GetSelectionMark();
```  
  
### <a name="return-value"></a>반환 값  
 0부터 시작 선택 영역 표시 또는 선택 표시가 없는 경우-1입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetSelectionMark](http://msdn.microsoft.com/library/windows/desktop/bb774998)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

```cpp  
    // Set the selection mark to the first item only if no other item is 
    // selected.
    if (m_myListCtrl.GetSelectionMark() == -1)
        m_myListCtrl.SetSelectionMark(0);
```

  
##  <a name="a-namegetstringwidtha--clistctrlgetstringwidth"></a><a name="getstringwidth"></a>CListCtrl::GetStringWidth  
 지정된 된 문자열의 모든 표시 하는 데 필요한 최소 열 너비를 결정 합니다.  
  
```  
int GetStringWidth(LPCTSTR lpsz) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpsz`  
 해당 너비를 결정 해야 하는 null로 끝나는 문자열의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 너비를 가리키는 문자열의 크기를 픽셀 단위로 `lpsz`합니다.  
  
### <a name="remarks"></a>주의  
 반환 된 너비는 컨트롤의 현재 글꼴 및 열 여백 하지만 작은 아이콘의 너비가 아닌을 고려 합니다.  
  
### <a name="example"></a>예제  

```cpp  
        CString strColumn;
        int nWidth;

        // Insert six columns in the list view control. Make the width of
        // the column be the width of the column header plus 50%.
        for (int i = 0; i < 6; i++)
        {
            strColumn.Format(_T("column %d"), i);
            nWidth = 3*m_myListCtrl.GetStringWidth(strColumn)/2;
            m_myListCtrl.InsertColumn(i, strColumn, LVCFMT_LEFT, nWidth);
        }
```

  
##  <a name="a-namegetsubitemrecta--clistctrlgetsubitemrect"></a><a name="getsubitemrect"></a>CListCtrl::GetSubItemRect  
 목록 뷰 컨트롤에 있는 항목의 경계 사각형을 검색 합니다.  
  
```  
BOOL GetSubItemRect(
    int iItem,  
    int iSubItem,  
    int nArea,  
    CRect& ref);
```  
  
### <a name="parameters"></a>매개 변수  
 *iItem*  
 하위 항목의 부모 항목의 인덱스입니다.  
  
 *iSubItem*  
 하위 항목의&1;부터 시작 인덱스입니다.  
  
 *nArea*  
 검색할 (목록 보기의 하위 항목)의 경계 사각형의 부분을 결정 합니다. 경계 사각형의 부분 (아이콘, 레이블 또는 둘 다)은 다음 값 중 하나 이상의 비트 OR 연산자를 적용 하 여 지정 됩니다.  
  
- `LVIR_BOUNDS`아이콘 및 레이블을 포함 하 여 전체 항목의 경계 사각형을 반환 합니다.  
  
- `LVIR_ICON`아이콘 또는 작은 아이콘의 경계 사각형을 반환합니다.  
  
- `LVIR_LABEL`아이콘 및 레이블을 포함 하 여 전체 항목의 경계 사각형을 반환 합니다. 동일 `LVIR_BOUNDS`합니다.  
  
 `ref`  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 하위 항목의 좌표를 포함 하는 개체의 경계 사각형입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetSubItemRect](http://msdn.microsoft.com/library/windows/desktop/bb775004)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegettextbkcolora--clistctrlgettextbkcolor"></a><a name="gettextbkcolor"></a>CListCtrl::GetTextBkColor  
 목록 뷰 컨트롤의 텍스트 배경 색을 검색합니다.  
  
```  
COLORREF GetTextBkColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 색을 지정 하는 데 사용 되는 32 비트 값입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::SetTextBkColor](#settextbkcolor)합니다.  
  
##  <a name="a-namegettextcolora--clistctrlgettextcolor"></a><a name="gettextcolor"></a>CListCtrl::GetTextColor  
 목록 뷰 컨트롤의 텍스트 색을 검색합니다.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>반환 값  
 RGB 색을 지정 하는 데 사용 되는 32 비트 값입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::SetTextColor](#settextcolor)합니다.  
  
##  <a name="a-namegettileinfoa--clistctrlgettileinfo"></a><a name="gettileinfo"></a>CListCtrl::GetTileInfo  
 목록 뷰 컨트롤에서 타일에 대 한 정보를 검색합니다.  
  
```  
BOOL GetTileInfo(PLVTILEINFO pti) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pti*  
 에 대 한 포인터는 [LVTILEINFO](http://msdn.microsoft.com/library/windows/desktop/bb774766) 타일 정보를 수신 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETTILEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761081) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegettileviewinfoa--clistctrlgettileviewinfo"></a><a name="gettileviewinfo"></a>CListCtrl::GetTileViewInfo  
 Tile 보기에는 목록 뷰 컨트롤에 대 한 정보를 검색합니다.  
  
```  
BOOL GetTileViewInfo(PLVTILEVIEWINFO ptvi) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `ptvi`  
 에 대 한 포인터는 [LVTILEVIEWINFO](http://msdn.microsoft.com/library/windows/desktop/bb774768) 검색 된 정보를 수신 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETTILEVIEWINFO](http://msdn.microsoft.com/library/windows/desktop/bb761083) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegettooltipsa--clistctrlgettooltips"></a><a name="gettooltips"></a>CListCtrl::GetToolTips  
 목록 뷰 컨트롤에서 사용 하 여 도구 설명을 표시 하는 도구 설명 컨트롤을 검색 합니다.  
  
```  
CToolTipCtrl* GetToolTips() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CToolTipCtrl](ctooltipctrl-class.md) 목록 컨트롤에서 사용할 개체입니다. 경우는 [만들기](#create) 스타일을 사용 하는 멤버 함수 **LVS_NOTOOLTIPS**, 도구 설명 없음 사용 되 고 **NULL** 반환 됩니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [LVM_GETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb761085)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. MFC 구현 `GetToolTips` 반환는 `CToolTipCtrl` 도구 설명 컨트롤에 대 한 핸들 보다는 목록 컨트롤에서 사용 되는 개체입니다.  
  
### <a name="example"></a>예제  

```cpp  
        CToolTipCtrl* pTip = m_myListCtrl.GetToolTips();
        if (NULL != pTip)
        {
            pTip->UpdateTipText(_T("I'm a list view!"), &m_myListCtrl,
                IDD_MYLISTCTRL);
        }
```

  
##  <a name="a-namegettopindexa--clistctrlgettopindex"></a><a name="gettopindex"></a>CListCtrl::GetTopIndex  
 목록 보기 또는 보고서에서 표시 되는 맨 위에 있는 항목의 인덱스를 검색 합니다.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>반환 값  
 표시 되는 맨 위에 있는 항목의 인덱스입니다.  
  
### <a name="example"></a>예제  

 
```cpp  
        // Make sure the focus is set to the list view control.
        m_myListCtrl.SetFocus();

        // Select all of the items that are completely visible.
        int n = m_myListCtrl.GetTopIndex();
        int nLast = n + m_myListCtrl.GetCountPerPage();

        for (; n < nLast; n++)
        {
            m_myListCtrl.SetItemState(n, LVIS_SELECTED, LVIS_SELECTED);
            ASSERT(m_myListCtrl.GetItemState(n, LVIS_SELECTED) == LVIS_SELECTED); 
        }
```

  
##  <a name="a-namegetviewa--clistctrlgetview"></a><a name="getview"></a>CListCtrl::GetView  
 목록 뷰 컨트롤의 뷰를 가져옵니다.  
  
```  
DWORD GetView() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 뷰 컨트롤의 현재 보기입니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_GETVIEW](http://msdn.microsoft.com/library/windows/desktop/bb761091) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetviewrecta--clistctrlgetviewrect"></a><a name="getviewrect"></a>CListCtrl::GetViewRect  
 목록 뷰 컨트롤의 모든 항목의 경계 사각형을 검색합니다.  
  
```  
BOOL GetViewRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 주소에 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 목록 보기 보기 아이콘 또는 작은 아이콘 보기에 있어야 합니다.  
  
##  <a name="a-namegetworkareasa--clistctrlgetworkareas"></a><a name="getworkareas"></a>CListCtrl::GetWorkAreas  
 목록 뷰 컨트롤의 현재 작업 영역을 검색합니다.  
  
```  
void GetWorkAreas(
    int nWorkAreas,  
    LPRECT prc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nWorkAreas`  
 수가 `RECT` 에 포함 된 구조는 *중국* 배열입니다.  
  
 `prc`  
 배열에 대 한 포인터 `RECT` 구조 (또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체)의 목록 보기 컨트롤의 작업 영역을 수신 하 합니다. 이러한 구조체의 값은 클라이언트 좌표입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_GetWorkAreas](http://msdn.microsoft.com/library/windows/desktop/bb775024)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetNumberOfWorkAreas](#getnumberofworkareas)합니다.  
  
##  <a name="a-namehasgroupa--clistctrlhasgroup"></a><a name="hasgroup"></a>CListCtrl::HasGroup  
 목록 뷰 컨트롤에서 지정된 된 그룹에 있는지 확인 합니다.  
  
```  
BOOL HasGroup(int iGroupId) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `iGroupId`  
 요청 되는 그룹의 식별자입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_HASGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761097) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namehittesta--clistctrlhittest"></a><a name="hittest"></a>CListCtrl::HitTest  
 지정된 된 위치에 있는 경우 목록 보기 항목을 결정 합니다.  
  
```  
int HitTest(LVHITTESTINFO* pHitTestInfo) const;  
  
int HitTest(
    CPoint pt,  
    UINT* pFlags = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pHitTestInfo`  
 주소에 **LVHITTESTINFO** 적중된 테스트의 결과 대 한 정보를 수신 하는 적중 테스트에 위치를 포함 하는 구조입니다.  
  
 `pt`  
 테스트 지점입니다.  
  
 `pFlags`  
 테스트의 결과 대 한 정보를 수신 하는 정수에 대 한 포인터입니다. 설명을 참조 하십시오.는 **플래그** 의 멤버는 [LVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774754) 구조에서 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 에 지정 된 위치에 있는 항목의 인덱스 `pHitTestInfo`, 그렇지 않으면-1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 사용할 수는 `LVHT_ABOVE`, `LVHT_BELOW`, `LVHT_TOLEFT`, 및 `LVHT_TORIGHT` 는 구조체의 값 **플래그** 멤버는 목록 뷰 컨트롤의 콘텐츠 스크롤 여부를 결정 합니다. 이러한 플래그 중 두 가지 결합할 수 있습니다, 예를 들어 위와 클라이언트 영역의 왼쪽에 위치는 경우.  
  
 테스트할 수 있습니다는 **LVHT_ONITEM** 구조체의 값 **플래그** 멤버 목록 보기 항목을 통해 지정된 된 위치 인지 여부를 확인 합니다. 이 값은 비트 OR 작업에는 `LVHT_ONITEMICON`, `LVHT_ONITEMLABEL`, 및 `LVHT_ONITEMSTATEICON` 는 구조체의 값 **플래그** 멤버입니다.  
  
### <a name="example"></a>예제  

```cpp  
void CListCtrlDlg::OnRClick(NMHDR* pNMHDR, LRESULT* pResult)
{
    LPNMITEMACTIVATE pia = (LPNMITEMACTIVATE)pNMHDR;
    CPoint point(pia->ptAction);

    // Select the item the user clicked on.
    UINT uFlags;
    int nItem = m_myListCtrl.HitTest(point, &uFlags);

    if (uFlags & LVHT_ONITEMLABEL)
    {
        m_myListCtrl.SetItem(nItem, 0, LVIF_STATE, NULL, 0, LVIS_SELECTED, 
            LVIS_SELECTED, 0);
    }

    *pResult = 0;
}
```

  
##  <a name="a-nameinsertcolumna--clistctrlinsertcolumn"></a><a name="insertcolumn"></a>CListCtrl::InsertColumn  
 목록 뷰 컨트롤에 새 열을 삽입합니다.  
  
```  
int InsertColumn(
    int nCol,  
    const LVCOLUMN* pColumn);

 
int InsertColumn(
    int nCol,  
    LPCTSTR lpszColumnHeading,  
    int nFormat = LVCFMT_LEFT,  
    int nWidth = -1,  
    int nSubItem = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCol`  
 새 열의 인덱스입니다.  
  
 `pColumn`  
 주소에 **LVCOLUMN** 새 열의 특성을 포함 하는 구조입니다.  
  
 *lpszColumnHeading*  
 열 머리글을 포함 하는 문자열의 주소입니다.  
  
 `nFormat`  
 열의 맞춤을 지정 하는 정수입니다. 다음이 값 중 하나일 수 있습니다: **LVCFMT_LEFT**, **LVCFMT_RIGHT**, 또는 **LVCFMT_CENTER**합니다.  
  
 `nWidth`  
 픽셀 단위로 열 너비입니다. 이 매개 변수는-1, 열 너비 설정 되지 않았습니다.  
  
 `nSubItem`  
 열에 연결 된 하위 항목의 인덱스입니다. 이 매개 변수는-1을 하위 항목이 없는 열과 연결 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하는 경우 새 열 또는 그렇지 않으면-1의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 목록 뷰 컨트롤에서 가장 왼쪽 열에는 왼쪽 정렬 해야 합니다.  
  
 [LVCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) 구조 보고서 보기에 있는 열의 특성을 포함 합니다. 열에 대 한 정보를 받을 사용 됩니다. 이 구조에 설명 된 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameinsertgroupa--clistctrlinsertgroup"></a><a name="insertgroup"></a>CListCtrl::InsertGroup  
 그룹 목록 뷰 컨트롤에 삽입합니다.  
  
```  
LRESULT InsertGroup(
    int index,  
    PLVGROUP pgrp);
```  
  
### <a name="parameters"></a>매개 변수  
 *인덱스*  
 그룹을 삽입할 수 있는 항목의 인덱스입니다.  
  
 `pgrp`  
 에 대 한 포인터는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 추가할 그룹을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 작업에 실패 하면 그룹에 추가 된 항목의 인덱스를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_INSERTGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761103) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameinsertgroupsorteda--clistctrlinsertgroupsorted"></a><a name="insertgroupsorted"></a>CListCtrl::InsertGroupSorted  
 그룹의 정렬 된 목록에 지정된 된 그룹을 삽입합니다.  
  
```  
LRESULT InsertGroupSorted(PLVINSERTGROUPSORTED pStructInsert);
```  
  
### <a name="parameters"></a>매개 변수  
 *pStructInsert*  
 에 대 한 포인터는 [LVINSERTGROUPSORTED](http://msdn.microsoft.com/library/windows/desktop/bb774756) 삽입 하는 그룹을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_INSERTGROUPSORTED](http://msdn.microsoft.com/library/windows/desktop/bb761105) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameinsertitema--clistctrlinsertitem"></a><a name="insertitem"></a>CListCtrl::InsertItem  
 목록 뷰 컨트롤에 항목을 삽입합니다.  
  
```  
int InsertItem(const LVITEM* pItem);

 
int InsertItem(
    int nItem,  
    LPCTSTR lpszItem);

 
int InsertItem(
    int nItem,  
    LPCTSTR lpszItem,  
    int nImage);

 
int InsertItem(
    UINT nMask,  
    int nItem,  
    LPCTSTR lpszItem,  
    UINT nState,  
    UINT nStateMask,  
    int nImage,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 에 대 한 포인터는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 에 설명 된 대로 항목의 특성을 지정 하는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 `nItem`  
 삽입할 항목의 인덱스입니다.  
  
 `lpszItem`  
 항목의 레이블을 포함 하는 문자열의 주소 또는 `LPSTR_TEXTCALLBACK` 경우 콜백 항목입니다. 콜백 항목에 대 한 자세한 내용은 참조 [CListCtrl::GetCallbackMask](#getcallbackmask)합니다.  
  
 `nImage`  
 항목의 이미지의 인덱스 또는 `I_IMAGECALLBACK` 경우 콜백 항목입니다. 콜백 항목에 대 한 자세한 내용은 참조 [CListCtrl::GetCallbackMask](#getcallbackmask)합니다.  
  
 `nMask`  
 `nMask` 어떤 항목을 지정 하는 매개 변수 매개 변수로 전달 된 특성은 유효 합니다. 에 설명 된 마스크 값 또는 하나 수 [LVITEM 구조](http://msdn.microsoft.com/library/windows/desktop/bb774760) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 비트 OR 연산자와 함께 사용할 수 있는 값을 결합할 수 있습니다.  
  
 `nState`  
 항목의 상태, 상태 이미지 및 오버레이 이미지를 나타냅니다. 참조는 [!INCLUDE[winSDK](./includes/winsdk_md.md)] 항목 [LVITEM 구조](http://msdn.microsoft.com/library/windows/desktop/bb774760) 에 대 한 자세한 내용은 및 [목록 뷰 항목 상태](http://msdn.microsoft.com/library/windows/desktop/bb774733) 유효한 플래그 목록은 합니다.  
  
 `nStateMask`  
 상태 멤버의 비트를 검색 하거나 수정할 수를 나타냅니다. 참조 [LVITEM 구조](http://msdn.microsoft.com/library/windows/desktop/bb774760) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
 `lParam`  
 항목에 연결 된 32 비트 응용 프로그램 관련 값입니다. 설정 해야이 매개 변수를 지정 하는 경우는 `nMask` 특성 `LVIF_PARAM`합니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면-1 또는 성공 하는 경우 새 항목의 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 발생할 수 있습니다이 메서드는 호출은 **LVM_INSERTITEM** 메시지를 컨트롤 창으로 보냅니다. 컨트롤에 대 한 연결 된 메시지 처리기를 특정 조건에서 해당 항목의 텍스트를 설정 하지 못할 수 있습니다 (예: 창 스타일을 사용 하는 등 **LVS_OWNERDRAW**). 이러한 조건에 대 한 자세한 내용은 참조 [LVM_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb761107) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

```cpp  
        CString strText;
        int nColumnCount = m_myListCtrl.GetHeaderCtrl()->GetItemCount();

        // Insert 10 items in the list view control.
        for (int i = 0; i < 10; i++)
        {
            strText.Format(TEXT("item %d"), i);

            // Insert the item, select every other item.
            m_myListCtrl.InsertItem(LVIF_TEXT | LVIF_STATE, i, strText, 
                (i % 2) == 0 ? LVIS_SELECTED : 0, LVIS_SELECTED, 0, 0);

            // Initialize the text of the subitems.
            for (int j = 1; j < nColumnCount; j++)
            {
                strText.Format(TEXT("sub-item %d %d"), i, j);
                m_myListCtrl.SetItemText(i, j, strText);
            }
        }
```

  
##  <a name="a-nameinsertmarkhittesta--clistctrlinsertmarkhittest"></a><a name="insertmarkhittest"></a>CListCtrl::InsertMarkHitTest  
 지정된 된 지점에 가장 가까운 삽입 포인터를 검색합니다.  
  
```  
int InsertMarkHitTest(
    LPPOINT pPoint,  
    LPLVINSERTMARK lvim) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pPoint`  
 에 대 한 포인터는 [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 목록 컨트롤의 클라이언트 영역을 기준으로 적중된 테스트를 포함 하는 구조를 조정 합니다.  
  
 `lvim`  
 에 대 한 포인터는 [LVINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774758) 지점 매개 변수에 의해 정의 된 좌표에 가장 가까운 삽입 지점을 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 가장 가까이 삽입 포인터를 지정 된 지점.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_INSERTMARKHITTEST](http://msdn.microsoft.com/library/windows/desktop/bb761131) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameisgroupviewenableda--clistctrlisgroupviewenabled"></a><a name="isgroupviewenabled"></a>CListCtrl::IsGroupViewEnabled  
 그룹 보기는 목록 뷰 컨트롤에 대 한 사용 되는지 여부를 결정 합니다.  
  
```  
BOOL IsGroupViewEnabled() const;  
```  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 그룹 보기를 사용 하는 경우 또는 **FALSE** 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_ISGROUPVIEWENABLED](http://msdn.microsoft.com/library/windows/desktop/bb761133) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameisitemvisiblea--clistctrlisitemvisible"></a><a name="isitemvisible"></a>CListCtrl::IsItemVisible  
 현재 목록 뷰 컨트롤에서 지정된 된 항목 표시 여부를 나타냅니다.  
  
```  
BOOL IsItemVisible(int index) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `index`|현재 목록 뷰 컨트롤에 있는 항목의&0;부터 시작 인덱스입니다.|  
  
### <a name="return-value"></a>반환 값  
 `true`지정 된 항목이 표시 되 고, 그렇지 않으면 경우 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_ISITEMVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb761135) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namemapidtoindexa--clistctrlmapidtoindex"></a><a name="mapidtoindex"></a>CListCtrl::MapIDToIndex  
 인덱스를 현재 목록 뷰 컨트롤에 있는 항목의 고유 ID를 매핑합니다.  
  
```  
UINT MapIDToIndex(UINT id) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `id`|항목의 고유 ID입니다.|  
  
### <a name="return-value"></a>반환 값  
 지정 된 ID에 대 한 현재 인덱스  
  
### <a name="remarks"></a>주의  
 내부적으로 목록 뷰 컨트롤 인덱스 별로 항목을 추적합니다. 인덱스는 컨트롤의 수명 동안 변경 될 수 있으므로 문제가 발생할 수 있습니다. 항목이 만들어질 때이 ID를 사용 하 여 목록 뷰 컨트롤의 수명 동안 고유성을 보장 하기 위해 목록 뷰 컨트롤에 id가 항목을 태그 수 있습니다.  
  
 Note 다중 스레드 환경에서 배경 스레드에서 하지 목록 뷰 컨트롤을 호스트 하는 스레드에서 인덱스 보장 됩니다.  
  
 이 메서드는 전송 된 [LVM_MAPIDTOINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761137) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namemapindextoida--clistctrlmapindextoid"></a><a name="mapindextoid"></a>CListCtrl::MapIndexToID  
 고유 ID를 현재 목록 뷰 컨트롤에 있는 항목의 인덱스를 매핑합니다.  
  
```  
UINT MapIndexToID(UINT index) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `index`|항목의&0;부터 시작 하는 인덱스입니다.|  
  
### <a name="return-value"></a>반환 값  
 지정된 된 항목에 대 한 고유 ID입니다.  
  
### <a name="remarks"></a>주의  
 내부적으로 목록 뷰 컨트롤 인덱스 별로 항목을 추적합니다. 인덱스는 컨트롤의 수명 동안 변경 될 수 있으므로 문제가 발생할 수 있습니다. 항목을 만들 때 목록 뷰 컨트롤에 id가 항목을 태그 수 있습니다. 목록 뷰 컨트롤의 수명에 대 한 특정 항목에 액세스 하려면이 ID를 사용할 수 있습니다.  
  
 Note 다중 스레드 환경에서 배경 스레드에서 하지 목록 뷰 컨트롤을 호스트 하는 스레드에서 인덱스 보장 됩니다.  
  
 이 메서드는 전송 된 [LVM_MAPINDEXTOID](http://msdn.microsoft.com/library/windows/desktop/bb761139) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_listCtrl`, 즉 현재 목록 뷰 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.    
  
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>예제  
 다음 코드 예제는 `MapIndexToID` 메서드. 이 코드 예제에서는 이전 단원에서 "ClientID" 및 "등급"이 보고서 뷰에서 라는 두 개의 열을 표시 하는 목록 뷰 컨트롤을 만들었습니다. 다음 예제에서는 각 목록 보기 항목의 인덱스 id 번호에 매핑하고 각 id에 대 한 인덱스를 검색 합니다. 마지막으로,이 예제에서는 원래 인덱스 검색 된 있는지 여부를 보고 합니다.    
  
```cpp  
    // MapIndexToID
    int iCount = m_listCtrl.GetItemCount();
    UINT nId = 0;
    UINT nIndex = 0;
    for (int iIndexOriginal = 0; iIndexOriginal < iCount; iIndexOriginal++)
    {
        // Map index to ID.
        nId = m_listCtrl.MapIndexToID((UINT)iIndexOriginal);

        // Map ID to index.
        nIndex = m_listCtrl.MapIDToIndex(nId);

        if (nIndex != (UINT)(iIndexOriginal))
        {
            CString str;
            str.Format(_T("Mapped index (%d) is not equal to original index (%d)"),
                nIndex, (UINT)(iIndexOriginal));
            AfxMessageBox(str);
            return;
        }
    }
    AfxMessageBox(_T("The mapped indexes and original indexes are equal."), 
        MB_ICONINFORMATION);
```

  
##  <a name="a-namemovegroupa--clistctrlmovegroup"></a><a name="movegroup"></a>CListCtrl::MoveGroup  
 지정 된 그룹에 지정 된 목록 뷰 컨트롤의&0; 기반된 인덱스를 이동 합니다.  
  
```  
LRESULT MoveGroup(
    int iGroupId,  
    int toIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `iGroupId`  
 이동 해야 하는 그룹의 식별자입니다.  
  
 `toIndex`  
 여기서 그룹을 이동 해야 하는&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_MOVEGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761141) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namemoveitemtogroupa--clistctrlmoveitemtogroup"></a><a name="moveitemtogroup"></a>CListCtrl::MoveItemToGroup  
 지정된 된 그룹에 지정된 된 항목을 이동합니다.  
  
```  
void MoveItemToGroup(
    int idItemFrom,  
    int idGroupTo);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `idItemFrom`  
 이동할 항목의 인덱스입니다.  
  
 [in] `idGroupTo`  
 그룹의 식별자는 항목으로 이동 됩니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  이 메서드가 현재 구현 되지 않았습니다.  
  
 기능을 에뮬레이션 하는이 메서드는 [LVM_MOVEITEMTOGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761143) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameredrawitemsa--clistctrlredrawitems"></a><a name="redrawitems"></a>CListCtrl::RedrawItems  
 항목의 범위를 다시 그려야 하는 목록 뷰 컨트롤을 강제로 수행 합니다.  
  
```  
BOOL RedrawItems(
    int nFirst,  
    int nLast);
```  
  
### <a name="parameters"></a>매개 변수  
 `nFirst`  
 그려야 하는 첫 번째 항목의 인덱스입니다.  
  
 `nLast`  
 그려야 하는 마지막 항목의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 지정된 된 항목 목록 보기 창에는 수신 될 때까지 실제로 다시 하지는 `WM_PAINT` 메시지입니다. 즉시 다시 그리게 하는 Windows 호출 [UpdateWindow](http://msdn.microsoft.com/library/windows/desktop/dd145167) 후이 함수를 사용 하는 함수입니다.  
  
##  <a name="a-nameremoveallgroupsa--clistctrlremoveallgroups"></a><a name="removeallgroups"></a>CListCtrl::RemoveAllGroups  
 목록 뷰 컨트롤에서 모든 그룹을 제거합니다.  
  
```  
void RemoveAllGroups();
```  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_REMOVEALLGROUPS](http://msdn.microsoft.com/library/windows/desktop/bb761147) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameremovegroupa--clistctrlremovegroup"></a><a name="removegroup"></a>CListCtrl::RemoveGroup  
 List view 컨트롤에서 지정된 된 그룹을 제거합니다.  
  
```  
LRESULT RemoveGroup(int iGroupId);
```  
  
### <a name="parameters"></a>매개 변수  
 `iGroupId`  
 제거할 그룹의 식별자입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면 성공 하는 경우 그룹의 인덱스를 반환 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_REMOVEGROUP](http://msdn.microsoft.com/library/windows/desktop/bb761149) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namescrolla--clistctrlscroll"></a><a name="scroll"></a>CListCtrl::Scroll  
 목록 뷰 컨트롤의 내용을 스크롤합니다.  
  
```  
BOOL Scroll(CSize size);
```  
  
### <a name="parameters"></a>매개 변수  
 `size`  
 A `CSize` 가로 및 세로 스크롤, 픽셀에서의 크기를 지정 하는 개체입니다. **y** 소속 `size` (픽셀) 목록 뷰 컨트롤의 각 줄의 높이 나눈 결과 수가 줄에서 컨트롤은 스크롤.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
##  <a name="a-namesetbkcolora--clistctrlsetbkcolor"></a><a name="setbkcolor"></a>CListCtrl::SetBkColor  
 목록 뷰 컨트롤의 배경색을 설정합니다.  
  
```  
BOOL SetBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>매개 변수  
 `cr`  
 배경색을 설정 하려면 또는 `CLR_NONE` 없는 배경색에 대 한 값입니다. 배경색을 사용 하 여 목록 뷰 컨트롤 스스로 다시 그릴 크게 배경색 없이 보다 더 빨리 합니다. 내용은 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  

 
```cpp  
        // Use the 3D button face color for the background.
        COLORREF crBkColor = ::GetSysColor(COLOR_3DFACE);
        m_myListCtrl.SetBkColor(crBkColor);
        ASSERT(m_myListCtrl.GetBkColor() == crBkColor);
```

  
##  <a name="a-namesetbkimagea--clistctrlsetbkimage"></a><a name="setbkimage"></a>CListCtrl::SetBkImage  
 목록 뷰 컨트롤의 배경 이미지를 설정합니다.  
  
```  
BOOL SetBkImage(LVBKIMAGE* plvbkImage);
 
BOOL SetBkImage(
    HBITMAP hbm,  
    BOOL fTile = TRUE,  
    int xOffsetPercent = 0,  
    int yOffsetPercent = 0);
 
BOOL SetBkImage(
    LPTSTR pszUrl,  
    BOOL fTile = TRUE,  
    int xOffsetPercent = 0,  
    int yOffsetPercent = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `plvbkImage`  
 주소에 **LVBKIMAGE** 새 배경 이미지 정보가 포함 된 구조입니다.  
  
 `hbm`  
 비트맵에 대 한 핸들입니다.  
  
 `pszUrl`  
 A **NULL**-배경 이미지의 URL이 포함 된 문자열을 종료 합니다.  
  
 *fTile*  
 이미지는 목록 뷰 컨트롤의 배경에 바둑판식으로 배열 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
 *xOffsetPercent*  
 목록 뷰 컨트롤의 원점에서 이미지의 왼쪽된 가장자리를 픽셀 단위로 오프셋입니다.  
  
 *yOffsetPercent*  
 목록 뷰 컨트롤의 원점에서 이미지의 위쪽 가장자리를 픽셀 단위로 오프셋입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면&0; 또는 성공 하면&0;이 아닌 반환 합니다.  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  때문에 `CListCtrl::SetBkImage` OLE COM 기능 활용, OLE 라이브러리를 사용 하기 전에 초기화 해야 `SetBkImage`합니다. 응용 프로그램이 초기화 될 때 COM 라이브러리를 초기화 하 고 응용 프로그램이 종료 될 때 라이브러리의 초기화를 취소 하는 것이 좋습니다. 이 작업은 자동으로 수행 하는 응용 프로그램 mfc에서 ActiveX 기술, OLE 자동화, OLE 링크/포함, 또는 ODBC/DAO 작업의 사용 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetBkImage](#getbkimage)합니다.  
  
##  <a name="a-namesetcallbackmaska--clistctrlsetcallbackmask"></a><a name="setcallbackmask"></a>CListCtrl::SetCallbackMask  
 목록 뷰 컨트롤에 대 한 콜백 마스크를 설정합니다.  
  
```  
BOOL SetCallbackMask(UINT nMask);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMask`  
 콜백 마스크의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  

 
```cpp  
    // Set the callback mask so that only the selected and focused states
    // are stored for each item.
    m_myListCtrl.SetCallbackMask(LVIS_SELECTED|LVIS_FOCUSED);
    ASSERT(m_myListCtrl.GetCallbackMask() == 
        (LVIS_SELECTED|LVIS_FOCUSED));
```


##  <a name="a-namesetchecka--clistctrlsetcheck"></a><a name="setcheck"></a>CListCtrl::SetCheck  
 목록 컨트롤 항목의 상태 이미지가 표시 되는지를 결정 합니다.  
  
```  
BOOL SetCheck(
    int nItem,  
    BOOL fCheck = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 목록 컨트롤 항목의&0;부터 시작 하는 인덱스입니다.  
  
 `fCheck`  
 항목의 상태 이미지 표시할지 여부를 지정 합니다. 기본적으로 *fCheck* 는 **TRUE** 상태 이미지 표시 됩니다. 경우 `fCheck` 는 **FALSE**, 표시 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 항목을 선택한 경우에 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예제  

 
```cpp  
        int nCount = m_myListCtrl.GetItemCount();
        BOOL fCheck = FALSE;

        // Set the check state of every other item to TRUE and 
        // all others to FALSE.
        for (int i = 0; i < nCount; i++)
        {
            m_myListCtrl.SetCheck(i, fCheck);
            ASSERT((m_myListCtrl.GetCheck(i) && fCheck) || 
                (!m_myListCtrl.GetCheck(i) && !fCheck));
            fCheck = !fCheck;
        }
```

  
##  <a name="a-namesetcolumna--clistctrlsetcolumn"></a><a name="setcolumn"></a>CListCtrl::SetColumn  
 목록 뷰 열 특성을 설정합니다.  
  
```  
BOOL SetColumn(
    int nCol,  
    const LVCOLUMN* pColumn);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCol`  
 설정 된 특성을 가진 열의 인덱스입니다.  
  
 `pColumn`  
 주소에 [LVCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743) 에 설명 된 대로 새 열이 포함 된 구조 특성은 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 구조체의 **마스크** 멤버는 열을 설정 하려면 특성을 지정 합니다. 하는 경우는 **마스크** 멤버 지정는 `LVCF_TEXT` 값 구조체의 **pszText** 멤버는 null로 끝나는 문자열 및 구조체의 주소 **cchTextMax** 멤버가 무시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetColumn](#getcolumn)합니다.  
  
##  <a name="a-namesetcolumnorderarraya--clistctrlsetcolumnorderarray"></a><a name="setcolumnorderarray"></a>CListCtrl::SetColumnOrderArray  
 목록 뷰 컨트롤의 열 순서 (왼쪽에서 오른쪽)를 설정 합니다.  
  
```  
BOOL SetColumnOrderArray(
    int iCount,  
    LPINT piArray);
```  
  
### <a name="parameters"></a>매개 변수  
 `piArray`  
 목록 뷰 컨트롤 (왼쪽에서 오른쪽)에 있는 열의 인덱스 값을 포함 하는 버퍼에 대 한 포인터입니다. 버퍼는 목록 뷰 컨트롤에서 열의 총 수를 포함할 수 있는 크기 여야 합니다.  
  
 `iCount`  
 목록 뷰 컨트롤에서 열 수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetColumnOrderArray](http://msdn.microsoft.com/library/windows/desktop/bb775072)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetColumnOrderArray](#getcolumnorderarray)합니다.  
  
##  <a name="a-namesetcolumnwidtha--clistctrlsetcolumnwidth"></a><a name="setcolumnwidth"></a>CListCtrl::SetColumnWidth  
 보고서 보기 또는 목록 보기에서 열 너비를 변경합니다.  
  
```  
BOOL SetColumnWidth(
    int nCol,  
    int cx);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCol`  
 너비 설정 하는 열의 인덱스입니다. 목록 보기에서이 매개 변수는 0 이어야 합니다.  
  
 `cx`  
 열의 새 너비입니다. 일 수 있습니다 **LVSCW_AUTOSIZE** 또는 **LVSCW_AUTOSIZE_USEHEADER**에 설명 된 대로 [LVM_SETCOLUMNWIDTH](http://msdn.microsoft.com/library/windows/desktop/bb761163) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
##  <a name="a-namesetextendedstylea--clistctrlsetextendedstyle"></a><a name="setextendedstyle"></a>CListCtrl::SetExtendedStyle  
 목록 뷰 컨트롤의 현재 확장된 스타일을 설정합니다.  
  
```  
DWORD SetExtendedStyle(DWORD dwNewStyle);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwNewStyle`  
 List view 컨트롤에서 사용할 확장된 스타일의 조합입니다. 이러한 스타일의 설명이 포함 된 목록에 대 한 참조는 [확장 목록 뷰 스타일](http://msdn.microsoft.com/library/windows/desktop/bb774732) 항목에는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 List view 컨트롤에서 사용 하는 이전 확장된 스타일의 조합입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetExtendedListViewStyle](http://msdn.microsoft.com/library/windows/desktop/bb775076)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

 
```cpp  
    // Allow the header controls item to be movable by the user.
    m_myListCtrl.SetExtendedStyle
        (m_myListCtrl.GetExtendedStyle()|LVS_EX_HEADERDRAGDROP);
```

  
##  <a name="a-namesetgroupinfoa--clistctrlsetgroupinfo"></a><a name="setgroupinfo"></a>CListCtrl::SetGroupInfo  
 현재 목록 뷰 컨트롤의 지정된 된 그룹을 설명 하는 정보를 설정 합니다.  
  
```  
int SetGroupInfo(
    int iGroupId,  
    PLVGROUP pgrp);
```  
  
### <a name="parameters"></a>매개 변수  
 `iGroupId`  
 해당 정보가 설정 되어 그룹의 식별자입니다.  
  
 `pgrp`  
 에 대 한 포인터는 [LVGROUP](http://msdn.microsoft.com/library/windows/desktop/bb774769) 설정 하는 정보를 포함 하는 구조입니다. 호출자는이 구조를 할당 하 고 해당 멤버를 설정 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 메서드가 성공 하면 그룹의 ID 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 전송 된 [LVM_SETGROUPINFO](http://msdn.microsoft.com/library/windows/desktop/bb761167) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetgroupmetricsa--clistctrlsetgroupmetrics"></a><a name="setgroupmetrics"></a>CListCtrl::SetGroupMetrics  
 목록 뷰 컨트롤의 그룹 메트릭을 설정합니다.  
  
```  
void SetGroupMetrics(PLVGROUPMETRICS pGroupMetrics);
```  
  
### <a name="parameters"></a>매개 변수  
 `pGroupMetrics`  
 에 대 한 포인터는 [LVGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb774752) 설정할 그룹 메트릭 정보를 포함 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETGROUPMETRICS](http://msdn.microsoft.com/library/windows/desktop/bb761168) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesethotcursora--clistctrlsethotcursor"></a><a name="sethotcursor"></a>CListCtrl::SetHotCursor  
 목록 뷰 컨트롤에 대해 핫 트래킹을 때 사용 되는 커서를 설정 합니다.  
  
```  
HCURSOR SetHotCursor(HCURSOR hc);
```  
  
### <a name="parameters"></a>매개 변수  
 *hc가*  
 핫 커서를 나타내는 데 사용 하 여 커서 리소스에 대 한 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 List view 컨트롤에서 사용 하 고 이전 핫 커서 리소스에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetHotCursor](http://msdn.microsoft.com/library/windows/desktop/bb775082)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 핫 커서 호버 선택을 사용 하는 경우에 표시 되는 모든 목록 보기 항목 위로 커서를 움직이면 나타납니다. 설정 하 여 호버 선택을 사용 하는지는 **LVS_EX_TRACKSELECT** 확장 스타일입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetHotCursor](#gethotcursor)합니다.  
  
##  <a name="a-namesethotitema--clistctrlsethotitem"></a><a name="sethotitem"></a>CListCtrl::SetHotItem  
 목록 뷰 컨트롤의 현재 활성 항목을 설정합니다.  
  
```  
int SetHotItem(int iIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `iIndex`  
 활성 항목으로 설정할 항목의&0;부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 핫 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetHotItem](http://msdn.microsoft.com/library/windows/desktop/bb775083)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetHotItem](#gethotitem)합니다.  
  
##  <a name="a-namesethovertimea--clistctrlsethovertime"></a><a name="sethovertime"></a>CListCtrl::SetHoverTime  
 목록 뷰 컨트롤의 현재 호버 시간을 설정합니다.  
  
```  
DWORD SetHoverTime(DWORD dwHoverTime = (DWORD)-1);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwHoverTime*  
 이 선택 되기 전에 마우스 커서를 항목 위로 해야 밀리초 새 지연입니다. 기본 값이 전달 되 면 시간 기본 호버 시간으로 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 이전 호버 시간 (밀리초)입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetHoverTime](http://msdn.microsoft.com/library/windows/desktop/bb775084)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetHoverTime](#gethovertime)합니다.  
  
##  <a name="a-nameseticonspacinga--clistctrlseticonspacing"></a><a name="seticonspacing"></a>CListCtrl::SetIconSpacing  
 목록 뷰 컨트롤의 아이콘 사이의 간격을 설정 합니다.  
  
```  
CSize SetIconSpacing(
    int cx,  
    int cy);  
  
CSize SetIconSpacing(CSize size);
```  
  
### <a name="parameters"></a>매개 변수  
 `cx`  
 거리 (픽셀 단위)는 x 축에 아이콘 사이입니다.  
  
 `cy`  
 거리 (픽셀 단위) y 축에 아이콘 사이입니다.  
  
 `size`  
 A `CSize` 아이콘에 x 축과 y 사이의 거리 (픽셀 단위)를 지정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) 아이콘 간격에 대 한 이전 값을 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetIconSpacing](http://msdn.microsoft.com/library/windows/desktop/bb775085)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

 
```cpp  
    // Leave lots of space between icons.
    m_myListCtrl.SetIconSpacing(CSize(100, 100));
```

  
##  <a name="a-namesetimagelista--clistctrlsetimagelist"></a><a name="setimagelist"></a>CListCtrl::SetImageList  
 이미지 목록을 목록 뷰 컨트롤에 할당합니다.  
  
```  
CImageList* SetImageList(
    CImageList* pImageList,  
    int nImageListType);
```  
  
### <a name="parameters"></a>매개 변수  
 `pImageList`  
 할당할 이미지 목록에 대 한 포인터입니다.  
  
 `nImageListType`  
 이미지 목록의 형식입니다. 다음이 값 중 하나일 수 있습니다.  
  
- `LVSIL_NORMAL`큰 아이콘으로 이미지 목록입니다.  
  
- `LVSIL_SMALL`작은 아이콘에 있는 이미지 목록입니다.  
  
- `LVSIL_STATE`상태 이미지와 이미지 목록입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 이미지 목록에 대 한 포인터입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetImageList](#getimagelist)합니다.  
  
##  <a name="a-namesetinfotipa--clistctrlsetinfotip"></a><a name="setinfotip"></a>CListCtrl::SetInfoTip  
 도구 설명 텍스트를 설정합니다.  
  
```  
BOOL SetInfoTip(PLVSETINFOTIP plvInfoTip);
```  
  
### <a name="parameters"></a>매개 변수  
 *plvInfoTip*  
 에 대 한 포인터는 [LVFSETINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb774764) 설정할 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETINFOTIP](http://msdn.microsoft.com/library/windows/desktop/bb761180) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetinsertmarka--clistctrlsetinsertmark"></a><a name="setinsertmark"></a>CListCtrl::SetInsertMark  
 정의 된 위치에 삽입 포인터를 설정합니다.  
  
```  
BOOL SetInsertMark(LPLVINSERTMARK lvim);
```  
  
### <a name="parameters"></a>매개 변수  
 `lvim`  
 에 대 한 포인터는 [LVINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb774758) 삽입 포인터를 설정 하는 위치를 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 하는 경우 또는 **FALSE** 그렇지 않은 경우. **FALSE** 경우 반환 됩니다의 크기는 `cbSize` 의 멤버는 **LVINSERTMARK** 구조는 구조와의 실제 크기와 일치 하지 않음을 또는 삽입점 때 현재 뷰에 적용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETINSERTMARK](http://msdn.microsoft.com/library/windows/desktop/bb761182) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetinsertmarkcolora--clistctrlsetinsertmarkcolor"></a><a name="setinsertmarkcolor"></a>CListCtrl::SetInsertMarkColor  
 삽입 포인터의 색을 설정 합니다.  
  
```  
COLORREF SetInsertMarkColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 A [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 삽입 포인터를 설정 하는 색을 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 **COLORREF** 이전 색이 포함 된 구조입니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETINSERTMARKCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761184) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetitema--clistctrlsetitem"></a><a name="setitem"></a>CListCtrl::SetItem  
 일부 또는 전체 목록 보기 항목의 특성을 설정합니다.  
  
```  
BOOL SetItem(const LVITEM* pItem);

 
BOOL SetItem(
    int nItem,  
    int nSubItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam);

 
BOOL SetItem(
    int nItem,  
    int nSubItem,  
    UINT nMask,  
    LPCTSTR lpszItem,  
    int nImage,  
    UINT nState,  
    UINT nStateMask,  
    LPARAM lParam,  
    int nIndent);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 주소에 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 에 설명 된 대로 새 항목을 포함 하는 구조 특성은 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 구조체의 **iItem** 및 **iSubItem** 항목 또는 하위 항목이 고 구조체의 멤버를 식별 **마스크** 멤버 특성 집합을 지정 합니다. 대 한 자세한 내용은 **마스크** 멤버 참조는 **주의**합니다.  
  
 `nItem`  
 설정 된 특성을 가진 항목의 인덱스입니다.  
  
 `nSubItem`  
 설정 된 특성을 가진 하위 항목의 인덱스입니다.  
  
 `nMask`  
 (주의 참조)을 설정할 수 있는 특성을 지정 합니다.  
  
 `lpszItem`  
 항목의 레이블을 지정 하는 null로 끝나는 문자열의 주소입니다.  
  
 `nImage`  
 이미지 목록 내에서 항목의 이미지의 인덱스입니다.  
  
 `nState`  
 변경할 (설명 부분 참조) 상태에 대 한 값을 지정 합니다.  
  
 `nStateMask`  
 (주의 참조)을 변경할 수 있는 상태 지정 합니다.  
  
 `lParam`  
 항목에 연결할 수는 32 비트 응용 프로그램 관련 값입니다.  
  
 `nIndent`  
 들여쓰기를 픽셀 단위로 너비입니다. 경우 `nIndent` 작으면 시스템에 정의 된 최소 너비 보다으로 새 너비는 시스템에 정의 된 최소로 설정 되어  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 **iItem** 및 **iSubItem** 의 멤버는 **LVITEM** 구조 및 `nItem` 및 `nSubItem` 항목과 하위 항목이 설정 된 특성을 가진 매개 변수를 식별 합니다.  
  
 **마스크** 의 멤버는 **LVITEM** 구조 및 `nMask` 어떤 항목을 지정 하는 매개 변수를 설정할 특성은:  
  
- `LVIF_TEXT`**pszText** 멤버 또는 `lpszItem` 매개 변수는 null로 끝나는 문자열의 주소 이며, **cchTextMax** 멤버가 무시 됩니다.  
  
- `LVIF_STATE`**stateMask** 멤버 또는 `nStateMask` 매개 변수를 변경 하는 항목 상태 지정 및 **상태** 멤버 또는 `nState` 매개 변수는 해당 상태에 대 한 값을 포함 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::HitTest](#hittest)합니다.  
  
##  <a name="a-namesetitemcounta--clistctrlsetitemcount"></a><a name="setitemcount"></a>CListCtrl::SetItemCount  
 많은 수의 항목을 추가 하는 데는 목록 뷰 컨트롤을 준비 합니다.  
  
```  
void SetItemCount(int nItems);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItems`  
 컨트롤은 궁극적으로 포함 하는 항목 수입니다.  
  
### <a name="remarks"></a>주의  
 가상 목록 뷰 컨트롤에 대 한 항목 수를 설정 하려면 참조 [CListCtrl::SetItemCountEx](#setitemcountex)합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetItemCount](http://msdn.microsoft.com/library/windows/desktop/bb775093)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

 
```cpp  
        CString str;

        // Add 1024 items to the list view control.
        m_myListCtrl.SetItemCount(1024);

        for (int i = 0; i < 1024; i++)
        {
            str.Format(TEXT("item %d"), i);
            m_myListCtrl.InsertItem(i, str);
        }
```

  
##  <a name="a-namesetitemcountexa--clistctrlsetitemcountex"></a><a name="setitemcountex"></a>CListCtrl::SetItemCountEx  
 가상 목록 뷰 컨트롤에 대 한 항목 수를 설정합니다.  
  
```  
BOOL SetItemCountEx(
    int iCount,  
    DWORD dwFlags = LVSICF_NOINVALIDATEALL);
```  
  
### <a name="parameters"></a>매개 변수  
 `iCount`  
 컨트롤은 궁극적으로 포함 하는 항목 수입니다.  
  
 `dwFlags`  
 항목 수를 재설정 한 후 목록 뷰 컨트롤의 동작을 지정 합니다. 이 값은 다음의 조합 수 있습니다.  
  
- **LVSICF_NOINVALIDATEALL** 영향을 받는 항목 보기의 현재 없으면 목록 뷰 컨트롤에서이 그려집니다. 기본값입니다.  
  
- **LVSICF_NOSCROLL** 목록 뷰 컨트롤의 항목 수 변경 하는 경우 스크롤 위치를 변경 되지 것입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetItemCountEx](http://msdn.microsoft.com/library/windows/desktop/bb775095)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]가상 목록 보기에만 호출 해야 합니다.  
  
### <a name="example"></a>예제  

 
```cpp  
        CString str;

        // Add 1024 items to the list view control.

        // Force my virtual list view control to allocate 
        // enough memory for my 1024 items.
        m_myVirtualListCtrl.SetItemCountEx(1024, LVSICF_NOSCROLL|
            LVSICF_NOINVALIDATEALL);

        for (int i = 0; i < 1024; i++)
        {
            str.Format(TEXT("item %d"), i);
            m_myVirtualListCtrl.InsertItem(i, str);
        }
```

  
##  <a name="a-namesetitemdataa--clistctrlsetitemdata"></a><a name="setitemdata"></a>CListCtrl::SetItemData  
 지정 된 항목과 연결 된 32 비트 응용 프로그램 관련 값을 설정 `nItem`합니다.  
  
```  
BOOL SetItemData(int nItem, DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 해당 데이터를 설정할 목록 항목의 인덱스입니다.  
  
 `dwData`  
 항목에 연결할 수는 32 비트 값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 값은는 **lParam** 의 멤버는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 구조체에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

 
```cpp  
    // Set the data of each item to be equal to its index.
    for (int i = 0; i < m_myListCtrl.GetItemCount(); i++)
    {
        m_myListCtrl.SetItemData(i, i);
    }
```

  
##  <a name="a-namesetitemindexstatea--clistctrlsetitemindexstate"></a><a name="setitemindexstate"></a>CListCtrl::SetItemIndexState  
 현재 목록 뷰 컨트롤에서 항목의 상태를 설정합니다.  
  
```  
BOOL SetItemIndexState(
    PLVITEMINDEX pItemIndex,   
    DWORD dwState,   
    DWORD dwMask) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pItemIndex`|에 대 한 포인터는 [LVITEMINDEX](http://msdn.microsoft.com/library/windows/desktop/bb774762) 는 항목을 설명 하는 구조입니다. 호출자는이 구조를 할당 하 고 해당 멤버를 설정 해야 합니다.|  
|[in] `dwState`|해당 항목을 설정 하려면 상태의 비트 조합입니다 [보기 항목 상태 목록](http://msdn.microsoft.com/library/windows/desktop/bb774733)합니다. 재설정 하는&0; 또는 상태를 설정 하려면 하나를 지정 합니다.|  
|[in] `dwMask`|지정 된 상태로의 유효한 비트 마스크는 `dwState` 매개 변수입니다. 비트 조합 (OR)을 지정 [보기 항목 상태 목록](http://msdn.microsoft.com/library/windows/desktop/bb774733)합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 자세한 내용은 `dwState` 매개 변수를 참조 하십시오 [목록 보기 항목 상태](http://msdn.microsoft.com/library/windows/desktop/bb774733)합니다.  
  
 에 대 한 자세한 내용은 `dwMask` 매개 변수 참조는 `stateMask` 의 멤버는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 구조입니다.  
  
 이 메서드는 전송 된 [LVM_SETITEMINDEXSTATE](http://msdn.microsoft.com/library/windows/desktop/bb761190) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetitempositiona--clistctrlsetitemposition"></a><a name="setitemposition"></a>CListCtrl::SetItemPosition  
 목록 뷰 컨트롤의 지정된 된 위치에 항목을 이동합니다.  
  
```  
BOOL SetItemPosition(
    int nItem,  
    POINT pt);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 해당 위치를 설정할 항목의 인덱스입니다.  
  
 `pt`  
 A [지점](http://msdn.microsoft.com/library/windows/desktop/dd162805) 항목의 왼쪽 위 모퉁이의 보기에서 새 위치를 지정 하는 구조를 조정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤은 아이콘 또는 작은 아이콘 보기에 있어야 합니다.  
  
 목록 뷰 컨트롤에는 `LVS_AUTOARRANGE` 스타일 목록 보기 항목의 위치를 설정한 후에 정렬 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetItemPosition](#getitemposition)합니다.  
  
##  <a name="a-namesetitemstatea--clistctrlsetitemstate"></a><a name="setitemstate"></a>CListCtrl::SetItemState  
 목록 뷰 컨트롤에 있는 항목의 상태를 변경합니다.  
  
```  
BOOL SetItemState(
    int nItem,  
    LVITEM* pItem);

 
BOOL SetItemState(
    int nItem,  
    UINT nState,  
    UINT nMask);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 상태가 설정할 항목의 인덱스입니다.  
  
 `pItem`  
 주소에 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 구조체에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다. 구조체의 **stateMask** 멤버는 상태 변경 및 구조체의 비트 지정 **상태** 멤버 이러한 비트에 대 한 새 값을 포함 합니다. 다른 멤버는 무시 됩니다.  
  
 `nState`  
 상태 비트에 대 한 새 값입니다. 가능한 값 목록은 참조 하십시오. [CListCtrl::GetNextItem](#getnextitem) 및 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 상태 멤버입니다.  
  
 `nMask`  
 상태를 변경 하려면 비트를 지정 하는 마스크입니다. 이 값의 stateMask 멤버에 해당 하는 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 항목의 "상태"에 항목의 가용성을 지정 하 고, 사용자 작업을 나타내는 또는 그렇지 않으면 항목의 상태를 반영 하는 값입니다. 목록 뷰 컨트롤 사용자가 항목을 선택 하는 경우와 같은 일부 상태 비트를 변경 합니다. 응용 프로그램을 비활성화 하거나 해당 항목을 숨길 하거나 오버레이 이미지 또는 상태 이미지를 지정 하려면 다른 상태 비트를 변경할 수 있습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetTopIndex](#gettopindex)합니다.  
  
##  <a name="a-namesetitemtexta--clistctrlsetitemtext"></a><a name="setitemtext"></a>CListCtrl::SetItemText  
 목록 보기 항목 또는 하위 항목의 텍스트를 변경합니다.  
  
```  
BOOL SetItemText(
    int nItem,  
    int nSubItem,  
    LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 설정 되어야 하는 텍스트가 포함 된 항목의 인덱스입니다.  
  
 `nSubItem`  
 항목 레이블을 설정 하는 하위 항목이 또는&0;의 인덱스입니다.  
  
 `lpszText`  
 새 항목의 텍스트를 포함 하는 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 아니며 LVS_OWNERDATA 창 스타일을 포함 하는 컨트롤과 (사실,이 인해 어설션에서의 디버그 빌드). 이 목록 컨트롤 스타일에 대 한 자세한 내용은 참조 [목록 뷰 컨트롤 개요](http://msdn.microsoft.com/library/windows/desktop/bb774735)합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::InsertItem](#insertitem)합니다.  
  
##  <a name="a-namesetoutlinecolora--clistctrlsetoutlinecolor"></a><a name="setoutlinecolor"></a>CListCtrl::SetOutlineColor  
 목록 뷰 컨트롤의 테두리의 색을 설정 하는 경우는 [LVS_EX_BORDERSELECT](http://msdn.microsoft.com/library/windows/desktop/bb774739) 확장된 창 스타일을 설정 합니다.  
  
```  
COLORREF SetOutlineColor(COLORREF color);
```  
  
### <a name="parameters"></a>매개 변수  
 `color`  
 새 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 윤곽선 색을 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 **COLORREF** 윤곽선 색을 포함 하는 구조  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETOUTLINECOLOR](http://msdn.microsoft.com/library/windows/desktop/bb761200) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetselectedcolumna--clistctrlsetselectedcolumn"></a><a name="setselectedcolumn"></a>CListCtrl::SetSelectedColumn  
 목록 뷰 컨트롤의 선택된 된 열을 설정합니다.  
  
```  
LRESULT SetSelectedColumn(int iCol);
```  
  
### <a name="parameters"></a>매개 변수  
 *iCol*  
 인덱스 열을 선택할 수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETSELECTEDCOLUMN](http://msdn.microsoft.com/library/windows/desktop/bb761202) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetselectionmarka--clistctrlsetselectionmark"></a><a name="setselectionmark"></a>CListCtrl::SetSelectionMark  
 목록 뷰 컨트롤의 선택 표시를 설정합니다.  
  
```  
int SetSelectionMark(int iIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `iIndex`  
 여러 선택의 첫 번째 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 선택 영역 표시 또는 선택 표시가 없으면 되었으면-1입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetSelectionMark](http://msdn.microsoft.com/library/windows/desktop/bb775112)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetSelectionMark](#getselectionmark)합니다.  
  
##  <a name="a-namesettextbkcolora--clistctrlsettextbkcolor"></a><a name="settextbkcolor"></a>CListCtrl::SetTextBkColor  
 목록 뷰 컨트롤에서 텍스트의 배경색을 설정합니다.  
  
```  
BOOL SetTextBkColor(COLORREF cr);
```  
  
### <a name="parameters"></a>매개 변수  
 `cr`  
 A **COLORREF** 새 텍스트 배경색을 지정 합니다. 내용은 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  

 
```cpp  
        // Use the 3D button face color for the background.
        COLORREF crBkColor = ::GetSysColor(COLOR_3DFACE);
        m_myListCtrl.SetTextBkColor(crBkColor);
        ASSERT(m_myListCtrl.GetTextBkColor() == crBkColor);
```

  
##  <a name="a-namesettextcolora--clistctrlsettextcolor"></a><a name="settextcolor"></a>CListCtrl::SetTextColor  
 목록 뷰 컨트롤의 텍스트 색을 설정합니다.  
  
```  
BOOL SetTextColor(COLORREF cr);
```  
  
### <a name="parameters"></a>매개 변수  
 `cr`  
 A **COLORREF** 새 텍스트 색을 지정 합니다. 내용은 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 에 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="example"></a>예제  

 
```cpp  
    // Use the window text color for
    // the item text of the list view control.
    COLORREF crTextColor = ::GetSysColor(COLOR_WINDOWTEXT);
    m_myListCtrl.SetTextColor(crTextColor);
    ASSERT(m_myListCtrl.GetTextColor() == crTextColor);
```

  
##  <a name="a-namesettileinfoa--clistctrlsettileinfo"></a><a name="settileinfo"></a>CListCtrl::SetTileInfo  
 목록 뷰 컨트롤의 타일에 대 한 정보를 설정합니다.  
  
```  
BOOL SetTileInfo(PLVTILEINFO pti);
```  
  
### <a name="parameters"></a>매개 변수  
 *pti*  
 에 대 한 포인터는 [LVTILEINFO](http://msdn.microsoft.com/library/windows/desktop/bb774766) 설정할 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETTILEINFO](http://msdn.microsoft.com/library/windows/desktop/bb761210) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesettileviewinfoa--clistctrlsettileviewinfo"></a><a name="settileviewinfo"></a>CListCtrl::SetTileViewInfo  
 Tile 보기에는 목록 뷰 컨트롤을 사용 하는 정보를 설정 합니다.  
  
```  
BOOL SetTileViewInfo(PLVTILEVIEWINFO ptvi);
```  
  
### <a name="parameters"></a>매개 변수  
 `ptvi`  
 에 대 한 포인터는 [LVTILEVIEWINFO](http://msdn.microsoft.com/library/windows/desktop/bb774768) 설정 하는 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETTILEVIEWINFO](http://msdn.microsoft.com/library/windows/desktop/bb761212) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesettooltipsa--clistctrlsettooltips"></a><a name="settooltips"></a>CListCtrl::SetToolTips  
 List view 컨트롤에서 도구 설명을 표시 하려면 사용할 도구 설명 컨트롤을 설정 합니다.  
  
```  
CToolTipCtrl* SetToolTips(CToolTipCtrl* pWndTip);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWndTip`  
 에 대 한 포인터는 `CToolTipCtrl` 목록 컨트롤에서 사용할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CToolTipCtrl](ctooltipctrl-class.md) 컨트롤에 의해 이전에 사용 되는 도구 설명이 포함 된 개체 또는 `NULL` 도구 설명 없음 이전에 사용 되는 경우.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [LVM_SETTOOLTIPS](http://msdn.microsoft.com/library/windows/desktop/bb761216)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
 도구 설명을 사용 하지 않도록를 나타내는 `LVS_NOTOOLTIPS` 스타일을 만들 때의 `CListCtrl` 개체입니다.  
  
##  <a name="a-namesetviewa--clistctrlsetview"></a><a name="setview"></a>CListCtrl::SetView  
 목록 뷰 컨트롤의 뷰를 설정합니다.  
  
```  
DWORD SetView(int iView);
```  
  
### <a name="parameters"></a>매개 변수  
 *iView*  
 선택할 수는 보기입니다.  
  
### <a name="return-value"></a>반환 값  
 그렇지 않으면-1 또는 1이 성공적으로 반환 합니다. 예를 들어 보기 올바르지 않으면-1이 반환 됩니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SETVIEW](http://msdn.microsoft.com/library/windows/desktop/bb761220) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetworkareasa--clistctrlsetworkareas"></a><a name="setworkareas"></a>CListCtrl::SetWorkAreas  
 목록 뷰 컨트롤의 아이콘 표시 될 수 있는 영역을 설정 합니다.  
  
```  
void SetWorkAreas(
    int nWorkAreas,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `nWorkAreas`  
 수가 `RECT` 구조 (또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체)로 가리키는 배열에 `lpRect`합니다.  
  
 `lpRect`  
 배열의 주소 `RECT` 구조 (또는 `CRect` 개체)의 목록 보기 컨트롤의 새 작업 영역을 지정 하는 합니다. 클라이언트 좌표에서 이러한 영역을 지정 해야 합니다. 이 매개 변수가 **NULL**, 작업 영역에서 컨트롤의 클라이언트 영역으로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SetWorkAreas](http://msdn.microsoft.com/library/windows/desktop/bb775128)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

 
```cpp  
    // Remove all working areas.
    m_myListCtrl.SetWorkAreas(0, NULL);
```

  
##  <a name="a-namesortgroupsa--clistctrlsortgroups"></a><a name="sortgroups"></a>CListCtrl::SortGroups  
 List view 컨트롤 내의 ID로 그룹을 정렬 하는 응용 프로그램 정의 된 비교 함수를 사용 합니다.  
  
```  
BOOL SortGroups(
    PFNLVGROUPCOMPARE _pfnGroupCompare,  
    LPVOID _plv);
```  
  
### <a name="parameters"></a>매개 변수  
 `_pfnGroupCompare`  
 그룹 비교 함수에 대 한 포인터입니다.  
  
 `_plv`  
 Void 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 `true`를 반환하고 실패하면 `false`를 반환합니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [LVM_SORTGROUPS](http://msdn.microsoft.com/library/windows/desktop/bb761225) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesortitemsa--clistctrlsortitems"></a><a name="sortitems"></a>CListCtrl::SortItems  
 응용 프로그램 정의 된 비교 함수를 사용 하 여 목록 보기 항목을 정렬 합니다.  
  
```  
BOOL SortItems(
    PFNLVCOMPARE pfnCompare,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `pfnCompare`  
 응용 프로그램 정의 비교 함수의 주소입니다.  
  
 정렬 작업을 두 개의 목록 항목의 상대 순서를 지정 해야 할 때마다 비교 함수를 호출 합니다. 비교 함수는 클래스의 정적 멤버 이거나 모든 클래스의 멤버가 되지 않는 독립 실행형 함수 여야 합니다.  
  
 [in] `dwData`  
 비교 함수에 전달 되는 응용 프로그램 정의 값입니다.  
  
### <a name="return-value"></a>반환 값  
 `true`경우 성공 메서드 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 새 값으로 각 항목의 인덱스를 변경 합니다.  
  
 비교 함수 `pfnCompare`, 형식은 다음과 같습니다.  
  
```  
int CALLBACK CompareFunc(LPARAM lParam1,
    LPARAM lParam2,
    LPARAM lParamSort);
```  
비교 함수는 첫 번째 항목 두 번째 앞에 야 하는 경우 음수 값을 반환 해야, 경우에는&0; 또는 두 번째, 첫 번째 항목을 따르면 양수 값을 두 항목이 같으면 있습니다.  
  
 `lParam1` 매개 변수는 32 비트 값을 비교 하는 첫 번째 항목에 연결 된 고 `lParam2` 매개 변수는 두 번째 항목에 연결 된 값입니다. 에 지정 된 값은는 `lParam` 항목의 소속 [LVITEM](http://msdn.microsoft.com/library/windows/desktop/bb774760) 목록에 삽입 한 구조입니다. `lParamSort` 매개 변수는 동일는 `dwData` 값입니다.  
  
 이 메서드는 전송 된 [LVM_SORTITEMS](http://msdn.microsoft.com/library/windows/desktop/bb761227) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 다음은 항목이로 정렬 하는 간단한 비교 함수는 `lParam` 값입니다.  
  
```cpp  
// Sort items by associated lParam
int CALLBACK CListCtrlDlg::MyCompareProc(LPARAM lParam1, LPARAM lParam2, 
    LPARAM lParamSort)
{
    UNREFERENCED_PARAMETER(lParamSort);
return (int)(lParam1 - lParam2);
}
```
  
```cpp  
// Sort the items by passing in the comparison function.
void CListCtrlDlg::Sort()
{
    m_myListCtrl.SortItems(&CListCtrlDlg::MyCompareProc, 0);
}
```
  
##  <a name="a-namesortitemsexa--clistctrlsortitemsex"></a><a name="sortitemsex"></a>CListCtrl::SortItemsEx  
 응용 프로그램 정의 된 비교 함수를 사용 하 여 현재 목록 뷰 컨트롤의 항목을 정렬 합니다.  
  
```  
BOOL SortItemsEx(
    PFNLVCOMPARE pfnCompare,   
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `pfnCompare`|응용 프로그램 정의 비교 함수의 주소입니다.<br /><br /> 정렬 작업을 두 개의 목록 항목의 상대 순서를 지정 해야 할 때마다 비교 함수를 호출 합니다. 비교 함수는 클래스의 정적 멤버 이거나 모든 클래스의 멤버가 되지 않는 독립 실행형 함수 여야 합니다.|  
|[in] `dwData`|응용 프로그램 정의 값 비교 함수에 전달 합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 새 값으로 각 항목의 인덱스를 변경 합니다.  
  
 비교 함수 `pfnCompare`, 형식은 다음과 같습니다.  
  
```  
int CALLBACK CompareFunc(LPARAM lParam1,
    LPARAM lParam2,
    LPARAM lParamSort);
```  
이 메시지는 같은 [LVM_SORTITEMS](http://msdn.microsoft.com/library/windows/desktop/bb761227), 비교 함수에 전달 된 정보 유형을 제외 하 고 있습니다. [LVM_SORTITEMS](http://msdn.microsoft.com/library/windows/desktop/bb761227), `lParam1` 및 `lParam2` 비교할 항목의 값입니다. [LVM_SORTITEMSEX](http://msdn.microsoft.com/library/windows/desktop/bb761228), `lParam1` 비교할 첫 번째 항목의 현재 인덱스 및 `lParam2` 는 두 번째 항목의 현재 인덱스입니다. 보낼 수는 [LVM_GETITEMTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761055) 메시지 항목에 대 한 자세한 정보를 검색 합니다.  
  
 비교 함수는 첫 번째 항목 두 번째 앞에 야 하는 경우 음수 값을 반환 해야, 경우에는&0; 또는 두 번째, 첫 번째 항목을 따르면 양수 값을 두 항목이 같으면 있습니다.  
  
> [!NOTE]
>  정렬 과정에서 목록 뷰 내용이 안정화 되지 않습니다. 콜백 함수 목록 뷰 컨트롤에 이외의 다른 모든 메시지를 보내는 경우 [LVM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb774953), 결과 예측할 수 없습니다.  
  
 이 메서드는 전송 된 [LVM_SORTITEMSEX](http://msdn.microsoft.com/library/windows/desktop/bb761228) 에 설명 된 메시지는 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 변수를 정의 하는 다음 코드 예제에서는 `m_listCtrl`, 즉 현재 목록 뷰 컨트롤에 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
```cpp  
public:
    // Variable used to access the list control.
    CListCtrl m_listCtrl; 
```

  
### <a name="example"></a>예제  
 다음 코드 예제는 `SortItemEx` 메서드. 이 코드 예제에서는 이전 단원에서 "ClientID" 및 "등급"이 보고서 뷰에서 라는 두 개의 열을 표시 하는 목록 뷰 컨트롤을 만들었습니다. 다음 코드 예제에서는 "등급"이 열에 값을 사용 하 여 테이블을 정렬 합니다.  
  

```cpp  
// The ListCompareFunc() method is a global function used by SortItemEx().
int CALLBACK ListCompareFunc(
                             LPARAM lParam1, 
                             LPARAM lParam2, 
                             LPARAM lParamSort)
{
    CListCtrl* pListCtrl = (CListCtrl*) lParamSort;
    CString    strItem1 = pListCtrl->GetItemText(static_cast<int>(lParam1), 1);
    CString    strItem2 = pListCtrl->GetItemText(static_cast<int>(lParam2), 1)
    int x1 = _tstoi(strItem1.GetBuffer());
    int x2 = _tstoi(strItem2.GetBuffer());
    int result = 0;
    if ((x1 - x2) < 0)
        result = -1;
    else if ((x1 - x2) == 0)
        result = 0;
    else
        result = 1;

    return result;
}

void CCListCtrl_s2Dlg::OnBnClickedButton1()
{
    // SortItemsEx
    m_listCtrl.SortItemsEx( ListCompareFunc, (LPARAM)&m_listCtrl );
}
```

  
##  <a name="a-namesubitemhittesta--clistctrlsubitemhittest"></a><a name="subitemhittest"></a>CListCtrl::SubItemHitTest  
 지정된 된 위치에 있는 경우 목록 보기 항목을 결정 합니다.  
  
```  
int SubItemHitTest(LPLVHITTESTINFO pInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `pInfo`  
 에 대 한 포인터는 [LVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb774754) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 항목 또는 하위 항목, 테스트할 (있는 경우), 그렇지 않으면-1의&1;부터 시작 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 매크로의 동작을 구현 [ListView_SubItemHitTest](http://msdn.microsoft.com/library/windows/desktop/bb775135)에 설명 된 대로 [!INCLUDE[winSDK](./includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  

```cpp  
void CListCtrlDlg::OnDblClk(NMHDR* pNMHDR, LRESULT* pResult)
{
    UNREFERENCED_PARAMETER(pResult);
LPNMITEMACTIVATE pia = (LPNMITEMACTIVATE)pNMHDR;
    LVHITTESTINFO lvhti;

    // Clear the subitem text the user clicked on.
    lvhti.pt = pia->ptAction;
    m_myListCtrl.SubItemHitTest(&lvhti);

    if (lvhti.flags & LVHT_ONITEMLABEL)
    {
        m_myListCtrl.SetItemText(lvhti.iItem, lvhti.iSubItem, NULL);
    }
}
```

  
##  <a name="a-nameupdatea--clistctrlupdate"></a><a name="update"></a>CListCtrl::Update  
 목록 뷰 컨트롤에 지정 된 항목 자동으로 그려지도록 강제 `nItem`합니다.  
  
```  
BOOL Update(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 업데이트할 항목의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우&0;이 아니고, 그렇지 않으면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 또한 목록 뷰 컨트롤을 정렬 올바르게 구성 되었으면는 `LVS_AUTOARRANGE` 스타일입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CListCtrl::GetSelectedCount](#getselectedcount)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 ROWLIST](../../visual-cpp-samples.md)   
 [CWnd 클래스](cwnd-class.md)   
 [계층 구조 차트](../hierarchy-chart.md)   
 [CImageList 클래스](cimagelist-class.md)


