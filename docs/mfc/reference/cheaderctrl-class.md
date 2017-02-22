---
title: "CHeaderCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHeaderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeaderCtrl class"
  - "header controls, CHeaderCtrl class"
  - "Windows common controls [C++], CHeaderCtrl"
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CHeaderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반적인 Windows 헤더 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CHeaderCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHeaderCtrl::CHeaderCtrl](../Topic/CHeaderCtrl::CHeaderCtrl.md)|`CHeaderCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHeaderCtrl::ClearAllFilters](../Topic/CHeaderCtrl::ClearAllFilters.md)|헤더 컨트롤에 대 한 모든 필터를 지웁니다.|  
|[CHeaderCtrl::ClearFilter](../Topic/CHeaderCtrl::ClearFilter.md)|헤더 컨트롤에 대 한 필터를 지웁니다.|  
|[CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md)|헤더 컨트롤을 만들고이에 연결 된 `CHeaderCtrl` 개체입니다.|  
|[CHeaderCtrl::CreateDragImage](../Topic/CHeaderCtrl::CreateDragImage.md)|헤더 컨트롤 내에서 항목의 이미지의 투명 한 버전을 만듭니다.|  
|[CHeaderCtrl::CreateEx](../Topic/CHeaderCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 머리글 컨트롤을 만들고 연결 하는 `CListCtrl` 개체입니다.|  
|[CHeaderCtrl::DeleteItem](../Topic/CHeaderCtrl::DeleteItem.md)|헤더 컨트롤에서 항목을 삭제합니다.|  
|[CHeaderCtrl::DrawItem](../Topic/CHeaderCtrl::DrawItem.md)|지정 된 항목의 머리글 컨트롤을 그립니다.|  
|[CHeaderCtrl::EditFilter](../Topic/CHeaderCtrl::EditFilter.md)|Header 컨트롤의 지정 된 필터 편집을 시작 합니다.|  
|[CHeaderCtrl::GetBitmapMargin](../Topic/CHeaderCtrl::GetBitmapMargin.md)|여백 머리글 컨트롤에 비트맵의 너비를 검색합니다.|  
|[CHeaderCtrl::GetFocusedItem](../Topic/CHeaderCtrl::GetFocusedItem.md)|포커스가 현재 머리글 컨트롤에서 항목의 식별자를 가져옵니다.|  
|[CHeaderCtrl::GetImageList](../Topic/CHeaderCtrl::GetImageList.md)|헤더 컨트롤에 헤더 항목을 드로잉에 사용 되는 이미지 목록을 핸들을 검색 합니다.|  
|[CHeaderCtrl::GetItem](../Topic/CHeaderCtrl::GetItem.md)|헤더 컨트롤에 있는 항목에 대 한 정보를 검색합니다.|  
|[CHeaderCtrl::GetItemCount](../Topic/CHeaderCtrl::GetItemCount.md)|헤더 컨트롤에 있는 항목의 개수를 검색합니다.|  
|[CHeaderCtrl::GetItemDropDownRect](../Topic/CHeaderCtrl::GetItemDropDownRect.md)|헤더 컨트롤에 드롭다운 단추에 대 한 경계 사각형 정보를 가져옵니다.|  
|[CHeaderCtrl::GetItemRect](../Topic/CHeaderCtrl::GetItemRect.md)|헤더 컨트롤에서 지정 된 항목의 경계 사각형을 검색합니다.|  
|[CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md)|항목 머리글 컨트롤에서의 왼쪽에서 오른쪽으로 순서를 검색합니다.|  
|[CHeaderCtrl::GetOverflowRect](../Topic/CHeaderCtrl::GetOverflowRect.md)|현재 머리글 컨트롤에 대 한 오버플로 단추의 경계 사각형을 가져옵니다.|  
|[CHeaderCtrl::HitTest](../Topic/CHeaderCtrl::HitTest.md)|머리글 항목을 지정 된 지점에 있는 경우, 있는지 확인 합니다.|  
|[CHeaderCtrl::InsertItem](../Topic/CHeaderCtrl::InsertItem.md)|헤더 컨트롤에 새 항목을 삽입합니다.|  
|[CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md)|크기와 지정 된 사각형 내의 머리글 컨트롤의 위치를 검색합니다.|  
|[CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md)|머리글 컨트롤에는 순서에 따라 항목의 인덱스 값을 검색 합니다.|  
|[CHeaderCtrl::SetBitmapMargin](../Topic/CHeaderCtrl::SetBitmapMargin.md)|헤더 컨트롤에서 비트맵의 여백의 너비를 설정합니다.|  
|[CHeaderCtrl::SetFilterChangeTimeout](../Topic/CHeaderCtrl::SetFilterChangeTimeout.md)|게시에서 필터 속성 변경에 소요 되는 시간 사이의 시간 간격 설정 하는 `HDN_FILTERCHANGE` 알림.|  
|[CHeaderCtrl::SetFocusedItem](../Topic/CHeaderCtrl::SetFocusedItem.md)|현재 헤더 컨트롤에 헤더를 지정 된 항목에 포커스를 설정합니다.|  
|[CHeaderCtrl::SetHotDivider](../Topic/CHeaderCtrl::SetHotDivider.md)|변경 내용을 수동으로 나타내려면 머리글 항목 사이의 구분선을 드래그 앤 드롭 머리글 항목의.|  
|[CHeaderCtrl::SetImageList](../Topic/CHeaderCtrl::SetImageList.md)|이미지 목록 컨트롤에 머리글을 할당합니다.|  
|[CHeaderCtrl::SetItem](../Topic/CHeaderCtrl::SetItem.md)|헤더 컨트롤에서 지정 된 항목의 특성을 설정합니다.|  
|[CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md)|헤더 컨트롤에서 항목의 왼쪽에서 오른쪽으로 순서를 설정합니다.|  
  
## 설명  
 헤더 컨트롤에 일반적으로 숫자 또는 텍스트 열 집합 위에 위치한 창입니다.  각 열 제목을 포함 한 부분으로 나눌 수 있습니다.  사용자가 각 열의 너비를 설정 하는 부분을 구분 하는 구분선을 끌 수 있습니다.  Header 컨트롤의 그림을 참조 하십시오.  [머리글 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775238).  
  
 이 컨트롤 \(즉의 `CHeaderCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 하는 프로그램에 사용할 수 있습니다.  
  
 Windows 95\/Internet Explorer 4.0 공용 컨트롤에 대 한 추가 기능을 다음과 같습니다.  
  
