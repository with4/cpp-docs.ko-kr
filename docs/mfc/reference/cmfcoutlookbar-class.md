---
title: "CMFCOutlookBar 클래스 | Microsoft Docs"
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
  - "CMFCOutlookBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCOutlookBar 클래스"
ms.assetid: 2b335f71-ce99-4efd-b103-e65ba43ffc36
caps.latest.revision: 34
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCOutlookBar 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

탭된 창에 표시 되는 모양 있는  **탐색 창** Microsoft Outlook 2000 또는 Outlook 2003에서.  `CMFCOutlookBar` 개체가 포함 된 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md) 개체와 일련의 탭.  탭 수 있습니다 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) 개체 또는 `CWnd`\-파생 개체입니다.  사용자에 게 Outlook 표시줄 일련의 단추와 표시 영역으로 표시 됩니다.  사용자가 단추를 클릭할 때 해당 컨트롤 또는 창 단추에 표시 됩니다.  
  
## 구문  
  
```  
class CMFCOutlookBar : public CBaseTabbedPane  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CMFCOutlookBar::CMFCOutlookBar`|기본 생성자입니다.|  
|`CMFCOutlookBar::~CMFCOutlookBar`|소멸자.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCOutlookBar::AllowDestroyEmptyTabbedPane](../Topic/CMFCOutlookBar::AllowDestroyEmptyTabbedPane.md)|탭된, 빈 창이 소멸 될 수 있는지 여부를 지정 합니다.  \(재정의 [CBaseTabbedPane::AllowDestroyEmptyTabbedPane](../Topic/CBaseTabbedPane::AllowDestroyEmptyTabbedPane.md).\)|  
|[CMFCOutlookBar::CanAcceptPane](../Topic/CMFCOutlookBar::CanAcceptPane.md)|다른 창 Outlook 표시줄 창에 도킹 될 수 있는지 여부를 결정 합니다.  \(CDockablePane::CanAcceptPane 무시 합니다.\)|  
|[CMFCOutlookBar::CanSetCaptionTextToTabName](../Topic/CMFCOutlookBar::CanSetCaptionTextToTabName.md)|탭된 창에 대 한 캡션 같은 텍스트를 활성 탭으로 표시 되는지 여부를 결정 합니다.  \(재정의 [CBaseTabbedPane::CanSetCaptionTextToTabName](../Topic/CBaseTabbedPane::CanSetCaptionTextToTabName.md).\)|  
|[CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md)|Outlook bar 컨트롤을 만듭니다.|  
|[CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md)|사용자 지정 Outlook 표시줄 탭을 만듭니다.|  
|`CMFCOutlookBar::CreateObject`|프레임 워크에 의해 이와 같은 클래스의 동적 인스턴스를 만드는 데 사용 합니다.|  
|[CMFCOutlookBar::DoesAllowDynInsertBefore](../Topic/CMFCOutlookBar::DoesAllowDynInsertBefore.md)|사용자 컨트롤 막대 Outlook 표시줄의 외부 가장자리에 고정할 수 있는지 여부를 결정 합니다.|  
|[CMFCOutlookBar::FloatTab](../Topic/CMFCOutlookBar::FloatTab.md)|분리 탭에서 현재 창 있으면만 창을 입력판이 놓입니다.  \(재정의 [CBaseTabbedPane::FloatTab](../Topic/CBaseTabbedPane::FloatTab.md).\)|  
|[CMFCOutlookBar::GetButtonsFont](../Topic/CMFCOutlookBar::GetButtonsFont.md)|Outlook 표시줄에 있는 단추는 텍스트의 글꼴을 반환합니다.|  
|[CMFCOutlookBar::GetTabArea](../Topic/CMFCOutlookBar::GetTabArea.md)|Outlook 표시줄에서 크기 및 위치 탭 영역을 반환합니다.  \(재정의 [CBaseTabbedPane::GetTabArea](../Topic/CBaseTabbedPane::GetTabArea.md).\)|  
|`CMFCOutlookBar::GetThisClass`|프레임 워크에 의해에 대 한 포인터를 가져오는 데 사용 된  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMFCOutlookBar::IsMode2003](../Topic/CMFCOutlookBar::IsMode2003.md)|\(설명 참조\) Microsoft Office Outlook 2003은 Outlook 표시줄의 동작을 모방 여부를 결정 합니다.|  
|[CMFCOutlookBar::OnAfterAnimation](../Topic/CMFCOutlookBar::OnAfterAnimation.md)|호출 하 [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) 활성 탭에서 애니메이션을 사용 하 여 설정한 후.|  
|[CMFCOutlookBar::OnBeforeAnimation](../Topic/CMFCOutlookBar::OnBeforeAnimation.md)|호출 하 [CMFCOutlookBarTabCtrl::SetActiveTab](../Topic/CMFCOutlookBarTabCtrl::SetActiveTab.md) 앞에 탭 페이지 애니메이션을 사용 하 여 현재 탭으로 설정 됩니다.|  
|[CMFCOutlookBar::OnScroll](../Topic/CMFCOutlookBar::OnScroll.md)|Outlook 표시줄 위나 아래로 스크롤 하는 경우 프레임 워크에 의해 호출 됩니다.|  
|[CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md)|사용자 지정 Outlook 표시줄 탭을 제거합니다.|  
|[CMFCOutlookBar::SetButtonsFont](../Topic/CMFCOutlookBar::SetButtonsFont.md)|Outlook 표시줄에 있는 단추는 텍스트의 글꼴을 설정합니다.|  
|[CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md)|Outlook 표시줄의 동작을 Outlook 2003 \(설명 참조\)의 모방 여부를 지정 합니다.|  
  
