---
title: "CDiscreteTransition 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDiscreteTransition"
  - "afxanimationcontroller/CDiscreteTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDiscreteTransition 클래스"
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CDiscreteTransition 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

불연속 전환을 캡슐화합니다.  
  
## 구문  
  
```  
class CDiscreteTransition : public CBaseTransition;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CDiscreteTransition::CDiscreteTransition](../Topic/CDiscreteTransition::CDiscreteTransition.md)|불연속 전환 개체를 생성하고 매개 변수를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CDiscreteTransition::Create](../Topic/CDiscreteTransition::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CDiscreteTransition::m\_dblFinalValue](../Topic/CDiscreteTransition::m_dblFinalValue.md)|전환이 끝날 때 애니메이션 변수의 값입니다.|  
|[CDiscreteTransition::m\_delay](../Topic/CDiscreteTransition::m_delay.md)|인스턴스화 스위치를 최종 값으로 지연시키는 기간입니다.|  
|[CDiscreteTransition::m\_hold](../Topic/CDiscreteTransition::m_hold.md)|변수를 최종 값으로 유지하는 기간입니다.|  
  
## 설명  
 불연속 전환 중에 애니메이션 변수는 지정된 지연 시간 동안 초기 값을 유지한 다음 즉시 최종 지정된 값으로 전환되고 지정된 대기 시간 동안 이 값을 유지합니다.  모든 전환은 자동으로 지워지므로 operator new를 사용하여 할당하는 것이 좋습니다.  캡슐화된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup에 의해 만들어집니다.  이 COM 개체 만든 후에 멤버 변수를 변경해도 효과가 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)