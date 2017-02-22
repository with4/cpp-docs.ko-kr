---
title: "CAnimationValue 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationValue"
  - "CAnimationValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationValue 클래스"
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationValue 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

하나의 값을 갖는 애니메이션 개체 기능을 구현합니다.  
  
## 구문  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationValue::CAnimationValue](../Topic/CAnimationValue::CAnimationValue.md)|오버로드.  CAnimationValue 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationValue::AddTransition](../Topic/CAnimationValue::AddTransition.md)|적용할 전환을 값에 추가합니다.|  
|[CAnimationValue::GetValue](../Topic/CAnimationValue::GetValue.md)|오버로드.  현재 값을 검색합니다.|  
|[CAnimationValue::GetVariable](../Topic/CAnimationValue::GetVariable.md)|캡슐화된 애니메이션 변수에 대한 액세스를 제공합니다.|  
|[CAnimationValue::SetDefaultValue](../Topic/CAnimationValue::SetDefaultValue.md)|기본값을 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationValue::GetAnimationVariableList](../Topic/CAnimationValue::GetAnimationVariableList.md)|캡슐화된 애니메이션 변수를 목록에 추가합니다.  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) 무시.\)|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationValue::operator DOUBLE](../Topic/CAnimationValue::operator%20DOUBLE.md)|CAnimationValue와 DOUBLE 사이의 변환을 제공합니다.|  
|[CAnimationValue::operator INT32](../Topic/CAnimationValue::operator%20INT32.md)|CAnimationValue와 INT32 사이의 변환을 제공합니다.|  
|[CAnimationValue::operator\=](../Topic/CAnimationValue::operator=.md)|오버로드.  CAnimationValue에 INT32 값을 할당합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationValue::m\_value](../Topic/CAnimationValue::m_value.md)|애니메이션 값을 나타내는 캡슐화된 애니메이션 변수입니다.|  
  
## 설명  
 CAnimationValue 클래스는 단일 CAnimationVariable 개체를 캡슐화하고 응용 프로그램을 단일 애니메이션 값으로 나타낼 수 있습니다.  예를 들어, 애니메이션 투명성\(페이드 효과\), 각도\(개체 회전\) 또는 단일 애니메이션 값에 따라 애니메이션을 만들어야 하는 기타 경우에 이 클래스를 사용할 수 있습니다.  응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 값에 적용할 각 전환에 대해 AddTransition을 호출합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationValue](../../mfc/reference/canimationvalue-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)