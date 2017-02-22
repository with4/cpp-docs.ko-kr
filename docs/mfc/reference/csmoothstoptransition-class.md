---
title: "CSmoothStopTransition 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSmoothStopTransition"
  - "afxanimationcontroller/CSmoothStopTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSmoothStopTransition 클래스"
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSmoothStopTransition 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

부드러운 중지 전환을 캡슐화합니다.  
  
## 구문  
  
```  
class CSmoothStopTransition : public CBaseTransition;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSmoothStopTransition::CSmoothStopTransition](../Topic/CSmoothStopTransition::CSmoothStopTransition.md)|부드러운 중지 전환을 생성하고 최대 기간과 마지막 값을 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSmoothStopTransition::Create](../Topic/CSmoothStopTransition::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CSmoothStopTransition::m\_dblFinalValue](../Topic/CSmoothStopTransition::m_dblFinalValue.md)|전환이 끝날 때 애니메이션 변수의 값입니다.|  
|[CSmoothStopTransition::m\_maximumDuration](../Topic/CSmoothStopTransition::m_maximumDuration.md)|전환의 최대 기간입니다.|  
  
## 설명  
 주어진 최종 값에 접근하고 속도 0에 도달하므로 부드러운 중지 전환은 속도가 느려집니다.  전환 기간은 초기 값과 최종 값 및 최대 기간 사이의 차인 초기 속도로 결정됩니다.  단일 포물선 원호로 구성되는 솔루션이 없는 경우 이 메서드는 3차원 전환을 만듭니다.  모든 전환은 자동으로 지워지므로 operator new를 사용하여 할당하는 것이 좋습니다.  캡슐화된 IUIAnimationTransition COM 개체는 NULL이 될 때까지 CAnimationController::AnimateGroup에 의해 만들어집니다.  이 COM 개체 만든 후에 멤버 변수를 변경해도 효과가 없습니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)