-   머리글 항목 사용자 지정 순서입니다.  
  
-   머리글 항목 끌어서 놓기, 헤더 항목의 순서 변경에 대 한.  사용 된 `HDS_DRAGDROP` 스타일을 만들 때의 `CHeaderCtrl` 개체.  
  
-   머리글 열의 텍스트 열 크기를 조정 하는 동안 계속 해 서 볼 수 있는입니다.  사용 된 `HDS_FULLDRAG` 스타일을 만들 때의 `CHeaderCtrl` 개체.  
  
-   위에 포인터를 가리킬 때에 머리글 항목이 강조 표시 됩니다 헤더 핫 트래킹.  사용 된 `HDS_HOTTRACK` 스타일을 만들 때의 `CHeaderCtrl` 개체.  
  
-   이미지 목록 지원 합니다.  머리글 항목에 저장 되어 있는 이미지를 포함할 수 있는 `CImageList` 개체 또는 텍스트입니다.  
  
 사용에 대 한 자세한 내용은 `CHeaderCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CHeaderCtrl 사용](../../mfc/using-cheaderctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHeaderCtrl`  
  
## 요구 사항  
 **헤더:** afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CTabCtrl Class](../../mfc/reference/ctabctrl-class.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)   
 [CImageList Class](../../mfc/reference/cimagelist-class.md)