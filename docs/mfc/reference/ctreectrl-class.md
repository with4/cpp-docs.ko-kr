---
title: "CTreeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl class"
  - "directory lists"
  - "file lists [C++]"
  - "tree view controls"
ms.assetid: 96e20031-6161-4143-8c12-8d1816c66d90
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows 공용 트리 뷰 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CTreeCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CTreeCtrl::CTreeCtrl](../Topic/CTreeCtrl::CTreeCtrl.md)|`CTreeCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTreeCtrl::Create](../Topic/CTreeCtrl::Create.md)|트리 뷰 컨트롤을 만들고이에 연결 된 `CTreeCtrl` 개체입니다.|  
|[CTreeCtrl::CreateDragImage](../Topic/CTreeCtrl::CreateDragImage.md)|지정 된 트리 뷰 항목을 끌기 비트맵을 만듭니다.|  
|[CTreeCtrl::CreateEx](../Topic/CTreeCtrl::CreateEx.md)|지정 된 Windows 확장된 스타일 트리 컨트롤을 만들고 연결 하는 `CTreeCtrl` 개체입니다.|  
|[CTreeCtrl::DeleteAllItems](../Topic/CTreeCtrl::DeleteAllItems.md)|트리 뷰 컨트롤에서 모든 항목을 삭제합니다.|  
|[CTreeCtrl::DeleteItem](../Topic/CTreeCtrl::DeleteItem.md)|새 트리 뷰 컨트롤에서 항목을 삭제합니다.|  
|[CTreeCtrl::EditLabel](../Topic/CTreeCtrl::EditLabel.md)|지정 된 트리 뷰 항목 전체를 편집합니다.|  
|[CTreeCtrl::EndEditLabelNow](../Topic/CTreeCtrl::EndEditLabelNow.md)|현재 트리 뷰 컨트롤에 트리 뷰 항목의 레이블을 편집 작업을 취소합니다.|  
|[CTreeCtrl::EnsureVisible](../Topic/CTreeCtrl::EnsureVisible.md)|트리 뷰 항목의 트리 뷰 컨트롤에 표시 됩니다.|  
|[CTreeCtrl::Expand](../Topic/CTreeCtrl::Expand.md)|확장 되거나 축소 되는 지정 된 트리 뷰 항목의 자식 항목입니다.|  
|[CTreeCtrl::GetBkColor](../Topic/CTreeCtrl::GetBkColor.md)|컨트롤의 현재 배경 색을 검색합니다.|  
|[CTreeCtrl::GetCheck](../Topic/CTreeCtrl::GetCheck.md)|Tree 컨트롤 항목의 선택 상태를 검색합니다.|  
|[CTreeCtrl::GetChildItem](../Topic/CTreeCtrl::GetChildItem.md)|자식을 지정 된 트리 뷰 항목을 검색합니다.|  
|[CTreeCtrl::GetCount](../Topic/CTreeCtrl::GetCount.md)|트리 뷰 컨트롤에 연결 된 트리 항목을 검색 합니다.|  
|[CTreeCtrl::GetDropHilightItem](../Topic/CTreeCtrl::GetDropHilightItem.md)|끌어서 놓기 작업의 대상으로 검색합니다.|  
|[CTreeCtrl::GetEditControl](../Topic/CTreeCtrl::GetEditControl.md)|지정 된 트리 뷰 항목을 편집 하는 편집 컨트롤의 핸들을 검색 합니다.|  
|[CTreeCtrl::GetExtendedStyle](../Topic/CTreeCtrl::GetExtendedStyle.md)|현재 트리 보기 컨트롤을 사용 하는 확장된 스타일을 검색 합니다.|  
|[CTreeCtrl::GetFirstVisibleItem](../Topic/CTreeCtrl::GetFirstVisibleItem.md)|지정 된 트리 뷰 항목의 표시 되는 첫 번째 항목을 검색합니다.|  
|[CTreeCtrl::GetImageList](../Topic/CTreeCtrl::GetImageList.md)|트리 뷰 컨트롤과 연결 된 이미지 목록의 핸들을 검색 합니다.|  
|[CTreeCtrl::GetIndent](../Topic/CTreeCtrl::GetIndent.md)|트리 뷰 항목의 오프셋 \(픽셀\)의 부모를 검색합니다.|  
|[CTreeCtrl::GetInsertMarkColor](../Topic/CTreeCtrl::GetInsertMarkColor.md)|트리 뷰에 대 한 삽입 표시를 그리는 데 사용 되는 색을 검색 합니다.|  
|[CTreeCtrl::GetItem](../Topic/CTreeCtrl::GetItem.md)|지정 된 트리 뷰 항목의 특성을 검색합니다.|  
|[CTreeCtrl::GetItemData](../Topic/CTreeCtrl::GetItemData.md)|항목과 연관 된 32 비트 응용 프로그램 특정 값을 반환 합니다.|  
|[CTreeCtrl::GetItemExpandedImageIndex](../Topic/CTreeCtrl::GetItemExpandedImageIndex.md)|지정한 항목이 현재 트리 뷰 컨트롤의 확장 된 상태일 때 표시할 이미지의 인덱스를 검색 합니다.|  
|[CTreeCtrl::GetItemHeight](../Topic/CTreeCtrl::GetItemHeight.md)|트리 보기 항목의 현재 높이 검색합니다.|  
|[CTreeCtrl::GetItemImage](../Topic/CTreeCtrl::GetItemImage.md)|항목에 연결 된 이미지를 검색 합니다.|  
|[CTreeCtrl::GetItemPartRect](../Topic/CTreeCtrl::GetItemPartRect.md)|현재 트리 뷰 컨트롤에서 지정된 된 항목의 지정 된 파트에 대 한 경계 사각형을 검색합니다.|  
|[CTreeCtrl::GetItemRect](../Topic/CTreeCtrl::GetItemRect.md)|트리 뷰 항목의 경계 사각형을 검색합니다.|  
|[CTreeCtrl::GetItemState](../Topic/CTreeCtrl::GetItemState.md)|항목의 상태를 반환합니다.|  
|[CTreeCtrl::GetItemStateEx](../Topic/CTreeCtrl::GetItemStateEx.md)|현재 트리 뷰 컨트롤에서 지정 된 항목의 확장된 상태를 검색합니다.|  
|[CTreeCtrl::GetItemText](../Topic/CTreeCtrl::GetItemText.md)|항목의 텍스트를 반환합니다.|  
|[CTreeCtrl::GetLastVisibleItem](../Topic/CTreeCtrl::GetLastVisibleItem.md)|현재 트리 뷰 컨트롤에서 마지막으로 확장 된 항목을 검색합니다.|  
|[CTreeCtrl::GetLineColor](../Topic/CTreeCtrl::GetLineColor.md)|Tree view 컨트롤에 현재 선 색을 검색합니다.|  
|[CTreeCtrl::GetNextItem](../Topic/CTreeCtrl::GetNextItem.md)|지정한 관계와 일치 하는 다음 트리 뷰 항목을 검색 합니다.|  
|[CTreeCtrl::GetNextSiblingItem](../Topic/CTreeCtrl::GetNextSiblingItem.md)|지정 된 트리 뷰 항목의 다음 형제를 검색합니다.|  
|[CTreeCtrl::GetNextVisibleItem](../Topic/CTreeCtrl::GetNextVisibleItem.md)|지정 된 트리 뷰 항목의 표시 되는 다음 항목을 검색합니다.|  
|[CTreeCtrl::GetParentItem](../Topic/CTreeCtrl::GetParentItem.md)|지정 된 트리 뷰 항목의 부모를 검색합니다.|  
|[CTreeCtrl::GetPrevSiblingItem](../Topic/CTreeCtrl::GetPrevSiblingItem.md)|지정 된 트리 뷰 항목의 이전 형제를 검색합니다.|  
|[CTreeCtrl::GetPrevVisibleItem](../Topic/CTreeCtrl::GetPrevVisibleItem.md)|지정 된 트리 뷰 항목의 표시 되는 이전 항목을 검색합니다.|  
|[CTreeCtrl::GetRootItem](../Topic/CTreeCtrl::GetRootItem.md)|지정 된 트리 뷰 항목의 루트를 검색합니다.|  
|[CTreeCtrl::GetScrollTime](../Topic/CTreeCtrl::GetScrollTime.md)|Tree view 컨트롤에 대 한 최대 스크롤 시간을 검색합니다.|  
|[CTreeCtrl::GetSelectedCount](../Topic/CTreeCtrl::GetSelectedCount.md)|현재 트리 뷰 컨트롤에서 선택한 항목의 수를 검색 합니다.|  
|[CTreeCtrl::GetSelectedItem](../Topic/CTreeCtrl::GetSelectedItem.md)|현재 선택된 된 트리 뷰 항목을 검색합니다.|  
|[CTreeCtrl::GetTextColor](../Topic/CTreeCtrl::GetTextColor.md)|현재 컨트롤의 텍스트 색을 검색합니다.|  
|[CTreeCtrl::GetToolTips](../Topic/CTreeCtrl::GetToolTips.md)|하위 트리 뷰 컨트롤에서 사용 되는 도구 설명 컨트롤에 대 한 핸들을 검색 합니다.|  
|[CTreeCtrl::GetVisibleCount](../Topic/CTreeCtrl::GetVisibleCount.md)|트리 뷰 컨트롤에 연결 된 표시 되는 트리 항목의 수를 검색 합니다.|  
|[CTreeCtrl::HitTest](../Topic/CTreeCtrl::HitTest.md)|반환 관련 커서의 현재 위치는 `CTreeCtrl` 개체.|  
|[CTreeCtrl::InsertItem](../Topic/CTreeCtrl::InsertItem.md)|트리 뷰 컨트롤에 새 항목을 삽입합니다.|  
|[CTreeCtrl::ItemHasChildren](../Topic/CTreeCtrl::ItemHasChildren.md)|자식 항목이 지정 된 항목이 있는 경우 0이 아닌 값을 반환 합니다.|  
|[CTreeCtrl::MapAccIdToItem](../Topic/CTreeCtrl::MapAccIdToItem.md)|지정 된 내게 필요한 옵션 식별자를 핸들 현재 트리 뷰 컨트롤에 트리 뷰의 항목에 매핑합니다.|  
|[CTreeCtrl::MapItemToAccID](../Topic/CTreeCtrl::MapItemToAccID.md)|트리 보기 항목에 현재 트리 뷰 컨트롤에서 내게 필요한 옵션 식별자로 지정 된 핸들을 매핑합니다.|  
|[CTreeCtrl::Select](../Topic/CTreeCtrl::Select.md)|선택, 스크롤되어 또는 지정 된 트리 뷰 항목을 다시 그립니다.|  
|[CTreeCtrl::SelectDropTarget](../Topic/CTreeCtrl::SelectDropTarget.md)|트리 항목을 끌어서 놓기 작업의 대상으로 다시 그려집니다.|  
|[CTreeCtrl::SelectItem](../Topic/CTreeCtrl::SelectItem.md)|지정 된 트리 뷰 항목을 선택합니다.|  
|[CTreeCtrl::SelectSetFirstVisible](../Topic/CTreeCtrl::SelectSetFirstVisible.md)|지정 된 트리 뷰 항목으로 표시 되는 첫 번째 항목을 선택합니다.|  
|[CTreeCtrl::SetAutoscrollInfo](../Topic/CTreeCtrl::SetAutoscrollInfo.md)|현재 트리 뷰 컨트롤의 스크롤 속도 설정합니다.|  
|[CTreeCtrl::SetBkColor](../Topic/CTreeCtrl::SetBkColor.md)|컨트롤의 배경색을 설정합니다.|  
|[CTreeCtrl::SetCheck](../Topic/CTreeCtrl::SetCheck.md)|Tree 컨트롤 항목의 선택 상태를 설정합니다.|  
|[CTreeCtrl::SetExtendedStyle](../Topic/CTreeCtrl::SetExtendedStyle.md)|현재 트리 뷰 컨트롤을 위한 확장된 스타일을 설정합니다.|  
|[CTreeCtrl::SetImageList](../Topic/CTreeCtrl::SetImageList.md)|트리 뷰 컨트롤과 연결 된 이미지 목록의 핸들을 설정 합니다.|  
|[CTreeCtrl::SetIndent](../Topic/CTreeCtrl::SetIndent.md)|트리 뷰 항목의 오프셋 \(픽셀\)의 부모를 설정합니다.|  
|[CTreeCtrl::SetInsertMark](../Topic/CTreeCtrl::SetInsertMark.md)|Tree view 컨트롤에서 삽입 표시를 설정합니다.|  
|[CTreeCtrl::SetInsertMarkColor](../Topic/CTreeCtrl::SetInsertMarkColor.md)|트리 뷰에 대 한 삽입 표시를 그리는 데 사용 되는 색을 설정 합니다.|  
|[CTreeCtrl::SetItem](../Topic/CTreeCtrl::SetItem.md)|지정 된 트리 뷰 항목의 특성을 설정합니다.|  
|[CTreeCtrl::SetItemData](../Topic/CTreeCtrl::SetItemData.md)|항목과 연관 된 32 비트 응용 프로그램 특정 값을 설정 합니다.|  
|[CTreeCtrl::SetItemExpandedImageIndex](../Topic/CTreeCtrl::SetItemExpandedImageIndex.md)|지정한 항목이 현재 트리 뷰 컨트롤의 확장 된 상태일 때 표시할 이미지의 인덱스를 설정 합니다.|  
|[CTreeCtrl::SetItemHeight](../Topic/CTreeCtrl::SetItemHeight.md)|높이 트리 뷰 항목을 설정합니다.|  
|[CTreeCtrl::SetItemImage](../Topic/CTreeCtrl::SetItemImage.md)|이미지를 항목에 연결 합니다.|  
|[CTreeCtrl::SetItemState](../Topic/CTreeCtrl::SetItemState.md)|항목의 상태를 설정합니다.|  
|[CTreeCtrl::SetItemStateEx](../Topic/CTreeCtrl::SetItemStateEx.md)|현재 트리 뷰 컨트롤에서 지정된 된 항목의 확장된 상태를 설정합니다.|  
|[CTreeCtrl::SetItemText](../Topic/CTreeCtrl::SetItemText.md)|항목의 텍스트를 설정합니다.|  
|[CTreeCtrl::SetLineColor](../Topic/CTreeCtrl::SetLineColor.md)|Tree view 컨트롤에 현재 선 색을 설정합니다.|  
|[CTreeCtrl::SetScrollTime](../Topic/CTreeCtrl::SetScrollTime.md)|Tree view 컨트롤에 대 한 최대 스크롤 시간을 설정합니다.|  
|[CTreeCtrl::SetTextColor](../Topic/CTreeCtrl::SetTextColor.md)|컨트롤의 텍스트 색을 설정합니다.|  
|[CTreeCtrl::SetToolTips](../Topic/CTreeCtrl::SetToolTips.md)|하위 트리 뷰 컨트롤의 도구 설명 컨트롤을 설정합니다.|  
|[CTreeCtrl::ShowInfoTip](../Topic/CTreeCtrl::ShowInfoTip.md)|현재 트리 뷰 컨트롤에는 지정 된 항목에 대 한 정보 팁을 표시합니다.|  
|[CTreeCtrl::SortChildren](../Topic/CTreeCtrl::SortChildren.md)|지정 된 부모 항목의 자식으로 정렬합니다.|  
|[CTreeCtrl::SortChildrenCB](../Topic/CTreeCtrl::SortChildrenCB.md)|응용 프로그램 정의 정렬 함수를 사용 하 여 지정 된 부모 항목의 자식으로 정렬 합니다.|  
  
## 설명  
 "트리 보기 컨트롤" 디스크 등 문서, 제목, 인덱스 파일 및 디렉터리에 있는 항목의 계층적 목록을 표시 하는 창입니다.  각 항목은 레이블과 선택적 비트맵 이미지로 구성 되 고 각 항목에 연결 된 하위 항목 목록을 가질 수 있습니다.  항목을 클릭 하 여 확장 하 고 연결 된 하위 항목 목록을 축소 사용자 있습니다.  
  
 이 컨트롤 \(즉의 `CTreeCtrl` 클래스\) Windows NT 및 Windows 98 버전 4에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 사용에 대 한 자세한 내용은 `CTreeCtrl`을 참조 하십시오.  
  
-   [컨트롤](../../mfc/controls-mfc.md)  
  
-   [CTreeCtrl 사용](../../mfc/using-ctreectrl.md)  
  
-   [트리 보기 제어 참조](http://msdn.microsoft.com/library/windows/desktop/bb759988) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
-   기술 자료 문서 Q222905: 방법: Ctreectrl에 대 한 컨텍스트 메뉴를 표시 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTreeCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [MFC 샘플 CMNCTRL1](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)