---
title: "CCustomInterpolator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CCustomInterpolator"
  - "CCustomInterpolator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomInterpolator 클래스"
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CCustomInterpolator 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 보간자를 구현합니다.  
  
## 구문  
  
```  
class CCustomInterpolator;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCustomInterpolator::CCustomInterpolator](../Topic/CCustomInterpolator::CCustomInterpolator.md)|오버로드.  사용자 지정 보간기 개체를 생성하고 기간과 속도를 지정된 값으로 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCustomInterpolator::GetDependencies](../Topic/CCustomInterpolator::GetDependencies.md)|보간기의 종속성을 가져옵니다.|  
|[CCustomInterpolator::GetDuration](../Topic/CCustomInterpolator::GetDuration.md)|보간기의 기간을 가져옵니다.|  
|[CCustomInterpolator::GetFinalValue](../Topic/CCustomInterpolator::GetFinalValue.md)|보간기가 안내하는 최종 값을 가져옵니다.|  
|[CCustomInterpolator::Init](../Topic/CCustomInterpolator::Init.md)|기간 및 최종 값을 초기화합니다.|  
|[CCustomInterpolator::InterpolateValue](../Topic/CCustomInterpolator::InterpolateValue.md)|지정된 오프셋에서 값을 보간합니다.|  
|[CCustomInterpolator::InterpolateVelocity](../Topic/CCustomInterpolator::InterpolateVelocity.md)|지정된 오프셋에서 속도를 보간합니다.|  
|[CCustomInterpolator::SetDuration](../Topic/CCustomInterpolator::SetDuration.md)|보간기의 기간을 설정합니다.|  
|[CCustomInterpolator::SetInitialValueAndVelocity](../Topic/CCustomInterpolator::SetInitialValueAndVelocity.md)|보간기의 초기 값 및 속도를 설정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCustomInterpolator::m\_currentValue](../Topic/CCustomInterpolator::m_currentValue.md)|보간된 값입니다.|  
|[CCustomInterpolator::m\_currentVelocity](../Topic/CCustomInterpolator::m_currentVelocity.md)|보간된 속도입니다.|  
|[CCustomInterpolator::m\_duration](../Topic/CCustomInterpolator::m_duration.md)|전환 기간입니다.|  
|[CCustomInterpolator::m\_finalValue](../Topic/CCustomInterpolator::m_finalValue.md)|전환이 끝날 때 변수의 최종 값입니다.|  
|[CCustomInterpolator::m\_initialValue](../Topic/CCustomInterpolator::m_initialValue.md)|전환을 시작할 때 변수의 값입니다.|  
|[CCustomInterpolator::m\_initialVelocity](../Topic/CCustomInterpolator::m_initialVelocity.md)|전환을 시작할 때 변수의 속도입니다.|  
  
## 설명  
 CCustomInterpolator에서 클래스를 파생시키고 사용자 지정 보간 알고리즘을 구현하기 위해 필요한 모든 메서드를 재정의합니다.  이 클래스에 대한 포인터를 CCustomTransition에 매개 변수로 전달해야 합니다.  
  
## 상속 계층 구조  
 [CCustomInterpolator](../../mfc/reference/ccustominterpolator-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)