---
title: "CAnimationVariableChangeHandler 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationVariableChangeHandler"
  - "CAnimationVariableChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableChangeHandler 클래스"
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CAnimationVariableChangeHandler 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션 변수 값이 변경될 때 애니메이션 API에서 호출하는 콜백을 구현합니다.  
  
## 구문  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|`CAnimationVariableChangeHandler` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|`CAnimationVariableChangeHandler::CreateInstance`|인스턴스를 만들고 `CAnimationVariableChangeHandler` 개체입니다.|  
|[CAnimationVariableChangeHandler::OnValueChanged](../Topic/CAnimationVariableChangeHandler::OnValueChanged.md)|애니메이션 변수의 값이 변경될 때 호출되었습니다.  \(재정의 `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.\)|  
|[CAnimationVariableChangeHandler::SetAnimationController](../Topic/CAnimationVariableChangeHandler::SetAnimationController.md)|애니메이션 컨트롤러에 대한 포인터를 라우팅 이벤트에 저장합니다.|  
  
## 설명  
 이 이벤트 처리기를 만들고 전달 `IUIAnimationVariable::SetVariableChangeHandler` 메서드를 호출 하면 `CAnimationVariable::EnableValueChangedEvent` 또는 `CAnimationBaseObject::EnableValueChangedEvent` \(있습니다이 애니메이션 개체에 캡슐화 된 모든 애니메이션 변수에 대 한이 이벤트\).  
  
## 상속 계층 구조  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)