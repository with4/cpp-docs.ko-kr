---
title: "CMFCVisualManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCVisualManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManager class"
ms.assetid: beed80f7-36a2-4d64-9f09-e807cfefc3fe
caps.latest.revision: 58
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 60
---
# CMFCVisualManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

전역 수준에서 응용 프로그램의 모양을 변경 하는 지원 합니다.  `CMFCVisualManager` 클래스는 일관 된 스타일을 사용 하 여 응용 프로그램의 GUI 컨트롤을 그리는 명령을 제공 하는 클래스와 함께 작동 합니다.  이러한 다른 클래스를 비주얼 관리자 라고 하는 상속 `CMFCBaseVisualManager`.  
  
## 구문  
  
```  
class CMFCVisualManager : public CMFCBaseVisualManager  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CMFCVisualManager::CMFCVisualManager`|기본 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCVisualManager::AdjustFrames](../Topic/CMFCVisualManager::AdjustFrames.md)||  
|[CMFCVisualManager::AdjustToolbars](../Topic/CMFCVisualManager::AdjustToolbars.md)||  
|[CMFCVisualManager::AlwaysHighlight3DTabs](../Topic/CMFCVisualManager::AlwaysHighlight3DTabs.md)|3D 탭 항상 강조 색을 사용 하 여 그려야 할지 여부를 결정 하는 프레임 워크에서 호출 합니다.|  
|[CMFCVisualManager::DestroyInstance](../Topic/CMFCVisualManager::DestroyInstance.md)||  
|[CMFCVisualManager::DoDrawHeaderSortArrow](../Topic/CMFCVisualManager::DoDrawHeaderSortArrow.md)||  
|[CMFCVisualManager::DrawComboDropButtonWinXP](../Topic/CMFCVisualManager::DrawComboDropButtonWinXP.md)||  
|[CMFCVisualManager::DrawPushButtonWinXP](../Topic/CMFCVisualManager::DrawPushButtonWinXP.md)||  
|[CMFCVisualManager::DrawTextOnGlass](../Topic/CMFCVisualManager::DrawTextOnGlass.md)||  
|[CMFCVisualManager::GetAutoHideButtonTextColor](../Topic/CMFCVisualManager::GetAutoHideButtonTextColor.md)|자동 숨기기 단추의 텍스트 색을 검색 하는 프레임 워크에서 호출 합니다.|  
|[CMFCVisualManager::GetButtonExtraBorder](../Topic/CMFCVisualManager::GetButtonExtraBorder.md)|현재 비주얼 관리자 단추를 그리는 데 필요한 향상 된 단추 크기를 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::GetCaptionBarTextColor](../Topic/CMFCVisualManager::GetCaptionBarTextColor.md)|캡션 표시줄의 텍스트 색을 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::GetDockingTabsBordersSize](../Topic/CMFCVisualManager::GetDockingTabsBordersSize.md)|고정된 탭된 막대의 테두리 크기를 검색 하는 프레임 워크에서 호출 합니다.|  
|[CMFCVisualManager::GetHighlightedMenuItemTextColor](../Topic/CMFCVisualManager::GetHighlightedMenuItemTextColor.md)||  
|[CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)|반환에 대 한 포인터는 `CMFCVisualManager` 개체입니다.|  
|[CMFCVisualManager::GetMDITabsBordersSize](../Topic/CMFCVisualManager::GetMDITabsBordersSize.md)|MDITabs 창 테두리 크기를 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::GetMenuItemTextColor](../Topic/CMFCVisualManager::GetMenuItemTextColor.md)||  
|[CMFCVisualManager::GetMenuShadowDepth](../Topic/CMFCVisualManager::GetMenuShadowDepth.md)|폭과 메뉴 그림자의 높이 결정 하는 값을 반환 합니다.|  
|[CMFCVisualManager::GetNcBtnSize](../Topic/CMFCVisualManager::GetNcBtnSize.md)|현재 비주얼 관리자에 따라 시스템 단추의 크기를 결정 하는 프레임 워크에서 호출 합니다.  단추 캡션에 주 프레임의 명령에 매핑하는 시스템 단추입니다  **닫기**,  **최소화**,  **최대화**, 및  **복원**.|  
|[CMFCVisualManager::GetPopupMenuBorderSize](../Topic/CMFCVisualManager::GetPopupMenuBorderSize.md)|팝업 메뉴 테두리의 크기를 검색 하는 프레임 워크에서 호출 합니다.|  
|[CMFCVisualManager::GetPropertyGridGroupColor](../Topic/CMFCVisualManager::GetPropertyGridGroupColor.md)|배경색 속성 목록을 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::GetPropertyGridGroupTextColor](../Topic/CMFCVisualManager::GetPropertyGridGroupTextColor.md)|속성은 텍스트 색을 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::GetRibbonHyperlinkTextColor](../Topic/CMFCVisualManager::GetRibbonHyperlinkTextColor.md)||  
|[CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md)||  
|[CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarTextColor.md)||  
|[CMFCVisualManager::GetRibbonSliderColors](../Topic/CMFCVisualManager::GetRibbonSliderColors.md)||  
|[CMFCVisualManager::GetShowAllMenuItemsHeight](../Topic/CMFCVisualManager::GetShowAllMenuItemsHeight.md)||  
|[CMFCVisualManager::GetSmartDockingBaseGuideColors](../Topic/CMFCVisualManager::GetSmartDockingBaseGuideColors.md)||  
|[CMFCVisualManager::GetSmartDockingHighlightToneColor](../Topic/CMFCVisualManager::GetSmartDockingHighlightToneColor.md)||  
|[CMFCVisualManager::GetSmartDockingTheme](../Topic/CMFCVisualManager::GetSmartDockingTheme.md)|스마트 도킹 마커를 표시 하는 데 사용 되는 테마를 반환 합니다.|  
|[CMFCVisualManager::GetStatusBarPaneTextColor](../Topic/CMFCVisualManager::GetStatusBarPaneTextColor.md)||  
|[CMFCVisualManager::GetTabFrameColors](../Topic/CMFCVisualManager::GetTabFrameColors.md)|탭 프레임을 그릴 때 사용 하는 색 집합을 검색 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::GetTabTextColor](../Topic/CMFCVisualManager::GetTabTextColor.md)||  
|[CMFCVisualManager::GetToolbarButtonTextColor](../Topic/CMFCVisualManager::GetToolbarButtonTextColor.md)|도구 모음 단추에 텍스트의 현재 색을 검색 하는 프레임 워크에서 호출 합니다.  이 색은 현재 비주얼 관리자 및 단추 상태에 따라 다릅니다.|  
|[CMFCVisualManager::GetToolbarDisabledTextColor](../Topic/CMFCVisualManager::GetToolbarDisabledTextColor.md)|도구 모음을 사용할 수 없는 요소에 표시 되는 텍스트의 색을 결정 하는 프레임 워크에서 호출 합니다.|  
|[CMFCVisualManager::GetToolbarHighlightColor](../Topic/CMFCVisualManager::GetToolbarHighlightColor.md)||  
|[CMFCVisualManager::GetToolTipInfo](../Topic/CMFCVisualManager::GetToolTipInfo.md)||  
|[CMFCVisualManager::HasOverlappedAutoHideButtons](../Topic/CMFCVisualManager::HasOverlappedAutoHideButtons.md)|자동 숨기기 단추를 겹치는 지 여부를 지정 합니다.|  
|[CMFCVisualManager::IsDockingTabHasBorder](../Topic/CMFCVisualManager::IsDockingTabHasBorder.md)|현재 비주얼 관리자 탭된 도킹 막대 주위에 테두리를 그릴지 여부를 지정 합니다.|  
|[CMFCVisualManager::IsEmbossDisabledImage](../Topic/CMFCVisualManager::IsEmbossDisabledImage.md)|사용할 수 없는 이미지를 볼록하게 설정 여부를 지정 합니다.|  
|[CMFCVisualManager::IsFadeInactiveImage](../Topic/CMFCVisualManager::IsFadeInactiveImage.md)|비활성 이미지 도구 모음이 나 메뉴에서 흐리게 표시 되는지 여부를 결정 하는 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::IsMenuFlatLook](../Topic/CMFCVisualManager::IsMenuFlatLook.md)|메뉴 단추 모양이 병합 여부를 지정 합니다.|  
|[CMFCVisualManager::IsOfficeXPStyleMenus](../Topic/CMFCVisualManager::IsOfficeXPStyleMenus.md)|Office XP 스타일 메뉴는 비주얼 관리자를 구현 하는지 여부를 지정 합니다.|  
|[CMFCVisualManager::IsOwnerDrawCaption](../Topic/CMFCVisualManager::IsOwnerDrawCaption.md)|소유자가 그린 프레임 창의 캡션을 현재 비주얼 관리자를 구현 하는지 여부를 지정 합니다.|  
|[CMFCVisualManager::IsShadowHighlightedImage](../Topic/CMFCVisualManager::IsShadowHighlightedImage.md)|강조 표시 된 이미지에 그림자가 있는지 여부를 지정 합니다.|  
|[CMFCVisualManager::OnDrawAutoHideButtonBorder](../Topic/CMFCVisualManager::OnDrawAutoHideButtonBorder.md)|자동 숨기기 단추의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawBarGripper](../Topic/CMFCVisualManager::OnDrawBarGripper.md)|컨트롤 막대의 그리퍼를 그릴 때 프레임 워크에 의해 호출 됩니다.  사용자 컨트롤 막대를 이동 하려면 그리퍼를 클릭 해야 합니다.|  
|[CMFCVisualManager::OnDrawBrowseButton](../Topic/CMFCVisualManager::OnDrawBrowseButton.md)|편집 컨트롤에 속해 있는 찾아보기 단추를 그릴 때 프레임 워크에서 호출 \([CMFCEditBrowseCtrl Class](../../mfc/reference/cmfceditbrowsectrl-class.md)\).|  
|[CMFCVisualManager::OnDrawButtonBorder](../Topic/CMFCVisualManager::OnDrawButtonBorder.md)|도구 모음 단추의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawButtonSeparator](../Topic/CMFCVisualManager::OnDrawButtonSeparator.md)||  
|[CMFCVisualManager::OnDrawCaptionBarBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarBorder.md)|캡션 표시줄 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawCaptionBarButtonBorder](../Topic/CMFCVisualManager::OnDrawCaptionBarButtonBorder.md)||  
|[CMFCVisualManager::OnDrawCaptionBarInfoArea](../Topic/CMFCVisualManager::OnDrawCaptionBarInfoArea.md)||  
|[CMFCVisualManager::OnDrawCaptionButton](../Topic/CMFCVisualManager::OnDrawCaptionButton.md)|캡션 단추를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawCheckBox](../Topic/CMFCVisualManager::OnDrawCheckBox.md)||  
|[CMFCVisualManager::OnDrawCheckBoxEx](../Topic/CMFCVisualManager::OnDrawCheckBoxEx.md)||  
|[CMFCVisualManager::OnDrawComboBorder](../Topic/CMFCVisualManager::OnDrawComboBorder.md)|콤보 상자 단추의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawComboDropButton](../Topic/CMFCVisualManager::OnDrawComboDropButton.md)|콤보 상자 드롭다운 단추를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawControlBorder](../Topic/CMFCVisualManager::OnDrawControlBorder.md)||  
|[CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md)|기본 리본 이미지를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawEditBorder](../Topic/CMFCVisualManager::OnDrawEditBorder.md)|주위에 테두리를 그릴 때 프레임 워크에 의해 호출 된  [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) 개체입니다.|  
|[CMFCVisualManager::OnDrawExpandingBox](../Topic/CMFCVisualManager::OnDrawExpandingBox.md)||  
|[CMFCVisualManager::OnDrawFloatingToolbarBorder](../Topic/CMFCVisualManager::OnDrawFloatingToolbarBorder.md)|부동 도구 모음의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.  부동 도구 모음으로 미니 프레임 창에 나타나는 도구 모음이입니다.|  
|[CMFCVisualManager::OnDrawHeaderCtrlBorder](../Topic/CMFCVisualManager::OnDrawHeaderCtrlBorder.md)|헤더 컨트롤에 있는 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawHeaderCtrlSortArrow](../Topic/CMFCVisualManager::OnDrawHeaderCtrlSortArrow.md)|헤더 컨트롤 정렬 화살표를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawMenuArrowOnCustomizeList](../Topic/CMFCVisualManager::OnDrawMenuArrowOnCustomizeList.md)||  
|[CMFCVisualManager::OnDrawMenuBorder](../Topic/CMFCVisualManager::OnDrawMenuBorder.md)|메뉴 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md)||  
|[CMFCVisualManager::OnDrawMenuItemButton](../Topic/CMFCVisualManager::OnDrawMenuItemButton.md)||  
|[CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md)||  
|[CMFCVisualManager::OnDrawMenuResizeBar](../Topic/CMFCVisualManager::OnDrawMenuResizeBar.md)||  
|[CMFCVisualManager::OnDrawMenuScrollButton](../Topic/CMFCVisualManager::OnDrawMenuScrollButton.md)|메뉴 스크롤 단추를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawMenuShadow](../Topic/CMFCVisualManager::OnDrawMenuShadow.md)||  
|[CMFCVisualManager::OnDrawMenuSystemButton](../Topic/CMFCVisualManager::OnDrawMenuSystemButton.md)|시스템 메뉴 단추를 그릴 때 프레임 워크에 의해 호출  **닫기**,  **최소화**,  **최대화**, 및  **복원**.|  
|[CMFCVisualManager::OnDrawMiniFrameBorder](../Topic/CMFCVisualManager::OnDrawMiniFrameBorder.md)||  
|[CMFCVisualManager::OnDrawOutlookBarSplitter](../Topic/CMFCVisualManager::OnDrawOutlookBarSplitter.md)|Outlook 표시줄에 분할자를 그릴 때 프레임 워크에 의해 호출 됩니다.  분할자 그룹 컨트롤에 사용 되는 가로 막대입니다.|  
|[CMFCVisualManager::OnDrawOutlookPageButtonBorder](../Topic/CMFCVisualManager::OnDrawOutlookPageButtonBorder.md)|Outlook 페이지 단추의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.  Outlook 표시줄 창에 표시할 수 있는 보다 많은 단추가 포함 되어 있는 경우 outlook 페이지 단추에 표시 됩니다.|  
|[CMFCVisualManager::OnDrawPaneBorder](../Topic/CMFCVisualManager::OnDrawPaneBorder.md)|테두리를 그릴 때 프레임 워크에 의해 호출 된 [CPane Class](../../mfc/reference/cpane-class.md).|  
|[CMFCVisualManager::OnDrawPaneCaption](../Topic/CMFCVisualManager::OnDrawPaneCaption.md)|캡션을 그릴 때 프레임 워크에 의해 호출 된 `CPane`.|  
|[CMFCVisualManager::OnDrawPaneDivider](../Topic/CMFCVisualManager::OnDrawPaneDivider.md)||  
|[CMFCVisualManager::OnDrawPopupWindowBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowButtonBorder](../Topic/CMFCVisualManager::OnDrawPopupWindowButtonBorder.md)||  
|[CMFCVisualManager::OnDrawPopupWindowCaption](../Topic/CMFCVisualManager::OnDrawPopupWindowCaption.md)||  
|[CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md)|이 그릴 때 프레임 워크에 의해 호출의  **기본 단추** 리본 메뉴.|  
|[CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md)|리본 단추 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonButtonsGroup](../Topic/CMFCVisualManager::OnDrawRibbonButtonsGroup.md)|리본 메뉴에 단추 그룹을 그리면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md)|프레임 워크에서 주 프레임의 캡션 그리면 되지만 리본 표시줄 프레임을 통합 하는 경우 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md)|리본 메뉴 모음에 있는 캡션 단추를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md)|리본 범주를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonCategoryCaption](../Topic/CMFCVisualManager::OnDrawRibbonCategoryCaption.md)|리본 범주에 대 한 캡션을 그리면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonCategoryScroll](../Topic/CMFCVisualManager::OnDrawRibbonCategoryScroll.md)||  
|[CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md)|리본 범주에 대 한 탭을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonCheckBoxOnList](../Topic/CMFCVisualManager::OnDrawRibbonCheckBoxOnList.md)||  
|[CMFCVisualManager::OnDrawRibbonColorPaletteBox](../Topic/CMFCVisualManager::OnDrawRibbonColorPaletteBox.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonContext.md)||  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md)|리본 메뉴 창의 기본 단추를 그릴 때 프레임 워크에 의해 호출 됩니다.  너무 작은 리본 요소를 표시할 수 있도록 사용자가 리본 패널 축소할 때 기본 단추로 표시 됩니다.  기본 단추 대신 그려지고 리본 요소 드롭다운 메뉴에 항목으로 추가 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButtonIndicator.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryBorder](../Topic/CMFCVisualManager::OnDrawRibbonGalleryBorder.md)||  
|[CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md)||  
|[CMFCVisualManager::OnDrawRibbonKeyTip](../Topic/CMFCVisualManager::OnDrawRibbonKeyTip.md)||  
|[CMFCVisualManager::OnDrawRibbonLabel](../Topic/CMFCVisualManager::OnDrawRibbonLabel.md)|리본 레이블을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelButtonBorder.md)|위치에 있는 리본 메뉴 단추는 테두리를 그릴 때 프레임 워크에 의해 호출 된  **주** 패널.  **주** 패널 수를 클릭할 때 나타나는 패널의  **기본 단추**.|  
|[CMFCVisualManager::OnDrawRibbonMainPanelFrame](../Topic/CMFCVisualManager::OnDrawRibbonMainPanelFrame.md)|주위의 프레임을 그릴 때 프레임 워크에 의해 호출 된  **주** 패널입니다.|  
|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md)||  
|[CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md)|리본 패널을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md)|리본 패널의 캡션을 그리면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md)|이 그릴 때 프레임 워크에 의해 호출 된  [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) 개체.|  
|[CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator](../Topic/CMFCVisualManager::OnDrawRibbonQuickAccessToolBarSeparator.md)|이 리본 구분 기호를 그릴 때 프레임 워크에서 호출  **빠른 액세스 도구 모음**.|  
|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md)|최근에 사용한 파일 목록 주위에 프레임을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md)|채널을 그리면 프레임 워크에서 호출을  [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md) 개체입니다.|  
|[CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md)|엄지를 그리면 프레임 워크에서 호출을 `CMFCRibbonSlider` 개체입니다.|  
|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md)|확대\/축소 단추를 그릴 때 프레임 워크에 의해 호출 된 `CMFCRibbonSlider` 개체입니다.|  
|[CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md)|리본 메뉴의 상태 표시줄 창 그리면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md)|리본 탭의 집합을 주위에 프레임을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawScrollButtons](../Topic/CMFCVisualManager::OnDrawScrollButtons.md)||  
|[CMFCVisualManager::OnDrawSeparator](../Topic/CMFCVisualManager::OnDrawSeparator.md)|구분 기호를 그릴 때 프레임 워크에 의해 호출 됩니다.  구분 기호 그룹 아이콘을 구분 하려면 컨트롤 막대에 주로 사용 됩니다.|  
|[CMFCVisualManager::OnDrawShowAllMenuItems](../Topic/CMFCVisualManager::OnDrawShowAllMenuItems.md)||  
|[CMFCVisualManager::OnDrawSpinButtons](../Topic/CMFCVisualManager::OnDrawSpinButtons.md)|스핀 단추를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawSplitterBorder](../Topic/CMFCVisualManager::OnDrawSplitterBorder.md)|분할 창의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawSplitterBox](../Topic/CMFCVisualManager::OnDrawSplitterBox.md)|분할 끌어서 상자 분할 창이 그리면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnDrawStatusBarPaneBorder](../Topic/CMFCVisualManager::OnDrawStatusBarPaneBorder.md)|상태 표시줄 창의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawStatusBarProgress](../Topic/CMFCVisualManager::OnDrawStatusBarProgress.md)|상태 표시줄 진행률 표시기를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManager::OnDrawStatusBarSizeBox.md)|상태 표시줄 크기 상자를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawTab](../Topic/CMFCVisualManager::OnDrawTab.md)|이 그릴 때 프레임 워크에 의해 호출 된  [CMFCTabCtrl](../../mfc/reference/cmfctabctrl-class.md) 개체.|  
|[CMFCVisualManager::OnDrawTabCloseButton](../Topic/CMFCVisualManager::OnDrawTabCloseButton.md)|이 그릴 때 프레임 워크에 의해 호출 된  **닫기** 활성 탭 단추.|  
|[CMFCVisualManager::OnDrawTabContent](../Topic/CMFCVisualManager::OnDrawTabContent.md)|내부 탭 \(이미지, 텍스트\)를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawTabsButtonBorder](../Topic/CMFCVisualManager::OnDrawTabsButtonBorder.md)|탭 버튼의 테두리를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawTask](../Topic/CMFCVisualManager::OnDrawTask.md)|작업 창에서 작업 그리면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnDrawTasksGroupAreaBorder](../Topic/CMFCVisualManager::OnDrawTasksGroupAreaBorder.md)|이 작업창에서 그룹 영역 주위에 테두리를 그립니다 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawTasksGroupCaption](../Topic/CMFCVisualManager::OnDrawTasksGroupCaption.md)|작업 창에서 작업 그룹에 대 한 캡션을 그리면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnDrawTasksGroupIcon](../Topic/CMFCVisualManager::OnDrawTasksGroupIcon.md)||  
|[CMFCVisualManager::OnDrawTearOffCaption](../Topic/CMFCVisualManager::OnDrawTearOffCaption.md)|분리 된 캡션을 분리 막대를 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnDrawToolBoxFrame](../Topic/CMFCVisualManager::OnDrawToolBoxFrame.md)||  
|[CMFCVisualManager::OnEraseMDIClientArea](../Topic/CMFCVisualManager::OnEraseMDIClientArea.md)|MDI 클라이언트 영역을 지울 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnErasePopupWindowButton](../Topic/CMFCVisualManager::OnErasePopupWindowButton.md)||  
|[CMFCVisualManager::OnEraseTabsArea](../Topic/CMFCVisualManager::OnEraseTabsArea.md)|탭 창에서 탭 영역을 지울 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnEraseTabsButton](../Topic/CMFCVisualManager::OnEraseTabsButton.md)|아이콘 및 단추 탭의 텍스트를 지울 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnEraseTabsFrame](../Topic/CMFCVisualManager::OnEraseTabsFrame.md)|탭 프레임을 지울 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnFillAutoHideButtonBackground](../Topic/CMFCVisualManager::OnFillAutoHideButtonBackground.md)|자동 숨기기 단추의 배경을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillBarBackground](../Topic/CMFCVisualManager::OnFillBarBackground.md)|이 컨트롤 막대의 배경을 채우는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillButtonInterior](../Topic/CMFCVisualManager::OnFillButtonInterior.md)|도구 모음 단추의 배경을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillCaptionBarButton](../Topic/CMFCVisualManager::OnFillCaptionBarButton.md)||  
|[CMFCVisualManager::OnFillCommandsListBackground](../Topic/CMFCVisualManager::OnFillCommandsListBackground.md)|속한 명령 목록에는 사용자 지정 대화 상자를 포함 하는 도구 모음 단추의 배경을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillHeaderCtrlBackground](../Topic/CMFCVisualManager::OnFillHeaderCtrlBackground.md)|이 헤더 컨트롤의 배경을 채우는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillMiniFrameCaption](../Topic/CMFCVisualManager::OnFillMiniFrameCaption.md)|미니 프레임 창의 캡션을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillOutlookBarCaption](../Topic/CMFCVisualManager::OnFillOutlookBarCaption.md)|배경에 Outlook 표시줄 캡션의 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillOutlookPageButton](../Topic/CMFCVisualManager::OnFillOutlookPageButton.md)|Outlook 페이지 단추의 내부를 채울 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnFillPopupWindowBackground](../Topic/CMFCVisualManager::OnFillPopupWindowBackground.md)|팝업 창의 배경을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md)|리본 메뉴 단추를 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillRibbonEdit](../Topic/CMFCVisualManager::OnFillRibbonEdit.md)|리본 편집 컨트롤의 내부를 채우는 경우 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillRibbonMainPanelButton](../Topic/CMFCVisualManager::OnFillRibbonMainPanelButton.md)|내부에 있는 리본 메뉴 단추를 채우면 프레임 워크에 의해 호출 된  **주** 패널입니다.|  
|[CMFCVisualManager::OnFillRibbonMenuFrame](../Topic/CMFCVisualManager::OnFillRibbonMenuFrame.md)|기본 리본 패널의 메뉴 프레임을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md)||  
|[CMFCVisualManager::OnFillSplitterBackground](../Topic/CMFCVisualManager::OnFillSplitterBackground.md)|분할 창의 배경을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillTab](../Topic/CMFCVisualManager::OnFillTab.md)|배경 탭을 채우면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnFillTasksGroupInterior](../Topic/CMFCVisualManager::OnFillTasksGroupInterior.md)|내부를 채우면 프레임 워크에서 호출을  [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 개체에  [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md).|  
|[CMFCVisualManager::OnFillTasksPaneBackground](../Topic/CMFCVisualManager::OnFillTasksPaneBackground.md)|배경색을 채우면 프레임 워크에서 호출을 `CMFCTasksPane` 제어 합니다.|  
|[CMFCVisualManager::OnHighlightMenuItem](../Topic/CMFCVisualManager::OnHighlightMenuItem.md)|강조 표시 된 메뉴 항목을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnHighlightRarelyUsedMenuItems](../Topic/CMFCVisualManager::OnHighlightRarelyUsedMenuItems.md)|강조를 그릴 때 프레임 워크 및 거의 사용된 되지 않는 메뉴 항목에서 호출 됩니다.|  
|[CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md)|비클라이언트 영역을 그릴 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::OnSetWindowRegion](../Topic/CMFCVisualManager::OnSetWindowRegion.md)|프레임 및 팝업 메뉴를 포함 하는 영역을 설정 하면 프레임 워크에서 호출 됩니다.|  
|[CMFCVisualManager::OnUpdateSystemColors](../Topic/CMFCVisualManager::OnUpdateSystemColors.md)|시스템 색상 설정이 변경 될 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCVisualManager::RedrawAll](../Topic/CMFCVisualManager::RedrawAll.md)|응용 프로그램에서 모든 컨트롤 막대를 다시 그립니다.|  
|[CMFCVisualManager::RibbonCategoryColorToRGB](../Topic/CMFCVisualManager::RibbonCategoryColorToRGB.md)||  
|[CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)|기본 비주얼 관리자를 설정합니다.|  
|[CMFCVisualManager::SetEmbossDisabledImage](../Topic/CMFCVisualManager::SetEmbossDisabledImage.md)|엠보스 이미지 도구 모음을 사용할 수 없는 모드를 사용할 수 있거나.|  
|[CMFCVisualManager::SetFadeInactiveImage](../Topic/CMFCVisualManager::SetFadeInactiveImage.md)|비활성 이미지에 대 한 조명 효과 메뉴 또는 도구 모음에서 사용할 수 있거나.|  
|[CMFCVisualManager::SetMenuFlatLook](../Topic/CMFCVisualManager::SetMenuFlatLook.md)|응용 프로그램 메뉴 단추 모양이 병합 여부를 나타내는 플래그를 설정 합니다.|  
|[CMFCVisualManager::SetMenuShadowDepth](../Topic/CMFCVisualManager::SetMenuShadowDepth.md)|너비와 높이의 메뉴 그림자를 설정합니다.|  
|[CMFCVisualManager::SetShadowHighlightedImage](../Topic/CMFCVisualManager::SetShadowHighlightedImage.md)|강조 표시 된 이미지를 렌더링할 때 그림자를 표시할지 여부를 나타내는 플래그를 설정 합니다.|  
  
