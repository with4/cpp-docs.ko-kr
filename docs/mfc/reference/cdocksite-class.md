---
title: "CDockSite Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockSite class"
ms.assetid: 0fcfff79-5f50-4281-b2de-a55653bbea40
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CDockSite Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 [CPane Class](../../mfc/reference/cpane-class.md)에서 파생되는 창을 행 집합으로 배열하기 위한 기능을 제공합니다.  
  
## 구문  
  
```  
class CDockSite: public CBasePane  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CDockSite::AddRow](../Topic/CDockSite::AddRow.md)||  
|[CDockSite::AdjustDockingLayout](../Topic/CDockSite::AdjustDockingLayout.md)|\([CBasePane::AdjustDockingLayout](../Topic/CBasePane::AdjustDockingLayout.md) 재정의\)|  
|[CDockSite::AdjustLayout](../Topic/CDockSite::AdjustLayout.md)|\([CBasePane::AdjustLayout](../Topic/CBasePane::AdjustLayout.md) 재정의\)|  
|[CDockSite::AlignDockSite](../Topic/CDockSite::AlignDockSite.md)||  
|[CDockSite::CalcFixedLayout](../Topic/CDockSite::CalcFixedLayout.md)|\([CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md) 재정의\)|  
|[CDockSite::CanAcceptPane](../Topic/CDockSite::CanAcceptPane.md)|\([CBasePane::CanAcceptPane](../Topic/CBasePane::CanAcceptPane.md) 재정의\)|  
|[CDockSite::CreateEx](../Topic/CDockSite::CreateEx.md)|\([CBasePane::CreateEx](../Topic/CBasePane::CreateEx.md) 재정의\)|  
|[CDockSite::CreateRow](../Topic/CDockSite::CreateRow.md)||  
|[CDockSite::DockPane](../Topic/CDockSite::DockPane.md)|\([CBasePane::DockPane](../Topic/CBasePane::DockPane.md) 재정의\)|  
|[CDockSite::DoesAllowDynInsertBefore](../Topic/CDockSite::DoesAllowDynInsertBefore.md)|\([CBasePane::DoesAllowDynInsertBefore](../Topic/CBasePane::DoesAllowDynInsertBefore.md) 재정의\)|  
|[CDockSite::FindRowIndex](../Topic/CDockSite::FindRowIndex.md)||  
|[CDockSite::FixupVirtualRects](../Topic/CDockSite::FixupVirtualRects.md)||  
|[CDockSite::GetDockSiteID](../Topic/CDockSite::GetDockSiteID.md)||  
|[CDockSite::GetDockSiteRowsList](../Topic/CDockSite::GetDockSiteRowsList.md)||  
|[CDockSite::IsAccessibilityCompatible](../Topic/CDockSite::IsAccessibilityCompatible.md)|\(`CBasePane::IsAccessibilityCompatible` 재정의\)|  
|[CDockSite::IsDragMode](../Topic/CDockSite::IsDragMode.md)||  
|[CDockSite::IsLastRow](../Topic/CDockSite::IsLastRow.md)||  
|[CDockSite::IsRectWithinDockSite](../Topic/CDockSite::IsRectWithinDockSite.md)||  
|[CDockSite::IsResizable](../Topic/CDockSite::IsResizable.md)|\([CBasePane::IsResizable](../Topic/CBasePane::IsResizable.md) 재정의\)|  
|[CDockSite::MovePane](../Topic/CDockSite::MovePane.md)||  
|[CDockSite::OnInsertRow](../Topic/CDockSite::OnInsertRow.md)||  
|[CDockSite::OnRemoveRow](../Topic/CDockSite::OnRemoveRow.md)||  
|[CDockSite::OnResizeRow](../Topic/CDockSite::OnResizeRow.md)||  
|[CDockSite::OnSetWindowPos](../Topic/CDockSite::OnSetWindowPos.md)||  
|[CDockSite::OnShowRow](../Topic/CDockSite::OnShowRow.md)||  
|[CDockSite::OnSizeParent](../Topic/CDockSite::OnSizeParent.md)||  
|[CDockSite::PaneFromPoint](../Topic/CDockSite::PaneFromPoint.md)|주어진 매개 변수로 지정된 지점에서 도킹 사이트에 도킹된 창을 반환합니다.|  
|[CDockSite::DockPaneLeftOf](../Topic/CDockSite::DockPaneLeftOf.md)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[CDockSite::FindPaneByID](../Topic/CDockSite::FindPaneByID.md)|지정된 ID로 식별되는 창을 반환합니다.|  
|[CDockSite::GetPaneList](../Topic/CDockSite::GetPaneList.md)|도킹 사이트에 도킹된 창 목록을 반환합니다.|  
|[CDockSite::RectSideFromPoint](../Topic/CDockSite::RectSideFromPoint.md)||  
|[CDockSite::RemovePane](../Topic/CDockSite::RemovePane.md)||  
|[CDockSite::RemoveRow](../Topic/CDockSite::RemoveRow.md)||  
|[CDockSite::ReplacePane](../Topic/CDockSite::ReplacePane.md)||  
|[CDockSite::RepositionPanes](../Topic/CDockSite::RepositionPanes.md)||  
|[CDockSite::ResizeDockSite](../Topic/CDockSite::ResizeDockSite.md)||  
|[CDockSite::ResizeRow](../Topic/CDockSite::ResizeRow.md)||  
|[CDockSite::ShowPane](../Topic/CDockSite::ShowPane.md)|창을 표시합니다.|  
|[CDockSite::ShowRow](../Topic/CDockSite::ShowRow.md)||  
|[CDockSite::SwapRows](../Topic/CDockSite::SwapRows.md)||  
  
## 설명  
 [CFrameWndEx::EnableDocking](../Topic/CFrameWndEx::EnableDocking.md)을 호출하면 프레임워크에서 `CDockSite` 개체를 자동으로 만듭니다.  도킹 사이트 창은 주 프레임 창에서 클라이언트 영역의 가장자리에 배치됩니다.  
  
 도킹 사이트에서 제공하는 서비스는 일반적으로 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)에서 처리하기 때문에 호출하지 않아도 됩니다.  
  
## 예제  
 다음 예제에서는 `CDockSite` 클래스의 개체를 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#27](../../mfc/reference/codesnippet/CPP/cdocksite-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CDockSite](../../mfc/reference/cdocksite-class.md)  
  
## 요구 사항  
 **헤더:** afxDockSite.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CBasePane Class](../../mfc/reference/cbasepane-class.md)