---
title: "CListCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl 클래스"
  - "list view controls"
  - "list view controls, CListCtrl 클래스"
  - "LVS_ICON"
  - "LVS_LIST"
  - "LVS_REPORT"
  - "LVS_SMALLICON"
  - "Windows common controls [C++], CListCtrl"
ms.assetid: fe08a1ca-4b05-4ff7-a12a-ee4c765a2197
caps.latest.revision: 23
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"표시는 컬렉션의 각 레이블 및 아이콘 \(이미지 목록\)에서 구성 항목을 목록 뷰 컨트롤에"의 기능을 캡슐화 합니다.  
  
## 구문  
  
```  
class CListCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CListCtrl::CListCtrl](../Topic/CListCtrl::CListCtrl.md)|`CListCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CListCtrl::ApproximateViewRect](../Topic/CListCtrl::ApproximateViewRect.md)|너비 및 높이 목록 뷰 컨트롤의 항목을 표시 하는 데 필요한 결정 합니다.|  
|[CListCtrl::Arrange](../Topic/CListCtrl::Arrange.md)|항목 눈금에 맞춥니다.|  
|[CListCtrl::CancelEditLabel](../Topic/CListCtrl::CancelEditLabel.md)|항목 텍스트 편집 작업을 취소 합니다.|  
|[CListCtrl::Create](../Topic/CListCtrl::Create.md)|목록 컨트롤을 만들고이에 연결 된 `CListCtrl` 개체입니다.|  
|[CListCtrl::CreateDragImage](../Topic/CListCtrl::CreateDragImage.md)|지정 된 항목에 대 한 끌기 이미지 목록을 만듭니다.|  
|[CListCtrl::CreateEx](../Topic/CListCtrl::CreateEx.md)|지정 된 Windows 확장된 스타일 목록 컨트롤을 만들고 연결 하는 `CListCtrl` 개체입니다.|  
|[CListCtrl::DeleteAllItems](../Topic/CListCtrl::DeleteAllItems.md)|컨트롤에서 모든 항목을 삭제합니다.|  
|[CListCtrl::DeleteColumn](../Topic/CListCtrl::DeleteColumn.md)|List view 컨트롤에서 열을 삭제합니다.|  
|[CListCtrl::DeleteItem](../Topic/CListCtrl::DeleteItem.md)|컨트롤에서 항목을 삭제합니다.|  
|[CListCtrl::DrawItem](../Topic/CListCtrl::DrawItem.md)|시각적 측면이 있는 소유자 그리기 컨트롤 변경 되 면 호출 됩니다.|  
|[CListCtrl::EditLabel](../Topic/CListCtrl::EditLabel.md)|항목의 텍스트를 현재 위치에서 편집을 시작 합니다.|  
|[CListCtrl::EnableGroupView](../Topic/CListCtrl::EnableGroupView.md)|사용 하거나 항목을 목록 뷰 컨트롤을 그룹으로 표시 여부를 지정 합니다.|  
|[CListCtrl::EnsureVisible](../Topic/CListCtrl::EnsureVisible.md)|항목이 표시 됩니다.|  
|[CListCtrl::FindItem](../Topic/CListCtrl::FindItem.md)|지정 된 특징을 가진 목록 보기 항목을 검색 합니다.|  
|[CListCtrl::GetBkColor](../Topic/CListCtrl::GetBkColor.md)|목록 뷰 컨트롤의 배경 색을 검색합니다.|  
|[CListCtrl::GetBkImage](../Topic/CListCtrl::GetBkImage.md)|목록 뷰 컨트롤의 현재 배경 이미지를 검색합니다.|  
|[CListCtrl::GetCallbackMask](../Topic/CListCtrl::GetCallbackMask.md)|목록 뷰 컨트롤에 대 한 콜백 마스크를 검색합니다.|  
|[CListCtrl::GetCheck](../Topic/CListCtrl::GetCheck.md)|항목에 연결 되는 상태 이미지의 현재 표시 상태를 검색 합니다.|  
|[CListCtrl::GetColumn](../Topic/CListCtrl::GetColumn.md)|컨트롤의 열 특성을 검색합니다.|  
|[CListCtrl::GetColumnOrderArray](../Topic/CListCtrl::GetColumnOrderArray.md)|목록 뷰 컨트롤의 열 순서 \(왼쪽에서 오른쪽\)를 검색 합니다.|  
|[CListCtrl::GetColumnWidth](../Topic/CListCtrl::GetColumnWidth.md)|목록 보기 또는 보고서 보기에서 열의 너비를 검색합니다.|  
|[CListCtrl::GetCountPerPage](../Topic/CListCtrl::GetCountPerPage.md)|목록 뷰 컨트롤에 세로 방향으로 맞출 수 있는 항목 수를 계산 합니다.|  
|[CListCtrl::GetEditControl](../Topic/CListCtrl::GetEditControl.md)|항목의 텍스트를 편집 하는 데 사용 하는 편집 컨트롤의 핸들을 검색 합니다.|  
|[CListCtrl::GetEmptyText](../Topic/CListCtrl::GetEmptyText.md)|현재 목록 뷰 컨트롤이 비어 있는 경우 표시 되는 문자열을 검색 합니다.|  
|[CListCtrl::GetExtendedStyle](../Topic/CListCtrl::GetExtendedStyle.md)|현재 확장된 목록 뷰 컨트롤의 스타일을 검색합니다.|  
|[CListCtrl::GetFirstSelectedItemPosition](../Topic/CListCtrl::GetFirstSelectedItemPosition.md)|목록 뷰 컨트롤의 첫 번째 선택된 목록 보기 항목의 위치를 검색합니다.|  
|[CListCtrl::GetFocusedGroup](../Topic/CListCtrl::GetFocusedGroup.md)|현재 목록 뷰 컨트롤에 키보드 포커스가 있는 그룹을 검색 합니다.|  
|[CListCtrl::GetGroupCount](../Topic/CListCtrl::GetGroupCount.md)|현재 목록 보기 컨트롤에서 그룹을 검색합니다.|  
|[CListCtrl::GetGroupInfo](../Topic/CListCtrl::GetGroupInfo.md)|목록 뷰 컨트롤의 지정 된 그룹에 대 한 정보를 가져옵니다.|  
|[CListCtrl::GetGroupInfoByIndex](../Topic/CListCtrl::GetGroupInfoByIndex.md)|현재 목록 뷰 컨트롤에 지정 된 그룹에 대 한 정보를 검색합니다.|  
|[CListCtrl::GetGroupMetrics](../Topic/CListCtrl::GetGroupMetrics.md)|메트릭 그룹을 검색합니다.|  
|[CListCtrl::GetGroupRect](../Topic/CListCtrl::GetGroupRect.md)|현재 목록 뷰 컨트롤에 지정 된 그룹에 대 한 경계 사각형을 검색합니다.|  
|[CListCtrl::GetGroupState](../Topic/CListCtrl::GetGroupState.md)|현재 목록 뷰 컨트롤에 지정 된 그룹의 상태를 검색합니다.|  
|[CListCtrl::GetHeaderCtrl](../Topic/CListCtrl::GetHeaderCtrl.md)|목록 뷰 컨트롤의 머리글 컨트롤을 검색합니다.|  
|[CListCtrl::GetHotCursor](../Topic/CListCtrl::GetHotCursor.md)|목록 뷰 컨트롤에 대해 핫 트래킹을 사용 하는 경우 사용 되는 커서를 검색 합니다.|  
|[CListCtrl::GetHotItem](../Topic/CListCtrl::GetHotItem.md)|커서에서 현재 목록 보기 항목을 검색합니다.|  
|[CListCtrl::GetHoverTime](../Topic/CListCtrl::GetHoverTime.md)|현재 호버 시간 목록 뷰 컨트롤을 검색합니다.|  
|[CListCtrl::GetImageList](../Topic/CListCtrl::GetImageList.md)|드로잉 목록 보기 항목에 사용 되는 이미지 목록에 대 한 핸들을 검색 합니다.|  
|[CListCtrl::GetInsertMark](../Topic/CListCtrl::GetInsertMark.md)|삽입 표시의 현재 위치를 검색합니다.|  
|[CListCtrl::GetInsertMarkColor](../Topic/CListCtrl::GetInsertMarkColor.md)|삽입 표시의 현재 색을 검색합니다.|  
|[CListCtrl::GetInsertMarkRect](../Topic/CListCtrl::GetInsertMarkRect.md)|삽입점을 바인딩하는 사각형을 검색 합니다.|  
|[CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)|목록 뷰 항목의 특성을 검색합니다.|  
|[CListCtrl::GetItemCount](../Topic/CListCtrl::GetItemCount.md)|List view 컨트롤에서 항목을 검색합니다.|  
|[CListCtrl::GetItemData](../Topic/CListCtrl::GetItemData.md)|응용 프로그램 특정 항목과 관련 된 값을 검색 합니다.|  
|[CListCtrl::GetItemIndexRect](../Topic/CListCtrl::GetItemIndexRect.md)|현재 목록 보기 컨트롤에서 하위 항목의 전체 또는 일부에 대 한 경계 사각형을 검색합니다.|  
|[CListCtrl::GetItemPosition](../Topic/CListCtrl::GetItemPosition.md)|목록 보기 항목의 위치를 검색합니다.|  
|[CListCtrl::GetItemRect](../Topic/CListCtrl::GetItemRect.md)|항목에 대 한 경계 사각형을 검색합니다.|  
|[CListCtrl::GetItemSpacing](../Topic/CListCtrl::GetItemSpacing.md)|현재 목록 보기 컨트롤에서 항목 사이의 간격을 계산합니다.|  
|[CListCtrl::GetItemState](../Topic/CListCtrl::GetItemState.md)|목록 보기 항목의 상태를 검색합니다.|  
|[CListCtrl::GetItemText](../Topic/CListCtrl::GetItemText.md)|목록 보기 항목 또는 하위 항목의 텍스트를 검색합니다.|  
|[CListCtrl::GetNextItem](../Topic/CListCtrl::GetNextItem.md)|목록 보기 항목 지정 된 속성 및 지정 된 항목에 지정 된 관계를 검색 합니다.|  
|[CListCtrl::GetNextItemIndex](../Topic/CListCtrl::GetNextItemIndex.md)|지정 된 속성 집합이 현재 목록 뷰 컨트롤에 있는 항목의 인덱스를 검색 합니다.|  
|[CListCtrl::GetNextSelectedItem](../Topic/CListCtrl::GetNextSelectedItem.md)|목록 보기 항목 위치 및 위치 반복 다음 선택한 목록 보기 항목의 인덱스를 검색합니다.|  
|[CListCtrl::GetNumberOfWorkAreas](../Topic/CListCtrl::GetNumberOfWorkAreas.md)|현재 작업 영역에 목록 뷰 컨트롤의 수를 검색합니다.|  
|[CListCtrl::GetOrigin](../Topic/CListCtrl::GetOrigin.md)|목록 뷰 컨트롤의 현재 뷰 원점을 검색합니다.|  
|[CListCtrl::GetOutlineColor](../Topic/CListCtrl::GetOutlineColor.md)|목록 뷰 컨트롤의 테두리 색을 검색합니다.|  
|[CListCtrl::GetSelectedColumn](../Topic/CListCtrl::GetSelectedColumn.md)|목록 컨트롤에서 현재 선택한 열의 인덱스를 검색합니다.|  
|[CListCtrl::GetSelectedCount](../Topic/CListCtrl::GetSelectedCount.md)|List view 컨트롤에서 선택한 항목의 수를 검색 합니다.|  
|[CListCtrl::GetSelectionMark](../Topic/CListCtrl::GetSelectionMark.md)|목록 뷰 컨트롤의 선택 영역 표시를 검색합니다.|  
|[CListCtrl::GetStringWidth](../Topic/CListCtrl::GetStringWidth.md)|지정 된 문자열을 표시 하는 데 필요한 최소 열 너비를 결정 합니다.|  
|[CListCtrl::GetSubItemRect](../Topic/CListCtrl::GetSubItemRect.md)|List view 컨트롤에 있는 항목의 경계 사각형을 검색합니다.|  
|[CListCtrl::GetTextBkColor](../Topic/CListCtrl::GetTextBkColor.md)|목록 뷰 컨트롤의 텍스트 배경 색을 검색합니다.|  
|[CListCtrl::GetTextColor](../Topic/CListCtrl::GetTextColor.md)|목록 뷰 컨트롤의 텍스트 색을 검색합니다.|  
|[CListCtrl::GetTileInfo](../Topic/CListCtrl::GetTileInfo.md)|List view 컨트롤에서 타일에 대 한 정보를 검색합니다.|  
|[CListCtrl::GetTileViewInfo](../Topic/CListCtrl::GetTileViewInfo.md)|Tile 보기에서 목록 뷰 컨트롤에 대 한 정보를 검색합니다.|  
|[CListCtrl::GetToolTips](../Topic/CListCtrl::GetToolTips.md)|목록 뷰 컨트롤을 사용 하 여 도구 설명을 표시 하려면 tooltip 컨트롤을 검색 합니다.|  
|[CListCtrl::GetTopIndex](../Topic/CListCtrl::GetTopIndex.md)|맨 위에 표시 되는 항목의 인덱스를 검색합니다.|  
|[CListCtrl::GetView](../Topic/CListCtrl::GetView.md)|목록 뷰 컨트롤의 뷰를 가져옵니다.|  
|[CListCtrl::GetViewRect](../Topic/CListCtrl::GetViewRect.md)|List view 컨트롤에서 모든 항목의 경계 사각형을 검색합니다.|  
|[CListCtrl::GetWorkAreas](../Topic/CListCtrl::GetWorkAreas.md)|현재 작업 영역에 목록 뷰 컨트롤을 검색합니다.|  
|[CListCtrl::HasGroup](../Topic/CListCtrl::HasGroup.md)|목록 뷰 컨트롤의 지정 된 그룹 인지 여부를 결정 합니다.|  
|[CListCtrl::HitTest](../Topic/CListCtrl::HitTest.md)|확인 목록 보기 항목에 지정 된 위치입니다.|  
|[CListCtrl::InsertColumn](../Topic/CListCtrl::InsertColumn.md)|목록 뷰 컨트롤에 새 열을 삽입 합니다.|  
|[CListCtrl::InsertGroup](../Topic/CListCtrl::InsertGroup.md)|그룹 목록 뷰 컨트롤에 삽입합니다.|  
|[CListCtrl::InsertGroupSorted](../Topic/CListCtrl::InsertGroupSorted.md)|순서가 지정 된 목록을 그룹에 지정 된 그룹을 삽입합니다.|  
|[CListCtrl::InsertItem](../Topic/CListCtrl::InsertItem.md)|새 항목을 목록 뷰 컨트롤에 삽입합니다.|  
|[CListCtrl::InsertMarkHitTest](../Topic/CListCtrl::InsertMarkHitTest.md)|지정 된 위치에 가장 가까운 삽입 포인터를 검색합니다.|  
|[CListCtrl::IsGroupViewEnabled](../Topic/CListCtrl::IsGroupViewEnabled.md)|그룹 보기는 목록 뷰 컨트롤에 대 한 사용 여부를 결정 합니다.|  
|[CListCtrl::IsItemVisible](../Topic/CListCtrl::IsItemVisible.md)|지정된 된 항목을 현재 목록 뷰 컨트롤에 표시 되는지 여부를 나타냅니다.|  
|[CListCtrl::MapIDToIndex](../Topic/CListCtrl::MapIDToIndex.md)|현재 목록 뷰 컨트롤에 있는 항목의 고유 ID를 인덱스에 매핑합니다.|  
|[CListCtrl::MapIndexToID](../Topic/CListCtrl::MapIndexToID.md)|현재 목록 뷰 컨트롤에 있는 항목의 인덱스를 고유 ID로 매핑합니다.|  
|[CListCtrl::MoveGroup](../Topic/CListCtrl::MoveGroup.md)|지정 된 그룹을 이동합니다.|  
|[CListCtrl::MoveItemToGroup](../Topic/CListCtrl::MoveItemToGroup.md)|지정 된 지정 제로 기반된 인덱스 목록 뷰 컨트롤의 그룹을 이동 합니다.|  
|[CListCtrl::RedrawItems](../Topic/CListCtrl::RedrawItems.md)|항목 범위를 다시 표시 하는 목록 뷰 컨트롤을 강제로 합니다.|  
|[CListCtrl::RemoveAllGroups](../Topic/CListCtrl::RemoveAllGroups.md)|List view 컨트롤에서 모든 그룹을 제거합니다.|  
|[CListCtrl::RemoveGroup](../Topic/CListCtrl::RemoveGroup.md)|List view 컨트롤에서 지정 된 그룹을 제거합니다.|  
|[CListCtrl::Scroll](../Topic/CListCtrl::Scroll.md)|목록 뷰 컨트롤의 내용을 스크롤합니다.|  
|[CListCtrl::SetBkColor](../Topic/CListCtrl::SetBkColor.md)|목록 뷰 컨트롤의 배경색을 설정합니다.|  
|[CListCtrl::SetBkImage](../Topic/CListCtrl::SetBkImage.md)|목록 뷰 컨트롤의 현재 배경 이미지를 설정합니다.|  
|[CListCtrl::SetCallbackMask](../Topic/CListCtrl::SetCallbackMask.md)|목록 뷰 컨트롤에 대 한 콜백 마스크를 설정합니다.|  
|[CListCtrl::SetCheck](../Topic/CListCtrl::SetCheck.md)|현재 설정 항목과 연결 되는 상태 이미지의 상태를 표시 합니다.|  
|[CListCtrl::SetColumn](../Topic/CListCtrl::SetColumn.md)|목록 보기 열의 특성을 설정합니다.|  
|[CListCtrl::SetColumnOrderArray](../Topic/CListCtrl::SetColumnOrderArray.md)|목록 뷰 컨트롤의 열 순서 \(왼쪽에서 오른쪽으로\)을 설정 합니다.|  
|[CListCtrl::SetColumnWidth](../Topic/CListCtrl::SetColumnWidth.md)|목록 보기 또는 보고서 보기에서 열의 너비를 변경합니다.|  
|[CListCtrl::SetExtendedStyle](../Topic/CListCtrl::SetExtendedStyle.md)|현재 확장된 목록 뷰 컨트롤의 스타일을 설정합니다.|  
|[CListCtrl::SetGroupInfo](../Topic/CListCtrl::SetGroupInfo.md)|목록 뷰 컨트롤의 지정 된 그룹에 대 한 정보를 설정합니다.|  
|[CListCtrl::SetGroupMetrics](../Topic/CListCtrl::SetGroupMetrics.md)|List view 컨트롤의 그룹 메트릭을 설정합니다.|  
|[CListCtrl::SetHotCursor](../Topic/CListCtrl::SetHotCursor.md)|목록 뷰 컨트롤에 대해 핫 트래킹을 사용 하는 경우 사용 되는 커서를 설정 합니다.|  
|[CListCtrl::SetHotItem](../Topic/CListCtrl::SetHotItem.md)|현재 활성 항목을 목록 뷰 컨트롤을 설정합니다.|  
|[CListCtrl::SetHoverTime](../Topic/CListCtrl::SetHoverTime.md)|목록 뷰 컨트롤의 현재 호버 시간을 설정합니다.|  
|[CListCtrl::SetIconSpacing](../Topic/CListCtrl::SetIconSpacing.md)|아이콘 목록 뷰 컨트롤에서 사이의 간격을 설정합니다.|  
|[CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md)|이미지 목록에 목록 뷰 컨트롤에 할당합니다.|  
|[CListCtrl::SetInfoTip](../Topic/CListCtrl::SetInfoTip.md)|도구 설명 텍스트를 설정합니다.|  
|[CListCtrl::SetInsertMark](../Topic/CListCtrl::SetInsertMark.md)|정의 된 위치에 삽입 포인터를 설정합니다.|  
|[CListCtrl::SetInsertMarkColor](../Topic/CListCtrl::SetInsertMarkColor.md)|커서의 색을 설정합니다.|  
|[CListCtrl::SetItem](../Topic/CListCtrl::SetItem.md)|일부 또는 모든 목록 뷰 항목의 특성을 설정합니다.|  
|[CListCtrl::SetItemCount](../Topic/CListCtrl::SetItemCount.md)|목록 뷰 컨트롤은 많은 수의 항목을 추가 하는 데 준비 합니다.|  
|[CListCtrl::SetItemCountEx](../Topic/CListCtrl::SetItemCountEx.md)|가상 목록 뷰 컨트롤의 항목 수를 설정합니다.|  
|[CListCtrl::SetItemData](../Topic/CListCtrl::SetItemData.md)|항목의 응용 프로그램 특정 값을 설정합니다.|  
|[CListCtrl::SetItemIndexState](../Topic/CListCtrl::SetItemIndexState.md)|현재 목록 보기 컨트롤에서 항목의 상태를 설정합니다.|  
|[CListCtrl::SetItemPosition](../Topic/CListCtrl::SetItemPosition.md)|항목 목록 뷰 컨트롤에 지정 된 위치로 이동합니다.|  
|[CListCtrl::SetItemState](../Topic/CListCtrl::SetItemState.md)|List view 컨트롤에 있는 항목의 상태를 변경합니다.|  
|[CListCtrl::SetItemText](../Topic/CListCtrl::SetItemText.md)|목록 보기 항목 또는 하위 항목의 텍스트를 변경합니다.|  
|[CListCtrl::SetOutlineColor](../Topic/CListCtrl::SetOutlineColor.md)|목록 뷰 컨트롤의 테두리 색을 설정합니다.|  
|[CListCtrl::SetSelectedColumn](../Topic/CListCtrl::SetSelectedColumn.md)|목록 뷰 컨트롤의 선택된 된 열을 설정합니다.|  
|[CListCtrl::SetSelectionMark](../Topic/CListCtrl::SetSelectionMark.md)|목록 뷰 컨트롤의 선택 표시를 설정합니다.|  
|[CListCtrl::SetTextBkColor](../Topic/CListCtrl::SetTextBkColor.md)|List view 컨트롤에서 텍스트의 배경색을 설정합니다.|  
|[CListCtrl::SetTextColor](../Topic/CListCtrl::SetTextColor.md)|목록 뷰 컨트롤의 텍스트 색을 설정합니다.|  
|[CListCtrl::SetTileInfo](../Topic/CListCtrl::SetTileInfo.md)|목록 뷰 컨트롤의 타일에 대 한 정보를 설정합니다.|  
|[CListCtrl::SetTileViewInfo](../Topic/CListCtrl::SetTileViewInfo.md)|Tile 보기에서 목록 뷰 컨트롤을 사용 하 여 정보를 설정 합니다.|  
|[CListCtrl::SetToolTips](../Topic/CListCtrl::SetToolTips.md)|도구 설명을 표시 하는 데 사용할 목록 뷰 컨트롤의 도구 설명 컨트롤을 설정 합니다.|  
|[CListCtrl::SetView](../Topic/CListCtrl::SetView.md)|목록 뷰 컨트롤의 뷰를 설정합니다.|  
|[CListCtrl::SetWorkAreas](../Topic/CListCtrl::SetWorkAreas.md)|List view 컨트롤에서 아이콘이 표시 될 수 있습니다 영역을 설정 합니다.|  
|[CListCtrl::SortGroups](../Topic/CListCtrl::SortGroups.md)|그룹 목록을 정렬 합니다. 컨트롤에 사용자 정의 함수를 보여 줍니다.|  
|[CListCtrl::SortItems](../Topic/CListCtrl::SortItems.md)|응용 프로그램\-정의 된 비교 함수를 사용 하 여 목록 보기 항목을 정렬 합니다.|  
|[CListCtrl::SortItemsEx](../Topic/CListCtrl::SortItemsEx.md)|응용 프로그램\-정의 된 비교 함수를 사용 하 여 목록 보기 항목을 정렬 합니다.|  
|[CListCtrl::SubItemHitTest](../Topic/CListCtrl::SubItemHitTest.md)|지정 된 위치에 있을 경우 목록 보기 항목을 결정 합니다.|  
|[CListCtrl::Update](../Topic/CListCtrl::Update.md)|지정 된 항목을 다시 표시 하는 컨트롤을 강제로 합니다.|  
  
