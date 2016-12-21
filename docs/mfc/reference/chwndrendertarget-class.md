---
title: "CHwndRenderTarget 클래스 | Microsoft Docs"
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
  - "CHwndRenderTarget"
  - "afxrendertarget/CHwndRenderTarget"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHwndRenderTarget 클래스"
ms.assetid: aa65b69f-7202-46ea-af81-ef325da0b840
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHwndRenderTarget 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ID2D1HwndRenderTarget에 대한 래퍼입니다.  
  
## 구문  
  
```  
class CHwndRenderTarget : public CRenderTarget;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CHwndRenderTarget::CHwndRenderTarget](../Topic/CHwndRenderTarget::CHwndRenderTarget.md)|HWND에서 CHwndRenderTarget 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHwndRenderTarget::Attach](../Topic/CHwndRenderTarget::Attach.md)|개체에 기존 렌더링 대상 인터페이스를 연결합니다.|  
|[CHwndRenderTarget::CheckWindowState](../Topic/CHwndRenderTarget::CheckWindowState.md)|이 렌더링 대상에 연결된 HWND가 내포되었는지 여부를 나타냅니다.|  
|[CHwndRenderTarget::Create](../Topic/CHwndRenderTarget::Create.md)|창에 연결된 렌더링 대상을 만듭니다.|  
|[CHwndRenderTarget::Detach](../Topic/CHwndRenderTarget::Detach.md)|개체에서 렌더링 대상 인터페이스를 분리합니다.|  
|[CHwndRenderTarget::GetHwnd](../Topic/CHwndRenderTarget::GetHwnd.md)|이 렌더링 대상과 연결된 HWND를 반환합니다.|  
|[CHwndRenderTarget::GetHwndRenderTarget](../Topic/CHwndRenderTarget::GetHwndRenderTarget.md)|ID2D1HwndRenderTarget 인터페이스를 반환합니다.|  
|[CHwndRenderTarget::ReCreate](../Topic/CHwndRenderTarget::ReCreate.md)|창에 연결된 렌더링 대상을 다시 만듭니다.|  
|[CHwndRenderTarget::Resize](../Topic/CHwndRenderTarget::Resize.md)|렌더링 대상의 크기를 지정된 픽셀 크기로 변경합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CHwndRenderTarget::operator ID2D1HwndRenderTarget\*](../Topic/CHwndRenderTarget::operator%20ID2D1HwndRenderTarget*.md)|ID2D1HwndRenderTarget 인터페이스를 반환합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CHwndRenderTarget::m\_pHwndRenderTarget](../Topic/CHwndRenderTarget::m_pHwndRenderTarget.md)|ID2D1HwndRenderTarget 개체에 대한 포인터입니다.|  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
 [CHwndRenderTarget](../../mfc/reference/chwndrendertarget-class.md)  
  
## 요구 사항  
 **헤더:** afxrendertarget.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)