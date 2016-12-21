---
title: "CTabbedPane Class | Microsoft Docs"
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
  - "CTabbedPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabbedPane class"
ms.assetid: f4dc5215-b789-4f2d-8c62-477aceda3578
caps.latest.revision: 27
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTabbedPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

분리 가능한 탭이 포함된 창의 기능을 구현합니다.  
  
## 구문  
  
```  
class CTabbedPane : public CBaseTabbedPane  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CTabbedPane::CTabbedPane`|기본 생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CTabbedPane::DetachPane](../Topic/CTabbedPane::DetachPane.md)|\([CBaseTabbedPane::DetachPane](../Topic/CBaseTabbedPane::DetachPane.md)을 재정의합니다.\)|  
|[CTabbedPane::EnableTabAutoColor](../Topic/CTabbedPane::EnableTabAutoColor.md)|탭의 자동 색 지정을 사용하거나 사용하지 않도록 설정합니다.|  
|[CTabbedPane::FloatTab](../Topic/CTabbedPane::FloatTab.md)|창이 현재 분리 가능한 탭에 있는 경우에만 창을 부동합니다.  \([CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md)을 재정의합니다.\)|  
|[CTabbedPane::GetTabArea](../Topic/CTabbedPane::GetTabArea.md)|탭 창 내 탭 영역의 크기와 위치를 반환합니다.|  
|[CTabbedPane::GetTabWnd](../Topic/CTabbedPane::GetTabWnd.md)||  
|[CTabbedPane::HasAutoHideMode](../Topic/CTabbedPane::HasAutoHideMode.md)|탭 창을 자동 숨기기 모드로 전환할 수 있는지 여부를 결정합니다.  \([CBaseTabbedPane::HasAutoHideMode](../Topic/CBaseTabbedPane::HasAutoHideMode.md)를 재정의합니다.\)|  
|[CTabbedPane::IsTabLocationBottom](../Topic/CTabbedPane::IsTabLocationBottom.md)|탭이 창의 맨 아래에 있는지 여부를 결정합니다.|  
|[CTabbedPane::ResetTabs](../Topic/CTabbedPane::ResetTabs.md)|모든 탭 창을 기본 상태로 다시 설정합니다.|  
|[CTabbedPane::SetTabAutoColors](../Topic/CTabbedPane::SetTabAutoColors.md)|자동 색 기능이 사용되는 경우 사용할 수 있는 사용자 지정 색 목록을 설정합니다.|  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CTabbedPane::m\_bTabsAlwaysTop](../Topic/CTabbedPane::m_bTabsAlwaysTop.md)|응용 프로그램에서 탭의 기본 위치입니다.|  
|[CTabbedPane::m\_pTabWndRTC](../Topic/CTabbedPane::m_pTabWndRTC.md)|사용자 지정 `CMFCTabCtrl` 파생 개체에 대한 런타임 클래스 정보입니다.|  
  
## 설명  
 사용자가 두 번째 창의 캡션을 가리켜서 한 창을 다른 창에 연결하는 경우 프레임워크에서 자동으로 이 클래스의 인스턴스를 만듭니다.  프레임워크에서 만든 모든 탭 창의 ID는 \-1입니다.  
  
 Outlook 스타일 탭 대신 일반 탭을 지정하려면 `AFX_CBRS_REGULAR_TABS` 스타일을 [CDockablePane::CreateEx](../Topic/CDockablePane::CreateEx.md) 메서드에 전달합니다.  
  
 분리 가능한 탭을 포함하는 탭 창을 만드는 경우 프레임워크에서 자동으로 창을 삭제할 수 있으므로 포인터를 저장하면 안 됩니다.  탭 창에 대한 포인터를 가져오려면 `CBasePane::GetParentTabbedPane` 메서드를 호출합니다.  
  
## 예제  
 이 예제에서는 `CTabbedPane` 개체를 만듭니다.  다음에는 [CBaseTabbedPane::AddTab](../Topic/CBaseTabbedPane::AddTab.md)을 사용하여 추가 탭을 연결합니다.  
  
```  
CTabbedPane* pTabbededBar = new CTabbedPane (TRUE);  
if (!pTabbededBar->Create (_T(""), this, CRect (0, 0, 200, 200),  
                           TRUE,   
                           (UINT) -1,  
                           WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS |  
                           WS_CLIPCHILDREN | CBRS_LEFT |    
                           CBRS_FLOAT_MULTI))  
{  
    TRACE0("Failed to create Solution Explorer bar\n");  
    return FALSE;      // fail to create  
}  
  
pTabbededBar->AddTab (&m_wndClassView);  
pTabbededBar->AddTab (&m_wndResourceView);  
pTabbededBar->AddTab (&m_wndFileView);  
pTabbededBar->EnableDocking(CBRS_ALIGN_ANY);  
DockPane(pTabbededBar);  
```  
  
## 예제  
 탭 컨트롤 막대 개체를 만드는 또 다른 방법은 [CDockablePane::AttachToTabWnd](../Topic/CDockablePane::AttachToTabWnd.md)를 사용하는 것입니다.  `AttachToTabWnd` 메서드는 [CDockablePane::SetTabbedPaneRTC](../Topic/CDockablePane::SetTabbedPaneRTC.md)에 의해 설정된 런타임 클래스 정보를 사용하여 탭 창 개체를 동적으로 만듭니다.  
  
 이 예제에서는 탭 창을 동적으로 만들고 두 탭을 연결한 다음 두 번째 탭을 분리 불가능하게 만듭니다.  
  
```  
DockPane(&m_wndClassView);  
CTabbedPane* pTabbedBar = NULL;  
m_wndResourceView.AttachToTabWnd (&m_wndClassView, DM_SHOW, TRUE,  
                                  (CDockablePane**) &pTabbedBar);  
m_wndFileView.AttachToTabWnd (pTabbedBar, DM_SHOW, TRUE,  
                              (CDockablePane**) &pTabbedBar);  
pTabbedBar->GetUnderlyingWindow ()->EnableTabDetach (1, FALSE);  
```  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CTabbedPane](../../mfc/reference/ctabbedpane-class.md)  
  
## 요구 사항  
 **헤더:** afxTabbedPane.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md)   
 [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBar 클래스](../../mfc/reference/cmfcoutlookbar-class.md)