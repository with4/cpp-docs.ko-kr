---
title: "CD2DGradientBrush 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DGradientBrush"
  - "afxrendertarget/CD2DGradientBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGradientBrush 클래스"
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DGradientBrush 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CD2DLinearGradientBrush 및 CD2DRadialGradientBrush 클래스의 기본 클래스입니다.  
  
## 구문  
  
```  
class CD2DGradientBrush : public CD2DBrush;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DGradientBrush::CD2DGradientBrush](../Topic/CD2DGradientBrush::CD2DGradientBrush.md)|CD2DGradientBrush 개체를 생성합니다.|  
|[CD2DGradientBrush::~CD2DGradientBrush](../Topic/CD2DGradientBrush::~CD2DGradientBrush.md)|소멸자  D2D 그라데이션 브러시 개체가 소멸될 때 호출됩니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DGradientBrush::Destroy](../Topic/CD2DGradientBrush::Destroy.md)|CD2DGradientBrush 개체를 소멸시킵니다.  \([CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md) 무시.\)|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DGradientBrush::m\_arGradientStops](../Topic/CD2DGradientBrush::m_arGradientStops.md)|D2D1\_GRADIENT\_STOP 구조의 배열입니다.|  
|[CD2DGradientBrush::m\_colorInterpolationGamma](../Topic/CD2DGradientBrush::m_colorInterpolationGamma.md)|그라데이션 중지 사이의 색 보간이 수행되는 공간입니다.|  
|[CD2DGradientBrush::m\_extendMode](../Topic/CD2DGradientBrush::m_extendMode.md)|\[0,1\]의 표준화된 범위를 벗어난 그라데이션 동작입니다.|  
|[CD2DGradientBrush::m\_pGradientStops](../Topic/CD2DGradientBrush::m_pGradientStops.md)|D2D1\_GRADIENT\_STOP 구조의 배열에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)