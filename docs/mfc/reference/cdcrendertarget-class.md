---
title: "CDCRenderTarget 클래스 | Microsoft Docs"
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
  - "afxrendertarget/CDCRenderTarget"
  - "CDCRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDCRenderTarget 클래스"
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
caps.latest.revision: 16
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDCRenderTarget 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1DCRenderTarget에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CDCRenderTarget : public CRenderTarget;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDCRenderTarget::CDCRenderTarget](../Topic/CDCRenderTarget::CDCRenderTarget.md)|CDCRenderTarget 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDCRenderTarget::Attach](../Topic/CDCRenderTarget::Attach.md)|개체에 기존 렌더링 대상 인터페이스를 연결합니다.|  
|[CDCRenderTarget::BindDC](../Topic/CDCRenderTarget::BindDC.md)|그리기 명령을 실행하는 장치 컨텍스트에 렌더링 대상을 바인딩합니다.|  
|[CDCRenderTarget::Create](../Topic/CDCRenderTarget::Create.md)|CDCRenderTarget을 만듭니다.|  
|[CDCRenderTarget::Detach](../Topic/CDCRenderTarget::Detach.md)|개체에서 렌더링 대상 인터페이스를 분리합니다.|  
|[CDCRenderTarget::GetDCRenderTarget](../Topic/CDCRenderTarget::GetDCRenderTarget.md)|ID2D1DCRenderTarget 인터페이스를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CDCRenderTarget::operator ID2D1DCRenderTarget\*](../Topic/CDCRenderTarget::operator%20ID2D1DCRenderTarget*.md)|ID2D1DCRenderTarget 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDCRenderTarget::m\_pDCRenderTarget](../Topic/CDCRenderTarget::m_pDCRenderTarget.md)|ID2D1DCRenderTarget 개체에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)