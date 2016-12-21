---
title: "CMFCRibbonSlider Class | Microsoft Docs"
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
  - "CMFCRibbonSlider"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSlider class"
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonSlider Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonSlider` 리본 메뉴 모음 또는 리본 상태 표시줄에 추가할 수 있는 슬라이더 컨트롤 클래스를 구현 합니다.  리본 슬라이더 컨트롤 Office 2007 응용 프로그램에서 표시 되는 확대\/축소 슬라이더를 비슷합니다.  
  
## 구문  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](../Topic/CMFCRibbonSlider::CMFCRibbonSlider.md)|만들고 리본 슬라이더 컨트롤을 초기화 합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonSlider::GetPos](../Topic/CMFCRibbonSlider::GetPos.md)|슬라이더 컨트롤의 현재 위치를 반환합니다.|  
|[CMFCRibbonSlider::GetRangeMax](../Topic/CMFCRibbonSlider::GetRangeMax.md)|슬라이더의 최대 값을 반환합니다.|  
|[CMFCRibbonSlider::GetRangeMin](../Topic/CMFCRibbonSlider::GetRangeMin.md)|슬라이더의 최소 값을 반환합니다.|  
|[CMFCRibbonSlider::GetRegularSize](../Topic/CMFCRibbonSlider::GetRegularSize.md)|일반 크기의 리본 요소를 반환합니다.  \(재정의 [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonSlider::GetZoomIncrement](../Topic/CMFCRibbonSlider::GetZoomIncrement.md)|확대\/축소 증분에 대 한 슬라이더 컨트롤의 크기를 반환합니다.|  
|[CMFCRibbonSlider::HasZoomButtons](../Topic/CMFCRibbonSlider::HasZoomButtons.md)|슬라이더에서 확대\/축소 단추가 있는지 여부를 지정 합니다.|  
|[CMFCRibbonSlider::OnDraw](../Topic/CMFCRibbonSlider::OnDraw.md)|리본 요소를 그리려면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md).\)|  
|[CMFCRibbonSlider::SetPos](../Topic/CMFCRibbonSlider::SetPos.md)|슬라이더 컨트롤의 현재 위치를 설정합니다.|  
|[CMFCRibbonSlider::SetRange](../Topic/CMFCRibbonSlider::SetRange.md)|최소 및 최대 값을 설정 하 여 slider 컨트롤의 범위를 지정 합니다.|  
|[CMFCRibbonSlider::SetZoomButtons](../Topic/CMFCRibbonSlider::SetZoomButtons.md)|표시 하거나 확대\/축소 단추를 숨깁니다.|  
|[CMFCRibbonSlider::SetZoomIncrement](../Topic/CMFCRibbonSlider::SetZoomIncrement.md)|확대\/축소 증분에 대 한 슬라이더 컨트롤의 크기를 설정합니다.|  
  
## 설명  
 사용할 수 있는 `SetRange` 확대\/축소 증분 슬라이더의 범위를 구성 하는 메서드.  슬라이더의 현재 위치를 사용 하 여 설정할 수 있는 `SetPos` 메서드.  
  
 순환 확대\/축소 단추 왼쪽과 오른쪽의 슬라이더 컨트롤을 사용 하 여 변경할 수 있는 `SetZoomButtons` 메서드.  기본적으로 슬라이더 가로 되 빼기 기호 왼쪽된 확대\/축소 단추 표시 및 더하기 기호 오른쪽 확대\/축소 단추를 표시 합니다.  
  
 `SetZoomIncrement` 메서드 정의에 추가 하거나 확대\/축소 단추를 클릭할 때 현재 위치에서 빼기 증가 합니다.  
  
## 예제  
 다음 예제에서는 다양 한 메서드를 사용 하는 방법의 `CMFCRibbonSlider` 클래스는 슬라이더의 속성을 설정 합니다.  예제를 생성 하는 방법을 보여 줍니다 있는 `CMFCRibbonSlider` 개체 확대\/축소 단추 표시, 슬라이더 컨트롤의 현재 위치 설정 하 고 범위 슬라이더 컨트롤의 값을 설정 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#12](../../mfc/reference/codesnippet/CPP/cmfcribbonslider-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## 요구 사항  
 **헤더:** afxribbonslider.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)