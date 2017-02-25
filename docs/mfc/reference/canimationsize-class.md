---
title: "CAnimationSize 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationSize"
  - "CAnimationSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationSize 클래스"
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationSize 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

차원에 애니메이션을 적용할 수 있는 크기 개체 기능을 구현합니다.  
  
## 구문  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationSize::CAnimationSize](../Topic/CAnimationSize::CAnimationSize.md)|오버로드.  애니메이션 크기 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationSize::AddTransition](../Topic/CAnimationSize::AddTransition.md)|너비 및 높이에 대한 전환을 추가합니다.|  
|[CAnimationSize::GetCX](../Topic/CAnimationSize::GetCX.md)|너비를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationSize::GetCY](../Topic/CAnimationSize::GetCY.md)|높이를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationSize::GetDefaultValue](../Topic/CAnimationSize::GetDefaultValue.md)|너비 및 높이 기본값을 반환합니다.|  
|[CAnimationSize::GetValue](../Topic/CAnimationSize::GetValue.md)|현재값을 반환합니다.|  
|[CAnimationSize::SetDefaultValue](../Topic/CAnimationSize::SetDefaultValue.md)|기본값을 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationSize::GetAnimationVariableList](../Topic/CAnimationSize::GetAnimationVariableList.md)|캡슐화된 애니메이션 변수를 목록에 추가합니다.  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) 무시.\)|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationSize::operator CSize](../Topic/CAnimationSize::operator%20CSize.md)|CAnimationSize를 CSize로 변환합니다.|  
|[CAnimationSize::operator\=](../Topic/CAnimationSize::operator=.md)|CAnimationSize에 szSrc를 할당합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationSize::m\_cxValue](../Topic/CAnimationSize::m_cxValue.md)|애니메이션 크기 중 너비를 나타내는 캡슐화된 애니메이션 변수입니다.|  
|[CAnimationSize::m\_cyValue](../Topic/CAnimationSize::m_cyValue.md)|애니메이션 크기 중 높이를 나타내는 캡슐화된 애니메이션 변수입니다.|  
  
## 설명  
 CAnimationSize 클래스는 두 개의 CAnimationVariable 개체를 캡슐화하고 응용 프로그램을 한 크기로 나타낼 수 있습니다.  예를 들어, 이 클래스를 사용하여 화면에서 2차원 개체의 크기\(사각형, 컨트롤 등\)에 애니메이션 효과를 줄 수 있습니다.  응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 너비 및\/또는 높이에 적용할 각 전환에 대해 AddTransition을 호출합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationSize](../../mfc/reference/canimationsize-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)