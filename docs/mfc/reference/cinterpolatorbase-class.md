---
title: "CInterpolatorBase 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CInterpolatorBase"
  - "CInterpolatorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterpolatorBase 클래스"
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CInterpolatorBase 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션 API에서 애니메이션 변수의 새 값을 계산해야 할 때 호출하는 콜백을 구현합니다.  
  
## 구문  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CInterpolatorBase::CInterpolatorBase](../Topic/CInterpolatorBase::CInterpolatorBase.md)|생성 된 `CInterpolatorBase` 개체입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CInterpolatorBase::CreateInstance](../Topic/CInterpolatorBase::CreateInstance.md)|인스턴스를 만들고 `CInterpolatorBase` 이벤트를 처리 하는 사용자 지정 interpolator에 대 한 포인터를 저장 합니다.|  
|[CInterpolatorBase::GetDependencies](../Topic/CInterpolatorBase::GetDependencies.md)|보간기의 종속성을 가져옵니다.  \(재정의 `CUIAnimationInterpolatorBase::GetDependencies`.\)|  
|[CInterpolatorBase::GetDuration](../Topic/CInterpolatorBase::GetDuration.md)|보간기의 기간을 가져옵니다.  \(재정의 `CUIAnimationInterpolatorBase::GetDuration`.\)|  
|[CInterpolatorBase::GetFinalValue](../Topic/CInterpolatorBase::GetFinalValue.md)|보간기가 안내하는 최종 값을 가져옵니다.  \(재정의 `CUIAnimationInterpolatorBase::GetFinalValue`.\)|  
|[CInterpolatorBase::InterpolateValue](../Topic/CInterpolatorBase::InterpolateValue.md)|지정 된 오프셋 값을 보간하여 \(재정의 `CUIAnimationInterpolatorBase::InterpolateValue`.\)|  
|[CInterpolatorBase::InterpolateVelocity](../Topic/CInterpolatorBase::InterpolateVelocity.md)|보간 속도 지정 된 오프셋 \(재정의 `CUIAnimationInterpolatorBase::InterpolateVelocity`.\)|  
|[CInterpolatorBase::SetCustomInterpolator](../Topic/CInterpolatorBase::SetCustomInterpolator.md)|이벤트를 처리할 사용자 지정 interpolator에 대한 포인터를 저장합니다.|  
|[CInterpolatorBase::SetDuration](../Topic/CInterpolatorBase::SetDuration.md)|Interpolator의 기간 설정 \(재정의 `CUIAnimationInterpolatorBase::SetDuration`.\)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](../Topic/CInterpolatorBase::SetInitialValueAndVelocity.md)|보간기의 초기 값 및 속도를 설정합니다.  \(재정의 `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.\)|  
  
## 설명  
 이 처리기를 만들고 전달 `IUIAnimationTransitionFactory::CreateTransition` 경우는 `CCustomTransition` 개체 애니메이션 초기화 프로세스의 일부로 생성 됩니다 \(시작 `CAnimationController::AnimateGroup`\).  일반적으로이 클래스를 직접 사용 하지 않아도, 모든 이벤트를 방금 routs는 `CCustomInterpolator`\-해당 포인터의 생성자에 전달 되는 클래스를 파생 `CCustomTransition`.  
  
## 상속 계층 구조  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)