## 설명  
 때문에 `CMFCVisualManager` 클래스는 응용 프로그램의 GUI를 제어 하 고 각 응용 프로그램의 인스턴스 중 하나를 가질 수는 `CMFCVisualManager`, 또는 파생 클래스의 인스턴스 하나에서 `CMFCVisualManager`.  응용 프로그램 없이 작동할 수 있는 `CMFCVisualManager`.  정적 메서드를 사용 `GetInstance` 에 대 한 포인터는 현재 `CMFCVisualManager`\-개체를 파생 합니다.  
  
 응용 프로그램의 모양을 변경 하려면 모든 응용 프로그램의 시각적 요소를 그리기 위한 메서드를 제공 하는 다른 클래스를 사용 해야 합니다.  이러한 클래스의 예로 [CMFCVisualManagerOfficeXP Class](../../mfc/reference/cmfcvisualmanagerofficexp-class.md), [CMFCVisualManagerOffice2003 Class](../../mfc/reference/cmfcvisualmanageroffice2003-class.md), 및 [CMFCVisualManagerOffice2007 Class](../../mfc/reference/cmfcvisualmanageroffice2007-class.md).  응용 프로그램의 모양을 변경할 때 이러한 비주얼 관리자 중 하나를 메서드에 전달 `SetDefaultManager`.  어떻게 응용 프로그램 Microsoft Office 2003의 모양을 모방 하는 방법을 보여 주는 예제를 보려면를 참조 하십시오. [CMFCVisualManagerOffice2003 Class](../../mfc/reference/cmfcvisualmanageroffice2003-class.md).  
  
 모든 드로잉 메서드는 가상 메서드입니다.  이 응용 프로그램의 GUI에 대 한 사용자 지정 비주얼 스타일을 만들 수 있습니다.  비주얼 스타일을 만들 경우 비주얼 관리자 클래스 중 하나에서 클래스를 파생 및 변경 하려는 드로잉 메서드를 재정의 합니다.  
  
