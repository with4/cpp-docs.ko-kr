---
title: "CSinusoidalTransitionFromVelocity 클래스 | Microsoft Docs"
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
  - "CSinusoidalTransitionFromVelocity"
  - "afxanimationcontroller/CSinusoidalTransitionFromVelocity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSinusoidalTransitionFromVelocity 클래스"
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSinusoidalTransitionFromVelocity 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션 변수의 초기 속도에 의해 진폭이 결정되는 사인 곡선 속도 전환을 캡슐화합니다.  
  
## 구문  
  
```  
class CSinusoidalTransitionFromVelocity : public CBaseTransition;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](../Topic/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity.md)|전환 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSinusoidalTransitionFromVelocity::Create](../Topic/CSinusoidalTransitionFromVelocity::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CSinusoidalTransitionFromVelocity::m\_duration](../Topic/CSinusoidalTransitionFromVelocity::m_duration.md)|전환 기간입니다.|  
|[CSinusoidalTransitionFromVelocity::m\_period](../Topic/CSinusoidalTransitionFromVelocity::m_period.md)|sinusoidal 웨이브의 진동 기간\(초\)입니다.|  
  
## 설명  
 애니메이션 변수의 값은 sinusoidal 범위 전환의 전체 기간 동안 초기 값 주변을 오고 갑니다.  전환을 시작할 때 진폭 속도는 애니메이션 변수 속도에 의해 결정됩니다.  모든 전환은 자동으로 지워지므로 operator new를 사용하여 할당하는 것이 좋습니다.  캡슐화된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup에 의해 만들어집니다.  이 COM 개체 만든 후에 멤버 변수를 변경해도 효과가 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)