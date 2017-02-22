---
title: "CMFCRibbonCategory Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonCategory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonCategory class"
ms.assetid: 99ba25b6-d060-4fdd-bfab-3c46c22981bb
caps.latest.revision: 38
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 40
---
# CMFCRibbonCategory Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonCategory` 클래스는 그룹에 포함 되어 있는 리본 탭 구현  [리본 패널](../../mfc/reference/cmfcribbonpanel-class.md).  
  
## 구문  
  
```  
class CMFCRibbonCategory : public CObject  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonCategory::CMFCRibbonCategory](../Topic/CMFCRibbonCategory::CMFCRibbonCategory.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonCategory::AddHidden](../Topic/CMFCRibbonCategory::AddHidden.md)|리본 범주에는 숨겨진된 요소를 추가합니다.|  
|[CMFCRibbonCategory::AddPanel](../Topic/CMFCRibbonCategory::AddPanel.md)|새 패널 리본 범주에 추가합니다.|  
|[CMFCRibbonCategory::CopyFrom](../Topic/CMFCRibbonCategory::CopyFrom.md)||  
|[CMFCRibbonCategory::FindByData](../Topic/CMFCRibbonCategory::FindByData.md)||  
|[CMFCRibbonCategory::FindByID](../Topic/CMFCRibbonCategory::FindByID.md)||  
|[CMFCRibbonCategory::FindPanelWithElem](../Topic/CMFCRibbonCategory::FindPanelWithElem.md)||  
|[CMFCRibbonCategory::GetContextID](../Topic/CMFCRibbonCategory::GetContextID.md)|리본 메뉴 항목의 컨텍스트 ID를 반환합니다.|  
|[CMFCRibbonCategory::GetData](../Topic/CMFCRibbonCategory::GetData.md)|리본 범주와 관련 된 사용자 정의 데이터를 반환 합니다.|  
|[CMFCRibbonCategory::GetDroppedDown](../Topic/CMFCRibbonCategory::GetDroppedDown.md)||  
|[CMFCRibbonCategory::GetElements](../Topic/CMFCRibbonCategory::GetElements.md)||  
|[CMFCRibbonCategory::GetElementsByID](../Topic/CMFCRibbonCategory::GetElementsByID.md)||  
|[CMFCRibbonCategory::GetFirstVisibleElement](../Topic/CMFCRibbonCategory::GetFirstVisibleElement.md)|리본 범주에 속한 첫 번째 보이는 요소를 가져옵니다.|  
|[CMFCRibbonCategory::GetFocused](../Topic/CMFCRibbonCategory::GetFocused.md)|포커스가 있는 요소를 반환합니다.|  
|[CMFCRibbonCategory::GetHighlighted](../Topic/CMFCRibbonCategory::GetHighlighted.md)|강조 표시 된 요소를 반환합니다.|  
|[CMFCRibbonCategory::GetImageCount](../Topic/CMFCRibbonCategory::GetImageCount.md)||  
|[CMFCRibbonCategory::GetImageSize](../Topic/CMFCRibbonCategory::GetImageSize.md)||  
|[CMFCRibbonCategory::GetItemIDsList](../Topic/CMFCRibbonCategory::GetItemIDsList.md)||  
|[CMFCRibbonCategory::GetLastVisibleElement](../Topic/CMFCRibbonCategory::GetLastVisibleElement.md)|리본 범주에 속하는 보이는 마지막 요소로 얻기|  
|[CMFCRibbonCategory::GetLargeImages](../Topic/CMFCRibbonCategory::GetLargeImages.md)|리본 메뉴 범주를 사용 하 여 큰 이미지 목록에 대 한 참조를 반환 합니다.|  
|[CMFCRibbonCategory::GetMaxHeight](../Topic/CMFCRibbonCategory::GetMaxHeight.md)||  
|[CMFCRibbonCategory::GetName](../Topic/CMFCRibbonCategory::GetName.md)||  
|[CMFCRibbonCategory::GetPanel](../Topic/CMFCRibbonCategory::GetPanel.md)|지정 된 인덱스에 있는 리본 패널에 포인터를 반환 합니다.|  
|[CMFCRibbonCategory::GetPanelCount](../Topic/CMFCRibbonCategory::GetPanelCount.md)|리본 패널이 리본 범주에 반환합니다.|  
|[CMFCRibbonCategory::GetPanelFromPoint](../Topic/CMFCRibbonCategory::GetPanelFromPoint.md)||  
|[CMFCRibbonCategory::GetPanelIndex](../Topic/CMFCRibbonCategory::GetPanelIndex.md)|지정 된 리본 패널의 인덱스를 반환합니다.|  
|[CMFCRibbonCategory::GetParentButton](../Topic/CMFCRibbonCategory::GetParentButton.md)||  
|[CMFCRibbonCategory::GetParentMenuBar](../Topic/CMFCRibbonCategory::GetParentMenuBar.md)||  
|[CMFCRibbonCategory::GetParentRibbonBar](../Topic/CMFCRibbonCategory::GetParentRibbonBar.md)||  
|[CMFCRibbonCategory::GetRect](../Topic/CMFCRibbonCategory::GetRect.md)||  
|[CMFCRibbonCategory::GetSmallImages](../Topic/CMFCRibbonCategory::GetSmallImages.md)|목록 범주를 사용 하 여 작은 이미지에 대 한 참조를 반환 합니다.|  
|[CMFCRibbonCategory::GetTabColor](../Topic/CMFCRibbonCategory::GetTabColor.md)|리본 범주 탭의 현재 색을 반환 합니다.|  
|[CMFCRibbonCategory::GetTabRect](../Topic/CMFCRibbonCategory::GetTabRect.md)||  
|[CMFCRibbonCategory::GetTextTopLine](../Topic/CMFCRibbonCategory::GetTextTopLine.md)||  
|[CMFCRibbonCategory::GetVisibleElements](../Topic/CMFCRibbonCategory::GetVisibleElements.md)|리본 범주에 속한 모든 표시 요소를 가져옵니다.|  
|[CMFCRibbonCategory::HighlightPanel](../Topic/CMFCRibbonCategory::HighlightPanel.md)||  
|[CMFCRibbonCategory::HitTest](../Topic/CMFCRibbonCategory::HitTest.md)||  
|[CMFCRibbonCategory::HitTestEx](../Topic/CMFCRibbonCategory::HitTestEx.md)||  
|[CMFCRibbonCategory::HitTestScrollButtons](../Topic/CMFCRibbonCategory::HitTestScrollButtons.md)||  
|[CMFCRibbonCategory::IsActive](../Topic/CMFCRibbonCategory::IsActive.md)||  
|[CMFCRibbonCategory::IsVisible](../Topic/CMFCRibbonCategory::IsVisible.md)|리본 메뉴의 항목을 표시할지 여부를 결정 합니다.|  
|[CMFCRibbonCategory::IsWindows7Look](../Topic/CMFCRibbonCategory::IsWindows7Look.md)|상위 리본 Windows 7 스타일 모양 \(사각형 작은 응용 프로그램 단추\) 여부를 나타냅니다.|  
|[CMFCRibbonCategory::NotifyControlCommand](../Topic/CMFCRibbonCategory::NotifyControlCommand.md)||  
|[CMFCRibbonCategory::OnCancelMode](../Topic/CMFCRibbonCategory::OnCancelMode.md)||  
|[CMFCRibbonCategory::OnDraw](../Topic/CMFCRibbonCategory::OnDraw.md)||  
|[CMFCRibbonCategory::OnDrawImage](../Topic/CMFCRibbonCategory::OnDrawImage.md)||  
|[CMFCRibbonCategory::OnDrawMenuBorder](../Topic/CMFCRibbonCategory::OnDrawMenuBorder.md)||  
|[CMFCRibbonCategory::OnKey](../Topic/CMFCRibbonCategory::OnKey.md)|키보드 단추를 누를 때 프레임 워크에 의해 호출 됩니다.|  
|[CMFCRibbonCategory::OnLButtonDown](../Topic/CMFCRibbonCategory::OnLButtonDown.md)||  
|[CMFCRibbonCategory::OnLButtonUp](../Topic/CMFCRibbonCategory::OnLButtonUp.md)||  
|[CMFCRibbonCategory::OnMouseMove](../Topic/CMFCRibbonCategory::OnMouseMove.md)||  
|[CMFCRibbonCategory::OnRTLChanged](../Topic/CMFCRibbonCategory::OnRTLChanged.md)||  
|[CMFCRibbonCategory::OnScrollHorz](../Topic/CMFCRibbonCategory::OnScrollHorz.md)||  
|[CMFCRibbonCategory::OnUpdateCmdUI](../Topic/CMFCRibbonCategory::OnUpdateCmdUI.md)||  
|[CMFCRibbonCategory::RecalcLayout](../Topic/CMFCRibbonCategory::RecalcLayout.md)||  
|[CMFCRibbonCategory::RemovePanel](../Topic/CMFCRibbonCategory::RemovePanel.md)||  
|[CMFCRibbonCategory::ReposPanels](../Topic/CMFCRibbonCategory::ReposPanels.md)||  
|[CMFCRibbonCategory::SetCollapseOrder](../Topic/CMFCRibbonCategory::SetCollapseOrder.md)|리본 범주에 있는 리본 패널이 축소 순서를 정의 합니다.|  
|[CMFCRibbonCategory::SetData](../Topic/CMFCRibbonCategory::SetData.md)|리본 메뉴 범주에 사용자 정의 데이터를 저장합니다.|  
|[CMFCRibbonCategory::SetKeys](../Topic/CMFCRibbonCategory::SetKeys.md)|리본 범주에 keytip을 할당합니다.|  
|[CMFCRibbonCategory::SetName](../Topic/CMFCRibbonCategory::SetName.md)||  
|[CMFCRibbonCategory::SetTabColor](../Topic/CMFCRibbonCategory::SetTabColor.md)|리본 메뉴 항목의 색을 설정합니다.|  
  
## 설명  
 일반적으로 리본 메뉴 범주를 직접 호출 하 여 만든지 않습니다 [CMFCRibbonBar::AddCategory](../Topic/CMFCRibbonBar::AddCategory.md), 새로 만든된 리본 범주에 포인터를 반환 합니다.  호출 하 여 범주에 패널 추가 [CMFCRibbonCategory::AddPanel](../Topic/CMFCRibbonCategory::AddPanel.md).  
  
 `CMFCRibbonTab` 리본 범주 클래스를 그립니다.  [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)에서 파생됩니다.  
  
 다음 예제는 리본 범주를 만들고 패널을 추가 하는 방법을 보여 줍니다.  
  
 `// Create a new ribbon category and get a pointer to it`  
  
 `CMFCRibbonCategory* pCategory = m_wndRibbonBar.AddCategory`  
  
 `(_T("&Write"),           // Category name`  
  
 `IDB_WRITE,              // Category small images (16 x 16)`  
  
 `IDB_WRITE_LARGE);   // Category large images (32 x 32)`  
  
 `// Add a panel to the new category`  
  
 `CMFCRibbonPanel* pPanel = pCategory->AddPanel (`  
  
 `_T("Clipboard"),                       // Panel name`  
  
 `m_PanelIcons.ExtractIcon (0));  // Panel icon`  
  
 다음은 홈 범주에서 RibbonApp 샘플 응용 프로그램의 그림을 보여 줍니다.  
  
 ![CMFCRibbonCategory 이미지](../../mfc/reference/media/cmfcribboncategory.png "CMFCRibbonCategory")  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonCategory](../../mfc/reference/cmfcribboncategory-class.md)  
  
## 요구 사항  
 **헤더:** afxribboncategory.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)