## 설명  
 아이콘 및 레이블 외에 각 항목의 아이콘 및 레이블 오른쪽 열에 표시 되는 정보를 가질 수 있습니다.  이 컨트롤 \(즉의 `CListCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 다음은 간략 한 개요입니다는 `CListCtrl` 클래스입니다.  자세한 개념 토론을 참조 하십시오.  [CListCtrl 사용](../../mfc/using-clistctrl.md) 및  [컨트롤](../../mfc/controls-mfc.md).  
  
## 뷰  
 목록 뷰 컨트롤의 내용을 "뷰" 라는 네 가지 방법으로 표시할 수 있습니다.  
  
-   아이콘 보기  
  
     각 항목이 전체 크기의 아이콘 \(32 x 32 픽셀\)으로 아래에 레이블이 나타납니다.  사용자 목록 보기 창에서 임의의 위치로 항목을 끕니다 수 있습니다.  
  
-   작은 아이콘 보기  
  
     각 항목 오른쪽에 레이블이 있는 작은 아이콘 \(16 x 16 픽셀\)를 나타납니다.  사용자 목록 보기 창에서 임의의 위치로 항목을 끕니다 수 있습니다.  
  
-   목록 보기  
  
     각 항목의 오른쪽에 레이블이 있는 작은 아이콘 표시 됩니다.  항목 열에서 정렬 및 목록 보기 창의 어느 위치로 든 끌 수 없습니다.  
  
-   보고서 보기  
  
     자세한 정보는 오른쪽 정렬 각 항목 자체 줄에 나타납니다.  맨 왼쪽 열에 작은 아이콘 및 레이블이 포함 및 하위 응용 프로그램에 의해 지정 된 다음 열이 포함 됩니다.  에 포함 된 헤더 컨트롤 \(클래스  [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)\)이이 열을 구현 합니다.  헤더 컨트롤 및 보고서 보기에서 열에 대 한 자세한 내용은  [CListCtrl 사용: 추가 열 \(보고서 보기\)를](../../mfc/adding-columns-to-the-control-report-view.md).  
  
 참고 항목:  
  
-   기술 자료 문서 Q250614: 방법: 보고서 보기에서는 CListCtrl 항목 정렬  
  
-   기술 자료 문서 Q200054: PRB: OnTimer\(\) 되지 않습니다 라는 반복적 목록 컨트롤에 대 한  
  
 현재 보기의 현재 목록 뷰 컨트롤의 스타일을 결정합니다.  이러한 스타일과 사용법에 대 한 자세한 내용은 참조 하십시오.  [CListCtrl 사용: 목록 컨트롤 스타일 변경](../../mfc/changing-list-control-styles.md).  
  
## 확장 스타일  
 표준 목록 스타일 외에도 클래스 `CListCtrl` 큰 풍부해 진된 기능을 제공 하는 확장된 스타일을 지원 합니다.  이 기능의 예를 들면 다음과 같습니다.  
  
-   호버 선택  
  
     특정 기간에 대 한 항목 위로 커서를 유지할 때 사용 하는 경우 항목이 자동 선택이 있습니다.  
  
-   가상 목록 보기  
  
     활성화 되 면 컨트롤을 지 원하는 최대 수 `DWORD` 항목.  항목 데이터는 응용 프로그램에서 관리 하는 오버 헤드를 배치 하 여 수 있습니다.  항목 선택 및 포커스 정보를 제외한 모든 항목 정보는 응용 프로그램에서 관리 해야 합니다.  자세한 내용은  [CListCtrl 사용: 가상 List 컨트롤](../../mfc/virtual-list-controls.md).  
  
-   One– 및 two– 정품 인증을 클릭합니다.  
  
     활성화 되 면 \(자동 항목의 텍스트를 강조 표시\) 추적 핫 있습니다 one– 또는 two– 활성화의 강조 표시 된 항목을 클릭 합니다.  
  
-   드래그 앤 드롭 열 순서  
  
     활성화 되 면 드래그 앤 드롭 list view 컨트롤에서 열 순서를 바꿀 수 있습니다.  보고서 보기 에서만 사용할 수 있습니다.  
  
 확장 스타일을 이러한 새 사용 하는 방법에 대 한 참조 하십시오.  [CListCtrl 사용: 목록 컨트롤 스타일 변경](../../mfc/changing-list-control-styles.md).  
  
## 항목 및 하위 항목  
 List view 컨트롤에서 각 항목 \(이미지 목록\)에서 아이콘 레이블을, 현재 상태, \("데이터 항목"이 라고도 함\) 응용 프로그램 정의 값으로 구성 됩니다.  하나 이상의 하위 각 항목과 연관 될 수도 있습니다.  "하위" 보고서 보기에서 항목의 아이콘 및 레이블 오른쪽 열에 표시 될 수 있는 문자열입니다.  모든 항목을 목록 뷰 컨트롤에 하위 항목 수가 있어야 합니다.  
  
 클래스  **CListCtrl**  삽입, 삭제, 찾기 및 이러한 항목의 수정에 대 한 여러 가지 기능을 제공 합니다.  자세한 내용은  [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md),  [CListCtrl::InsertItem](../Topic/CListCtrl::InsertItem.md), 및  [CListCtrl::FindItem](../Topic/CListCtrl::FindItem.md),  [CListCtrl 사용: 컨트롤에 항목 추가](../../mfc/adding-items-to-the-control.md), 및  [CListCtrl 사용: 스크롤, 정렬, 정렬 및 찾기 목록 컨트롤에서](../../mfc/scrolling-arranging-sorting-and-finding-in-list-controls.md).  
  
 기본적으로 목록 보기 컨트롤 항목의 아이콘 및 텍스트 특성을 저장 하는 책임입니다.  그러나 이러한 항목 형식 뿐만 아니라 클래스 `CListCtrl` "콜백 항목" 지원 목록 보기 항목의 "콜백 항목"입니다 응용 프로그램\-컨트롤 대신\-텍스트, 아이콘 또는 둘 다를 저장 합니다.  콜백 마스크 지정 항목 특성 \(텍스트 및\/또는 아이콘\) 응용 프로그램에서 제공 하는 데 사용 됩니다.  응용 프로그램 콜백 항목을 사용 하는 경우 주문형 아이콘 및 텍스트 특성을 제공할 수 있어야 합니다.  콜백 항목은 응용 프로그램을 이미이 정보 중 일부를 유지 하는 경우에 유용 합니다.  자세한 내용은  [를 사용 하 여 포함 시켜야: 콜백 항목 및 콜백 마스크](../../mfc/callback-items-and-the-callback-mask.md).  
  
## 이미지 목록  
 아이콘, 헤더 항목 이미지 및 application– 정의 상태의 목록 보기 항목 몇 가지 이미지 목록에 포함 된에 대 한 \(클래스에 의해 구현  [CImageList](../../mfc/reference/cimagelist-class.md)\), 생성 및 목록 뷰 컨트롤에 할당 합니다.  각 목록 뷰 컨트롤까지 네 가지 이미지 목록 사용할 수 있습니다.  
  
-   큰 아이콘  
  
     아이콘 보기에서 큰 아이콘을 사용 합니다.  
  
-   작은 아이콘  
  
     작은 아이콘, 목록 및 보고서 보기에서 아이콘 보기에서 사용 하는 아이콘의 작은 버전을 사용 합니다.  
  
-   응용 프로그램 정의 상태  
  
     응용 프로그램 정의 상태를 나타내는 항목의 아이콘 옆에 표시 되는 상태 이미지를 포함 합니다.  
  
-   Header item  
  
     보고서 보기에서 각 머리글 컨트롤 항목을 표시 하는 작은 이미지를 사용 합니다.  
  
 기본적으로 이미지 목록을 소멸 되 면 지정 된 목록 뷰 컨트롤을 소멸 시킵니다. 그러나 개발자는 더 이상 사용 되 면 응용 프로그램에 의해 결정 되는 각 이미지 목록을 파괴 하 여이 동작을 지정할 수 없습니다.  자세한 내용은  [CListCtrl 사용: 목록 항목 및 목록 이미지](../../mfc/list-items-and-image-lists.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [Rowlist에서는 MFC 샘플](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)