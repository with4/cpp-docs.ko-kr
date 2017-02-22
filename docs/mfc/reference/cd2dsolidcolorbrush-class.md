---
title: "CD2DSolidColorBrush 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DSolidColorBrush"
  - "afxrendertarget/CD2DSolidColorBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DSolidColorBrush 클래스"
ms.assetid: d4506637-acce-4f74-8a9b-f0a45571a735
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CD2DSolidColorBrush 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1SolidColorBrush에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DSolidColorBrush : public CD2DBrush;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DSolidColorBrush::CD2DSolidColorBrush](../Topic/CD2DSolidColorBrush::CD2DSolidColorBrush.md)|오버로드.  CD2DSolidColorBrush 개체를 생성합니다.|  
|[CD2DSolidColorBrush::~CD2DSolidColorBrush](../Topic/CD2DSolidColorBrush::~CD2DSolidColorBrush.md)|소멸자  D2D 단색 브러시 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DSolidColorBrush::Attach](../Topic/CD2DSolidColorBrush::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DSolidColorBrush::Create](../Topic/CD2DSolidColorBrush::Create.md)|CD2DSolidColorBrush를 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DSolidColorBrush::Destroy](../Topic/CD2DSolidColorBrush::Destroy.md)|CD2DSolidColorBrush 개체를 소멸시킵니다.  \([CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md) 무시.\)|  
|[CD2DSolidColorBrush::Detach](../Topic/CD2DSolidColorBrush::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DSolidColorBrush::Get](../Topic/CD2DSolidColorBrush::Get.md)|ID2D1SolidColorBrush 인터페이스를 반환합니다.|  
|[CD2DSolidColorBrush::GetColor](../Topic/CD2DSolidColorBrush::GetColor.md)|단색 브러시 색을 검색합니다.|  
|[CD2DSolidColorBrush::SetColor](../Topic/CD2DSolidColorBrush::SetColor.md)|이 단색 브러시의 색을 지정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DSolidColorBrush::operator ID2D1SolidColorBrush\*](../Topic/CD2DSolidColorBrush::operator%20ID2D1SolidColorBrush*.md)|ID2D1SolidColorBrush 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DSolidColorBrush::m\_colorSolid](../Topic/CD2DSolidColorBrush::m_colorSolid.md)|브러시 단색입니다.|  
|[CD2DSolidColorBrush::m\_pSolidColorBrush](../Topic/CD2DSolidColorBrush::m_pSolidColorBrush.md)|ID2D1SolidColorBrush 개체에 대한 포인터를 저장합니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
 [CD2DSolidColorBrush](../../mfc/reference/cd2dsolidcolorbrush-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)