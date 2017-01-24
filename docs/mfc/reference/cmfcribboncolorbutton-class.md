---
title: "CMFCRibbonColorButton 클래스 | Microsoft Docs"
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
  - "CMFCRibbonColorButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonColorButton 클래스"
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: 36
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonColorButton 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonColorButton` 클래스는 리본 표시줄에 추가할 수 있는 색 단추를 구현합니다. 리본 색 단추는 하나 이상의 색상표가 포함된 드롭다운 메뉴를 표시합니다.  
  
## 구문  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](../Topic/CMFCRibbonColorButton::CMFCRibbonColorButton.md)||  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonColorButton::AddColorsGroup](../Topic/CMFCRibbonColorButton::AddColorsGroup.md)|일반 색 영역에 색 그룹을 추가합니다.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](../Topic/CMFCRibbonColorButton::EnableAutomaticButton.md)|**자동** 단추를 사용할지 여부를 지정합니다.|  
|[CMFCRibbonColorButton::EnableOtherButton](../Topic/CMFCRibbonColorButton::EnableOtherButton.md)|**기타** 단추를 사용하도록 설정합니다.|  
|[CMFCRibbonColorButton::GetAutomaticColor](../Topic/CMFCRibbonColorButton::GetAutomaticColor.md)||  
|[CMFCRibbonColorButton::GetColor](../Topic/CMFCRibbonColorButton::GetColor.md)|현재 선택된 색을 반환합니다.|  
|[CMFCRibbonColorButton::GetColorBoxSize](../Topic/CMFCRibbonColorButton::GetColorBoxSize.md)|색 막대에 표시되는 색 요소의 크기를 반환합니다.|  
|[CMFCRibbonColorButton::GetColumns](../Topic/CMFCRibbonColorButton::GetColumns.md)||  
|[CMFCRibbonColorButton::GetHighlightedColor](../Topic/CMFCRibbonColorButton::GetHighlightedColor.md)|팝업 색상표에서 현재 선택된 요소의 색을 반환합니다.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](../Topic/CMFCRibbonColorButton::RemoveAllColorGroups.md)|일반 색 영역에서 모든 색 그룹을 제거합니다.|  
|[CMFCRibbonColorButton::SetColor](../Topic/CMFCRibbonColorButton::SetColor.md)|일반 색 영역에서 색을 선택합니다.|  
|[CMFCRibbonColorButton::SetColorBoxSize](../Topic/CMFCRibbonColorButton::SetColorBoxSize.md)|색 막대에 표시되는 모든 색 요소의 크기를 설정합니다.|  
|[CMFCRibbonColorButton::SetColorName](../Topic/CMFCRibbonColorButton::SetColorName.md)||  
|[CMFCRibbonColorButton::SetColumns](../Topic/CMFCRibbonColorButton::SetColumns.md)||  
|[CMFCRibbonColorButton::SetDocumentColors](../Topic/CMFCRibbonColorButton::SetDocumentColors.md)|문서 색 영역에 표시할 RGB 값의 목록을 지정합니다.|  
|[CMFCRibbonColorButton::SetPalette](../Topic/CMFCRibbonColorButton::SetPalette.md)||  
|[CMFCRibbonColorButton::UpdateColor](../Topic/CMFCRibbonColorButton::UpdateColor.md)||  
  
## 설명  
 리본 색 단추는 사용자가 누를 때 색 막대를 표시합니다. 기본적으로 이 색 막대에는 일반 색 영역이라는 색 선택 색상표가 포함되어 있습니다. 필요에 따라 색 막대에 기본 색을 선택할 수 있는 **자동** 단추와 추가 색이 포함된 팝업 색상표를 표시하는 **기타** 단추가 표시될 수 있습니다.  
  
## 예제  
 다음 예제에서는 `CMFCRibbonColorButton` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 이 예제에서는 `CMFCRibbonColorButton` 개체 생성, 큰 이미지 설정, **자동** 단추 사용, **기타** 단추 사용, 열 수 설정, 색 막대에 표시되는 모든 색 요소의 크기 설정, 일반 색 영역에 색 그룹 추가, 문서 색 영역에 표시할 RGB 값 목록 지정 등을 수행하는 방법을 보여 줍니다. 이 코드 조각은 [클라이언트 그리기 샘플](../../top/visual-cpp-samples.md)의 일부입니다.  
  
 [!code-cpp[NVC_MFC_DrawClient#3](../../mfc/reference/codesnippet/CPP/cmfcribboncolorbutton-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## 요구 사항  
 **헤더:** afxribboncolorbutton.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery Class](../../mfc/reference/cmfcribbongallery-class.md)