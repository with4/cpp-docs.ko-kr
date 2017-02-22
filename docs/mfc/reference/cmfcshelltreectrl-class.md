---
title: "CMFCShellTreeCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCShellTreeCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCShellTreeCtrl class"
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCShellTreeCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCShellTreeCtrl` 클래스를 확장 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md) 셸 항목의 계층 구조를 표시 하는 기능입니다.  
  
## 구문  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](../Topic/CMFCShellTreeCtrl::EnableShellContextMenu.md)|바로 가기 메뉴를 사용할 수 있거나.|  
|[CMFCShellTreeCtrl::GetFlags](../Topic/CMFCShellTreeCtrl::GetFlags.md)|전달 되는 플래그의 조합을 반환 합니다.  [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
|[CMFCShellTreeCtrl::GetItemPath](../Topic/CMFCShellTreeCtrl::GetItemPath.md)|항목의 경로 검색합니다.|  
|[CMFCShellTreeCtrl::GetRelatedList](../Topic/CMFCShellTreeCtrl::GetRelatedList.md)|반환에 대 한 포인터는 [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md) 개체와 함께 사용 됩니다 `CMFCShellTreeCtrl` 는 탐색기와 유사한 창을 만들려면 개체.|  
|[CMFCShellTreeCtrl::OnChildNotify](../Topic/CMFCShellTreeCtrl::OnChildNotify.md)|이 창에 적용 되는 알림 메시지를 받을 때이 멤버 함수가이 창의 부모 창에서 호출 됩니다.  \(재정의 [CWnd::OnChildNotify](../Topic/CWnd::OnChildNotify.md).\)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](../Topic/CMFCShellTreeCtrl::OnGetItemIcon.md)||  
|[CMFCShellTreeCtrl::OnGetItemText](../Topic/CMFCShellTreeCtrl::OnGetItemText.md)||  
|[CMFCShellTreeCtrl::Refresh](../Topic/CMFCShellTreeCtrl::Refresh.md)|새로 고치고 다시 현재 `CMFCShellTreeCtrl` 개체입니다.|  
|[CMFCShellTreeCtrl::SelectPath](../Topic/CMFCShellTreeCtrl::SelectPath.md)|제공 된 PIDL 또는 문자열 경로에 따라 적절 한 트리 컨트롤 항목을 선택 합니다.|  
|[CMFCShellTreeCtrl::SetFlags](../Topic/CMFCShellTreeCtrl::SetFlags.md)|트리 컨텍스트를 필터링 하는 플래그를 설정 \(사용 플래그와 마찬가지로 `IShellFolder::EnumObjects`\).|  
|[CMFCShellTreeCtrl::SetRelatedList](../Topic/CMFCShellTreeCtrl::SetRelatedList.md)|현재 사이 관계를 설정 합니다. `CMFCShellTreeCtrl` 개체와 `CMFCShellListCtrl` 개체입니다.|  
  
## 설명  
 이 클래스의 확장은 `CTreeCtrl` 트리에서 Windows 셸 항목을 포함 하 여 프로그램을 사용 하 여 클래스.  이 클래스에 연결할 수 있는 `CMFCShellListCtrl` 개체 전체 탐색기 창을 만들 수 있습니다.  그런 다음 트리에서 항목을 선택 합니다. Windows 셸 항목 목록을 연결 된 목록에 표시 됩니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md)  
  
## 요구 사항  
 **헤더:** afxshelltreeCtrl.h  
  
## 예제  
 다음 예제에서는 개체를 만드는 방법을 보여 줍니다.을 `CMFCShellTreeCtrl` 클래스입니다.  이 코드 조각에 속해 있는  [탐색기 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/CPP/cmfcshelltreectrl-class_2.cpp)]  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl Class](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl Class](../../mfc/reference/cmfcshelllistctrl-class.md)