## 예제  
 이 샘플에서는 인스턴스화하는 표준 및 사용자 지정 `CMFCVisualManager` 개체입니다.  
  
```  
void CMFCSkinsApp::SetSkin (int iIndex)  
{   // destroy the current visual manager  
   if (CMFCVisualManager::GetInstance () != NULL)  
   {  
      delete CMFCVisualManager::GetInstance ();  
   }  
   switch (iIndex)  
  {  
   case 0:  
      CMFCVisualManager::GetInstance (); // create the standard visual manager  
      break;  
   case 1:  
      new CMyVisualManager (); // create the first custom visual manager  
      break;  
   case 2:  
      new CMacStyle ();  // create the second custom visual manager  
      break;  
   }  
  
   // access the manager and set it properly  
   CMFCVisualManager::GetInstance ()->SetLook2000 ();  
   CMFCVisualManager::GetInstance ()->RedrawAll ();  
}  
```  
  
## 예제  
 다음 예제에서는 기본 값을 검색 하는 방법을 보여 줍니다.을 `CMFCVisualManager` 개체입니다.  이 코드 조각에 속하지는  [작업 창 예제](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TasksPane#1](../../mfc/reference/codesnippet/CPP/cmfcvisualmanager-class_1.h)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxvisualmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager::GetInstance](../Topic/CMFCVisualManager::GetInstance.md)   
 [시각화 관리자](../../mfc/visualization-manager.md)