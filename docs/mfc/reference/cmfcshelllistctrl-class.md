---
title: "CMFCShellListCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCShellListCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellListCtrl class"
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCShellListCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCShellListCtrl` 클래스 Windows 목록 컨트롤 기능을 제공 하 고 셸 항목 목록을 표시 하는 기능을 포함 하 여 확장 됩니다.  
  
## 구문  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCShellListCtrl::DisplayFolder](../Topic/CMFCShellListCtrl::DisplayFolder.md)|제공 된 폴더에 포함 된 항목의 목록을 표시 합니다.|  
|[CMFCShellListCtrl::DisplayParentFolder](../Topic/CMFCShellListCtrl::DisplayParentFolder.md)|현재 표시 된 폴더의 부모 폴더에 포함 된 항목의 목록을 표시 합니다.|  
|[CMFCShellListCtrl::EnableShellContextMenu](../Topic/CMFCShellListCtrl::EnableShellContextMenu.md)|바로 가기 메뉴를 사용할 수 있거나.|  
|[CMFCShellListCtrl::GetCurrentFolder](../Topic/CMFCShellListCtrl::GetCurrentFolder.md)|현재 폴더의 경로 검색합니다.|  
|[CMFCShellListCtrl::GetCurrentFolderName](../Topic/CMFCShellListCtrl::GetCurrentFolderName.md)|현재 폴더의 이름을 검색합니다.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](../Topic/CMFCShellListCtrl::GetCurrentItemIdList.md)|PIDL 현재 list 컨트롤 항목을 반환합니다.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](../Topic/CMFCShellListCtrl::GetCurrentShellFolder.md)|현재 셸 폴더에 대 한 포인터를 반환합니다.|  
|[CMFCShellListCtrl::GetItemPath](../Topic/CMFCShellListCtrl::GetItemPath.md)|텍스트 항목의 경로 반환합니다.|  
|[CMFCShellListCtrl::GetItemTypes](../Topic/CMFCShellListCtrl::GetItemTypes.md)|목록 컨트롤이 표시 하는 셸 항목 형식을 반환 합니다.|  
|[CMFCShellListCtrl::IsDesktop](../Topic/CMFCShellListCtrl::IsDesktop.md)|현재 선택한 폴더를 바탕 화면 폴더에 있는지 확인 합니다.|  
|[CMFCShellListCtrl::OnCompareItems](../Topic/CMFCShellListCtrl::OnCompareItems.md)|두 항목을 비교 하면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCListCtrl::OnCompareItems](../Topic/CMFCListCtrl::OnCompareItems.md).\)|  
|[CMFCShellListCtrl::OnFormatFileDate](../Topic/CMFCShellListCtrl::OnFormatFileDate.md)|프레임 워크 목록 컨트롤에 표시 되는 파일 날짜를 검색 하는 경우 호출 됩니다.|  
|[CMFCShellListCtrl::OnFormatFileSize](../Topic/CMFCShellListCtrl::OnFormatFileSize.md)|프레임 워크 파일 목록 컨트롤의 크기를 변환 하는 경우 호출 됩니다.|  
|[CMFCShellListCtrl::OnGetItemIcon](../Topic/CMFCShellListCtrl::OnGetItemIcon.md)|프레임 워크 목록 컨트롤 항목의 아이콘을 검색 하는 경우 호출 됩니다.|  
|[CMFCShellListCtrl::OnGetItemText](../Topic/CMFCShellListCtrl::OnGetItemText.md)|프레임 워크는 컨트롤 목록 항목의 텍스트를 변환 하는 경우 호출 됩니다.|  
|[CMFCShellListCtrl::OnSetColumns](../Topic/CMFCShellListCtrl::OnSetColumns.md)|이 열의 이름을 설정 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCShellListCtrl::Refresh](../Topic/CMFCShellListCtrl::Refresh.md)|새로 고쳐지고 목록 컨트롤을 다시 그립니다.|  
|[CMFCShellListCtrl::SetItemTypes](../Topic/CMFCShellListCtrl::SetItemTypes.md)|목록 컨트롤에 표시 되는 항목의 형식을 설정 합니다.|  
  
## 설명  
 `CMFCShellListCtrl` 클래스의 기능을 확장 하는 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md) Windows 셸 항목 목록에 프로그램을 사용 하 여.  표시 형식을 사용 하는 탐색기 창에는 목록 보기의 같은입니다.  
  
 A  [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) 개체를 관련 된는 `CMFCShellListCtrl` 완전 탐색기 창을 만들 수 있는 개체입니다.  다음 항목을 선택 하는 `CMFCShellTreeCtrl` 발생 합니다의 `CMFCShellListCtrl` 개체에서 선택한 항목의 내용을 나열 합니다.  
  
## 예제  
 다음 예제에서는 개체를 만드는 방법을 보여 줍니다.을 `CMFCShellListCtrl` 클래스 및 현재 표시 된 폴더의 부모 폴더를 표시 하는 방법.  이 코드 조각에 속해 있는  [탐색기 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/CPP/cmfcshelllistctrl-class_3.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxshelllistCtrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl Class](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)