---
title: "COleIPFrameWndEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleIPFrameWndEx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleIPFrameWndEx class"
ms.assetid: ebff1560-a1eb-4854-af00-95d4a192bd55
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# COleIPFrameWndEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`COleIPFrameWndEx` 클래스는 MFC를 지원하는 OLE 컨테이너를 구현합니다. 응용 프로그램에 대한 현재 위치의 프레임 창 클래스는 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md) 클래스에서 파생하는 대신 `COleIPFrameWndEx` 클래스에서 파생해야 합니다.  
  
## 구문  
  
```  
class COleIPFrameWndEx : public COleIPFrameWnd  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[COleIPFrameWndEx::AddDockSite](../Topic/COleIPFrameWndEx::AddDockSite.md)||  
|[COleIPFrameWndEx::AddPane](../Topic/COleIPFrameWndEx::AddPane.md)||  
|[COleIPFrameWndEx::AdjustDockingLayout](../Topic/COleIPFrameWndEx::AdjustDockingLayout.md)||  
|[COleIPFrameWndEx::DockPane](../Topic/COleIPFrameWndEx::DockPane.md)||  
|[COleIPFrameWndEx::DockPaneLeftOf](../Topic/COleIPFrameWndEx::DockPaneLeftOf.md)|창을 다른 창의 왼쪽에 도킹합니다.|  
|[COleIPFrameWndEx::EnableAutoHidePanes](../Topic/COleIPFrameWndEx::EnableAutoHidePanes.md)||  
|[COleIPFrameWndEx::EnableDocking](../Topic/COleIPFrameWndEx::EnableDocking.md)||  
|[COleIPFrameWndEx::EnablePaneMenu](../Topic/COleIPFrameWndEx::EnablePaneMenu.md)||  
|[COleIPFrameWndEx::GetActivePopup](../Topic/COleIPFrameWndEx::GetActivePopup.md)|현재 표시된 팝업 메뉴에 대한 포인터를 반환합니다.|  
|[COleIPFrameWndEx::GetContainerFrameWindow](../Topic/COleIPFrameWndEx::GetContainerFrameWindow.md)||  
|[COleIPFrameWndEx::GetDefaultResId](../Topic/COleIPFrameWndEx::GetDefaultResId.md)|창이 로드될 때 지정한 프레임 창의 리소스 ID를 반환합니다.|  
|[COleIPFrameWndEx::GetDockFrame](../Topic/COleIPFrameWndEx::GetDockFrame.md)||  
|[COleIPFrameWndEx::GetDockingManager](../Topic/COleIPFrameWndEx::GetDockingManager.md)||  
|[COleIPFrameWndEx::GetMainFrame](../Topic/COleIPFrameWndEx::GetMainFrame.md)||  
|[COleIPFrameWndEx::GetMenuBar](../Topic/COleIPFrameWndEx::GetMenuBar.md)|프레임 창에 연결된 메뉴 모음 개체에 대한 포인터를 반환합니다.|  
|[COleIPFrameWndEx::GetPane](../Topic/COleIPFrameWndEx::GetPane.md)||  
|[COleIPFrameWndEx::GetTearOffBars](../Topic/COleIPFrameWndEx::GetTearOffBars.md)|분리 상태에 있는 창 개체의 목록을 반환합니다.|  
|[COleIPFrameWndEx::GetToolbarButtonToolTipText](../Topic/COleIPFrameWndEx::GetToolbarButtonToolTipText.md)|단추에 대한 도구 설명이 표시되기 전에 프레임워크에서 호출합니다.|  
|[COleIPFrameWndEx::InsertPane](../Topic/COleIPFrameWndEx::InsertPane.md)||  
|[COleIPFrameWndEx::IsMenuBarAvailable](../Topic/COleIPFrameWndEx::IsMenuBarAvailable.md)|메뉴 모음 개체에 대한 포인터가 `NULL`이 아닌지 여부를 확인합니다.|  
|[COleIPFrameWndEx::IsPointNearDockSite](../Topic/COleIPFrameWndEx::IsPointNearDockSite.md)||  
|[COleIPFrameWndEx::LoadFrame](../Topic/COleIPFrameWndEx::LoadFrame.md)|\(`COleIPFrameWnd::LoadFrame`을 재정의합니다.\)|  
|[COleIPFrameWndEx::OnCloseDockingPane](../Topic/COleIPFrameWndEx::OnCloseDockingPane.md)||  
|[COleIPFrameWndEx::OnCloseMiniFrame](../Topic/COleIPFrameWndEx::OnCloseMiniFrame.md)||  
|[COleIPFrameWndEx::OnClosePopupMenu](../Topic/COleIPFrameWndEx::OnClosePopupMenu.md)|활성 팝업 메뉴에서 WM\_DESTROY 메시지를 처리할 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnCmdMsg](../Topic/COleIPFrameWndEx::OnCmdMsg.md)|\(`CFrameWnd::OnCmdMsg`를 재정의합니다.\)|  
|[COleIPFrameWndEx::OnDrawMenuImage](../Topic/COleIPFrameWndEx::OnDrawMenuImage.md)|메뉴 항목과 연결된 이미지를 그릴 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnDrawMenuLogo](../Topic/COleIPFrameWndEx::OnDrawMenuLogo.md)|[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) 개체에서 WM\_PAINT 메시지를 처리할 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnMenuButtonToolHitTest](../Topic/COleIPFrameWndEx::OnMenuButtonToolHitTest.md)|[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md) 개체에서 WM\_NCHITTEST 메시지를 처리할 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnMoveMiniFrame](../Topic/COleIPFrameWndEx::OnMoveMiniFrame.md)||  
|[COleIPFrameWndEx::OnSetPreviewMode](../Topic/COleIPFrameWndEx::OnSetPreviewMode.md)|응용 프로그램의 주 프레임 창을 인쇄 미리 보기 모드 내부 및 외부로 설정하려면 이 멤버 함수를 호출합니다. \([CFrameWnd::OnSetPreviewMode](../Topic/CFrameWnd::OnSetPreviewMode.md)를 재정의합니다.\)|  
|[COleIPFrameWndEx::OnShowCustomizePane](../Topic/COleIPFrameWndEx::OnShowCustomizePane.md)||  
|[COleIPFrameWndEx::OnShowPanes](../Topic/COleIPFrameWndEx::OnShowPanes.md)||  
|[COleIPFrameWndEx::OnShowPopupMenu](../Topic/COleIPFrameWndEx::OnShowPopupMenu.md)|팝업 메뉴가 활성화될 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::OnTearOffMenu](../Topic/COleIPFrameWndEx::OnTearOffMenu.md)|분리 막대가 있는 메뉴가 활성화될 때 프레임워크에서 호출됩니다.|  
|[COleIPFrameWndEx::PaneFromPoint](../Topic/COleIPFrameWndEx::PaneFromPoint.md)||  
|[COleIPFrameWndEx::PreTranslateMessage](../Topic/COleIPFrameWndEx::PreTranslateMessage.md)|\(`COleIPFrameWnd::PreTranslateMessage`를 재정의합니다.\)|  
|[COleIPFrameWndEx::RecalcLayout](../Topic/COleIPFrameWndEx::RecalcLayout.md)|\(`COleIPFrameWnd::RecalcLayout`를 재정의합니다.\)|  
|[COleIPFrameWndEx::RemovePaneFromDockManager](../Topic/COleIPFrameWndEx::RemovePaneFromDockManager.md)||  
|[COleIPFrameWndEx::SetDockState](../Topic/COleIPFrameWndEx::SetDockState.md)|프레임 창에 속해 있는 창에 지정된 도킹 상태를 적용합니다.|  
|[COleIPFrameWndEx::SetupToolbarMenu](../Topic/COleIPFrameWndEx::SetupToolbarMenu.md)|더미 항목을 검색하고 지정된 사용자 정의 항목으로 대체하여 도구 모음 개체를 수정합니다.|  
|[COleIPFrameWndEx::ShowPane](../Topic/COleIPFrameWndEx::ShowPane.md)||  
|[COleIPFrameWndEx::WinHelp](../Topic/COleIPFrameWndEx::WinHelp.md)|WinHelp 응용 프로그램 또는 상황에 맞는 도움말을 시작하기 위해 프레임워크에서 호출됩니다.|  
  
### 보호된 메서드  
  
|이름|설명|  
|--------|--------|  
|[COleIPFrameWndEx::InitUserToobars](../Topic/COleIPFrameWndEx::InitUserToobars.md)|사용자 정의 도구 모음에 할당되는 컨트롤 ID의 범위를 초기화하도록 프레임워크에 지시합니다.|  
  
## 예제  
 다음 예제에서는 `COleIPFrameWndEx` 클래스의 인스턴스를 하위 클래스로 지정하고 해당 메서드를 재정의하는 방법을 보여 줍니다. 이 예제에서는 `OnDestory` 메서드, `RepositionFrame` 메서드, `RecalcLayout` 메서드 및 `CalcWindowRect` 메서드를 재정의하는 방법을 보여 줍니다. 이 코드 조각은 [워드 패드 샘플](../../top/visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_WordPad#1](../../mfc/reference/codesnippet/CPP/coleipframewndex-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [COleIPFrameWnd](../../mfc/reference/coleipframewnd-class.md)  
  
 [COleIPFrameWndEx](../../mfc/reference/coleipframewndex-class.md)  
  
## 요구 사항  
 **헤더:** afxoleipframewndex.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CFrameWndEx Class](../../mfc/reference/cframewndex-class.md)   
 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)