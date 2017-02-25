---
title: "CMFCVisualManagerWindows7 Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxvisualmanagerwindows7/CMFCVisualManagerWindows7"
  - "CMFCVisualManagerWindows7"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCVisualManagerWindows7 class"
ms.assetid: e8d87df1-0c09-4b58-8ade-4e911f796e42
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMFCVisualManagerWindows7 Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCVisualManagerWindows7` 응용 프로그램의 모습을 [!INCLUDE[win7](../../build/includes/win7_md.md)] 응용 프로그램.  
  
## 구문  
  
```  
class CMFCVisualManagerWindows7 : public CMFCVisualManagerWindows;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCVisualManagerWindows7::CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::CMFCVisualManagerWindows7.md)|기본 생성자입니다.|  
|[CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7](../Topic/CMFCVisualManagerWindows7::~CMFCVisualManagerWindows7.md)|기본 소멸자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CMFCVisualManagerWindows7::CleanStyle`|현재 비주얼 스타일을 지우고 기본 시각적 스타일을 다시 설정 합니다.|  
|`CMFCVisualManagerWindows7::CleanUp`|사용자 인터페이스에서 개체를 모두 지우고 메뉴를 다시 설정 합니다.|  
|`CMFCVisualManagerWindows7::DrawNcBtn`|단추가 비클라이언트 영역에 프레임을 그립니다.  프레임 워크 사용 최소화를 그리려면이 메서드를 최대화, 닫기 및 창 프레임의 오른쪽 위 모서리에서 복원 단추  프로그램 비 Aero 테마를 사용 하는 경우이 메서드는 호출 되지 않습니다.|  
|`CMFCVisualManagerWindows7::DrawNcText`|프레임에서 비클라이언트 영역에 텍스트를 그립니다.  프레임 워크 응용 프로그램 제목 프레임 창 맨 위에 있는 제목 표시줄을 그리려면이 메서드를 사용 합니다.|  
|`CMFCVisualManagerWindows7::DrawSeparator`|구분 기호를 그립니다 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md).|  
|`CMFCVisualManagerWindows7::GetRibbonBar`|검색은 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md) 사용자 인터페이스에 연결 합니다.|  
|[CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor](../Topic/CMFCVisualManagerWindows7::GetRibbonEditBackgroundColor.md)|리본 편집 상자 배경색을 가져옵니다.|  
|`CMFCVisualManagerWindows7::GetRibbonPopupBorderSize`|[CMFCVisualManager::GetRibbonPopupBorderSize](../Topic/CMFCVisualManager::GetRibbonPopupBorderSize.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarChevronOffset`|[CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarChevronOffset.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::GetRibbonQuickAccessToolBarRightMargin`|[CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin](../Topic/CMFCVisualManager::GetRibbonQuickAccessToolBarRightMargin.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::IsHighlightWholeMenuItem`|[CMFCVisualManagerWindows::IsHighlightWholeMenuItem](../Topic/CMFCVisualManagerWindows::IsHighlightWholeMenuItem.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::IsOwnerDrawMenuCheck`|[CMFCVisualManager::IsOwnerDrawMenuCheck](../Topic/CMFCVisualManager::IsOwnerDrawMenuCheck.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::IsRibbonPresent`|결정 여부는 `CMFCRibbonBar` 존재 하 고 있습니다.|  
|`CMFCVisualManagerWindows7::OnDrawButtonBorder`|[CMFCVisualManagerWindows::OnDrawButtonBorder](../Topic/CMFCVisualManagerWindows::OnDrawButtonBorder.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawCheckBoxEx`|[CMFCVisualManagerWindows::OnDrawCheckBoxEx](../Topic/CMFCVisualManagerWindows::OnDrawCheckBoxEx.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawComboDropButton`|[CMFCVisualManagerWindows::OnDrawComboDropButton](../Topic/CMFCVisualManagerWindows::OnDrawComboDropButton.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawDefaultRibbonImage`|[CMFCVisualManager::OnDrawDefaultRibbonImage](../Topic/CMFCVisualManager::OnDrawDefaultRibbonImage.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawMenuBorder`|[CMFCVisualManagerWindows::OnDrawMenuBorder](../Topic/CMFCVisualManagerWindows::OnDrawMenuBorder.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawMenuCheck`|[CMFCVisualManager::OnDrawMenuCheck](../Topic/CMFCVisualManager::OnDrawMenuCheck.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawMenuLabel`|[CMFCVisualManager::OnDrawMenuLabel](../Topic/CMFCVisualManager::OnDrawMenuLabel.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRadioButton`|`CMFCVisualManager::OnDrawRadioButton`를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonApplicationButton`|[CMFCVisualManager::OnDrawRibbonApplicationButton](../Topic/CMFCVisualManager::OnDrawRibbonApplicationButton.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonButtonBorder`|[CMFCVisualManager::OnDrawRibbonButtonBorder](../Topic/CMFCVisualManager::OnDrawRibbonButtonBorder.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaption`|[CMFCVisualManager::OnDrawRibbonCaption](../Topic/CMFCVisualManager::OnDrawRibbonCaption.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCaptionButton`|[CMFCVisualManager::OnDrawRibbonCaptionButton](../Topic/CMFCVisualManager::OnDrawRibbonCaptionButton.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategory`|[CMFCVisualManager::OnDrawRibbonCategory](../Topic/CMFCVisualManager::OnDrawRibbonCategory.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonCategoryTab`|[CMFCVisualManager::OnDrawRibbonCategoryTab](../Topic/CMFCVisualManager::OnDrawRibbonCategoryTab.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonDefaultPaneButton`|[CMFCVisualManager::OnDrawRibbonDefaultPaneButton](../Topic/CMFCVisualManager::OnDrawRibbonDefaultPaneButton.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonGalleryButton`|[CMFCVisualManager::OnDrawRibbonGalleryButton](../Topic/CMFCVisualManager::OnDrawRibbonGalleryButton.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonLaunchButton`|`CMFCVisualManager::OnDrawRibbonLaunchButton`를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonMenuCheckFrame`|[CMFCVisualManager::OnDrawRibbonMenuCheckFrame](../Topic/CMFCVisualManager::OnDrawRibbonMenuCheckFrame.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanel`|[CMFCVisualManager::OnDrawRibbonPanel](../Topic/CMFCVisualManager::OnDrawRibbonPanel.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonPanelCaption`|[CMFCVisualManager::OnDrawRibbonPanelCaption](../Topic/CMFCVisualManager::OnDrawRibbonPanelCaption.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonProgressBar`|[CMFCVisualManager::OnDrawRibbonProgressBar](../Topic/CMFCVisualManager::OnDrawRibbonProgressBar.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonRecentFilesFrame`|[CMFCVisualManager::OnDrawRibbonRecentFilesFrame](../Topic/CMFCVisualManager::OnDrawRibbonRecentFilesFrame.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderChannel`|[CMFCVisualManager::OnDrawRibbonSliderChannel](../Topic/CMFCVisualManager::OnDrawRibbonSliderChannel.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderThumb`|[CMFCVisualManager::OnDrawRibbonSliderThumb](../Topic/CMFCVisualManager::OnDrawRibbonSliderThumb.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonSliderZoomButton`|[CMFCVisualManager::OnDrawRibbonSliderZoomButton](../Topic/CMFCVisualManager::OnDrawRibbonSliderZoomButton.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonStatusBarPane`|[CMFCVisualManager::OnDrawRibbonStatusBarPane](../Topic/CMFCVisualManager::OnDrawRibbonStatusBarPane.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawRibbonTabsFrame`|[CMFCVisualManager::OnDrawRibbonTabsFrame](../Topic/CMFCVisualManager::OnDrawRibbonTabsFrame.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnDrawStatusBarSizeBox`|[CMFCVisualManagerWindows::OnDrawStatusBarSizeBox](../Topic/CMFCVisualManagerWindows::OnDrawStatusBarSizeBox.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnFillBarBackground`|[CMFCVisualManagerWindows::OnFillBarBackground](../Topic/CMFCVisualManagerWindows::OnFillBarBackground.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnFillButtonInterior`|[CMFCVisualManagerWindows::OnFillButtonInterior](../Topic/CMFCVisualManagerWindows::OnFillButtonInterior.md)를 재정의합니다.|  
|[CMFCVisualManagerWindows7::OnFillMenuImageRect](../Topic/CMFCVisualManagerWindows7::OnFillMenuImageRect.md)|프레임 워크 영역 주위로 메뉴 항목 이미지를 작성할 때이 메서드를 호출 합니다.|  
|`CMFCVisualManagerWindows7::OnFillRibbonButton`|[CMFCVisualManager::OnFillRibbonButton](../Topic/CMFCVisualManager::OnFillRibbonButton.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnFillRibbonQuickAccessToolBarPopup`|[CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup](../Topic/CMFCVisualManager::OnFillRibbonQuickAccessToolBarPopup.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnHighlightMenuItem`|[CMFCVisualManagerWindows::OnHighlightMenuItem](../Topic/CMFCVisualManagerWindows::OnHighlightMenuItem.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnNcActivate`|[CMFCVisualManager::OnNcActivate](../Topic/CMFCVisualManager::OnNcActivate.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnNcPaint`|[CMFCVisualManager::OnNcPaint](../Topic/CMFCVisualManager::OnNcPaint.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::OnUpdateSystemColors`|[CMFCVisualManagerWindows::OnUpdateSystemColors](../Topic/CMFCVisualManagerWindows::OnUpdateSystemColors.md)를 재정의합니다.|  
|`CMFCVisualManagerWindows7::SetResourceHandle`|비주얼 관리자의 특성을 설명 하는 리소스 핸들을 설정 합니다.|  
|`CMFCVisualManagerWindows7::SetStyle`|색 구성표를 설정 하는 `CMFCVisualManagerWindows7` GUI.|  
  
## 설명  
 사용 된 `CMFCVisualManagerWindows7` 기본값을 모방 하는 응용 프로그램의 모양을 변경 하려면 클래스 [!INCLUDE[win7](../../build/includes/win7_md.md)] 응용 프로그램.  이 클래스를 응용 프로그램의 Windows 버전에서 실행 되는 경우 유효 하지 않습니다 이전 보다 [!INCLUDE[win7](../../build/includes/win7_md.md)].  이 시나리오에서는 기본 비주얼 관리자에서 정의 된 응용 프로그램을 사용  [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md).  
  
 Cmfcvisualmanagerwindows7는 여러 메서드를 상속 된 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md) , `CMFCVisualManager` 클래스.  이전 섹션에서 설명한 방법에 새 메서드는는 `CMFCVisualManagerWindows7` 클래스입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
 [CMFCVisualManager](../../mfc/reference/cmfcvisualmanager-class.md)  
  
 [CMFCVisualManagerOfficeXP](../../mfc/reference/cmfcvisualmanagerofficexp-class.md)  
  
 [CMFCVisualManagerWindows](../../mfc/reference/cmfcvisualmanagerwindows-class.md)  
  
 `CMFCVisualManagerWindows7`  
  
## 요구 사항  
 **헤더:**  afxvisualmanagerwindows7.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md)   
 [CMFCVisualManagerWindows Class](../../mfc/reference/cmfcvisualmanagerwindows-class.md)   
 [CMFCVisualManager::SetDefaultManager](../Topic/CMFCVisualManager::SetDefaultManager.md)