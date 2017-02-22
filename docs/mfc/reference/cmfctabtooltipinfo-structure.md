---
title: "CMFCTabToolTipInfo Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCTabToolTipInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCTabToolTipInfo struct"
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 29
---
# CMFCTabToolTipInfo Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 구조를 가리키기는 MDI 탭에 대 한 정보를 제공 합니다.  
  
## 구문  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## Members  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCTabToolTipInfo::m\_nTabIndex](../Topic/CMFCTabToolTipInfo::m_nTabIndex.md)|탭 컨트롤의 인덱스를 지정합니다.|  
|[CMFCTabToolTipInfo::m\_pTabWnd](../Topic/CMFCTabToolTipInfo::m_pTabWnd.md)|탭 컨트롤에 대 한 포인터입니다.|  
|[CMFCTabToolTipInfo::m\_strText](../Topic/CMFCTabToolTipInfo::m_strText.md)|도구 설명 텍스트입니다.|  
  
## 설명  
 에 대 한 포인터는 `CMFCTabToolTipInfo` 구조체를 매개 변수로 전달 되는 `AFX_WM_ON_GET_TAB_TOOLTIP` 메시지.  이 메시지는 MDI 탭을 사용할 수 있으며 사용자는 탭 컨트롤을 가리킬 때 생성 됩니다.  
  
## 예제  
 다음 예제를 보여 줍니다 어떻게 `CMFCTabToolTipInfo` 에 사용 되는  [MDITabsDemo 샘플: MFC MDI 응용 프로그램 탭](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/CPP/cmfctabtooltipinfo-structure_1.cpp)]  
  
## 상속 계층 구조  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## 요구 사항  
 **헤더:** afxbasetabctrl.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx::EnableMDITabs](../Topic/CMDIFrameWndEx::EnableMDITabs.md)   
 [CMDITabInfo::m\_bTabCustomTooltips](../Topic/CMDITabInfo::m_bTabCustomTooltips.md)