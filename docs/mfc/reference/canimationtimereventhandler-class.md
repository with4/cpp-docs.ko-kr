---
title: "CAnimationTimerEventHandler 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationTimerEventHandler"
  - "CAnimationTimerEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationTimerEventHandler 클래스"
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationTimerEventHandler 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

타이밍 이벤트가 발생할 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## 구문  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationTimerEventHandler::CreateInstance](../Topic/CAnimationTimerEventHandler::CreateInstance.md)|인스턴스를 만들고 `CAnimationTimerEventHandler` 콜백 합니다.|  
|[CAnimationTimerEventHandler::OnPostUpdate](../Topic/CAnimationTimerEventHandler::OnPostUpdate.md)|애니메이션 업데이트가 완료된 후에 발생하는 이벤트를 처리합니다.  \(재정의 `CUIAnimationTimerEventHandlerBase::OnPostUpdate`.\)|  
|[CAnimationTimerEventHandler::OnPreUpdate](../Topic/CAnimationTimerEventHandler::OnPreUpdate.md)|애니메이션 업데이트가 시작되기 전에 발생하는 이벤트를 처리합니다.  \(재정의 `CUIAnimationTimerEventHandlerBase::OnPreUpdate`.\)|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](../Topic/CAnimationTimerEventHandler::OnRenderingTooSlow.md)|애니메이션에 대한 렌더링 프레임 속도가 원하는 최소 프레임 속도 이하일 때 발생하는 이벤트를 처리합니다.  \(재정의 `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`.\)|  
|[CAnimationTimerEventHandler::SetAnimationController](../Topic/CAnimationTimerEventHandler::SetAnimationController.md)|애니메이션 컨트롤러에 대한 포인터를 라우팅 이벤트에 저장합니다.|  
  
## 설명  
 이 이벤트 처리기가 만들어지고 CAnimationController::EnableAnimationTimerEventHandler를 호출할 때 IUIAnimationTimer::SetTimerEventHandler로 전달됩니다.  
  
## 상속 계층 구조  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)