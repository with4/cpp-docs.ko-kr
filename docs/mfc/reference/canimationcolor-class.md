---
title: "CAnimationColor 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationColor"
  - "afxanimationcontroller/CAnimationColor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationColor 클래스"
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationColor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

빨강, 녹색 및 파랑 구성 요소에 애니메이션을 적용할 수 있는 색 기능을 구현합니다.  
  
## 구문  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationColor::CAnimationColor](../Topic/CAnimationColor::CAnimationColor.md)|오버로드.  애니메이션 색 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationColor::AddTransition](../Topic/CAnimationColor::AddTransition.md)|빨강, 녹색 및 파랑 구성 요소에 대한 전환을 추가합니다.|  
|[CAnimationColor::GetB](../Topic/CAnimationColor::GetB.md)|파랑 구성 요소를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationColor::GetDefaultValue](../Topic/CAnimationColor::GetDefaultValue.md)|색 구성 요소의 기본값을 반환합니다.|  
|[CAnimationColor::GetG](../Topic/CAnimationColor::GetG.md)|녹색 구성 요소를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationColor::GetR](../Topic/CAnimationColor::GetR.md)|빨강 구성 요소를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationColor::GetValue](../Topic/CAnimationColor::GetValue.md)|현재값을 반환합니다.|  
|[CAnimationColor::SetDefaultValue](../Topic/CAnimationColor::SetDefaultValue.md)|기본값을 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationColor::GetAnimationVariableList](../Topic/CAnimationColor::GetAnimationVariableList.md)|캡슐화된 애니메이션 변수를 목록에 추가합니다.  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) 무시.\)|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationColor::operator COLORREF](../Topic/CAnimationColor::operator%20COLORREF.md)||  
|[CAnimationColor::operator\=](../Topic/CAnimationColor::operator=.md)|CAnimationColor에 색을 할당합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationColor::m\_bValue](../Topic/CAnimationColor::m_bValue.md)|애니메이션 색의 파랑 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.|  
|[CAnimationColor::m\_gValue](../Topic/CAnimationColor::m_gValue.md)|애니메이션 색의 녹색 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.|  
|[CAnimationColor::m\_rValue](../Topic/CAnimationColor::m_rValue.md)|애니메이션 색의 빨강 구성 요소를 나타내는 캡슐화된 애니메이션 변수입니다.|  
  
## 설명  
 CAnimationColor 클래스는 세 개의 CAnimationVariable 개체를 캡슐화하고 응용 프로그램을 한 색으로 나타낼 수 있습니다.  예를 들어, 이 클래스를 사용하여 화면에서 개체의 색상\(텍스트 색상, 배경색 등\)에 애니메이션 효과를 줄 수 있습니다.  응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 빨간색, 녹색 및 파란색 구성 요소에 적용할 각 전환에 대해 AddTransition을 호출합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationColor](../../mfc/reference/canimationcolor-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)