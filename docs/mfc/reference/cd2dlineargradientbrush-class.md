---
title: "CD2DLinearGradientBrush 클래스 | Microsoft Docs"
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
  - "afxrendertarget/CD2DLinearGradientBrush"
  - "CD2DLinearGradientBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DLinearGradientBrush 클래스"
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DLinearGradientBrush 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1LinearGradientBrush에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DLinearGradientBrush : public CD2DGradientBrush;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DLinearGradientBrush::CD2DLinearGradientBrush](../Topic/CD2DLinearGradientBrush::CD2DLinearGradientBrush.md)|CD2DLinearGradientBrush 개체를 생성합니다.|  
|[CD2DLinearGradientBrush::~CD2DLinearGradientBrush](../Topic/CD2DLinearGradientBrush::~CD2DLinearGradientBrush.md)|소멸자  D2D 선형 그라데이션 브러시 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DLinearGradientBrush::Attach](../Topic/CD2DLinearGradientBrush::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DLinearGradientBrush::Create](../Topic/CD2DLinearGradientBrush::Create.md)|CD2DLinearGradientBrush를 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DLinearGradientBrush::Destroy](../Topic/CD2DLinearGradientBrush::Destroy.md)|CD2DLinearGradientBrush 개체를 소멸시킵니다.  \([CD2DGradientBrush::Destroy](../Topic/CD2DGradientBrush::Destroy.md) 무시.\)|  
|[CD2DLinearGradientBrush::Detach](../Topic/CD2DLinearGradientBrush::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DLinearGradientBrush::Get](../Topic/CD2DLinearGradientBrush::Get.md)|ID2D1LinearGradientBrush 인터페이스를 반환합니다.|  
|[CD2DLinearGradientBrush::GetEndPoint](../Topic/CD2DLinearGradientBrush::GetEndPoint.md)|선형 그라데이션의 끝 좌표를 검색합니다.|  
|[CD2DLinearGradientBrush::GetStartPoint](../Topic/CD2DLinearGradientBrush::GetStartPoint.md)|선형 그라데이션의 시작 좌표를 검색합니다.|  
|[CD2DLinearGradientBrush::SetEndPoint](../Topic/CD2DLinearGradientBrush::SetEndPoint.md)|브러시의 좌표 공간에서 선형 그라데이션의 끝 좌표를 설정합니다.|  
|[CD2DLinearGradientBrush::SetStartPoint](../Topic/CD2DLinearGradientBrush::SetStartPoint.md)|브러시의 좌표 공간에서 선형 그라데이션의 시작 좌표를 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DLinearGradientBrush::operator ID2D1LinearGradientBrush\*](../Topic/CD2DLinearGradientBrush::operator%20ID2D1LinearGradientBrush*.md)|ID2D1LinearGradientBrush 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DLinearGradientBrush::m\_LinearGradientBrushProperties](../Topic/CD2DLinearGradientBrush::m_LinearGradientBrushProperties.md)|그라데이션의 시작점과 끝점입니다.|  
|[CD2DLinearGradientBrush::m\_pLinearGradientBrush](../Topic/CD2DLinearGradientBrush::m_pLinearGradientBrush.md)|ID2D1LinearGradientBrush에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)  
  
 [CD2DLinearGradientBrush](../../mfc/reference/cd2dlineargradientbrush-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)