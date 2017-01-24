---
title: "CMFCRibbonProgressBar Class | Microsoft Docs"
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
  - "CMFCRibbonProgressBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonProgressBar class"
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonProgressBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

시간이 오래 걸리는 작업의 진행률을 시각적으로 나타내는 컨트롤을 구현 합니다.  
  
## 구문  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](../Topic/CMFCRibbonProgressBar::CMFCRibbonProgressBar.md)|생성 및 초기화는 `CMFCRibbonProgressBar` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMFCRibbonProgressBar::GetPos](../Topic/CMFCRibbonProgressBar::GetPos.md)|현재 진행 상태를 반환합니다.|  
|[CMFCRibbonProgressBar::GetRangeMax](../Topic/CMFCRibbonProgressBar::GetRangeMax.md)|현재 범위의 최대 값을 반환합니다.|  
|[CMFCRibbonProgressBar::GetRangeMin](../Topic/CMFCRibbonProgressBar::GetRangeMin.md)|현재 범위의 최소 값을 반환합니다.|  
|[CMFCRibbonProgressBar::GetRegularSize](../Topic/CMFCRibbonProgressBar::GetRegularSize.md)|일반 크기의 리본 요소를 반환합니다.  \(재정의 [CMFCRibbonBaseElement::GetRegularSize](../Topic/CMFCRibbonBaseElement::GetRegularSize.md).\)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](../Topic/CMFCRibbonProgressBar::IsInfiniteMode.md)|진행률 표시줄 무한 모드에서 작동 중인지 여부를 지정 합니다.|  
|[CMFCRibbonProgressBar::OnDraw](../Topic/CMFCRibbonProgressBar::OnDraw.md)|리본 요소를 그리려면 프레임 워크에서 호출 됩니다.  \(재정의 [CMFCRibbonBaseElement::OnDraw](../Topic/CMFCRibbonBaseElement::OnDraw.md).\)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](../Topic/CMFCRibbonProgressBar::SetInfiniteMode.md)|무한 모드에서 작업 하는 진행률 표시줄을 설정 합니다.|  
|[CMFCRibbonProgressBar::SetPos](../Topic/CMFCRibbonProgressBar::SetPos.md)|현재 진행 상태를 설정합니다.|  
|[CMFCRibbonProgressBar::SetRange](../Topic/CMFCRibbonProgressBar::SetRange.md)|최소 및 최대 값을 설정합니다.|  
  
## 설명  
 A `CMFCRibbonProgressBar` 두 가지 모드로 작동할 수 있습니다: 일반 및 무한 합니다.  일반 모드에서 진행률 표시줄이 왼쪽에서 오른쪽으로 채워집니다 및 최대 값에 도달 하면 중지 합니다.  무한 모드에서 진행률 표시줄 반복적으로 최소값에서 최대값으로 채워집니다.  무한 모드를 사용 하면 작업 진행 후 완료 시간을 알 수 없음을 나타낼 수 있습니다.  
  
## 예제  
 다음 예제에서는 다양 한 방법에 있는 `CMFCRibbonProgressBar` 클래스입니다.  진행률 표시줄의 최소 및 최대 값을 설정 하 고 진행률 표시줄의 현재 위치 설정 \(여기서 작업의 완료 시간 알 수 없는\) 무한 모드에서 작업 하는 진행률 표시줄을 설정 하는 예를 보여줍니다.  이 코드 조각에 속해 있는  [MS Office 2007 데모 샘플](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/CPP/cmfcribbonprogressbar-class_1.cpp)]  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## 요구 사항  
 **헤더:** afxRibbonProgressBar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement Class](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar Class](../../mfc/reference/cmfcribbonbar-class.md)