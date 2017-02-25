---
title: "CMDIChildWndEx 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMDIChildWndEx"
  - "GetThisClass"
  - "CMDIChildWndEx::PreTranslateMessage"
  - "CMDIChildWndEx::ActivateFrame"
  - "CMDIChildWndEx.GetThisClass"
  - "CMDIChildWndEx::AddDockSite"
  - "CMDIChildWndEx.CreateObject"
  - "CMDIChildWndEx::CreateObject"
  - "CMDIChildWndEx.ActivateFrame"
  - "CMDIChildWndEx::GetThisClass"
  - "CMDIChildWndEx.PreTranslateMessage"
  - "PreTranslateMessage"
  - "ActivateFrame"
  - "CreateObject"
  - "CMDIChildWndEx.AddDockSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMDIChildWndEx 클래스"
  - "ActivateFrame 메서드"
  - "PreTranslateMessage 메서드"
  - "GetThisClass 메서드"
  - "CreateObject 메서드"
ms.assetid: d39fec06-0bd6-4271-917d-35aae3b24d8e
caps.latest.revision: 35
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 37
---
# CMDIChildWndEx 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMDIChildWndEx` 클래스는 다중 문서 인터페이스 \(MDI\) 자식 창이 Windows의 기능을 제공 합니다.  기능을 확장 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md).  특정 mfc MDI 응용 프로그램을 사용 하는 경우이 클래스 프레임 워크를 필요로 합니다.  
  
## 구문  
  
