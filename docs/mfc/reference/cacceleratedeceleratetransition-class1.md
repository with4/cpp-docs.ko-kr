---
title: "CAccelerateDecelerateTransition Class1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAccelerateDecelerateTransition"
  - "afxanimationcontroller/CAccelerateDecelerateTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccelerateDecelerateTransition 클래스"
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CAccelerateDecelerateTransition 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가속\-감속 전환을 구현합니다.  
  
## 구문  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](../Topic/CAccelerateDecelerateTransition::CAccelerateDecelerateTransition.md)|전환 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAccelerateDecelerateTransition::Create](../Topic/CAccelerateDecelerateTransition::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAccelerateDecelerateTransition::m\_accelerationRatio](../Topic/CAccelerateDecelerateTransition::m_accelerationRatio.md)|기간으로 가속하는 데 걸리는 시간의 비율입니다.|  
|[CAccelerateDecelerateTransition::m\_decelerationRatio](../Topic/CAccelerateDecelerateTransition::m_decelerationRatio.md)|기간으로 감속하는 데 걸리는 시간의 비율입니다.|  
|[CAccelerateDecelerateTransition::m\_duration](../Topic/CAccelerateDecelerateTransition::m_duration.md)|전환 기간입니다.|  
|[CAccelerateDecelerateTransition::m\_finalValue](../Topic/CAccelerateDecelerateTransition::m_finalValue.md)|전환이 끝날 때 애니메이션 변수의 값입니다.|  
  
## 설명  
 가속\-감속 전환 중에 애니메이션 변수는 전환 기간 동안 가속되었다가 감속되고 지정된 값에서 끝납니다.  다른 가속 및 감속 속도를 지정하여 변수를 얼마나 빠르게 독립적으로 가속하고 감속할지 제어할 수 있습니다.  초기 속도가 0이면 가속 속도는 변수가 가속에 사용하는 기간의 일부이며, 감속 속도에서도 마찬가지입니다.  초기 속도가 0이 아닌 경우 0에 도달하는 속도와 전환 끝 사이의 시간입니다.  가속 비율 및 감속 비율 합계가 최대 1.0이 되어야 합니다.  모든 전환은 자동으로 지워지므로 operator new를 사용하여 할당하는 것이 좋습니다.  캡슐화된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup에 의해 만들어집니다.  이 COM 개체 만든 후에 멤버 변수를 변경해도 효과가 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CAccelerateDecelerateTransition](../../mfc/reference/cacceleratedeceleratetransition-class1.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)