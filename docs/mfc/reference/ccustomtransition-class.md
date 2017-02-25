---
title: "CCustomTransition 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CCustomTransition"
  - "CCustomTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomTransition 클래스"
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CCustomTransition 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

사용자 지정 전환을 구현합니다.  
  
## 구문  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CCustomTransition::CCustomTransition](../Topic/CCustomTransition::CCustomTransition.md)|사용자 지정 전환 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CCustomTransition::Create](../Topic/CCustomTransition::Create.md)|전환 라이브러리를 호출하여 캡슐화된 전환 COM 개체를 만듭니다.  \([CBaseTransition::Create](../Topic/CBaseTransition::Create.md) 무시.\)|  
|[CCustomTransition::SetInitialValue](../Topic/CCustomTransition::SetInitialValue.md)|이 전환과 관련된 애니메이션 변수에 적용할 초기 값을 설정합니다.|  
|[CCustomTransition::SetInitialVelocity](../Topic/CCustomTransition::SetInitialVelocity.md)|이 전환과 관련된 애니메이션 변수에 적용할 초기 속도를 설정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CCustomTransition::m\_bInitialValueSpecified](../Topic/CCustomTransition::m_bInitialValueSpecified.md)|초기 값이 SetInitialValue로 지정되었는지 여부를 지정합니다.|  
|[CCustomTransition::m\_bInitialVelocitySpecified](../Topic/CCustomTransition::m_bInitialVelocitySpecified.md)|초기 속도가 SetInitialVelocity로 지정되었는지 여부를 지정합니다.|  
|[CCustomTransition::m\_initialValue](../Topic/CCustomTransition::m_initialValue.md)|초기값을 저장합니다.|  
|[CCustomTransition::m\_initialVelocity](../Topic/CCustomTransition::m_initialVelocity.md)|초기 속도를 저장합니다.|  
|[CCustomTransition::m\_pInterpolator](../Topic/CCustomTransition::m_pInterpolator.md)|사용자 지정 보간기에 대한 포인터를 저장합니다.|  
  
## 설명  
 CCustomTransitions 클래스를 사용하면 개발자가 사용자 지정 전환을 구현할 수 있습니다.  표준 전환으로 만들고 사용되지만 생성자는 사용자 지정 보간기에 대한 포인터를 매개 변수로 받습니다.  사용자 지정 전환을 사용하려면 다음 단계를 수행하십시오: 1.  CCustomInterpolator에서 클래스를 파생시키고 최소한 InterpolateValue 메서드를 구현합니다.  2.  사용자 지정 보간기 개체의 수명은 사용되는 애니메이션 기간보다 길어야 합니다.  3.  \(new 연산자 사용\) CCustomTransition 개체를 인스턴스화하고 생성자의 사용자 지정 보간기에 포인터를 전달합니다.  4.  이러한 매개 변수에 사용자 지정 보간이 필요한 경우 CCustomTransition::SetInitialValue 및 CCustomTransition::SetInitialVelocity를 호출합니다.  5.  사용자 지정 전환에 대한 포인터를 애니메이션 개체의 AddTransition 메서드에 전달하여 사용자 지정 알고리즘으로 값을 애니메이션해야 합니다.  6.  애니메이션 개체의 값을 변경해야 할 때 Windows 애니메이션 API는 CCustomInterpolator에서 InterpolateValue\(및 다른 관련 메서드\)를 호출합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CCustomTransition](../../mfc/reference/ccustomtransition-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)