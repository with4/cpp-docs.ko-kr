---
title: "CAnimationPoint 클래스 | Microsoft Docs"
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
  - "CAnimationPoint"
  - "afxanimationcontroller/CAnimationPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationPoint 클래스"
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
caps.latest.revision: 17
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationPoint 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

좌표에 애니메이션을 적용할 수 있는 점 기능을 구현합니다.  
  
## 구문  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationPoint::CAnimationPoint](../Topic/CAnimationPoint::CAnimationPoint.md)|오버로드.  CAnimationPoint 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationPoint::AddTransition](../Topic/CAnimationPoint::AddTransition.md)|X 및 Y 좌표에 대한 전환을 추가합니다.|  
|[CAnimationPoint::GetDefaultValue](../Topic/CAnimationPoint::GetDefaultValue.md)|X 및 Y 좌표의 기본값을 반환합니다.|  
|[CAnimationPoint::GetValue](../Topic/CAnimationPoint::GetValue.md)|현재값을 반환합니다.|  
|[CAnimationPoint::GetX](../Topic/CAnimationPoint::GetX.md)|X 좌표의 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationPoint::GetY](../Topic/CAnimationPoint::GetY.md)|Y 좌표의 CAnimationVariable에 대한 액세스를 제공합니다.|  
|[CAnimationPoint::SetDefaultValue](../Topic/CAnimationPoint::SetDefaultValue.md)|기본값을 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationPoint::GetAnimationVariableList](../Topic/CAnimationPoint::GetAnimationVariableList.md)|캡슐화된 애니메이션 변수를 목록에 추가합니다.  \([CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md) 무시.\)|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationPoint::operator CPoint](../Topic/CAnimationPoint::operator%20CPoint.md)|CAnimationPoint를 CPoint로 변환합니다.|  
|[CAnimationPoint::operator\=](../Topic/CAnimationPoint::operator=.md)|CAnimationPoint에 ptSrc를 할당합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationPoint::m\_xValue](../Topic/CAnimationPoint::m_xValue.md)|애니메이션 점의 X 좌표를 나타내는 캡슐화된 애니메이션 변수입니다.|  
|[CAnimationPoint::m\_yValue](../Topic/CAnimationPoint::m_yValue.md)|애니메이션 점의 Y 좌표를 나타내는 캡슐화된 애니메이션 변수입니다.|  
  
## 설명  
 CAnimationPoint 클래스는 두 개의 CAnimationVariable 개체를 캡슐화하고 응용 프로그램을 한 점으로 나타낼 수 있습니다.  예를 들어, 이 클래스를 사용하여 화면에서 개체의 위치\(텍스트 문자열, 원, 지점 등\)에 애니메이션 효과를 줄 수 있습니다.  응용 프로그램에서 이 클래스를 사용하려면 이 클래스의 개체를 인스턴스화하고 CAnimationController::AddAnimationObject를 사용하여 애니메이션 컨트롤러에 추가하고 X 및\/또는 Y 좌표에 적용할 각 전환에 대해 AddTransition을 호출합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationPoint](../../mfc/reference/canimationpoint-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)