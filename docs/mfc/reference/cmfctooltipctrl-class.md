---
title: "CMFCToolTipCtrl Class | Microsoft Docs"
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
  - "CMFCToolTipCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolTipCtrl class"
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolTipCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)를 기반으로 하는 확장된 도구 설명 구현입니다.  `CMFCToolTipCtrl` 클래스 기반의 도구 설명은 아이콘, 레이블 및 설명을 표시할 수 있습니다.  그라데이션 채우기, 사용자 지정 텍스트와 테두리 색, 굵은 텍스트, 둥근 모서리 또는 풍선 스타일을 사용하여 시각적인 모양을 사용자 지정할 수 있습니다.  
  
## 구문  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|기본 생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CMFCToolTipCtrl::GetIconSize](../Topic/CMFCToolTipCtrl::GetIconSize.md)|도구 설명에 아이콘 크기를 반환합니다.|  
|[CMFCToolTipCtrl::GetParams](../Topic/CMFCToolTipCtrl::GetParams.md)|도구 설명의 표시 설정을 반환합니다.|  
|[CMFCToolTipCtrl::OnDrawBorder](../Topic/CMFCToolTipCtrl::OnDrawBorder.md)|도구 설명의 테두리를 그립니다.|  
|[CMFCToolTipCtrl::OnDrawDescription](../Topic/CMFCToolTipCtrl::OnDrawDescription.md)||  
|[CMFCToolTipCtrl::OnDrawIcon](../Topic/CMFCToolTipCtrl::OnDrawIcon.md)|도구 설명에 아이콘을 표시합니다.|  
|[CMFCToolTipCtrl::OnDrawLabel](../Topic/CMFCToolTipCtrl::OnDrawLabel.md)|도구 설명의 레이블을 그리거나 레이블의 크기를 계산합니다.|  
|[CMFCToolTipCtrl::OnDrawSeparator](../Topic/CMFCToolTipCtrl::OnDrawSeparator.md)|도구 설명에서 레이블과 설명 사이에 구분 기호를 그립니다.|  
|[CMFCToolTipCtrl::OnFillBackground](../Topic/CMFCToolTipCtrl::OnFillBackground.md)|도구 설명 배경을 채웁니다.|  
|[CMFCToolTipCtrl::SetDescription](../Topic/CMFCToolTipCtrl::SetDescription.md)|도구 설명에 표시할 설명을 설정합니다.|  
|[CMFCToolTipCtrl::SetFixedWidth](../Topic/CMFCToolTipCtrl::SetFixedWidth.md)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](../Topic/CMFCToolTipCtrl::SetHotRibbonButton.md)||  
|[CMFCToolTipCtrl::SetLocation](../Topic/CMFCToolTipCtrl::SetLocation.md)||  
|[CMFCToolTipCtrl::SetParams](../Topic/CMFCToolTipCtrl::SetParams.md)|`CMFCToolTipInfo` 개체를 사용하여 도구 설명의 시각적 모양을 지정합니다.|  
  
## 설명  
 `CMFCToolTipCtrl`, `CMFCToolTipInfo` 및 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md) 개체를 함께 사용하여 응용 프로그램에서 사용자 지정 도구 설명을 구현합니다.  
  
 예를 들어 풍선 스타일의 도구 설명을 사용하려면 다음 단계를 수행합니다.  
  
 1.  [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) 메서드를 사용하여 응용 프로그램에서 도구 설명 관리자를 초기화합니다.  
  
 2.  `CMFCToolTipInfo` 구조체를 만들어 원하는 시각적 스타일을 지정합니다.  
  
```  
CMFCToolTipInfo params;  
 params.m_bBoldLabel = FALSE;  
 params.m_bDrawDescription = FALSE;  
 params.m_bDrawIcon = FALSE;  
 params.m_bRoundedCorners = TRUE;  
 params.m_bDrawSeparator = FALSE;  
 if (m_bCustomColors)  
 {  
  params.m_clrFill = RGB (255, 255, 255);  
  params.m_clrFillGradient = RGB (228, 228, 240);  
  params.m_clrText = RGB (61, 83, 80);  
  params.m_clrBorder = RGB (144, 149, 168);  
 }  
```  
  
 3.  [CTooltipManager::SetTooltipParams](../Topic/CTooltipManager::SetTooltipParams.md) 메서드를 사용하여 `CMFCToolTipInfo` 개체에 정의된 스타일을 통해 응용 프로그램의 모든 도구 설명에 대한 시각적 스타일을 설정합니다.  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);  
```  
  
 `CMFCToolTipCtrl`에서 새 클래스를 파생시켜 도구 설명 동작과 렌더링을 제어할 수도 있습니다.  새 도구 설명 컨트롤 클래스를 지정하려면 `CTooltipManager::SetTooltipParams` 메서드를 사용합니다.  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
  
 기본 도구 설명 컨트롤 클래스를 복원하고 도구 설명 모양을 기본 상태로 다시 설정하려면 `SetTooltipParams`의 런타임 클래스 및 도구 설명 정보 매개 변수에 NULL을 지정합니다.  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL, NULL);  
```  
  
## 예제  
 다음 예제에서는 `CMFCToolTipCtrl` 개체를 생성하고, 도구 설명에 표시되는 설명을 설정하고, 도구 설명 컨트롤의 너비를 설정하는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/CPP/cmfctooltipctrl-class_1.cpp)]  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## 요구 사항  
 **헤더:** afxtooltipctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager Class](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo Class](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)