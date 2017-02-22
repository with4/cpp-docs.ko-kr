---
title: "CSinusoidalTransitionFromRange 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CSinusoidalTransitionFromRange"
  - "CSinusoidalTransitionFromRange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSinusoidalTransitionFromRange 클래스"
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSinusoidalTransitionFromRange 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

진동 범위가 지정된 사인 곡선 범위 전환을 캡슐화합니다.  
  
## 구문  
  
```  
class CSinusoidalTransitionFromRange : public CBaseTransition;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange](../Topic/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange.md)|전환 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSinusoidalTransitionFromRange::Create](../Topic/CSinusoidalTransitionFromRange::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CSinusoidalTransitionFromRange::m\_dblMaximumValue](../Topic/CSinusoidalTransitionFromRange::m_dblMaximumValue.md)|최대 sinusoidal 웨이브에서 애니메이션 변수의 값입니다.|  
|[CSinusoidalTransitionFromRange::m\_dblMinimumValue](../Topic/CSinusoidalTransitionFromRange::m_dblMinimumValue.md)|저점 sinusoidal 웨이브에서 애니메이션 변수의 값입니다.|  
|[CSinusoidalTransitionFromRange::m\_duration](../Topic/CSinusoidalTransitionFromRange::m_duration.md)|전환 기간입니다.|  
|[CSinusoidalTransitionFromRange::m\_period](../Topic/CSinusoidalTransitionFromRange::m_period.md)|sinusoidal 웨이브의 진동 기간\(초\)입니다.|  
|[CSinusoidalTransitionFromRange::m\_slope](../Topic/CSinusoidalTransitionFromRange::m_slope.md)|전환을 시작할 때의 슬로프입니다.|  
  
## 설명  
 애니메이션 변수의 값은 sinusoidal 범위 전환의 전체 기간 동안 지정한 최소 및 최대 값 사이에서 변동합니다.  기울기 매개 변수는 다른 매개 변수에 의해 지정된 두 가지 가능한 사인파를 구분하는 데 사용됩니다.  모든 전환은 자동으로 지워지므로 operator new를 사용하여 할당하는 것이 좋습니다.  캡슐화된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup에 의해 만들어집니다.  이 COM 개체 만든 후에 멤버 변수를 변경해도 효과가 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)