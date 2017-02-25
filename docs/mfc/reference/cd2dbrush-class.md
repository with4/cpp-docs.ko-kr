---
title: "CD2DBrush 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DBrush"
  - "afxrendertarget/CD2DBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBrush 클래스"
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DBrush 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1Brush에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DBrush::CD2DBrush](../Topic/CD2DBrush::CD2DBrush.md)|CD2DBrush 개체를 생성합니다.|  
|[CD2DBrush::~CD2DBrush](../Topic/CD2DBrush::~CD2DBrush.md)|소멸자  D2D 브러시 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DBrush::Attach](../Topic/CD2DBrush::Attach.md)|개체에 기존 리소스 인터페이스를 연결합니다.|  
|[CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md)|CD2DBrush 개체를 소멸시킵니다.  \([CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md) 무시.\)|  
|[CD2DBrush::Detach](../Topic/CD2DBrush::Detach.md)|개체에서 리소스 인터페이스를 분리합니다.|  
|[CD2DBrush::Get](../Topic/CD2DBrush::Get.md)|ID2D1Brush 인터페이스를 반환합니다.|  
|[CD2DBrush::GetOpacity](../Topic/CD2DBrush::GetOpacity.md)|브러시의 불투명도를 가져옵니다.|  
|[CD2DBrush::GetTransform](../Topic/CD2DBrush::GetTransform.md)|렌더링 대상의 현재 변환을 가져옵니다.|  
|[CD2DBrush::IsValid](../Topic/CD2DBrush::IsValid.md)|리소스 유효성 검사\([CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md) 무시\)|  
|[CD2DBrush::SetOpacity](../Topic/CD2DBrush::SetOpacity.md)|이 브러시의 불투명도를 설정합니다.|  
|[CD2DBrush::SetTransform](../Topic/CD2DBrush::SetTransform.md)|렌더링 대상에 지정된 변환을 적용하여 기존 변환을 바꿉니다.  이후의 모든 그리기 작업은 변환된 공간에서 발생합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CD2DBrush::operator ID2D1Brush\*](../Topic/CD2DBrush::operator%20ID2D1Brush*.md)|ID2D1Brush 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DBrush::m\_pBrush](../Topic/CD2DBrush::m_pBrush.md)|ID2D1Brush 개체에 대한 포인터를 저장합니다.|  
|[CD2DBrush::m\_pBrushProperties](../Topic/CD2DBrush::m_pBrushProperties.md)|Brush 속성입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)