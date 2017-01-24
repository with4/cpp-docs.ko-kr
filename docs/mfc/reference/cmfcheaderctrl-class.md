---
title: "CMFCHeaderCtrl Class | Microsoft Docs"
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
  - "CMFCHeaderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCHeaderCtrl class"
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
caps.latest.revision: 29
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCHeaderCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCHeaderCtrl` 클래스를 지 원하는 헤더 컨트롤에 여러 열을 정렬 합니다.  
  
## 구문  
  
```  
class CMFCHeaderCtrl : public CHeaderCtrl  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCHeaderCtrl::CMFCHeaderCtrl](../Topic/CMFCHeaderCtrl::CMFCHeaderCtrl.md)|`CMFCHeaderCtrl` 개체를 생성합니다.|  
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|소멸자.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCHeaderCtrl::EnableMultipleSort](../Topic/CMFCHeaderCtrl::EnableMultipleSort.md)|설정 또는 해제  *여러 열 정렬* 현재 머리글 컨트롤 모드입니다.|  
|[CMFCHeaderCtrl::GetColumnState](../Topic/CMFCHeaderCtrl::GetColumnState.md)|열 정렬 됩니다 또는 오름차순 또는 내림차순으로 정렬 되어 있는지 여부를 나타냅니다.|  
|[CMFCHeaderCtrl::GetSortColumn](../Topic/CMFCHeaderCtrl::GetSortColumn.md)|첫 번째 정렬된 열 머리글 컨트롤에서의 인덱스를 검색합니다.|  
|`CMFCHeaderCtrl::GetThisClass`|프레임 워크에서 사용 되는 포인터를 얻을 수 있는  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCHeaderCtrl::IsAscending](../Topic/CMFCHeaderCtrl::IsAscending.md)|열 머리글 컨트롤을 오름차순으로 정렬할지 여부를 나타냅니다.|  
|[CMFCHeaderCtrl::IsDialogControl](../Topic/CMFCHeaderCtrl::IsDialogControl.md)|현재 머리글 컨트롤의 부모 창 대화 상자 인지 여부를 나타냅니다.|  
|[CMFCHeaderCtrl::IsMultipleSort](../Topic/CMFCHeaderCtrl::IsMultipleSort.md)|현재 헤더 컨트롤에 있는지 여부를 나타내는  *여러 열 정렬* 모드.|  
|[CMFCHeaderCtrl::RemoveSortColumn](../Topic/CMFCHeaderCtrl::RemoveSortColumn.md)|지정 된 열의 열 정렬 목록에서 제거합니다.|  
|[CMFCHeaderCtrl::SetSortColumn](../Topic/CMFCHeaderCtrl::SetSortColumn.md)|헤더 컨트롤에서 지정 된 열의 정렬 순서를 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCHeaderCtrl::OnDrawItem](../Topic/CMFCHeaderCtrl::OnDrawItem.md)|열 머리글 컨트롤을 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCHeaderCtrl::OnDrawSortArrow](../Topic/CMFCHeaderCtrl::OnDrawSortArrow.md)|정렬 화살표를 그리려면 프레임 워크에서 호출 됩니다.|  
|[CMFCHeaderCtrl::OnFillBackground](../Topic/CMFCHeaderCtrl::OnFillBackground.md)|열 머리글 컨트롤의 배경을 채우는 데 프레임 워크에서 호출 됩니다.|  
  
## 예제  
 다음 예제에서는 개체를 생성 하는 방법을 보여 줍니다.는 `CMFCHeaderCtrl` 클래스 및 사용 방법  *여러 열 정렬* 현재 머리글 컨트롤 모드.  
  
 [!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/CPP/cmfcheaderctrl-class_1.cpp)]  
  
## 설명  
 `CMFCHeaderCtrl` 클래스는 정렬 된 열을 나타내려면 머리글 컨트롤 열에 정렬 화살표를 그립니다.  사용  *여러 열 정렬* 부모 목록 컨트롤에서 열 집합 경우 모드 \([CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)\) 동시에 정렬할 수 있습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)  
  
 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxheaderctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)