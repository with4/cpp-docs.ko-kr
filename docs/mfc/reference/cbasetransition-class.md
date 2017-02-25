---
title: "CBaseTransition 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBaseTransition"
  - "afxanimationcontroller/CBaseTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTransition 클래스"
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CBaseTransition 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 전환을 나타냅니다.  
  
## 구문  
  
```  
class CBaseTransition : public CObject;  
```  
  
## Members  
  
### Public 열거형  
  
|Name|설명|  
|----------|--------|  
|[CBaseTransition::TRANSITION\_TYPE 열거형](../Topic/CBaseTransition::TRANSITION_TYPE%20Enumeration.md)|Windows 애니메이션 API의 MFC 구현에서 현재 지원하는 전환 유형을 정의합니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CBaseTransition::CBaseTransition](../Topic/CBaseTransition::CBaseTransition.md)|기본 전환 개체를 생성합니다.|  
|[CBaseTransition::~CBaseTransition](../Topic/CBaseTransition::~CBaseTransition.md)|소멸자  전환 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CBaseTransition::AddToStoryboard](../Topic/CBaseTransition::AddToStoryboard.md)|전환을 스토리보드에 추가합니다.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](../Topic/CBaseTransition::AddToStoryboardAtKeyframes.md)|전환을 스토리보드에 추가합니다.|  
|[CBaseTransition::Clear](../Topic/CBaseTransition::Clear.md)|캡슐화된 IUIAnimationTransition COM 개체를 해제합니다.|  
|[CBaseTransition::Create](../Topic/CBaseTransition::Create.md)|COM 전환을 만듭니다.|  
|[CBaseTransition::GetEndKeyframe](../Topic/CBaseTransition::GetEndKeyframe.md)|시작 키프레임을 반환합니다.|  
|[CBaseTransition::GetRelatedVariable](../Topic/CBaseTransition::GetRelatedVariable.md)|관련 변수에 대한 포인터를 반환합니다.|  
|[CBaseTransition::GetStartKeyframe](../Topic/CBaseTransition::GetStartKeyframe.md)|시작 키프레임을 반환합니다.|  
|[CBaseTransition::GetTransition](../Topic/CBaseTransition::GetTransition.md)|오버로드.  내부 COM 전환 개체에 대한 포인터를 반환합니다.|  
|[CBaseTransition::GetType](../Topic/CBaseTransition::GetType.md)|전환 형식을 반환합니다.|  
|[CBaseTransition::IsAdded](../Topic/CBaseTransition::IsAdded.md)|전환이 스토리보드에 추가되었는지 여부를 지정합니다.|  
|[CBaseTransition::SetKeyframes](../Topic/CBaseTransition::SetKeyframes.md)|전환을 위한 키프레임을 설정합니다.|  
|[CBaseTransition::SetRelatedVariable](../Topic/CBaseTransition::SetRelatedVariable.md)|애니메이션 변수와 전환 간에 관계를 설정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CBaseTransition::m\_bAdded](../Topic/CBaseTransition::m_bAdded.md)|전환이 스토리보드에 추가되었는지 여부를 지정합니다.|  
|[CBaseTransition::m\_pEndKeyframe](../Topic/CBaseTransition::m_pEndKeyframe.md)|전환의 끝을 지정하는 키프레임에 대한 포인터를 저장합니다.|  
|[CBaseTransition::m\_pRelatedVariable](../Topic/CBaseTransition::m_pRelatedVariable.md)|m\_transition에 저장된 애니메이션으로 애니메이션 효과가 적용되는 애니메이션 변수에 대한 포인터입니다.|  
|[CBaseTransition::m\_pStartKeyframe](../Topic/CBaseTransition::m_pStartKeyframe.md)|전환의 시작을 지정하는 키프레임에 대한 포인터를 저장합니다.|  
|[CBaseTransition::m\_transition](../Topic/CBaseTransition::m_transition.md)|IUIAnimationTransition에 대한 포인터를 저장합니다.  전환 COM 개체를 만들지 않은 경우 NULL입니다.|  
|[CBaseTransition::m\_type](../Topic/CBaseTransition::m_type.md)|전환 형식을 저장합니다.|  
  
## 설명  
 이 클래스는 IUIAnimationTransition 인터페이스를 캡슐화하고 모든 전환에 대한 기본 클래스로 사용됩니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)