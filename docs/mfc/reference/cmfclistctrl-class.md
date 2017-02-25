---
title: "CMFCListCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCListCtrl class"
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCListCtrl` 클래스의 기능을 확장 [CListCtrl Class](../../mfc/reference/clistctrl-class.md) 에서 고급 헤더 컨트롤 기능을 지 원하는 클래스는 [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md).  
  
## 구문  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCListCtrl::EnableMarkSortedColumn](../Topic/CMFCListCtrl::EnableMarkSortedColumn.md)|정렬 된 열에 다른 배경색을 표시할 수가 있습니다.|  
|[CMFCListCtrl::EnableMultipleSort](../Topic/CMFCListCtrl::EnableMultipleSort.md)|여러 정렬 모드를 사용할 수 있습니다.|  
|[CMFCListCtrl::GetHeaderCtrl](../Topic/CMFCListCtrl::GetHeaderCtrl.md)|밑줄이 그어진된 머리글 컨트롤에 대 한 참조를 반환합니다.|  
|[CMFCListCtrl::IsMultipleSort](../Topic/CMFCListCtrl::IsMultipleSort.md)|목록 컨트롤에서 다중 정렬 모드 인지를 확인 합니다.|  
|[CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md)|목록 컨트롤 항목 두 개를 비교 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCListCtrl::OnGetCellBkColor](../Topic/CMFCListCtrl::OnGetCellBkColor.md)|개별 셀의 배경색을 결정 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCListCtrl::OnGetCellFont](../Topic/CMFCListCtrl::OnGetCellFont.md)|그리고 셀 글꼴 필요한 때는 프레임 워크에서 호출 됩니다.|  
|[CMFCListCtrl::OnGetCellTextColor](../Topic/CMFCListCtrl::OnGetCellTextColor.md)|개별 셀의 텍스트 색을 결정 해야 하는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCListCtrl::RemoveSortColumn](../Topic/CMFCListCtrl::RemoveSortColumn.md)|정렬 열은 정렬 된 열 목록에서 제거합니다.|  
|[CMFCListCtrl::SetSortColumn](../Topic/CMFCListCtrl::SetSortColumn.md)|현재 정렬된 열과 정렬 순서를 설정합니다.|  
|[CMFCListCtrl::Sort](../Topic/CMFCListCtrl::Sort.md)|목록 컨트롤을 정렬합니다.|  
  
## 설명  
 `CMFCListCtrl`두 가지 고급 기능을 제공 [CListCtrl Class](../../mfc/reference/clistctrl-class.md) 클래스입니다.  첫째, 열 정렬 옵션을 자동으로 정렬 화살표가 머리글을 그려서 임을 나타냅니다.  둘째, 동시에 여러 개의 열에 정렬 된 데이터를 지원 합니다.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCListCtrl` 클래스입니다.  목록 컨트롤을 만드는, 열 삽입, 항목 삽입 텍스트 항목의 설정 및 목록 컨트롤의 글꼴을 설정 하는 방법의 예제를 보여 줍니다.  이 코드 조각에 속해 있는  [Visual Studio 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/CPP/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/CPP/cmfclistctrl-class_2.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxlistctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CListCtrl Class](../../mfc/reference/clistctrl-class.md)