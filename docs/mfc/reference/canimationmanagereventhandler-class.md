---
title: "CAnimationManagerEventHandler 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationManagerEventHandler"
  - "CAnimationManagerEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationManagerEventHandler 클래스"
ms.assetid: 6089ec07-e661-4805-b227-823b4652aade
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationManagerEventHandler 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션 관리자의 상태가 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## 구문  
  
```  
class CAnimationManagerEventHandler : public CUIAnimationManagerEventHandlerBase<CAnimationManagerEventHandler>;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationManagerEventHandler::CAnimationManagerEventHandler](../Topic/CAnimationManagerEventHandler::CAnimationManagerEventHandler.md)|`CAnimationManagerEventHandler` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationManagerEventHandler::CreateInstance](../Topic/CAnimationManagerEventHandler::CreateInstance.md)|인스턴스를 만들고 `CAnimationManagerEventHandler` 개체입니다.|  
|[CAnimationManagerEventHandler::OnManagerStatusChanged](../Topic/CAnimationManagerEventHandler::OnManagerStatusChanged.md)|애니메이션 관리자의 상태가 변경될 때 호출됩니다.  \(재정의 `CUIAnimationManagerEventHandlerBase::OnManagerStatusChanged`.\)|  
|[CAnimationManagerEventHandler::SetAnimationController](../Topic/CAnimationManagerEventHandler::SetAnimationController.md)|애니메이션 컨트롤러에 대한 포인터를 라우팅 이벤트에 저장합니다.|  
  
## 설명  
 이 이벤트 처리기가 만들어지고 CAnimationController::EnableAnimationManagerEvent를 호출할 때 IUIAnimationManager::SetManagerEventHandler 메서드에 전달됩니다.  
  
## 상속 계층 구조  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationManagerEventHandlerBase`  
  
 `CAnimationManagerEventHandler`  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)