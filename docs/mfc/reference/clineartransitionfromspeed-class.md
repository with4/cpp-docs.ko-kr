---
title: "CLinearTransitionFromSpeed 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CLinearTransitionFromSpeed"
  - "CLinearTransitionFromSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransitionFromSpeed 클래스"
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CLinearTransitionFromSpeed 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

선형 속도 전환을 캡슐화합니다.  
  
## 구문  
  
```  
class CLinearTransitionFromSpeed : public CBaseTransition;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](../Topic/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed.md)|선형 속도 전환 개체를 생성하고 속도와 마지막 값으로 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CLinearTransitionFromSpeed::Create](../Topic/CLinearTransitionFromSpeed::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CLinearTransitionFromSpeed::m\_dblFinalValue](../Topic/CLinearTransitionFromSpeed::m_dblFinalValue.md)|전환이 끝날 때 애니메이션 변수의 값입니다.|  
|[CLinearTransitionFromSpeed::m\_dblSpeed](../Topic/CLinearTransitionFromSpeed::m_dblSpeed.md)|변수 속도의 절대값입니다.|  
  
## 설명  
 선형 속도 전환 중에 지정한 속도로 애니메이션 변수의 값을 변경합니다.  전환 기간은 초기 값과 지정된 최종 값 사이의 차로 결정됩니다.  모든 전환은 자동으로 지워지므로 operator new를 사용하여 할당하는 것이 좋습니다.  캡슐화된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup에 의해 만들어집니다.  이 COM 개체 만든 후에 멤버 변수를 변경해도 효과가 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)