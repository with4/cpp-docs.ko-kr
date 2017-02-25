---
title: "CMFCToolTipInfo Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipInfo class"
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCToolTipInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

도구 설명의 시각적 모양에 대한 정보를 저장합니다.  
  
## 구문  
  
```  
class CMFCToolTipInfo  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCToolTipInfo::operator\=](../Topic/CMFCToolTipInfo::operator=.md)||  
  
### 데이터 멤버  
  
|이름|설명|  
|--------|--------|  
|[CMFCToolTipInfo::m\_bBalloonTooltip](../Topic/CMFCToolTipInfo::m_bBalloonTooltip.md)|도구 설명이 풍선 모양인지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m\_bBoldLabel](../Topic/CMFCToolTipInfo::m_bBoldLabel.md)|도구 설명 레이블이 굵은 글꼴로 표시되는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m\_bDrawDescription](../Topic/CMFCToolTipInfo::m_bDrawDescription.md)|도구 설명이 설명을 포함하는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m\_bDrawIcon](../Topic/CMFCToolTipInfo::m_bDrawIcon.md)|도구 설명이 아이콘을 포함하는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m\_bDrawSeparator](../Topic/CMFCToolTipInfo::m_bDrawSeparator.md)|도구 설명 레이블과 도구 설명 사이에 구분 기호가 표시되는지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m\_bRoundedCorners](../Topic/CMFCToolTipInfo::m_bRoundedCorners.md)|도구 설명 모서리가 둥근지 여부를 나타내는 부울 변수입니다.|  
|[CMFCToolTipInfo::m\_bVislManagerTheme](../Topic/CMFCToolTipInfo::m_bVislManagerTheme.md)|시각화 관리자에서 도구 설명의 모양을 제어해야 하는지 여부를 나타내는 부울 변수입니다\([CMFCVisualManager Class](../../mfc/reference/cmfcvisualmanager-class.md) 참조\).|  
|[CMFCToolTipInfo::m\_clrBorder](../Topic/CMFCToolTipInfo::m_clrBorder.md)|도구 설명 테두리 색입니다.|  
|[CMFCToolTipInfo::m\_clrFill](../Topic/CMFCToolTipInfo::m_clrFill.md)|도구 설명 배경색입니다.|  
|[CMFCToolTipInfo::m\_clrFillGradient](../Topic/CMFCToolTipInfo::m_clrFillGradient.md)|도구 설명의 그라데이션 채우기 색입니다.|  
|[CMFCToolTipInfo::m\_clrText](../Topic/CMFCToolTipInfo::m_clrText.md)|도구 설명의 텍스트 색입니다.|  
|[CMFCToolTipInfo::m\_nGradientAngle](../Topic/CMFCToolTipInfo::m_nGradientAngle.md)|도구 설명의 그라데이션 채우기 각도입니다.|  
|[CMFCToolTipInfo::m\_nMaxDescrWidth](../Topic/CMFCToolTipInfo::m_nMaxDescrWidth.md)|도구 설명의 가능한 최대 설명 너비\(픽셀\)입니다.|  
  
## 설명  
 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` 및 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)를 함께 사용하여 응용 프로그램에서 사용자 지정 도구 설명을 구현합니다.  이러한 도구 설명 클래스를 사용하는 방법의 예제를 보려면 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md) 항목을 참조하세요.  
  
## 예제  
 다음 예제에서는 `CMFCToolTipInfo` 클래스에서 다양한 멤버 변수의 값을 설정하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#42](../../mfc/reference/codesnippet/CPP/cmfctooltipinfo-class_1.cpp)]  
  
## 상속 계층  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## 요구 사항  
 **헤더:** afxtooltipctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md)