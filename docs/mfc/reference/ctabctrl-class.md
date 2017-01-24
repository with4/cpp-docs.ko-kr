---
title: "CTabCtrl Class | Microsoft Docs"
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
  - "CTabCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl class"
  - "CTabCtrl class, 공용 컨트롤"
  - "tab 컨트롤"
ms.assetid: 42e4aff6-46ae-4b2c-beaa-d1dce8d82138
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTabCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

일반적인 탭 Windows 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CTabCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CTabCtrl::CTabCtrl](../Topic/CTabCtrl::CTabCtrl.md)|`CTabCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTabCtrl::AdjustRect](../Topic/CTabCtrl::AdjustRect.md)|창 사각형을 지정 된 탭 컨트롤의 표시 영역을 계산 하거나 주어진된 표시 영역에 해당 하는 창 사각형을 계산 합니다.|  
|[CTabCtrl::Create](../Topic/CTabCtrl::Create.md)|탭 컨트롤을 만들고이 인스턴스에 연결 된 `CTabCtrl` 개체입니다.|  
|[CTabCtrl::CreateEx](../Topic/CTabCtrl::CreateEx.md)|지정한 Windows 확장된 스타일 탭 컨트롤을 만들고이 인스턴스에 연결 된 `CTabCtrl` 개체입니다.|  
|[CTabCtrl::DeleteAllItems](../Topic/CTabCtrl::DeleteAllItems.md)|탭 컨트롤에서 모든 항목을 제거합니다.|  
|[CTabCtrl::DeleteItem](../Topic/CTabCtrl::DeleteItem.md)|탭 컨트롤에서 항목을 제거합니다.|  
|[CTabCtrl::DeselectAll](../Topic/CTabCtrl::DeselectAll.md)|원하는 눌렀는지 지우기 탭 컨트롤에서 항목을 다시 설정 합니다.|  
|[CTabCtrl::DrawItem](../Topic/CTabCtrl::DrawItem.md)|탭 컨트롤의 지정 된 항목을 그립니다.|  
|[CTabCtrl::GetCurFocus](../Topic/CTabCtrl::GetCurFocus.md)|현재 포커스가 탭 컨트롤의 탭을 검색합니다.|  
|[CTabCtrl::GetCurSel](../Topic/CTabCtrl::GetCurSel.md)|현재 선택된 된 탭에서 탭 컨트롤을 결정합니다.|  
|[CTabCtrl::GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md)|현재 탭 컨트롤에 사용 되는 확장된 스타일을 검색 합니다.|  
|[CTabCtrl::GetImageList](../Topic/CTabCtrl::GetImageList.md)|탭 컨트롤에 연결 된 이미지 목록을 검색 합니다.|  
|[CTabCtrl::GetItem](../Topic/CTabCtrl::GetItem.md)|탭 컨트롤에서 탭에 대 한 정보를 검색합니다.|  
|[CTabCtrl::GetItemCount](../Topic/CTabCtrl::GetItemCount.md)|탭 컨트롤에서 탭을 검색합니다.|  
|[CTabCtrl::GetItemRect](../Topic/CTabCtrl::GetItemRect.md)|탭 컨트롤에서 탭에 대 한 경계 사각형을 검색합니다.|  
|[CTabCtrl::GetItemState](../Topic/CTabCtrl::GetItemState.md)|지정 된 탭 컨트롤 항목의 상태를 검색합니다.|  
|[CTabCtrl::GetRowCount](../Topic/CTabCtrl::GetRowCount.md)|현재 탭에서 탭 컨트롤의 행 개수를 검색합니다.|  
|[CTabCtrl::GetToolTips](../Topic/CTabCtrl::GetToolTips.md)|탭 컨트롤과 연결 된 도구 설명 컨트롤의 핸들을 검색 합니다.|  
|[CTabCtrl::HighlightItem](../Topic/CTabCtrl::HighlightItem.md)|탭 항목의 강조 표시 상태를 설정합니다.|  
|[CTabCtrl::HitTest](../Topic/CTabCtrl::HitTest.md)|지정 된 화면 위치에 있으면 어떤 탭을 인지 확인 합니다.|  
|[CTabCtrl::InsertItem](../Topic/CTabCtrl::InsertItem.md)|새 탭에서 탭 컨트롤을 삽입합니다.|  
|[CTabCtrl::RemoveImage](../Topic/CTabCtrl::RemoveImage.md)|탭 컨트롤의 이미지 목록에서 이미지를 제거합니다.|  
|[CTabCtrl::SetCurFocus](../Topic/CTabCtrl::SetCurFocus.md)|지정한 탭 탭 컨트롤에 포커스를 설정합니다.|  
|[CTabCtrl::SetCurSel](../Topic/CTabCtrl::SetCurSel.md)|탭 컨트롤에 탭을 선택합니다.|  
|[CTabCtrl::SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md)|탭 컨트롤에 대 한 확장된 스타일을 설정합니다.|  
|[CTabCtrl::SetImageList](../Topic/CTabCtrl::SetImageList.md)|이미지 목록 탭 컨트롤에 할당합니다.|  
|[CTabCtrl::SetItem](../Topic/CTabCtrl::SetItem.md)|일부 또는 전부를 탭 속성을 설정합니다.|  
|[CTabCtrl::SetItemExtra](../Topic/CTabCtrl::SetItemExtra.md)|탭 탭 컨트롤에서 응용 프로그램 정의 데이터에 대 한 예약 당 바이트 수를 설정 합니다.|  
|[CTabCtrl::SetItemSize](../Topic/CTabCtrl::SetItemSize.md)|너비와 높이의 항목을 설정합니다.|  
|[CTabCtrl::SetItemState](../Topic/CTabCtrl::SetItemState.md)|지정 된 탭 컨트롤 항목의 상태를 설정합니다.|  
|[CTabCtrl::SetMinTabWidth](../Topic/CTabCtrl::SetMinTabWidth.md)|탭 컨트롤에서 항목의 최소 너비를 설정합니다.|  
|[CTabCtrl::SetPadding](../Topic/CTabCtrl::SetPadding.md)|각 탭의 아이콘 및 레이블 탭 컨트롤에서 \(안쪽\) 간격을 설정 합니다.|  
|[CTabCtrl::SetToolTips](../Topic/CTabCtrl::SetToolTips.md)|도구 설명 컨트롤에 탭 컨트롤에 할당합니다.|  
  
## 설명  
 "탭 컨트롤"은 노트북에서 구분선 또는 파일 캐비닛의 레이블에 비슷합니다.  응용 프로그램에서는 탭 컨트롤을 이용하여 창 또는 대화 상자의 동일한 영역을 여러 페이지로 정의할 수 있습니다.  각 페이지에 정보 또는 해당 탭을 선택할 때 응용 프로그램을 표시 하는 컨트롤의 그룹 집합으로 구성 됩니다.  특수 한 유형의 탭 컨트롤 단추 처럼 표시 되는 탭을 표시 합니다.  단추를 클릭 하면 페이지를 표시 하지 않고 명령을 즉시 수행 해야 합니다.  
  
 이 컨트롤 \(즉의 `CTabCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 사용에 대 한 자세한 내용은 `CTabCtrl`를 참조 하십시오  [컨트롤](../../mfc/controls-mfc.md) 및  [CTabCtrl 사용](../../mfc/using-ctabctrl.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CTabCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CHeaderCtrl Class](../../mfc/reference/cheaderctrl-class.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)