---
title: "CMFCRibbonBar Class | Microsoft Docs"
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
  - "CMFCRibbonBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonBar class"
ms.assetid: a65d06fa-1a28-4cc0-8971-bc9d7c9198fe
caps.latest.revision: 41
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonBar` 클래스는 Office 2007에서 사용한 것과 비슷한 리본 표시줄을 구현합니다.  
  
## 구문  
  
```  
class CMFCRibbonBar : public CPane  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CMFCRibbonBar::CMFCRibbonBar`|기본 생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonBar::ActivateContextCategory](../Topic/CMFCRibbonBar::ActivateContextCategory.md)|이미 표시된 컨텍스트 범주를 활성화합니다.|  
|[CMFCRibbonBar::AddCategory](../Topic/CMFCRibbonBar::AddCategory.md)|리본 메뉴에 새 리본 범주를 추가합니다.|  
|[CMFCRibbonBar::AddContextCategory](../Topic/CMFCRibbonBar::AddContextCategory.md)|컨텍스트 범주를 추가합니다.|  
|[CMFCRibbonBar::AddMainCategory](../Topic/CMFCRibbonBar::AddMainCategory.md)|새 기본 리본 범주를 추가합니다.|  
|[CMFCRibbonBar::AddPrintPreviewCategory](../Topic/CMFCRibbonBar::AddPrintPreviewCategory.md)||  
|[CMFCRibbonBar::AddQATOnlyCategory](../Topic/CMFCRibbonBar::AddQATOnlyCategory.md)||  
|[CMFCRibbonBar::AddToTabs](../Topic/CMFCRibbonBar::AddToTabs.md)|리본 표시줄 오른쪽에 리본 요소를 추가합니다.|  
|[CMFCRibbonBar::CreateEx](../Topic/CMFCRibbonBar::CreateEx.md)|컨트롤 막대를 만들고 [CPane](../../mfc/reference/cpane-class.md) 개체에 연결합니다.  \([CPane::CreateEx](../Topic/CPane::CreateEx.md)를 재정의합니다.\)|  
|[CMFCRibbonBar::Create](../Topic/CMFCRibbonBar::Create.md)|리본 표시줄 컨트롤을 만들고 리본 표시줄에 연결합니다.|  
|[CMFCRibbonBar::DeactivateKeyboardFocus](../Topic/CMFCRibbonBar::DeactivateKeyboardFocus.md)||  
|[CMFCRibbonBar::DrawMenuImage](../Topic/CMFCRibbonBar::DrawMenuImage.md)||  
|[CMFCRibbonBar::DWMCompositionChanged](../Topic/CMFCRibbonBar::DWMCompositionChanged.md)||  
|[CMFCRibbonBar::EnableKeyTips](../Topic/CMFCRibbonBar::EnableKeyTips.md)|리본 컨트롤에 대한 키 팁을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCRibbonBar::EnablePrintPreview](../Topic/CMFCRibbonBar::EnablePrintPreview.md)|**인쇄 미리 보기** 탭을 사용하도록 설정합니다.|  
|[CMFCRibbonBar::EnableToolTips](../Topic/CMFCRibbonBar::EnableToolTips.md)|리본 표시줄에서 도구 설명 및 도구 설명에 대한 설명을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCRibbonBar::FindByData](../Topic/CMFCRibbonBar::FindByData.md)|사용자가 지정하는 데이터를 사용하여 리본 요소를 찾습니다.|  
|[CMFCRibbonBar::FindByID](../Topic/CMFCRibbonBar::FindByID.md)|지정된 명령 ID를 가진 리본 요소를 찾습니다.|  
|[CMFCRibbonBar::FindCategoryIndexByData](../Topic/CMFCRibbonBar::FindCategoryIndexByData.md)|사용자 정의 데이터를 포함하는 리본 범주의 인덱스를 찾습니다.|  
|[CMFCRibbonBar::ForceRecalcLayout](../Topic/CMFCRibbonBar::ForceRecalcLayout.md)||  
|[CMFCRibbonBar::GetActiveCategory](../Topic/CMFCRibbonBar::GetActiveCategory.md)|활성 범주에 대한 포인터를 가져옵니다.|  
|[CMFCRibbonBar::GetCaptionHeight](../Topic/CMFCRibbonBar::GetCaptionHeight.md)|캡션 높이를 반환합니다.  \([CBasePane::GetCaptionHeight](../Topic/CBasePane::GetCaptionHeight.md)를 재정의합니다.\)|  
|[CMFCRibbonBar::GetCategory](../Topic/CMFCRibbonBar::GetCategory.md)|지정된 인덱스에 있는 범주에 대한 포인터를 가져옵니다.|  
|[CMFCRibbonBar::GetCategoryCount](../Topic/CMFCRibbonBar::GetCategoryCount.md)|리본 표시줄에서 리본 범주 수를 가져옵니다.|  
|[CMFCRibbonBar::GetCategoryHeight](../Topic/CMFCRibbonBar::GetCategoryHeight.md)||  
|[CMFCRibbonBar::GetCategoryIndex](../Topic/CMFCRibbonBar::GetCategoryIndex.md)|리본 범주의 인덱스를 반환합니다.|  
|[CMFCRibbonBar::GetContextName](../Topic/CMFCRibbonBar::GetContextName.md)|ID를 사용하여 지정한 컨텍스트 범주 캡션 이름을 검색합니다.|  
|[CMFCRibbonBar::GetDroppedDown](../Topic/CMFCRibbonBar::GetDroppedDown.md)||  
|[CMFCRibbonBar::GetElementsByID](../Topic/CMFCRibbonBar::GetElementsByID.md)|지정된 ID를 가진 모든 리본 요소에 대한 포인터를 포함하는 배열을 가져옵니다.|  
|[CMFCRibbonBar::GetApplicationButton](../Topic/CMFCRibbonBar::GetApplicationButton.md)|리본 단추에 대한 포인터를 가져옵니다.|  
|[CMFCRibbonBar::GetFocused](../Topic/CMFCRibbonBar::GetFocused.md)|포커스가 지정된 요소를 반환합니다.|  
|[CMFCRibbonBar::GetHideFlags](../Topic/CMFCRibbonBar::GetHideFlags.md)||  
|[CMFCRibbonBar::GetItemIDsList](../Topic/CMFCRibbonBar::GetItemIDsList.md)||  
|[CMFCRibbonBar::GetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::GetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelCurrent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelCurrent.md)||  
|[CMFCRibbonBar::GetKeyboardNavLevelParent](../Topic/CMFCRibbonBar::GetKeyboardNavLevelParent.md)||  
|[CMFCRibbonBar::GetMainCategory](../Topic/CMFCRibbonBar::GetMainCategory.md)|현재 선택된 리본 범주에 대한 포인터를 반환합니다.|  
|[CMFCRibbonBar::GetQATCommandsLocation](../Topic/CMFCRibbonBar::GetQATCommandsLocation.md)||  
|[CMFCRibbonBar::GetQATDroppedDown](../Topic/CMFCRibbonBar::GetQATDroppedDown.md)||  
|[CMFCRibbonBar::GetQuickAccessCommands](../Topic/CMFCRibbonBar::GetQuickAccessCommands.md)|빠른 실행 도구 모음에 나타나는 모든 요소의 명령 ID를 포함하는 목록을 채웁니다.|  
|[CMFCRibbonBar::GetQuickAccessToolbarLocation](../Topic/CMFCRibbonBar::GetQuickAccessToolbarLocation.md)||  
|[CMFCRibbonBar::GetTabTrancateRatio](../Topic/CMFCRibbonBar::GetTabTrancateRatio.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthLargeImage](../Topic/CMFCRibbonBar::GetTooltipFixedWidthLargeImage.md)||  
|[CMFCRibbonBar::GetTooltipFixedWidthRegular](../Topic/CMFCRibbonBar::GetTooltipFixedWidthRegular.md)||  
|[CMFCRibbonBar::GetVisibleCategoryCount](../Topic/CMFCRibbonBar::GetVisibleCategoryCount.md)||  
|[CMFCRibbonBar::HideAllContextCategories](../Topic/CMFCRibbonBar::HideAllContextCategories.md)|표시되고 활성 상태인 모든 범주를 숨깁니다.|  
|[CMFCRibbonBar::HideKeyTips](../Topic/CMFCRibbonBar::HideKeyTips.md)||  
|[CMFCRibbonBar::HitTest](../Topic/CMFCRibbonBar::HitTest.md)|리본 표시줄 클라이언트 좌표의 지정된 지점에 있는 리본 요소에 대한 포인터를 찾습니다.|  
|[CMFCRibbonBar::IsKeyTipEnabled](../Topic/CMFCRibbonBar::IsKeyTipEnabled.md)|키 팁을 사용할지 결정합니다.|  
|[CMFCRibbonBar::IsMainRibbonBar](../Topic/CMFCRibbonBar::IsMainRibbonBar.md)||  
|[CMFCRibbonBar::IsPrintPreviewEnabled](../Topic/CMFCRibbonBar::IsPrintPreviewEnabled.md)|**인쇄 미리 보기** 탭을 사용하도록 설정할지 결정합니다.|  
|[CMFCRibbonBar::IsQATEmpty](../Topic/CMFCRibbonBar::IsQATEmpty.md)||  
|[CMFCRibbonBar::IsQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::IsQuickAccessToolbarOnTop.md)|빠른 실행 도구 모음을 리본 표시줄 위에 표시할지 지정합니다.|  
|[CMFCRibbonBar::IsReplaceFrameCaption](../Topic/CMFCRibbonBar::IsReplaceFrameCaption.md)|리본 표시줄이 주 프레임 캡션을 대체할지, 아니면 프레임 캡션 아래에 추가할지를 결정합니다.|  
|[CMFCRibbonBar::IsShowGroupBorder](../Topic/CMFCRibbonBar::IsShowGroupBorder.md)||  
|[CMFCRibbonBar::IsToolTipDescrEnabled](../Topic/CMFCRibbonBar::IsToolTipDescrEnabled.md)|도구 설명에 대한 설명을 사용하도록 설정할지 결정합니다.|  
|[CMFCRibbonBar::IsToolTipEnabled](../Topic/CMFCRibbonBar::IsToolTipEnabled.md)|리본 표시줄에 대한 도구 설명을 사용하도록 설정할지 결정합니다.|  
|[CMFCRibbonBar::IsTransparentCaption](../Topic/CMFCRibbonBar::IsTransparentCaption.md)||  
|[CMFCRibbonBar::IsWindows7Look](../Topic/CMFCRibbonBar::IsWindows7Look.md)|리본 메뉴에 Windows 7 스타일 모양\(작은 사각형 응용 프로그램 단추\)이 있는지 여부를 나타냅니다.|  
|[CMFCRibbonBar::LoadFromResource](../Topic/CMFCRibbonBar::LoadFromResource.md)|오버로드됨.  응용 프로그램 리소스에서 리본 표시줄을 로드합니다.|  
|[CMFCRibbonBar::OnClickButton](../Topic/CMFCRibbonBar::OnClickButton.md)||  
|[CMFCRibbonBar::OnEditContextMenu](../Topic/CMFCRibbonBar::OnEditContextMenu.md)||  
|[CMFCRibbonBar::OnRTLChanged](../Topic/CMFCRibbonBar::OnRTLChanged.md)|\(`CPane::OnRTLChanged`를 재정의합니다.\)|  
|[CMFCRibbonBar::OnSetAccData](../Topic/CMFCRibbonBar::OnSetAccData.md)|\([CBasePane::OnSetAccData](../Topic/CBasePane::OnSetAccData.md)를 재정의합니다.\)|  
|[CMFCRibbonBar::OnShowRibbonContextMenu](../Topic/CMFCRibbonBar::OnShowRibbonContextMenu.md)||  
|[CMFCRibbonBar::OnShowRibbonQATMenu](../Topic/CMFCRibbonBar::OnShowRibbonQATMenu.md)||  
|[CMFCRibbonBar::OnSysKeyDown](../Topic/CMFCRibbonBar::OnSysKeyDown.md)||  
|[CMFCRibbonBar::OnSysKeyUp](../Topic/CMFCRibbonBar::OnSysKeyUp.md)||  
|[CMFCRibbonBar::PopTooltip](../Topic/CMFCRibbonBar::PopTooltip.md)||  
|[CMFCRibbonBar::PreTranslateMessage](../Topic/CMFCRibbonBar::PreTranslateMessage.md)|\(`CBasePane::PreTranslateMessage`를 재정의합니다.\)|  
|[CMFCRibbonBar::RecalcLayout](../Topic/CMFCRibbonBar::RecalcLayout.md)|\([CPane::RecalcLayout](../Topic/CPane::RecalcLayout.md)을 재정의합니다.\)|  
|[CMFCRibbonBar::RemoveAllCategories](../Topic/CMFCRibbonBar::RemoveAllCategories.md)|리본 표시줄에서 모든 리본 범주를 제거합니다.|  
|[CMFCRibbonBar::RemoveAllFromTabs](../Topic/CMFCRibbonBar::RemoveAllFromTabs.md)|탭 영역에서 모든 리본 요소를 제거합니다.|  
|[CMFCRibbonBar::RemoveCategory](../Topic/CMFCRibbonBar::RemoveCategory.md)|지정된 인덱스에 있는 리본 범주를 제거합니다.|  
|[CMFCRibbonBar::SaveToXMLBuffer](../Topic/CMFCRibbonBar::SaveToXMLBuffer.md)|리본 표시줄을 버퍼에 저장합니다.|  
|[CMFCRibbonBar::SaveToXMLFile](../Topic/CMFCRibbonBar::SaveToXMLFile.md)|리본 표시줄을 XML 파일에 저장합니다.|  
|[CMFCRibbonBar::SetActiveCategory](../Topic/CMFCRibbonBar::SetActiveCategory.md)|지정된 리본 범주를 활성으로 설정합니다.|  
|[CMFCRibbonBar::SetActiveMDIChild](../Topic/CMFCRibbonBar::SetActiveMDIChild.md)||  
|[CMFCRibbonBar::SetElementKeys](../Topic/CMFCRibbonBar::SetElementKeys.md)|지정된 명령 ID를 가진 모든 리본 요소에 대해 지정된 키 팁을 설정합니다.|  
|[CMFCRibbonBar::SetApplicationButton](../Topic/CMFCRibbonBar::SetApplicationButton.md)|리본 표시줄에 응용 프로그램 리본 단추를 할당합니다.|  
|[CMFCRibbonBar::SetKeyboardNavigationLevel](../Topic/CMFCRibbonBar::SetKeyboardNavigationLevel.md)||  
|[CMFCRibbonBar::SetMaximizeMode](../Topic/CMFCRibbonBar::SetMaximizeMode.md)||  
|[CMFCRibbonBar::SetQuickAccessCommands](../Topic/CMFCRibbonBar::SetQuickAccessCommands.md)|빠른 실행 도구 모음에 하나 이상의 리본 요소를 추가합니다.|  
|[CMFCRibbonBar::SetQuickAccessDefaultState](../Topic/CMFCRibbonBar::SetQuickAccessDefaultState.md)|빠른 실행 도구 모음에 대한 기본 상태를 지정합니다.|  
|[CMFCRibbonBar::SetQuickAccessToolbarOnTop](../Topic/CMFCRibbonBar::SetQuickAccessToolbarOnTop.md)|QAT\(빠른 실행 도구 모음\)를 리본 표시줄 위 또는 아래에 배치합니다.|  
|[CMFCRibbonBar::SetTooltipFixedWidth](../Topic/CMFCRibbonBar::SetTooltipFixedWidth.md)||  
|[CMFCRibbonBar::SetWindows7Look](../Topic/CMFCRibbonBar::SetWindows7Look.md)|리본 Windows 7 스타일 모양\(작은 사각형 응용 프로그램 단추\)을 사용하거나 사용하지 않도록 설정합니다.|  
|[CMFCRibbonBar::ShowCategory](../Topic/CMFCRibbonBar::ShowCategory.md)|지정된 리본 범주를 표시하거나 숨깁니다.|  
|[CMFCRibbonBar::ShowContextCategories](../Topic/CMFCRibbonBar::ShowContextCategories.md)|지정된 ID를 가진 컨텍스트 범주를 표시하거나 숨깁니다.|  
|[CMFCRibbonBar::ShowKeyTips](../Topic/CMFCRibbonBar::ShowKeyTips.md)||  
|[CMFCRibbonBar::ToggleMimimizeState](../Topic/CMFCRibbonBar::ToggleMimimizeState.md)|리본 표시줄을 최소화 상태 또는 최대화 상태로 표시합니다.|  
|[CMFCRibbonBar::TranslateChar](../Topic/CMFCRibbonBar::TranslateChar.md)||  
  
## 설명  
 Microsoft에서는 Microsoft Office 2007을 릴리스할 때 동시에 Office Fluent 리본을 도입했습니다.  이 리본 표시줄은 단순한 새 컨트롤이 아니라  새로운 사용자 인터페이스 패러다임을 나타냅니다.  리본은 범주라는 탭 집합을 포함하는 창입니다.  각 범주는 논리적으로 리본 패널로 구분되고 각 패널에는 다양한 컨트롤과  명령 단추가 포함됩니다.  
  
 리본 표시줄에 표시되는 요소가 사용 가능한 공간에 가장 적합한 크기로 확장 및 축소됩니다.  예를 들어 리본 패널에 해당 요소를 표시할 공간이 부족하면 리본 메뉴는 하위 항목을 팝업 메뉴에 표시하는 메뉴 단추가 됩니다.  리본 표시줄은 정적\(부동화되지 않음\) 컨트롤 막대로 동작하고 프레임의 위쪽에 도킹될 수 있습니다.  
  
 `CMFCRibbonStatusBar` 클래스를 사용하여 Office 2007에서 사용된 것과 비슷한 상태 표시줄을 구현할 수 있습니다.  리본 범주에는 [리본 패널](../../mfc/reference/cmfcribbonpanel-class.md) 그룹이 포함 및 표시됩니다.  각 리본 패널에는 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)에서 파생되는 하나 이상의 리본 요소가 포함됩니다.  
  
 기존 MFC 응용 프로그램에 리본 표시줄을 추가하는 방법에 대한 자세한 내용은 [연습: MFC 자유 곡선 응용 프로그램 업데이트](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)를 참조하세요.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)  
  
## 요구 사항  
 **헤더:** afxribbonbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CPane Class](../../mfc/reference/cpane-class.md)   
 [CMFCRibbonCategory Class](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [연습: MFC 자유 곡선 응용 프로그램 업데이트](../../mfc/walkthrough-updating-the-mfc-scribble-application-part-1.md)