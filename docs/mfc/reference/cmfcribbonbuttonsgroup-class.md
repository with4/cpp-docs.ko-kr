---
title: "CMFCRibbonButtonsGroup 클래스 | Microsoft Docs"
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
  - "CMFCRibbonButtonsGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonButtonsGroup 클래스"
ms.assetid: b993d93e-fc1a-472f-a87f-1d7b7b499845
caps.latest.revision: 34
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonButtonsGroup 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonButtonsGroup` 클래스를 사용 하면 리본 메뉴 단추를 그룹으로 구성 합니다.  그룹의 모든 단추를 가로로 서로 인접 하 고 테두리에 둘러싸인.  
  
## 구문  
  
```  
class CMFCRibbonButtonsGroup : public CMFCRibbonBaseElement  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup](../Topic/CMFCRibbonButtonsGroup::CMFCRibbonButtonsGroup.md)|`CMFCRibbonButtonsGroup` 개체를 생성합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCRibbonButtonsGroup::AddButton](../Topic/CMFCRibbonButtonsGroup::AddButton.md)|단추 그룹에 추가합니다.|  
|[CMFCRibbonButtonsGroup::AddButtons](../Topic/CMFCRibbonButtonsGroup::AddButtons.md)|단추 그룹에 추가합니다.|  
|[CMFCRibbonButtonsGroup::GetButton](../Topic/CMFCRibbonButtonsGroup::GetButton.md)|지정 된 인덱스에 있는 단추에 대 한 포인터를 반환 합니다.|  
|[CMFCRibbonButtonsGroup::GetCount](../Topic/CMFCRibbonButtonsGroup::GetCount.md)|그룹에 단추 수를 반환합니다.|  
|[CMFCRibbonButtonsGroup::GetImageSize](../Topic/CMFCRibbonButtonsGroup::GetImageSize.md)|기본 이미지의 이미지 크기는 리본 메뉴의 그룹에 반환 \(우선 [CMFCRibbonBaseElement::GetImageSize](../Topic/CMFCRibbonBaseElement::GetImageSize.md).\)|  
|[CMFCRibbonButtonsGroup::GetRegularSize](../Topic/CMFCRibbonButtonsGroup::GetRegularSize.md)|일반 크기의 리본 요소를 반환 합니다. \(재정의 [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonButtonsGroup::HasImages](../Topic/CMFCRibbonButtonsGroup::HasImages.md)|보고서 여부는 `CMFCRibbonButtonsGroup` 개체에 도구 모음 이미지가 포함 되어 있습니다.|  
|[CMFCRibbonButtonsGroup::OnDrawImage](../Topic/CMFCRibbonButtonsGroup::OnDrawImage.md)|보통, 강조 표시 된 또는 사용할 수 없는 단추 인지에 따라 지정 된 단추에 대 한 적절 한 이미지를 그립니다.|  
|[CMFCRibbonButtonsGroup::RemoveAll](../Topic/CMFCRibbonButtonsGroup::RemoveAll.md)|모든 단추를 제거는 `CMFCRibbonButtonsGroup` 개체입니다.|  
|[CMFCRibbonButtonsGroup::SetImages](../Topic/CMFCRibbonButtonsGroup::SetImages.md)|이미지를 그룹에 할당 합니다.|  
|[CMFCRibbonButtonsGroup::SetParentCategory](../Topic/CMFCRibbonButtonsGroup::SetParentCategory.md)|부모 설정 `CMFCRibbonCategory` 에 `CMFCRibbonButtonsGroup` 개체와 그 안에 있는 모든 단추 \(재정의 [CMFCRibbonBaseElement::SetParentCategory](../Topic/CMFCRibbonBaseElement::SetParentCategory.md).\)|  
  
## 설명  
 그룹에서 파생 된  [CMFCBaseRibbonElement](../../mfc/reference/cmfcribbonbaseelement-class.md) 및 단일 엔터티로 조작할 수 있습니다.  모든 패널 또는 팝업 메뉴에서 그룹을 배치할 수 있습니다.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 `CMFCRibbonButtonsGroup` 클래스입니다.  예제를 생성 하는 방법을 보여 줍니다 있는 `CMFCRibbonButtonsGroup` 개체, 그룹 리본 단추에 이미지 할당 및 단추 리본 단추 그룹에 추가 합니다.  이 코드의 일부인의  [그릴 클라이언트 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#2](../../mfc/reference/codesnippet/CPP/cmfcribbonbuttonsgroup-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButtonsGroup](../../mfc/reference/cmfcribbonbuttonsgroup-class.md)  
  
## 요구 사항  
 **헤더:** afxribbonbuttonsgroup.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)