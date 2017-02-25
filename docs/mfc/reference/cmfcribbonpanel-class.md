---
title: "CMFCRibbonPanel Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonPanel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonPanel class"
ms.assetid: 51d70749-1140-4386-b103-f14082049ba6
caps.latest.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 36
---
# CMFCRibbonPanel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리본 요소 집합이 포함 된 패널을 구현 합니다.  패널을 그릴 때 패널의 크기를 지정 하는 가능한 한 많은 요소를 표시 합니다.  
  
## 구문  
  
```  
class CMFCRibbonPanel : public CObject  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonPanel::CMFCRibbonPanel](../Topic/CMFCRibbonPanel::CMFCRibbonPanel.md)|생성 및 초기화는 `CMFCRibbonPanel` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md)|리본 요소를 패널에 추가합니다.|  
|[CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md)|리본 패널에는 구분 기호를 추가합니다.|  
|[CMFCRibbonPanel::AddToolBar](../Topic/CMFCRibbonPanel::AddToolBar.md)|리본 패널에 있는 도구 모음을 추가합니다.|  
|[CMFCRibbonPanel::FindByData](../Topic/CMFCRibbonPanel::FindByData.md)||  
|[CMFCRibbonPanel::FindByID](../Topic/CMFCRibbonPanel::FindByID.md)|지정 된 명령 ID로 식별 되는 요소를 반환 합니다.|  
|[CMFCRibbonPanel::GetCaptionHeight](../Topic/CMFCRibbonPanel::GetCaptionHeight.md)||  
|[CMFCRibbonPanel::GetCount](../Topic/CMFCRibbonPanel::GetCount.md)|리본 패널에서 요소의 개수를 반환합니다.|  
|[CMFCRibbonPanel::GetData](../Topic/CMFCRibbonPanel::GetData.md)|패널에 연결 된 사용자 정의 데이터를 반환 합니다.|  
|[CMFCRibbonPanel::GetDefaultButton](../Topic/CMFCRibbonPanel::GetDefaultButton.md)||  
|[CMFCRibbonPanel::GetDroppedDown](../Topic/CMFCRibbonPanel::GetDroppedDown.md)||  
|[CMFCRibbonPanel::GetElement](../Topic/CMFCRibbonPanel::GetElement.md)|리본 메뉴의 지정 된 인덱스에 있는 요소를 반환 합니다.|  
|[CMFCRibbonPanel::GetElements](../Topic/CMFCRibbonPanel::GetElements.md)|리본 패널에 포함 된 모든 요소를 검색 합니다.|  
|[CMFCRibbonPanel::GetElementsByID](../Topic/CMFCRibbonPanel::GetElementsByID.md)||  
|[CMFCRibbonPanel::GetFocused](../Topic/CMFCRibbonPanel::GetFocused.md)|포커스가 있는 요소를 반환합니다.|  
|[CMFCRibbonPanel::GetGalleryRect](../Topic/CMFCRibbonPanel::GetGalleryRect.md)|갤러리 요소의 경계 사각형을 반환 합니다.|  
|[CMFCRibbonPanel::GetHighlighted](../Topic/CMFCRibbonPanel::GetHighlighted.md)||  
|[CMFCRibbonPanel::GetIndex](../Topic/CMFCRibbonPanel::GetIndex.md)||  
|[CMFCRibbonPanel::GetItemIDsList](../Topic/CMFCRibbonPanel::GetItemIDsList.md)||  
|[CMFCRibbonPanel::GetName](../Topic/CMFCRibbonPanel::GetName.md)||  
|[CMFCRibbonPanel::GetParentButton](../Topic/CMFCRibbonPanel::GetParentButton.md)||  
|[CMFCRibbonPanel::GetParentCategory](../Topic/CMFCRibbonPanel::GetParentCategory.md)|리본 패널의 부모 범주를 반환합니다.|  
|[CMFCRibbonPanel::GetParentMenuBar](../Topic/CMFCRibbonPanel::GetParentMenuBar.md)||  
|[CMFCRibbonPanel::GetPreferedMenuLocation](../Topic/CMFCRibbonPanel::GetPreferedMenuLocation.md)||  
|[CMFCRibbonPanel::GetPressed](../Topic/CMFCRibbonPanel::GetPressed.md)||  
|[CMFCRibbonPanel::GetRect](../Topic/CMFCRibbonPanel::GetRect.md)||  
|[CMFCRibbonPanel::GetVisibleElements](../Topic/CMFCRibbonPanel::GetVisibleElements.md)|표시 된 요소의 배열을 가져옵니다.|  
|[CMFCRibbonPanel::HasElement](../Topic/CMFCRibbonPanel::HasElement.md)||  
|[CMFCRibbonPanel::HitTest](../Topic/CMFCRibbonPanel::HitTest.md)||  
|[CMFCRibbonPanel::HitTestEx](../Topic/CMFCRibbonPanel::HitTestEx.md)||  
|[CMFCRibbonPanel::Insert](../Topic/CMFCRibbonPanel::Insert.md)|리본 요소에 지정 된 위치에 삽입합니다.|  
|[CMFCRibbonPanel::InsertSeparator](../Topic/CMFCRibbonPanel::InsertSeparator.md)|구분 기호를 지정 된 위치에 삽입합니다.|  
|[CMFCRibbonPanel::IsCenterColumnVert](../Topic/CMFCRibbonPanel::IsCenterColumnVert.md)|열을 기준으로 모든 패널 요소 \(맞춤\) 세로로 가운데 여부를 지정 합니다.|  
|[CMFCRibbonPanel::IsCollapsed](../Topic/CMFCRibbonPanel::IsCollapsed.md)||  
|[CMFCRibbonPanel::IsHighlighted](../Topic/CMFCRibbonPanel::IsHighlighted.md)||  
|[CMFCRibbonPanel::IsJustifyColumns](../Topic/CMFCRibbonPanel::IsJustifyColumns.md)|모든 패널 열 너비가 있는지 여부를 지정 합니다.|  
|[CMFCRibbonPanel::IsMainPanel](../Topic/CMFCRibbonPanel::IsMainPanel.md)||  
|[CMFCRibbonPanel::IsMenuMode](../Topic/CMFCRibbonPanel::IsMenuMode.md)||  
|[CMFCRibbonPanel::MakeGalleryItemVisible](../Topic/CMFCRibbonPanel::MakeGalleryItemVisible.md)|리본 메뉴를 지정 된 요소를 표시 하는 갤러리를 스크롤합니다.|  
|[CMFCRibbonPanel::OnKey](../Topic/CMFCRibbonPanel::OnKey.md)||  
|[CMFCRibbonPanel::RecalcWidths](../Topic/CMFCRibbonPanel::RecalcWidths.md)||  
|[CMFCRibbonPanel::Remove](../Topic/CMFCRibbonPanel::Remove.md)|제거 하 고 필요에 따라 지정 된 인덱스에 있는 요소를 삭제 합니다.|  
|[CMFCRibbonPanel::RemoveAll](../Topic/CMFCRibbonPanel::RemoveAll.md)|리본 패널에서 모든 요소를 제거합니다.|  
|[CMFCRibbonPanel::Replace](../Topic/CMFCRibbonPanel::Replace.md)|한 요소를 해당 인덱스 값을 기준으로 다른 바꿉니다.|  
|[CMFCRibbonPanel::ReplaceByID](../Topic/CMFCRibbonPanel::ReplaceByID.md)|지정 된 명령 ID를 기반으로 다른 요소를 대체|  
|[CMFCRibbonPanel::SetCenterColumnVert](../Topic/CMFCRibbonPanel::SetCenterColumnVert.md)|요소를 세로로 맞추려면 열을 기준으로 패널을 정렬 합니다.|  
|[CMFCRibbonPanel::SetData](../Topic/CMFCRibbonPanel::SetData.md)|리본 패널에 사용자 정의 데이터 연결입니다.|  
|[CMFCRibbonPanel::SetElementMenu](../Topic/CMFCRibbonPanel::SetElementMenu.md)|팝업 메뉴에서 특정된 명령 ID를 가진 요소에 할당|  
|[CMFCRibbonPanel::SetElementRTC](../Topic/CMFCRibbonPanel::SetElementRTC.md)|리본 패널에 제공 된 런타임 클래스 정보가 지정 된 경우 리본 요소가 추가 됩니다.|  
|[CMFCRibbonPanel::SetElementRTCByID](../Topic/CMFCRibbonPanel::SetElementRTCByID.md)|리본 패널에 제공 된 런타임 클래스 정보가 지정 된 경우 리본 요소가 추가 됩니다.|  
|[CMFCRibbonPanel::SetFocused](../Topic/CMFCRibbonPanel::SetFocused.md)|리본 요소에 지정 된 포커스를 설정 합니다.|  
|[CMFCRibbonPanel::SetJustifyColumns](../Topic/CMFCRibbonPanel::SetJustifyColumns.md)|열 맞춤을 사용할 수 있거나.|  
|[CMFCRibbonPanel::SetKeys](../Topic/CMFCRibbonPanel::SetKeys.md)|리본 패널에 표시 되는 바로 가기 키를 설정 합니다.|  
|[CMFCRibbonPanel::ShowPopup](../Topic/CMFCRibbonPanel::ShowPopup.md)||  
  
## 설명  
 리본 패널이 리본 범주 내에서 만들 관련된 작업을 논리적으로 그룹화 됩니다.  리본 변경 크기로 패널 레이아웃 가능한 한 많은 요소를 표시 하도록 자동 조정 됩니다.  
  
 리본 메뉴를 호출 하 여 리본 범주에 포함 된 패널 얻을 수 있는 [CMFCRibbonCategory::GetPanel](../Topic/CMFCRibbonCategory::GetPanel.md) 메서드.  
  
## 예제  
 구성 하는 방법 다음 예제는 `CMFCRibbonPanel` 의 다양 한 메서드를 사용 하 여 개체의 `CMFCRibbonPanel` 클래스.  이 예제에서는 리본 패널에 표시 되는 바로 가기 키를 설정 하 고 요소 패널에서 열을 기준으로 맞춥니다 열 맞춤을 사용 방법을 보여 줍니다.  이 코드 조각에 속해 있는  [MS Office 2007 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#10](../../mfc/reference/codesnippet/CPP/cmfcribbonpanel-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonPanel.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CMFCRibbonCategory Class](../../mfc/reference/cmfcribboncategory-class.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)