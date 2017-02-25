---
title: "CAnimationBaseObject 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationBaseObject"
  - "CAnimationBaseObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationBaseObject 클래스"
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationBaseObject 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

모든 애니메이션 개체의 기본 클래스입니다.  
  
## 구문  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationBaseObject::CAnimationBaseObject](../Topic/CAnimationBaseObject::CAnimationBaseObject.md)|오버로드.  애니메이션 개체를 생성합니다.|  
|[CAnimationBaseObject::~CAnimationBaseObject](../Topic/CAnimationBaseObject::~CAnimationBaseObject.md)|소멸자  애니메이션 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationBaseObject::ApplyTransitions](../Topic/CAnimationBaseObject::ApplyTransitions.md)|캡슐화된 애니메이션 변수가 있는 스토리보드에 전환을 추가합니다.|  
|[CAnimationBaseObject::ClearTransitions](../Topic/CAnimationBaseObject::ClearTransitions.md)|모든 관련된 전환을 제거합니다.|  
|[CAnimationBaseObject::ContainsVariable](../Topic/CAnimationBaseObject::ContainsVariable.md)|애니메이션 개체에 특정 애니메이션 변수가 포함되어 있는지 여부를 결정합니다.|  
|[CAnimationBaseObject::CreateTransitions](../Topic/CAnimationBaseObject::CreateTransitions.md)|애니메이션 개체와 관련된 전환을 만듭니다.|  
|[CAnimationBaseObject::DetachFromController](../Topic/CAnimationBaseObject::DetachFromController.md)|부모 애니메이션 컨트롤러에서 애니메이션 개체를 분리합니다.|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](../Topic/CAnimationBaseObject::EnableIntegerValueChangedEvent.md)|정수 값 변경 이벤트 처리기를 설정합니다.|  
|[CAnimationBaseObject::EnableValueChangedEvent](../Topic/CAnimationBaseObject::EnableValueChangedEvent.md)|값 변경 이벤트 처리기를 설정합니다.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](../Topic/CAnimationBaseObject::GetAutodestroyTransitions.md)|관련된 전환이 자동으로 소멸되는지 여부를 지정합니다.|  
|[CAnimationBaseObject::GetGroupID](../Topic/CAnimationBaseObject::GetGroupID.md)|현재 그룹 ID를 반환합니다.|  
|[CAnimationBaseObject::GetObjectID](../Topic/CAnimationBaseObject::GetObjectID.md)|현재 개체 ID를 반환합니다.|  
|[CAnimationBaseObject::GetUserData](../Topic/CAnimationBaseObject::GetUserData.md)|사용자 정의 데이터를 반환합니다.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](../Topic/CAnimationBaseObject::SetAutodestroyTransitions.md)|전환을 자동으로 소멸시키도록 주문하는 플래그를 설정합니다.|  
|[CAnimationBaseObject::SetID](../Topic/CAnimationBaseObject::SetID.md)|새 ID를 설정합니다.|  
|[CAnimationBaseObject::SetUserData](../Topic/CAnimationBaseObject::SetUserData.md)|사용자 정의 데이터를 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md)|포함된 애니메이션 변수에 포인터를 수집합니다.|  
|[CAnimationBaseObject::SetParentAnimationObjects](../Topic/CAnimationBaseObject::SetParentAnimationObjects.md)|애니메이션 개체와 컨테이너에 포함되어 있는 애니메이션 변수 간에 관계를 설정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationBaseObject::m\_bAutodestroyTransitions](../Topic/CAnimationBaseObject::m_bAutodestroyTransitions.md)|관련된 전환을 자동으로 소멸시킬지 여부를 지정합니다.|  
|[CAnimationBaseObject::m\_dwUserData](../Topic/CAnimationBaseObject::m_dwUserData.md)|사용자 정의 데이터를 저장합니다.|  
|[CAnimationBaseObject::m\_nGroupID](../Topic/CAnimationBaseObject::m_nGroupID.md)|애니메이션 개체의 그룹 ID를 지정합니다.|  
|[CAnimationBaseObject::m\_nObjectID](../Topic/CAnimationBaseObject::m_nObjectID.md)|애니메이션 개체의 개체 ID를 지정합니다.|  
|[CAnimationBaseObject::m\_pParentController](../Topic/CAnimationBaseObject::m_pParentController.md)|부모 애니메이션 컨트롤러에 대한 포인터입니다.|  
  
## 설명  
 이 클래스는 모든 애니메이션 개체의 기본 메서드를 구현합니다.  애니메이션 개체는 응용 프로그램에서 값, 지점, 크기, 사각형 또는 색상은 물론 사용자 지정 엔터티를 나타낼 수 있습니다.  애니메이션 개체는 애니메이션 그룹에 저장됩니다\(CAnimationGroup 참조\).  각 그룹은 별도로 애니메이션 효과를 적용할 수 있으며 스토리보드와 유사하게 취급할 수 있습니다.  애니메이션 개체는 논리적 표현에 따라 하나 이상의 애니메이션 변수\(CAnimationVariable 참조\)를 캡슐화합니다.  예를 들어, CAnimationRect는 직사각형 각 변에 대해 변수 하나씩 네 개의 애니메이션 변수를 포함합니다.  각 애니메이션 개체 클래스는 오버로드된 AddTransition 메서드를 노출하며 캡슐화된 애니메이션 변수에 전환을 적용하는 데 사용해야 합니다.  애니메이션 개체는 개체 ID\(선택적으로\) 및 그룹 ID로 식별할 수 있습니다.  그룹 ID는 애니메이션 개체를 올바른 그룹에 배치하는 데 필요하지만 그룹 ID가 지정되지 않은 경우 개체는 ID 0으로 기본 그룹에 배치됩니다.  다른 GroupID로 SetID를 호출하는 경우 애니메이션 개체는 다른 그룹으로 이동됩니다\(필요한 경우 새 그룹이 만들어짐\).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)