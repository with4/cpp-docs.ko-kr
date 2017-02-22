---
title: "CDockablePaneAdapter Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDockablePaneAdapter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDockablePaneAdapter class"
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDockablePaneAdapter Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CWnd` 파생 창에 대해 도킹 지원을 제공합니다.  
  
## 구문  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CDockablePaneAdapter::GetWrappedWnd](../Topic/CDockablePaneAdapter::GetWrappedWnd.md)|래핑된 창을 반환합니다.|  
|[CDockablePaneAdapter::LoadState](../Topic/CDockablePaneAdapter::LoadState.md)|\([CDockablePane::LoadState](http://msdn.microsoft.com/ko-kr/96110136-4f46-4764-8a76-3b4abaf77917) 재정의\)|  
|[CDockablePaneAdapter::SaveState](../Topic/CDockablePaneAdapter::SaveState.md)|\([CDockablePane::SaveState](http://msdn.microsoft.com/ko-kr/c5c24249-8d0d-46cb-96d9-9f5c6dc191db) 재정의\)|  
|[CDockablePaneAdapter::SetWrappedWnd](../Topic/CDockablePaneAdapter::SetWrappedWnd.md)||  
  
## 설명  
 [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) 또는 [CMFCBaseTabCtrl::InsertTab](../Topic/CMFCBaseTabCtrl::InsertTab.md) 메서드를 사용하는 경우 일반적으로 프레임워크에서 이 클래스의 개체를 인스턴스화합니다.  
  
 `CDockablePaneAdapter` 동작을 사용자 지정하려면 새 클래스를 파생하고 [CMFCBaseTabCtrl::SetDockingBarWrapperRTC](../Topic/CMFCBaseTabCtrl::SetDockingBarWrapperRTC.md)를 사용하여 런타임 클래스 정보를 탭 창으로 설정하기만 하면 됩니다.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## 요구 사항  
 **헤더:** afxDockablePaneAdapter.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)