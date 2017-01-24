---
title: "CD2DLayer 클래스 | Microsoft Docs"
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
  - "afxrendertarget/CD2DLayer"
  - "CD2DLayer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DLayer 클래스"
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DLayer 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Layer에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DLayer::CD2DLayer](../Topic/CD2DLayer::CD2DLayer.md)|CD2DLayer 개체를 생성합니다.|  
|[CD2DLayer::~CD2DLayer](../Topic/CD2DLayer::~CD2DLayer.md)|소멸자  D2D 계층 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DLayer::Attach](../Topic/CD2DLayer::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DLayer::Create](../Topic/CD2DLayer::Create.md)|CD2DLayer를 만듭니다.  \([CD2DResource::Create](../Topic/CD2DResource::Create.md) 무시.\)|  
|[CD2DLayer::Destroy](../Topic/CD2DLayer::Destroy.md)|CD2DLayer 개체를 소멸시킵니다.  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) 무시.\)|  
|[CD2DLayer::Detach](../Topic/CD2DLayer::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DLayer::Get](../Topic/CD2DLayer::Get.md)|ID2D1Layer 인터페이스를 반환합니다.|  
|[CD2DLayer::GetSize](../Topic/CD2DLayer::GetSize.md)|장치 독립적인 픽셀로 렌더링 대상의 크기를 반환합니다.|  
|[CD2DLayer::IsValid](../Topic/CD2DLayer::IsValid.md)|리소스 유효성 검사\([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) 무시\)|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DLayer::operator ID2D1Layer\*](../Topic/CD2DLayer::operator%20ID2D1Layer*.md)|ID2D1Layer 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DLayer::m\_pLayer](../Topic/CD2DLayer::m_pLayer.md)|ID2D1Layer 개체에 대한 포인터를 저장합니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DLayer](../../mfc/reference/cd2dlayer-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)