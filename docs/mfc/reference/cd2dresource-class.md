---
title: "CD2DResource 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DResource"
  - "CD2DResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DResource 클래스"
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DResource 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

브러시, 레이어 및 텍스트 같은 D2D 리소스를 만들고 관리하기 위한 인터페이스를 제공하는 추상 클래스입니다.  
  
## 구문  
  
```  
class CD2DResource : public CObject;  
```  
  
## Members  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[CD2DResource::CD2DResource](../Topic/CD2DResource::CD2DResource.md)|CD2DResource 개체를 생성합니다.|  
|[CD2DResource::~CD2DResource](../Topic/CD2DResource::~CD2DResource.md)|소멸자  D2D 리소스 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DResource::Create](../Topic/CD2DResource::Create.md)|CD2DResource를 만듭니다.|  
|[CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md)|CD2DResource 개체를 소멸시킵니다.|  
|[CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md)|리소스 유효성 검사|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CD2DResource::IsAutoDestroy](../Topic/CD2DResource::IsAutoDestroy.md)|자동 소멸 플래그를 검사합니다.|  
|[CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md)|CD2DResource를 다시 만듭니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CD2DResource::m\_bIsAutoDestroy](../Topic/CD2DResource::m_bIsAutoDestroy.md)|리소스는 소유자\(CRenderTarget\)에 의해 소멸됩니다.|  
|[CD2DResource::m\_pParentTarget](../Topic/CD2DResource::m_pParentTarget.md)|부모 CRenderTarget에 대한 포인터\)|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)