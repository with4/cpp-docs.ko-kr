---
title: "CMFCVisualManagerOffice2003 Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManagerOffice2003"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerOffice2003 class"
ms.assetid: 115482cd-e349-450a-8dc4-c6023d092aab
caps.latest.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CMFCVisualManagerOffice2003 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerOffice2003`응용 프로그램에 Microsoft Office 2003 모양을 제공합니다.  
  
## 구문  
  
```  
class CMFCVisualManagerOffice2003 : public CMFCVisualManagerOfficeXP  
```  
  
## Members  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCVisualManagerOffice2003::DrawComboBorderWinXP](../Topic/CMFCVisualManagerOffice2003::DrawComboBorderWinXP.md)|현재 Windows XP 테마를 사용 하 여 콤보 상자의 테두리를 그립니다.  \(재정의 [CMFCVisualManager::DrawComboBorderWinXP](../Topic/CMFCVisualManager::DrawComboBorderWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP](../Topic/CMFCVisualManagerOffice2003::DrawComboDropButtonWinXP.md)|현재 Windows XP 테마를 사용 하 여 콤보 상자 드롭다운 단추를 그립니다.  \(재정의 [CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::DrawCustomizeButton](../Topic/CMFCVisualManagerOffice2003::DrawCustomizeButton.md)|사용자 지정 단추를 그립니다.|  
|[CMFCVisualManagerOffice2003::DrawPushButtonWinXP](../Topic/CMFCVisualManagerOffice2003::DrawPushButtonWinXP.md)|현재 Windows XP 테마를 사용 하 여 누름 단추를 그립니다.  \(재정의 [CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md).\)|  
|[CMFCVisualManagerOffice2003::GetBaseThemeColor](../Topic/CMFCVisualManagerOffice2003::GetBaseThemeColor.md)|기본 테마의 색을 가져옵니다.|  
|[CMFCVisualManagerOffice2003::GetHighlightMenuItemColor](../Topic/CMFCVisualManagerOffice2003::GetHighlightMenuItemColor.md)|강조 표시 된 메뉴 항목에 사용 되는 색을 가져옵니다.|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupColor.md)|프레임 워크 속성 목록에 대 한 배경 색을 가져오려면이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::GetPropertyGridGroupColor`.\)|  
|[CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManagerOffice2003::GetPropertyGridGroupTextColor.md)|프레임 워크 속성은 텍스트 색을 검색 하려면이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::GetPropertyGridGroupTextColor`.\)|  
|[CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManagerOffice2003::GetShowAllMenuItemsHeight.md)|모든 메뉴 항목의 높이 반환합니다.  \(재정의 [CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md).\)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManagerOffice2003::GetSmartDockingBaseGuideColors.md)|지정 된 기본 그룹 배경색 및 테두리 색을 설정합니다.  \(재정의 `CMFCVisualManagerOfficeXP::GetSmartDockingBaseGuideColors`.\)|  
|[CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManagerOffice2003::GetSmartDockingHighlightToneColor.md)|밝은 톤의 색을 가져옵니다.  \(재정의 [CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md).\)|  
|[CMFCVisualManagerOffice2003::GetTabFrameColors](../Topic/CMFCVisualManagerOffice2003::GetTabFrameColors.md)|드로잉 탭 창에 대 한 색 집합을 검색 하는 경우이 함수를 호출 하는 프레임 워크입니다.  \(재정의 [CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md).\)|  
|[CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin](../Topic/CMFCVisualManagerOffice2003::GetToolBarCustomizeButtonMargin.md)|사용자 지정 도구 모음 단추를 가져옵니다.  \(재정의 `CMFCVisualManager::GetToolBarCustomizeButtonMargin`.\)|  
|[CMFCVisualManagerOffice2003::GetToolbarDisabledColor](../Topic/CMFCVisualManagerOffice2003::GetToolbarDisabledColor.md)|도구 모음에 사용할된 색을 가져옵니다.  \(재정의 `CMFCVisualManager::GetToolbarDisabledColor`.\)|  
|[CMFCVisualManagerOffice2003::GetToolTipInfo](../Topic/CMFCVisualManagerOffice2003::GetToolTipInfo.md)|도구 설명 정보를 가져오기 위해 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md).\)|  
|[CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled](../Topic/CMFCVisualManagerOffice2003::IsDefaultWinXPColorsEnabled.md)|비주얼 관리자 기본 Windows XP 테마 색을 사용 하는지 여부를 나타냅니다.|  
|[CMFCVisualManagerOffice2003::IsDockingTabHasBorder](../Topic/CMFCVisualManagerOffice2003::IsDockingTabHasBorder.md)|현재 비주얼 관리자 도킹 되어 탭 창 주위에 테두리를 그릴지 여부를 반환 합니다.  \(재정의 [CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md).\)|  
|[CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs](../Topic/CMFCVisualManagerOffice2003::IsHighlightOneNoteTabs.md)|OneNote 탭 강조 표시 해야 하는지 여부를 나타냅니다.  \(재정의 `CMFCVisualManager::IsHighlightOneNoteTabs`.\)|  
|[CMFCVisualManagerOffice2003::IsOffsetPressedButton](../Topic/CMFCVisualManagerOffice2003::IsOffsetPressedButton.md)|프레임 워크에서 도구 모음 단추에 그릴 때 호출 됩니다.  \(재정의 `CMFCVisualManager::IsOffsetPressedButton`.\)|  
|[CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook](../Topic/CMFCVisualManagerOffice2003::IsStatusBarOfficeXPLook.md)|상태 표시줄에 Office XP를 있는지 여부를 나타냅니다.|  
|[CMFCVisualManagerOffice2003::IsToolbarRoundShape](../Topic/CMFCVisualManagerOffice2003::IsToolbarRoundShape.md)|지정 된 도구 모음에 둥근 모양의 있는지 여부를 나타냅니다.  \(재정의 [CMFCVisualManager::IsToolbarRoundShape](../Topic/CMFCVisualManager::IsToolbarRoundShape.md).\)|  
|[CMFCVisualManagerOffice2003::IsUseGlobalTheme](../Topic/CMFCVisualManagerOffice2003::IsUseGlobalTheme.md)|전역 Windows XP 테마를 사용할지 여부를 나타냅니다.|  
|[CMFCVisualManagerOffice2003::IsWindowsThemingSupported](../Topic/CMFCVisualManagerOffice2003::IsWindowsThemingSupported.md)|Windows 테마를 지원 하는지 여부를 나타냅니다.  \(재정의 [CMFCVisualManager::IsWindowsThemingSupported](../Topic/CMFCVisualManager::IsWindowsThemingSupported.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawAutoHideButtonBorder.md)|프레임 워크는 자동 숨기기 단추의 테두리를 그릴 때이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawBarGripper](../Topic/CMFCVisualManagerOffice2003::OnDrawBarGripper.md)|컨트롤 막대의 그리퍼를 그릴 때 프레임 워크에 의해 호출 됩니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawBarGripper`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawBrowseButton](../Topic/CMFCVisualManagerOffice2003::OnDrawBrowseButton.md)|편집 컨트롤에 대 한 찾아보기 단추를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawBrowseButton`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawButtonBorder.md)|도구 모음 단추의 테두리를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawCaptionBarBorder.md)|프레임 워크의 테두리를 그릴 때이 메서드를 호출 하는 [CMFCCaptionBar 클래스](../../mfc/reference/cmfccaptionbar-class.md) 개체입니다.  \(재정의 [CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerOffice2003::OnDrawCheckBoxEx.md)|Checkbox를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 [CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawComboBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawComboBorder.md)|프레임 워크의 테두리를 그릴 때이 메서드를 호출 하는 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawComboBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawComboDropButton](../Topic/CMFCVisualManagerOffice2003::OnDrawComboDropButton.md)|프레임 워크의 드롭 단추를 그릴 때이 메서드를 호출 하는 [CMFCToolBarComboBoxButton Class](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawComboDropButton`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawControlBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawControlBorder.md)|컨트롤의 테두리를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 [CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawExpandingBox](../Topic/CMFCVisualManagerOffice2003::OnDrawExpandingBox.md)|확장 된 상자를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 [CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawHeaderCtrlBorder.md)|프레임 워크의 인스턴스 주위에 있는 테두리를 그릴 때이 메서드를 호출 하 여 [CMFCHeaderCtrl Class](../../mfc/reference/cmfcheaderctrl-class.md).  \(재정의 [CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawMenuBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawMenuBorder.md)|프레임 워크의 테두리를 그릴 때이 메서드를 호출 하는 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md).  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawMenuBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManagerOffice2003::OnDrawOutlookBarSplitter.md)|Outlook 표시줄에 분할자를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의[CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawOutlookPageButtonBorder.md)|Outlook 페이지 단추의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.  \(재정의 [CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneBorder.md)|프레임 워크의 테두리를 그릴 때이 메서드를 호출 하는 [CPane Class](../../mfc/reference/cpane-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawPaneBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPaneCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPaneCaption.md)|프레임 워크에 대 한 캡션을 그릴 때이 메서드를 호출 하는 [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawPaneCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowBorder.md)|팝업 창에서 테두리를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawPopupWindowBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowButtonBorder.md)|팝업 창에서 테두리 단추를 그리면이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawPopupWindowButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawPopupWindowCaption.md)|팝업 창의 캡션을 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawPopupWindowCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonButtonsGroup.md)|리본 메뉴에 단추 그룹을 그리면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonCategoryCaption.md)|이 리본 항목에 대 한 캡션 표시줄을 그립니다 때 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonCategoryTab.md)|탭 리본 범주를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 [CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonProgressBar.md)|이 메서드를 호출 하 여 그릴 때 프레임 워크는 [CMFCRibbonProgressBar Class](../../mfc/reference/cmfcribbonprogressbar-class.md).  \(재정의 [CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonQuickAccessToolBarSeparator.md)|프레임 워크는 빠른 액세스 도구 모음에는 리본 메뉴의 구분 기호를 그리면이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawRibbonQuickAccessToolBarSeparator`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderChannel.md)|프레임 워크의 채널을 그릴 때이 메서드를 호출 하는 [CMFCRibbonSlider Class](../../mfc/reference/cmfcribbonslider-class.md).  \(재정의 [CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderThumb.md)|프레임 워크의 엄지 단추를 그릴 때이 메서드를 호출 하는  [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) 개체입니다.  \(재정의 [CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonSliderZoomButton.md)|프레임 워크에 대 한 확대\/축소 단추를 그릴 때이 메서드를 호출 하는  [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) 개체입니다.  \(재정의 [CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManagerOffice2003::OnDrawRibbonStatusBarPane.md)|상태 표시줄에 있는 창 그리면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawRibbonStatusBarPane`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawScrollButtons](../Topic/CMFCVisualManagerOffice2003::OnDrawScrollButtons.md)|스크롤 단추를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawScrollButtons`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawSeparator](../Topic/CMFCVisualManagerOffice2003::OnDrawSeparator.md)|구분 기호를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawSeparator`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems](../Topic/CMFCVisualManagerOffice2003::OnDrawShowAllMenuItems.md)|이 메뉴에서 모든 항목을 그릴 때 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarPaneBorder.md)|프레임 워크에 대 한 테두리를 그릴 때이 메서드를 호출 하는 [CMFCStatusBar Class](../../mfc/reference/cmfcstatusbar-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawStatusBarPaneBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarProgress](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarProgress.md)|진행률 표시기가 그릴 때 프레임 워크가이 메서드를 호출 하는  [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md) 개체입니다.  \(재정의 [CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerOffice2003::OnDrawStatusBarSizeBox.md)|프레임 워크에 대 한 크기 상자를 그릴 때이 메서드를 호출 하는  [CMFCStatusBar](../../mfc/reference/cmfcstatusbar-class.md).  \(재정의 [CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md).\)|  
|[CMFCVisualManagerOffice2003::OnDrawTab](../Topic/CMFCVisualManagerOffice2003::OnDrawTab.md)|프레임 워크에 대 한 탭을 그릴 때이 메서드를 호출 하는 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawTab`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawTabsButtonBorder.md)|탭 버튼의 테두리를 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawTabsButtonBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTask](../Topic/CMFCVisualManagerOffice2003::OnDrawTask.md)|이 메서드를 호출 하 여 그릴 때 프레임 워크는 [CMFCTasksPaneTask Class](../../mfc/reference/cmfctaskspanetask-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawTask`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManagerOffice2003::OnDrawTasksGroupAreaBorder.md)|프레임 워크 그룹 주위에 테두리를 그릴 때이 메서드를 호출 하는 [CMFCTasksPane Class](../../mfc/reference/cmfctaskspane-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawTasksGroupAreaBorder`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawTasksGroupCaption.md)|프레임 워크의 캡션을 그릴 때이 메서드를 호출 하는 [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawTasksGroupCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnDrawTearOffCaption](../Topic/CMFCVisualManagerOffice2003::OnDrawTearOffCaption.md)|프레임 워크의 캡션을 그릴 때이 메서드를 호출 하는 [CMFCPopupMenu Class](../../mfc/reference/cmfcpopupmenu-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnDrawTearOffCaption`.\)|  
|[CMFCVisualManagerOffice2003::OnErasePopupWindowButton](../Topic/CMFCVisualManagerOffice2003::OnErasePopupWindowButton.md)|팝업 창에 있는 단추를 지울 때 프레임 워크가이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnErasePopupWindowButton`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsArea](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsArea.md)|프레임 워크는 탭 창의 탭 영역을 지울 때이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnEraseTabsArea`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsButton](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsButton.md)|텍스트 및 탭 단추 아이콘을 지울 때 프레임 워크가이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnEraseTabsButton`.\)|  
|[CMFCVisualManagerOffice2003::OnEraseTabsFrame](../Topic/CMFCVisualManagerOffice2003::OnEraseTabsFrame.md)|프레임 워크에서 프레임을 지울 때이 메서드를 호출 하는 [CMFCBaseTabCtrl Class](../../mfc/reference/cmfcbasetabctrl-class.md).  \(재정의 [CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManagerOffice2003::OnFillAutoHideButtonBackground.md)|프레임 워크는 자동 숨기기 단추의 배경을 채우면이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillBarBackground](../Topic/CMFCVisualManagerOffice2003::OnFillBarBackground.md)|배경의 채우면 프레임 워크가이 메서드를 호출 하는 [CBasePane Class](../../mfc/reference/cbasepane-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnFillBarBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillButtonInterior](../Topic/CMFCVisualManagerOffice2003::OnFillButtonInterior.md)|도구 모음 단추의 배경을 채우면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnFillButtonInterior`.\)|  
|[CMFCVisualManagerOffice2003::OnFillCommandsListBackground](../Topic/CMFCVisualManagerOffice2003::OnFillCommandsListBackground.md)|명령 목록에 속한 도구 모음 단추의 배경을 채우면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnFillCommandsListBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManagerOffice2003::OnFillHeaderCtrlBackground.md)|Header 컨트롤의 배경색을 채우면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillHighlightedArea](../Topic/CMFCVisualManagerOffice2003::OnFillHighlightedArea.md)|도구 모음 단추 강조 표시 된 영역을 채우면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnFillHighlightedArea`.\)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookBarCaption](../Topic/CMFCVisualManagerOffice2003::OnFillOutlookBarCaption.md)|해당 캡션 Outlook 표시줄의 배경을 채울 때 프레임 워크가이 메서드를 호출 합니다.  \(재정의 [CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillOutlookPageButton](../Topic/CMFCVisualManagerOffice2003::OnFillOutlookPageButton.md)|Outlook 페이지 단추의 내부를 채울 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 [CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md).\)|  
|[CMFCVisualManagerOffice2003::OnFillPopupWindowBackground](../Topic/CMFCVisualManagerOffice2003::OnFillPopupWindowBackground.md)|팝업 창의 배경색을 채우면 프레임 워크가이 메서드를 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnFillPopupWindowBackground`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTab](../Topic/CMFCVisualManagerOffice2003::OnFillTab.md)|탭 윈도우의 백그라운드를 작성할 때이 메서드를 호출 하는 프레임 워크.  \(재정의 `CMFCVisualManagerOfficeXP::OnFillTab`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTasksGroupInterior](../Topic/CMFCVisualManagerOffice2003::OnFillTasksGroupInterior.md)|프레임 워크의 내부를 작성할 때이 메서드를 호출 하는 [CMFCTasksPaneTaskGroup Class](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 개체입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnFillTasksGroupInterior`.\)|  
|[CMFCVisualManagerOffice2003::OnFillTasksPaneBackground](../Topic/CMFCVisualManagerOffice2003::OnFillTasksPaneBackground.md)|배경의 채우면 프레임 워크가이 메서드를 호출 하는  [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) 제어 합니다.  \(재정의 [CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md).\)|  
|[CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton](../Topic/CMFCVisualManagerOffice2003::OnHighlightQuickCustomizeMenuButton.md)|강조를 그릴 때이 메서드가 빠른\-사용자 지정 메뉴 단추 프레임 워크 호출 합니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnHighlightQuickCustomizeMenuButton`.\)|  
|[CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManagerOffice2003::OnHighlightRarelyUsedMenuItems.md)|강조 표시 된 메뉴 명령을 그릴 때이 메서드를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnHighlightRarelyUsedMenuItems`.\)|  
|[CMFCVisualManagerOffice2003::OnUpdateSystemColors](../Topic/CMFCVisualManagerOffice2003::OnUpdateSystemColors.md)|시스템 색을 변경 하는 경우이 함수를 호출 하는 프레임 워크입니다.  \(재정의 `CMFCVisualManagerOfficeXP::OnUpdateSystemColors`.\)|  
|[CMFCVisualManagerOffice2003::SetDefaultWinXPColors](../Topic/CMFCVisualManagerOffice2003::SetDefaultWinXPColors.md)|비주얼 관리자 기본 Windows XP 테마 색을 사용 해야 또는 색상에서 가져온 지정  [GetSysColor](http://msdn.microsoft.com/library/windows/desktop/ms724371).|  
|[CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook](../Topic/CMFCVisualManagerOffice2003::SetStatusBarOfficeXPLook.md)|전역 Windows XP 테마를 사용할지 여부를 지정 합니다.|  
|[CMFCVisualManagerOffice2003::SetUseGlobalTheme](../Topic/CMFCVisualManagerOffice2003::SetUseGlobalTheme.md)|전역 테마 비주얼 관리자를 사용 하는지 여부를 지정 합니다.|  
  
## 설명  
 사용 된 `CMFCVisualManagerOffice2003` 비슷한 Microsoft Office 2003 응용 프로그램의 시각적 모양을 변경 하는 클래스입니다.  
  
## 예제  
 다음 예제에서는 office 2003 비주얼 관리자를 설정 하는 방법을 보여 줍니다.  이 코드의 일부인의  [바탕 화면 경고 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DesktopAlertDemo#6](../../mfc/reference/codesnippet/CPP/cmfcvisualmanageroffice2003-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerOffice2003](../../mfc/reference/cmfcvisualmanageroffice2003-class.md)  
  
## 요구 사항  
 **헤더:** afxvisualmanageroffice2003.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)