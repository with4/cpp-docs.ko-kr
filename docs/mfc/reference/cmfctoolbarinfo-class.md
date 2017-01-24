---
title: "CMFCToolBarInfo Class | Microsoft Docs"
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
  - "CMFCToolBarInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarInfo class"
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarInfo Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

리소스를 Id의 다양 한 상태에서 도구 모음 이미지가 포함 되어 있습니다.  `CMFCToolBarInfo`매개 변수로 사용 되는 도우미 클래스입니다는 [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md) 메서드.  
  
## 구문  
  
```  
class CMFCToolBarInfo  
```  
  
## Members  
  
### 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CMFCToolBarInfo::m\_uiColdResID](../Topic/CMFCToolBarInfo::m_uiColdResID.md)|일반 \(콜드\) 도구 모음 이미지가 포함 된 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m\_uiDisabledResID](../Topic/CMFCToolBarInfo::m_uiDisabledResID.md)|사용할 수 없는 도구 모음 이미지가 포함 된 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m\_uiHotResID](../Topic/CMFCToolBarInfo::m_uiHotResID.md)|\(핫\) 선택한 도구 모음 이미지가 포함 된 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m\_uiLargeColdResID](../Topic/CMFCToolBarInfo::m_uiLargeColdResID.md)|대규모의 일반 도구 모음 이미지가 포함 된 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m\_uiLargeDisabledResID](../Topic/CMFCToolBarInfo::m_uiLargeDisabledResID.md)|큰 포함 된 도구 모음 비트맵의 리소스 ID를 이미지 도구 모음 사용 안 함.|  
|[CMFCToolBarInfo::m\_uiLargeHotResID](../Topic/CMFCToolBarInfo::m_uiLargeHotResID.md)|큰 포함 된 도구 모음 비트맵의 리소스 ID를 이미지 도구 모음을 선택 합니다.|  
|[CMFCToolBarInfo::m\_uiMenuDisabledResID](../Topic/CMFCToolBarInfo::m_uiMenuDisabledResID.md)|포함 이미지를 사용 하지 않는 메뉴는 도구 모음 비트맵의 리소스 ID입니다.|  
|[CMFCToolBarInfo::m\_uiMenuResID](../Topic/CMFCToolBarInfo::m_uiMenuResID.md)|이미지 메뉴에 있는 도구 모음 비트맵의 리소스 ID입니다.|  
  
## 설명  
 전체 도구 모음 비트맵 고정된 된 크기의 작은 도구 모음 이미지 \(단추\)의 구성 됩니다.  저장 된 각 리소스 ID는 `CMFCToolBarInfo` 개체 도구 모음 이미지를 단일 상태 \(예를 들어, 선택, 사용 안 함, 큰, 또는 메뉴 이미지\)의 전체 집합을 포함 하는 비트맵입니다.  
  
## 상속 계층 구조  
 [CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)  
  
## 요구 사항  
 **헤더:** afxtoolbar.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar Class](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBar::LoadToolBarEx](../Topic/CMFCToolBar::LoadToolBarEx.md)