---
title: "CAnimationStoryboardEventHandler 클래스 | Microsoft Docs"
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
  - "afxanimationcontroller/CAnimationStoryboardEventHandler"
  - "CAnimationStoryboardEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationStoryboardEventHandler 클래스"
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationStoryboardEventHandler 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스토리보드의 상태가 변경되거나 스토리보드가 업데이트될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## 구문  
  
```  
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](../Topic/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler.md)|`CAnimationStoryboardEventHandler` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationStoryboardEventHandler::CreateInstance](../Topic/CAnimationStoryboardEventHandler::CreateInstance.md)|인스턴스를 만들고 `CAnimationStoryboardEventHandler` 콜백 합니다.|  
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](../Topic/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged.md)|처리 `OnStoryboardStatusChanged` 스토리 보드의 상태가 변경 될 때 발생 하는 이벤트를 \(무시 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.\)|  
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](../Topic/CAnimationStoryboardEventHandler::OnStoryboardUpdated.md)|처리 `OnStoryboardUpdated` 스토리 보드를 업데이트할 때 발생 하는 이벤트를 \(무시 `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.\)|  
|[CAnimationStoryboardEventHandler::SetAnimationController](../Topic/CAnimationStoryboardEventHandler::SetAnimationController.md)|애니메이션 컨트롤러에 대한 포인터를 라우팅 이벤트에 저장합니다.|  
  
## 설명  
 이 이벤트 처리기를 만들고 전달 `IUIAnimationStoryboard::SetStoryboardEventHandler` 메서드를 호출 하면 `CAnimationController::EnableStoryboardEventHandler`.  
  
## 상속 계층 구조  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)