```  
class CMDIChildWndEx : public CMDIChildWnd  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMDIChildWndEx::ActivateTopLevelFrame](../Topic/CMDIChildWndEx::ActivateTopLevelFrame.md)|내부적으로 작업 표시줄 탭에서 응용 프로그램을 활성화 해야 하는 경우 최상위 수준 프레임을 활성화 하기 위해 프레임 워크에서 호출 됩니다.|  
|`CMDIChildWndEx::AddDockSite`|이 방법은 사용 하거나 구현 됩니다.|  
|[CMDIChildWndEx::AddPane](../Topic/CMDIChildWndEx::AddPane.md)|창에 추가합니다.|  
|[CMDIChildWndEx::AddTabbedPane](../Topic/CMDIChildWndEx::AddTabbedPane.md)|탭된 창에 추가합니다.|  
|[CMDIChildWndEx::AdjustDockingLayout](../Topic/CMDIChildWndEx::AdjustDockingLayout.md)|도킹 레이아웃을 조정합니다.|  
|[CMDIChildWndEx::CanShowOnMDITabs](../Topic/CMDIChildWndEx::CanShowOnMDITabs.md)||  
|[CMDIChildWndEx::CanShowOnTaskBarTabs](../Topic/CMDIChildWndEx::CanShowOnTaskBarTabs.md)|프레임 워크가 MDI 자식 Windows 7 작업 표시줄 탭에서 표시 될 수 있는지 여부를 알려 줍니다.|  
|[CMDIChildWndEx::CanShowOnWindowsList](../Topic/CMDIChildWndEx::CanShowOnWindowsList.md)|반환 `TRUE` MDI 자식 창 이름에 표시 될 수 있는지는 [CMFCWindowsManagerDialog Class](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 대화 상자.  그렇지 않으면 `FALSE`을 반환합니다.|  
|`CMDIChildWndEx::CreateObject`|이와 같은 클래스의 동적 인스턴스를 만드는 프레임 워크에 의해 호출 됩니다.|  
|[CMDIChildWndEx::DockPane](../Topic/CMDIChildWndEx::DockPane.md)|창을 도킹합니다.|  
|[CMDIChildWndEx::DockPaneLeftOf](../Topic/CMDIChildWndEx::DockPaneLeftOf.md)|한 창이 다른 창의 왼쪽에 도킹합니다.|  
|[CMDIChildWndEx::EnableAutoHidePanes](../Topic/CMDIChildWndEx::EnableAutoHidePanes.md)|수 있도록 자동 모드 창에 컨트롤이 지정 된 창의 측면에 도킹 된 경우 숨기기.|  
|[CMDIChildWndEx::EnableDocking](../Topic/CMDIChildWndEx::EnableDocking.md)|자식 창에 있는 주 프레임에 도킹 활성화|  
|[CMDIChildWndEx::EnableTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::EnableTaskbarThumbnailClipRect.md)|사용 하거나 해당 창의 작업 표시줄 축소판으로 표시 하는 창 클라이언트 영역의 일부를 자동으로 선택 해제 합니다.|  
|[CMDIChildWndEx::GetDockingManager](../Topic/CMDIChildWndEx::GetDockingManager.md)||  
|[CMDIChildWndEx::GetDocumentName](../Topic/CMDIChildWndEx::GetDocumentName.md)|MDI 자식 창에 표시 되는 문서의 이름을 반환 합니다.|  
|[CMDIChildWndEx::GetFrameIcon](../Topic/CMDIChildWndEx::GetFrameIcon.md)|MDI 자식 창 아이콘을 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::GetFrameText](../Topic/CMDIChildWndEx::GetFrameText.md)|MDI 자식 창에 대 한 텍스트를 검색 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::GetPane](../Topic/CMDIChildWndEx::GetPane.md)|창을 지정 된 컨트롤 id를 찾습니다.|  
|[CMDIChildWndEx::GetRelatedTabGroup](../Topic/CMDIChildWndEx::GetRelatedTabGroup.md)||  
|[CMDIChildWndEx::GetTabbedPane](../Topic/CMDIChildWndEx::GetTabbedPane.md)|탭된 문서를 변환 하는 포함 된 도킹 창에 대 한 포인터를 반환 합니다.|  
|[CMDIChildWndEx::GetTabProxyWnd](../Topic/CMDIChildWndEx::GetTabProxyWnd.md)|실제로 Windows 7 작업 표시줄 탭이 있는 등록 프록시 창 반환을 탭 합니다.|  
|[CMDIChildWndEx::GetTaskbarPreviewWnd](../Topic/CMDIChildWndEx::GetTaskbarPreviewWnd.md)|Windows 7 작업 표시줄 탭에서 축소판 그림을 표시할 자식 창 \(일반적으로 뷰 또는 분할자 창\)을 얻이 필요가 있을 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIChildWndEx::GetTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::GetTaskbarThumbnailClipRect.md)|해당 창의 작업 표시줄 축소판으로 표시 하는 창 클라이언트 영역의 일부를 선택 할 때 프레임 워크에 의해 호출 됩니다.|  
|`CMDIChildWndEx::GetThisClass`|에 대 한 포인터를 얻을 수 있는 프레임 워크에서 호출 된  [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 이 클래스 형식에 연결 된 개체입니다.|  
|[CMDIChildWndEx::GetToolbarButtonToolTipText](../Topic/CMDIChildWndEx::GetToolbarButtonToolTipText.md)|도구 모음 단추의 도구 설명을 검색 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::InsertPane](../Topic/CMDIChildWndEx::InsertPane.md)|지정한 창을 도킹 관리자에 등록합니다.|  
|[CMDIChildWndEx::InvalidateIconicBitmaps](../Topic/CMDIChildWndEx::InvalidateIconicBitmaps.md)|MDI 자식 아이콘 비트맵 표현을 무효화 됩니다.|  
|[CMDIChildWndEx::IsPointNearDockSite](../Topic/CMDIChildWndEx::IsPointNearDockSite.md)|지정 된 지점 근처 항구 사이트 인지 확인 합니다.|  
|[CMDIChildWndEx::IsReadOnly](../Topic/CMDIChildWndEx::IsReadOnly.md)|반환 `TRUE` 자식 창에 표시 되는 문서 읽기 전용인 경우.  그렇지 않으면 `FALSE`을 반환합니다.|  
|[CMDIChildWndEx::IsRegisteredWithTaskbarTabs](../Topic/CMDIChildWndEx::IsRegisteredWithTaskbarTabs.md)|MDI 자식 Windows 7 작업 표시줄 탭을 성공적으로 등록 된 경우 TRUE를 반환 합니다.|  
|[CMDIChildWndEx::IsTabbedPane](../Topic/CMDIChildWndEx::IsTabbedPane.md)|반환 `TRUE` 도킹 된 창 MDI 자식 창을 포함 하는 경우.  그렇지 않으면 `FALSE`을 반환합니다.|  
|[CMDIChildWndEx::IsTaskbarTabsSupportEnabled](../Topic/CMDIChildWndEx::IsTaskbarTabsSupportEnabled.md)|MDI 자식 Windows 7 작업 표시줄 탭을 표시할 수 있는지 알 수 있습니다.|  
|[CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled](../Topic/CMDIChildWndEx::IsTaskbarThumbnailClipRectEnabled.md)|해당 창의 작업 표시줄 축소판으로 표시 하는 창 클라이언트 영역의 일부를 자동으로 선택이 가능한 지 여부를 알 수 있습니다.|  
|[CMDIChildWndEx::m\_dwDefaultTaskbarTabPropertyFlags](../Topic/CMDIChildWndEx::m_dwDefaultTaskbarTabPropertyFlags.md)|Windows 7 작업 표시줄 탭 탭 \(MDI 자식\) 등록 되 면 프레임 워크에서 SetTaskbarTabProperties 메서드에 전달 되는 플래그의 조합입니다.  STPF\_USEAPPTHUMBNAILWHENACTIVE 기본 조합입니다 &#124; STPF\_USEAPPPEEKWHENACTIVE입니다.|  
|[CMDIChildWndEx::OnGetIconicLivePreviewBitmap](../Topic/CMDIChildWndEx::OnGetIconicLivePreviewBitmap.md)|실시간 미리 보기를 MDI 자식에 대 한 비트맵을 얻이 필요가 있을 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIChildWndEx::OnGetIconicThumbnail](../Topic/CMDIChildWndEx::OnGetIconicThumbnail.md)|MDI 자식 아이콘 축소판 그림에 대 한 비트맵을 얻이 필요가 있을 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIChildWndEx::OnMoveMiniFrame](../Topic/CMDIChildWndEx::OnMoveMiniFrame.md)|미니 프레임 창을 이동 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton](../Topic/CMDIChildWndEx::OnPressTaskbarThmbnailCloseButton.md)|작업 표시줄 탭의 미리 보기에서 닫기 단추를 누를 때 프레임 워크에 의해 호출.|  
|[CMDIChildWndEx::OnSetPreviewMode](../Topic/CMDIChildWndEx::OnSetPreviewMode.md)|입력 또는 인쇄 미리 보기 모드를 종료 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailActivate](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailActivate.md)|작업 표시줄 탭의 축소판 그림 WM\_ACTIVATE 메시지를 처리 해야 하는 경우 프레임 워크에 의해 호출 됩니다.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailMouseActivate.md)|작업 표시줄 탭의 축소판 그림 WM\_MOUSEACTIVATE 메시지를 처리 해야 하는 경우 프레임 워크에 의해 호출 됩니다.|  
|[CMDIChildWndEx::OnTaskbarTabThumbnailStretch](../Topic/CMDIChildWndEx::OnTaskbarTabThumbnailStretch.md)|Windows 7 작업 표시줄 탭 미리 보기를 MDI 자식에 대 한 비트맵을 늘릴 필요가 있을 때 프레임 워크에 의해 호출 됩니다.|  
|[CMDIChildWndEx::OnUpdateFrameTitle](../Topic/CMDIChildWndEx::OnUpdateFrameTitle.md)|프레임 제목 업데이트를 프레임 워크에 의해 호출 됩니다.  \(재정의 `CMDIChildWnd::OnUpdateFrameTitle`.\)|  
|[CMDIChildWndEx::PaneFromPoint](../Topic/CMDIChildWndEx::PaneFromPoint.md)|지정 된 점이 포함 된 창을 반환 합니다.|  
|`CMDIChildWndEx::PreTranslateMessage`|클래스에 의해 사용 되는  [CWinApp](../../mfc/reference/cwinapp-class.md) 창 메시지를 디스패치하기 전에 변환 하는  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수.  \(재정의 [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md).\)|  
|[CMDIChildWndEx::RecalcLayout](../Topic/CMDIChildWndEx::RecalcLayout.md)|창 레이아웃을 다시 계산합니다.|  
|[CMDIChildWndEx::RegisterTaskbarTab](../Topic/CMDIChildWndEx::RegisterTaskbarTab.md)|MDI 자식 Windows 7 작업 표시줄 탭을 등록합니다.|  
|[CMDIChildWndEx::RemovePaneFromDockManager](../Topic/CMDIChildWndEx::RemovePaneFromDockManager.md)|창 도킹 관리자에서 제거합니다.|  
|[CMDIChildWndEx::SetRelatedTabGroup](../Topic/CMDIChildWndEx::SetRelatedTabGroup.md)||  
|[CMDIChildWndEx::SetTaskbarTabActive](../Topic/CMDIChildWndEx::SetTaskbarTabActive.md)|Windows 7 작업 표시줄의 해당 탭을 활성화합니다.|  
|[CMDIChildWndEx::SetTaskbarTabOrder](../Topic/CMDIChildWndEx::SetTaskbarTabOrder.md)|MDI 자식 Windows 7 작업 표시줄 탭에서 지정 된 창 앞에 삽입합니다.|  
|[CMDIChildWndEx::SetTaskbarTabProperties](../Topic/CMDIChildWndEx::SetTaskbarTabProperties.md)|Windows 7 작업 표시줄 탭에 대 한 속성을 설정합니다.|  
|[CMDIChildWndEx::SetTaskbarThumbnailClipRect](../Topic/CMDIChildWndEx::SetTaskbarThumbnailClipRect.md)|내부적으로 해당 창의 작업 표시줄 축소판으로 표시 하는 창 클라이언트 영역의 일부를 선택 합니다 클리핑 사각형을 설정 하는 프레임 워크에서 호출 됩니다.|  
|[CMDIChildWndEx::ShowPane](../Topic/CMDIChildWndEx::ShowPane.md)||  
|[CMDIChildWndEx::UnregisterTaskbarTab](../Topic/CMDIChildWndEx::UnregisterTaskbarTab.md)|MDI 자식 Windows 7 작업 표시줄 탭에서 제거합니다.|  
|[CMDIChildWndEx::UpdateTaskbarTabIcon](../Topic/CMDIChildWndEx::UpdateTaskbarTabIcon.md)|Windows 7 작업 표시줄 탭 아이콘을 업데이트합니다.|  
  
## 설명  
 MDI 응용 프로그램에서 확장 된 도킹 기능을 활용 하려면 응용 프로그램의 MDI 자식 창 클래스를 파생 `CMDIChildWndEx` 대신  [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md).  
  
## 예제  
 다음 예제에서는 클래스에서 파생 된 `CMDIChildWndEx`.  이 코드에서 제공 되는  [VisualStudioDemo 샘플: MFC Visual Studio 응용 프로그램](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#3](../../mfc/codesnippet/CPP/cmdichildwndex-class_1.h)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md)  
  
 [CMDIChildWndEx](../../mfc/reference/cmdichildwndex-class.md)  
  
## 요구 사항  
 **헤더:** afxMDIChildWndEx.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMDIChildWnd Class](../../mfc/reference/cmdichildwnd-class.md)   
 [CMFCWindowsManagerDialog Class](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)   
 [CMDIFrameWndEx 클래스](../../mfc/reference/cmdiframewndex-class.md)