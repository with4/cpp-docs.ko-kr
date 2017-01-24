---
title: "CMFCAutoHideBar Class | Microsoft Docs"
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
  - "CMFCAutoHideBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideToolBar class"
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAutoHideBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCAutoHideBar` 클래스는 자동 숨기기 기능을 구현하는 특수 도구 모음 클래스입니다.  
  
## 구문  
  
```  
class CMFCAutoHideBar : public CPane  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCAutoHideBar::CMFCAutoHideBar](../Topic/CMFCAutoHideBar::CMFCAutoHideBar.md)||  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCAutoHideBar::AddAutoHideWindow](../Topic/CMFCAutoHideBar::AddAutoHideWindow.md)||  
|[CMFCAutoHideBar::AllowShowOnPaneMenu](../Topic/CMFCAutoHideBar::AllowShowOnPaneMenu.md)|\(`CPane::AllowShowOnPaneMenu`를 재정의합니다.\)|  
|[CMFCAutoHideBar::CalcFixedLayout](../Topic/CMFCAutoHideBar::CalcFixedLayout.md)|\([CBasePane::CalcFixedLayout](../Topic/CBasePane::CalcFixedLayout.md) 재정의\)|  
|[CMFCAutoHideBar::Create](../Topic/CMFCAutoHideBar::Create.md)|컨트롤 막대를 만들고 [CPane](../../mfc/reference/cpane-class.md) 개체에 연결합니다.  \([CPane::Create](../Topic/CPane::Create.md) 재정의\)|  
|[CMFCAutoHideBar::GetFirstAHWindow](../Topic/CMFCAutoHideBar::GetFirstAHWindow.md)||  
|[CMFCAutoHideBar::GetVisibleCount](../Topic/CMFCAutoHideBar::GetVisibleCount.md)||  
|[CMFCAutoHideBar::OnShowControlBarMenu](../Topic/CMFCAutoHideBar::OnShowControlBarMenu.md)|특수 창 메뉴를 표시하려고 할 때 프레임워크에서 호출됩니다.  \([CPane::OnShowControlBarMenu](../Topic/CPane::OnShowControlBarMenu.md) 재정의\)|  
|[CMFCAutoHideBar::RemoveAutoHideWindow](../Topic/CMFCAutoHideBar::RemoveAutoHideWindow.md)||  
|[CMFCAutoHideBar::SetActiveInGroup](../Topic/CMFCAutoHideBar::SetActiveInGroup.md)|\([CPane::SetActiveInGroup](../Topic/CPane::SetActiveInGroup.md) 재정의\)|  
|[CMFCAutoHideBar::SetRecentVisibleState](../Topic/CMFCAutoHideBar::SetRecentVisibleState.md)||  
|[CMFCAutoHideBar::ShowAutoHideWindow](../Topic/CMFCAutoHideBar::ShowAutoHideWindow.md)||  
|[CMFCAutoHideBar::StretchPane](../Topic/CMFCAutoHideBar::StretchPane.md)|창을 가로 또는 세로로 확장합니다.  \([CBasePane::StretchPane](../Topic/CBasePane::StretchPane.md) 재정의\)|  
|[CMFCAutoHideBar::UnSetAutoHideMode](../Topic/CMFCAutoHideBar::UnSetAutoHideMode.md)||  
|[CMFCAutoHideBar::UpdateVisibleState](../Topic/CMFCAutoHideBar::UpdateVisibleState.md)||  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CMFCAutoHideBar::m\_nShowAHWndDelay](../Topic/CMFCAutoHideBar::m_nShowAHWndDelay.md)|사용자가 [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md) 위에 마우스 커서를 놓은 순간과 프레임워크에 연결된 창이 표시되는 순간 사이의 시간 지연입니다.|  
  
## 설명  
 사용자가 도킹 창을 자동 숨기기 모드로 전환하면 프레임워크에서 자동으로 `CMFCAutoHideBar` 개체를 만듭니다.  또한 필요한 [CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md) 및 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md) 개체도 만듭니다.  각 `CAutoHideDockSite` 개체는 개별 `CMFCAutoHideButton`에 연결됩니다.  
  
 `CMFCAutoHideBar` 클래스는 사용자의 마우스로 `CMFCAutoHideButton`을 가리킬 때 `CAutoHideDockSite`의 표시를 구현합니다.  도구 모음에서 WM\_MOUSEMOVE 메시지를 받으면 `CMFCAutoHideBar`에서 타이머를 시작합니다.  타이머가 완료되면 도구 모음에 WM\_TIMER 이벤트 알림을 보냅니다.  도구 모음은 마우스 포인터가 타이머가 시작될 때 배치되었던 것과 동일한 자동 숨기기 단추에 배치되었는지 확인하여 이 이벤트를 처리합니다.  그럴 경우 연결된 `CAutoHideDockSite`가 표시됩니다.  
  
 `m_nShowAHWndDelay`를 설정하여 타이머의 지연 길이를 제어할 수 있습니다.  기본값은 400ms입니다.  
  
## 예제  
 다음 예제에서는 `CMFCAutoHideBar` 개체를 생성하고 해당 `GetDockSiteRow` 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/CPP/cmfcautohidebar-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)  
  
## 요구 사항  
 **헤더:** afxautohidebar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CAutoHideDockSite Class](../../mfc/reference/cautohidedocksite-class.md)   
 [CMFCAutoHideButton Class](../../mfc/reference/cmfcautohidebutton-class.md)