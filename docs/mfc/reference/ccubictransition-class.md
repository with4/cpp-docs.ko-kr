---
title: "CCubicTransition 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCubicTransition"
  - "afxanimationcontroller/CCubicTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCubicTransition 클래스"
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CCubicTransition 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

3차원 전환을 캡슐화합니다.  
  
## 구문  
  
```  
class CCubicTransition : public CBaseTransition;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCubicTransition::CCubicTransition](../Topic/CCubicTransition::CCubicTransition.md)|전환 개체를 생성하고 매개 변수를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCubicTransition::Create](../Topic/CCubicTransition::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCubicTransition::m\_dblFinalValue](../Topic/CCubicTransition::m_dblFinalValue.md)|전환이 끝날 때 애니메이션 변수의 값입니다.|  
|[CCubicTransition::m\_dblFinalVelocity](../Topic/CCubicTransition::m_dblFinalVelocity.md)|전환이 끝날 때 변수의 속도입니다.|  
|[CCubicTransition::m\_duration](../Topic/CCubicTransition::m_duration.md)|전환 기간입니다.|  
  
## 설명  
 큐빅 전환 중에 애니메이션 변수의 값이 전환 기간 동안 초기 값에서 최종 지정된 값으로 변경되고 지정된 속도로 끝납니다.  모든 전환은 자동으로 지워지므로 operator new를 사용하여 할당하는 것이 좋습니다.  캡슐화된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup에 의해 만들어집니다.  이 COM 개체 만든 후에 멤버 변수를 변경해도 효과가 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CCubicTransition](../../mfc/reference/ccubictransition-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)