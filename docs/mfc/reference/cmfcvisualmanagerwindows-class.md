---
title: "CMFCVisualManagerWindows Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManagerWindows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows class"
ms.assetid: 568b6e9e-8e67-4477-9a3d-2981cbd09861
caps.latest.revision: 46
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 48
---
# CMFCVisualManagerWindows Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows`Windows XP 또는 Vista 테마를 선택할 때 Microsoft Windows XP 또는 Microsoft Vista의 모양을 모방 합니다.  
  
## 구문  
  
```  
class CMFCVisualManagerWindows : public CMFCVisualManagerOfficeXP  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCVisualManagerWindows::CMFCVisualManagerWindows`|기본 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCVisualManagerWindows::AlwaysHighlight3DTabs](../Topic/CMFCVisualManagerWindows::AlwaysHighlight3DTabs.md)|프레임 워크 응용 프로그램에서 3D 탭 항상 강조 해야 하는지 여부를 확인 하려면이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md).\)|  
|[CMFCVisualManagerWindows::DrawComboBorderWinXP](../Topic/CMFCVisualManagerWindows::DrawComboBorderWinXP.md)|\(재정의 `CMFCVisualManager::DrawComboBorderWinXP`.\)|  
|[CMFCVisualManagerWindows::DrawComboDropButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawComboDropButtonWinXP.md)|\(재정의 [CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md).\)|  
|[CMFCVisualManagerWindows::DrawPushButtonWinXP](../Topic/CMFCVisualManagerWindows::DrawPushButtonWinXP.md)|\(재정의 [CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md).\)|  
|[CMFCVisualManagerWindows::GetButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetButtonExtraBorder.md)|도구 모음 단추를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 [CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md).\)|  
|[CMFCVisualManagerWindows::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManagerWindows::GetCaptionButtonExtraBorder.md)|\(재정의 [CMFCVisualManager::GetCaptionButtonExtraBorder](../Topic/CMFCVisualManager::GetCaptionButtonExtraBorder.md).\)|  
|[CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight](../Topic/CMFCVisualManagerWindows::GetDockingPaneCaptionExtraHeight.md)|\(재정의 `CMFCVisualManager::GetDockingPaneCaptionExtraHeight`.\)|  
|[CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManagerWindows::GetHighlightedMenuItemTextColor.md)|\(재정의 `CMFCVisualManagerOfficeXP::GetHighlightedMenuItemTextColor`.\)|  
|[CMFCVisualManagerWindows::GetPopupMenuGap](../Topic/CMFCVisualManagerWindows::GetPopupMenuGap.md)|\(재정의 `CMFCVisualManagerOfficeXP::GetPopupMenuGap`.\)|  
|[CMFCVisualManagerWindows::GetToolbarButtonTextColor](../Topic/CMFCVisualManagerWindows::GetToolbarButtonTextColor.md)|\(재정의 `CMFCVisualManagerOfficeXP::GetToolbarButtonTextColor`.\)|  
|[CMFCVisualManagerWindows::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManagerWindows::IsDefaultWinXPPopupButton.md)|\(재정의 [CMFCVisualManager::IsDefaultWinXPPopupButton](../Topic/CMFCVisualManager::IsDefaultWinXPPopupButton.md).\)|  
|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md)|\(재정의 `CMFCVisualManagerOfficeXP::IsHighlightWholeMenuItem`.\)|  
|[CMFCVisualManagerWindows::IsOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeStyleMenus.md)||  
|[CMFCVisualManagerWindows::IsOfficeXPStyleMenus](../Topic/CMFCVisualManagerWindows::IsOfficeXPStyleMenus.md)|Office XP 스타일 메뉴는 비주얼 관리자를 구현 하는지 여부를 나타냅니다.  \(재정의 [CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md).\)|  
|[CMFCVisualManagerWindows::IsWindowsThemingSupported](../Topic/CMFCVisualManagerWindows::IsWindowsThemingSupported.md)|\(재정의 `CMFCVisualManager::IsWindowsThemingSupported`.\)|  
|[CMFCVisualManagerWindows::IsWinXPThemeAvailable](../Topic/CMFCVisualManagerWindows::IsWinXPThemeAvailable.md)|Windows 테마를 사용할 수 있는지 여부를 나타냅니다.  Windows XP 테마는 테마를 사용할 수 있습니다 또는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 테마.|  
|[CMFCVisualManagerWindows::OnDrawBarGripper](../Topic/CMFCVisualManagerWindows::OnDrawBarGripper.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawBarGripper`.\)|  
|[CMFCVisualManagerWindows::OnDrawBrowseButton](../Topic/CMFCVisualManagerWindows::OnDrawBrowseButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawBrowseButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawButtonBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawButtonSeparator](../Topic/CMFCVisualManagerWindows::OnDrawButtonSeparator.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawButtonSeparator`.\)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButton](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawCaptionButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawCaptionButtonIcon](../Topic/CMFCVisualManagerWindows::OnDrawCaptionButtonIcon.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawCaptionButtonIcon`.\)|  
|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md)|\(재정의 [CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md).\)|  
|[CMFCVisualManagerWindows::OnDrawComboBorder](../Topic/CMFCVisualManagerWindows::OnDrawComboBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawComboBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawComboDropButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawControlBorder](../Topic/CMFCVisualManagerWindows::OnDrawControlBorder.md)|\(재정의 [CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md).\)|  
|[CMFCVisualManagerWindows::OnDrawEditBorder](../Topic/CMFCVisualManagerWindows::OnDrawEditBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawEditBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawExpandingBox](../Topic/CMFCVisualManagerWindows::OnDrawExpandingBox.md)|\(재정의 [CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md).\)|  
|[CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManagerWindows::OnDrawFloatingToolbarBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawFloatingToolbarBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlBorder.md)|프레임 워크의 인스턴스 주위의 테두리를 그릴 때이 메서드를 호출 하 여 [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md).  \(재정의 [CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md).\)|  
|[CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManagerWindows::OnDrawHeaderCtrlSortArrow.md)|Header 컨트롤의 정렬 화살표를 그릴 때 프레임 워크는이 함수를 호출 합니다.  \(재정의 [CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md).\)|  
|[CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawMenuBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawMenuSystemButton](../Topic/CMFCVisualManagerWindows::OnDrawMenuSystemButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawMenuSystemButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawMiniFrameBorder](../Topic/CMFCVisualManagerWindows::OnDrawMiniFrameBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawMiniFrameBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawOutlookPageButtonBorder.md)|Outlook 페이지 단추의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md).\)|  
|[CMFCVisualManagerWindows::OnDrawPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawPaneBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawPaneBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawPaneCaption](../Topic/CMFCVisualManagerWindows::OnDrawPaneCaption.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawPaneCaption`.\)|  
|[CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawPopupWindowButtonBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawScrollButtons](../Topic/CMFCVisualManagerWindows::OnDrawScrollButtons.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawScrollButtons`.\)|  
|[CMFCVisualManagerWindows::OnDrawSeparator](../Topic/CMFCVisualManagerWindows::OnDrawSeparator.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawSeparator`.\)|  
|[CMFCVisualManagerWindows::OnDrawSpinButtons](../Topic/CMFCVisualManagerWindows::OnDrawSpinButtons.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawSpinButtons`.\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarPaneBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarProgress](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarProgress.md)|진행률 표시기를 그릴 때 프레임 워크가이 메서드를 호출 하는  [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) 개체입니다.  \(재정의 [CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md).\)|  
|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md)|프레임 워크의 크기 상자를 그릴 때이 메서드를 호출 하는  [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md).  \(재정의 [CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md).\)|  
|[CMFCVisualManagerWindows::OnDrawTab](../Topic/CMFCVisualManagerWindows::OnDrawTab.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawTab`.\)|  
|[CMFCVisualManagerWindows::OnDrawTabCloseButton](../Topic/CMFCVisualManagerWindows::OnDrawTabCloseButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawTabCloseButton`.\)|  
|[CMFCVisualManagerWindows::OnDrawTabsButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawTabsButtonBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawTask](../Topic/CMFCVisualManagerWindows::OnDrawTask.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawTask`.\)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupAreaBorder.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`.\)|  
|[CMFCVisualManagerWindows::OnDrawTasksGroupCaption](../Topic/CMFCVisualManagerWindows::OnDrawTasksGroupCaption.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`.\)|  
|[CMFCVisualManagerWindows::OnDrawTearOffCaption](../Topic/CMFCVisualManagerWindows::OnDrawTearOffCaption.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`.\)|  
|[CMFCVisualManagerWindows::OnErasePopupWindowButton](../Topic/CMFCVisualManagerWindows::OnErasePopupWindowButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`.\)|  
|[CMFCVisualManagerWindows::OnEraseTabsArea](../Topic/CMFCVisualManagerWindows::OnEraseTabsArea.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnEraseTabsArea`.\)|  
|[CMFCVisualManagerWindows::OnEraseTabsButton](../Topic/CMFCVisualManagerWindows::OnEraseTabsButton.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnEraseTabsButton`.\)|  
|[CMFCVisualManagerWindows::OnEraseTabsFrame](../Topic/CMFCVisualManagerWindows::OnEraseTabsFrame.md)|프레임 워크에서 프레임을 지울 때이 메서드를 호출 하는 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md).  \(재정의 [CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md).\)|  
|[CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnFillBarBackground`.\)|  
|[CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnFillButtonInterior`.\)|  
|[CMFCVisualManagerWindows::OnFillCommandsListBackground](../Topic/CMFCVisualManagerWindows::OnFillCommandsListBackground.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`.\)|  
|[CMFCVisualManagerWindows::OnFillMiniFrameCaption](../Topic/CMFCVisualManagerWindows::OnFillMiniFrameCaption.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnFillMiniFrameCaption`.\)|  
|[CMFCVisualManagerWindows::OnFillOutlookPageButton](../Topic/CMFCVisualManagerWindows::OnFillOutlookPageButton.md)|Outlook 페이지 단추의 내부를 채울 때 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md).\)|  
|[CMFCVisualManagerWindows::OnFillTasksGroupInterior](../Topic/CMFCVisualManagerWindows::OnFillTasksGroupInterior.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`.\)|  
|[CMFCVisualManagerWindows::OnFillTasksPaneBackground](../Topic/CMFCVisualManagerWindows::OnFillTasksPaneBackground.md)|프레임 워크의 백그라운드를 작성할 때이 메서드를 호출 하는  [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) 제어 합니다.  \(재정의 [CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md).\)|  
|[CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnHighlightMenuItem`.\)|  
|[CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManagerWindows::OnHighlightRarelyUsedMenuItems.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`.\)|  
|[CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md)|\(재정의 `CMFCVisualManagerOfficeXP::OnUpdateSystemColors`.\)|  
|[CMFCVisualManagerWindows::SetOfficeStyleMenus](../Topic/CMFCVisualManagerWindows::SetOfficeStyleMenus.md)||  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCVisualManagerWindows::m\_b3DTabsXPTheme](../Topic/CMFCVisualManagerWindows::m_b3DTabsXPTheme.md)|Windows XP 테마를 3D 탭 표시 여부를 지정 합니다.|  
  
## 설명  
 사용 된 `CMFCVisualManagerWindows` 현재 Windows XP를 모방 하는 응용 프로그램의 모양을 변경 하려면 클래스 또는 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] 테마는 응용 프로그램을 실행 하는 컴퓨터에.  
  
 그러나 Windows 테마 응용 프로그램이 Windows XP 보다 이전 버전의 Windows에서 실행 중인 경우 또는 사용자가 사용 하 고 있기 때문에 테마를 사용할 수 없는 경우 사용할 수 없습니다는  **클래식** 보기.  테마 없음 사용할 수 있으면 응용 프로그램 정의 기본 비주얼 관리자 사용  [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
## 예제  
 다음 예제에서는 `CMFCVisualManagerWindows`을 사용하는 방법을 보여 줍니다.  이 코드 조각에 속하지는  [바탕 화면 경고 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#10](../../mfc/reference/codesnippet/CPP/cmfcvisualmanagerwindows-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
## 요구 사항  
 **헤더:** afxvisualmanagerwindows.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)