## 설명  
 Outlook 표시줄의 예는  [OutlookDemo 샘플: MFC OutlookDemo 응용 프로그램](../../top/visual-cpp-samples.md).  
  
## Outlook 표시줄을 구현합니다.  
 사용 하는 `CMFCOutlookBar` 응용 프로그램의 컨트롤에서 다음이 단계를 따르십시오:  
  
1.  포함 된 `CMFCOutlookBar` 주 프레임 창 클래스에 대 한 개체.  
  
    ```  
    class CMainFrame : public CMDIFrameWnd  
     { ...  
         CMFCOutlookBar         m_wndOutlookBar;  
         CMFCOutlookBarPane     m_wndOutlookPane;  
    ... };  
    ```  
  
2.  처리할 때의 `WM_CREATE` 메시지가 주 프레임에서 호출 된 [CMFCOutlookBar::Create](../Topic/CMFCOutlookBar::Create.md) Outlook 표시줄 탭 컨트롤을 만드는 방법을.  
  
    ```  
    m_wndOutlookBar.Create (_T("Shortcuts"), this, CRect (0, 0, 100, 100), ID_VIEW_OUTLOOKBAR, WS_CHILD | WS_VISIBLE | CBRS_LEFT);  
    ```  
  
3.  내부에 대 한 포인터를 가져오는 `CMFCOutlookBarTabCtrl` 를 사용 하 여 [CBaseTabbedPane::GetUnderlyingWindow](../Topic/CBaseTabbedPane::GetUnderlyingWindow.md).  
  
    ```  
    CMFCOutlookBarTabCtrl* pOutlookBar = (CMFCOutlookBarTabCtrl*) m_wndOutlookBar.GetUnderlyingWindow ();  
    ```  
  
4.  만들기는 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) 단추를 포함 하는 각 탭에 대 한 개체입니다.  
  
    ```  
    m_wndOutlookPane.Create (&m_wndOutlookBar, AFX_DEFAULT_TOOLBAR_STYLE, ID_OUTLOOK_PANE_GENERAL, AFX_CBRS_FLOAT | AFX_CBRS_RESIZE);  
    // make the Outlook pane detachable (enable docking)  
    m_wndOutlookPane.EnableDocking (CBRS_ALIGN_ANY);  
    // add buttons  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_MAINFRAME), "About", ID_APP_ABOUT);  
    m_wndOutlookPane.AddButton (theApp.LoadIcon (IDR_CUSTOM_OPEN_ICON), "Open", ID_FILE_OPEN);  
    ```  
  
5.  호출 [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) 각 새 탭을 추가 합니다.  설정 된 `bDetachable` 매개 변수를 `FALSE` 분리 되지 않은 페이지 수 있도록 합니다.  또는 사용 [CMFCOutlookBarTabCtrl::AddControl](../Topic/CMFCOutlookBarTabCtrl::AddControl.md) 분리 가능한 페이지를 추가 합니다.  
  
    ```  
    pOutlookBar->AddTab (&m_wndOutlookPane, "General", (UINT) -1, TRUE);   
    ```  
  
6.  추가 하는 `CWnd`\-파생 컨트롤 \(예를 들어, [CMFCShellTreeCtrl Class](../../mfc/reference/cmfcshelltreectrl-class.md)\) 제어 및 호출으로 탭을 만들 [CMFCBaseTabCtrl::AddTab](../Topic/CMFCBaseTabCtrl::AddTab.md) Outlook 표시줄에 추가 합니다.  
  
> [!NOTE]
>  각각에 대해 고유 컨트롤 Id를 사용 해야 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md) 개체 및 각 `CWnd`\-파생 개체입니다.  
  
 동적으로 추가 하거나 런타임에 새 페이지를 삭제 하려면 사용 [CMFCOutlookBar::CreateCustomPage](../Topic/CMFCOutlookBar::CreateCustomPage.md) 및 [CMFCOutlookBar::RemoveCustomPage](../Topic/CMFCOutlookBar::RemoveCustomPage.md).  
  
## Outlook 2003 모드  
 Outlook 2003 모드에서 탭 단추 Outlook 표시줄 창 맨 아래에 배치 됩니다.  단추를 표시할 충분 한 공간이 없으면 도구 모음 같은 영역 창 아래쪽에 아이콘으로 표시 됩니다.  
  
 사용 [CMFCOutlookBar::SetMode2003](../Topic/CMFCOutlookBar::SetMode2003.md) 모드로 Outlook 2003을 사용 합니다.  사용 [CMFCOutlookBarTabCtrl::SetToolbarImageList](../Topic/CMFCOutlookBarTabCtrl::SetToolbarImageList.md) Outlook 표시줄 아래쪽에 표시 되는 아이콘이 포함 된 비트맵을 설정 합니다.  비트맵에서 아이콘 탭 인덱스가 정렬 되어야 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CBaseTabbedPane](../../mfc/reference/cbasetabbedpane-class.md)  
  
 [CMFCOutlookBar](../../mfc/reference/cmfcoutlookbar-class.md)  
  
## 요구 사항  
 **헤더:** afxoutlookbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CBaseTabbedPane 클래스](../../mfc/reference/cbasetabbedpane-class.md)   
 [CMFCOutlookBarTabCtrl Class](../../mfc/reference/cmfcoutlookbartabctrl-class.md)   
 [CMFCOutlookBarPane Class](../../mfc/reference/cmfcoutlookbarpane-class.md)