---
title: "CTooltipManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTooltipManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTooltipManager class"
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CTooltipManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

도구 설명에 대한 런타임 정보를 유지합니다.  `CTooltipManager` 클래스는 응용 프로그램당 한 번씩 인스턴스화됩니다.  
  
## 구문  
  
```  
class CTooltipManager : public CObject  
```  
  
## 멤버  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CTooltipManager::CreateToolTip](../Topic/CTooltipManager::CreateToolTip.md)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤을 만듭니다.|  
|[CTooltipManager::DeleteToolTip](../Topic/CTooltipManager::DeleteToolTip.md)|도구 설명 컨트롤을 삭제합니다.|  
|[CTooltipManager::SetTooltipParams](../Topic/CTooltipManager::SetTooltipParams.md)|지정된 Windows 컨트롤 형식에 대한 도구 설명 컨트롤의 시각적 모양을 사용자 지정합니다.|  
|[CTooltipManager::SetTooltipText](../Topic/CTooltipManager::SetTooltipText.md)|도구 설명 컨트롤에 대한 텍스트 및 설명을 설정합니다.|  
|[CTooltipManager::UpdateTooltips](../Topic/CTooltipManager::UpdateTooltips.md)||  
  
## 설명  
 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo` 및 `CTooltipManager`를 함께 사용하여 응용 프로그램에서 사용자 지정 도구 설명을 구현합니다.  이러한 도구 설명 클래스를 사용하는 방법의 예제를 보려면 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md) 항목을 참조하세요.  
  
## 상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## 요구 사항  
 **헤더:** afxtooltipmanager.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl Class](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo Class](../../mfc/reference/cmfctooltipinfo-class.md)