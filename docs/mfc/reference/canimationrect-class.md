---
title: "CAnimationRect 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationRect"
  - "afxanimationcontroller/CAnimationRect"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationRect 클래스"
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationRect 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

면에 애니메이션을 적용할 수 있는 사각형 기능을 구현합니다.  
  
## 구문  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationRect::CAnimationRect](../Topic/CAnimationRect::CAnimationRect.md)|오버로드.  애니메이션 rect 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationRect::AddTransition](../Topic/CAnimationRect::AddTransition.md)|왼쪽, 위쪽, 오른쪽 및 아래쪽 좌표에 대한 전환을 추가합니다.|  
|[CAnimationRect::GetBottom](../Topic/CAnimationRect::GetBottom.md)|아래쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationRect::GetDefaultValue](../Topic/CAnimationRect::GetDefaultValue.md)|사각형 경계의 기본값을 반환합니다.|  
|[CAnimationRect::GetLeft](../Topic/CAnimationRect::GetLeft.md)|왼쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationRect::GetRight](../Topic/CAnimationRect::GetRight.md)|오른쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationRect::GetTop](../Topic/CAnimationRect::GetTop.md)|위쪽 좌표를 나타내는 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationRect::GetValue](../Topic/CAnimationRect::GetValue.md)|현재값을 반환합니다.|  
|[CAnimationRect::SetDefaultValue](../Topic/CAnimationRect::SetDefaultValue.md)|기본값을 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationRect::GetAnimationVariableList](../Topic/CAnimationRect::GetAnimationVariableList.md)|캡슐화된 애니메이션 변수를 목록에 추가합니다.  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) 무시.\)|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationRect::operator RECT](../Topic/CAnimationRect::operator%20RECT.md)|CAnimationRect를 RECT로 변환합니다.|  
|[CAnimationRect::operator\=](../Topic/CAnimationRect::operator=.md)|CAnimationRect에 rect를 할당합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationRect::m\_bFixedSize](../Topic/CAnimationRect::m_bFixedSize.md)|사각형의 크기가 고정되어 있는지 여부를 지정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationRect::m\_bottomValue](../Topic/CAnimationRect::m_bottomValue.md)|애니메이션 사각형의 아래쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|  
|[CAnimationRect::m\_leftValue](../Topic/CAnimationRect::m_leftValue.md)|애니메이션 사각형의 왼쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|  
|[CAnimationRect::m\_rightValue](../Topic/CAnimationRect::m_rightValue.md)|애니메이션 사각형의 오른쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|  
|[CAnimationRect::m\_szInitial](../Topic/CAnimationRect::m_szInitial.md)|애니메이션 사각형의 초기 크기를 지정합니다.|  
|[CAnimationRect::m\_topValue](../Topic/CAnimationRect::m_topValue.md)|애니메이션 사각형의 위쪽 경계를 나타내는 캡슐화된 애니메이션 변수입니다.|  
  
## 설명  
 CAnimationRect 클래스는 네 개의 CAnimationVariable 개체를 캡슐화하고 응용 프로그램을 한 사각형으로 나타낼 수 있습니다.  응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 왼쪽, 오른쪽 상단 및 하단 좌표에 적용할 각 전환에 대해 AddTransition을 호출합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationRect](../../mfc/reference/canimationrect-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)