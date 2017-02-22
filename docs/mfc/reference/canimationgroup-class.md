---
title: "CAnimationGroup 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationGroup"
  - "CAnimationGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationGroup 클래스"
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationGroup 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션 스토리보드, 애니메이션 개체 및 전환을 결합하여 애니메이션을 정의하는 애니메이션 그룹을 구현합니다.  
  
## 구문  
  
```  
class CAnimationGroup;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationGroup::CAnimationGroup](../Topic/CAnimationGroup::CAnimationGroup.md)|애니메이션 그룹을 생성합니다.|  
|[CAnimationGroup::~CAnimationGroup](../Topic/CAnimationGroup::~CAnimationGroup.md)|소멸자  애니메이션 그룹이 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationGroup::Animate](../Topic/CAnimationGroup::Animate.md)|그룹에 애니메이션 효과를 적용합니다.|  
|[CAnimationGroup::ApplyTransitions](../Topic/CAnimationGroup::ApplyTransitions.md)|애니메이션 개체에 전환을 적용합니다.|  
|[CAnimationGroup::FindAnimationObject](../Topic/CAnimationGroup::FindAnimationObject.md)|지정된 애니메이션 변수를 포함하고 있는 애니메이션 개체를 찾습니다.|  
|[CAnimationGroup::GetGroupID](../Topic/CAnimationGroup::GetGroupID.md)|GroupID를 반환합니다.|  
|[CAnimationGroup::RemoveKeyframes](../Topic/CAnimationGroup::RemoveKeyframes.md)|애니메이션 그룹에 속하는 모든 키프레임을 제거하고 선택적으로 소멸시킵니다.|  
|[CAnimationGroup::RemoveTransitions](../Topic/CAnimationGroup::RemoveTransitions.md)|애니메이션 그룹에 속하는 애니메이션 개체에서 전환을 제거합니다.|  
|[CAnimationGroup::Schedule](../Topic/CAnimationGroup::Schedule.md)|지정한 시간에 애니메이션을 예약합니다.|  
|[CAnimationGroup::SetAutodestroyTransitions](../Topic/CAnimationGroup::SetAutodestroyTransitions.md)|전환을 자동으로 소멸시키는 그룹에 속하는 모든 애니메이션 개체를 지시합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationGroup::AddKeyframes](../Topic/CAnimationGroup::AddKeyframes.md)|키프레임을 스토리보드에 추가하는 도우미입니다.|  
|[CAnimationGroup::AddTransitions](../Topic/CAnimationGroup::AddTransitions.md)|전환을 스토리보드에 추가하는 도우미입니다.|  
|[CAnimationGroup::CreateTransitions](../Topic/CAnimationGroup::CreateTransitions.md)|COM 전환 개체를 만드는 도우미입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationGroup::m\_bAutoclearTransitions](../Topic/CAnimationGroup::m_bAutoclearTransitions.md)|그룹에 속한 애니메이션 개체에서 전환을 지우는 방법을 지정합니다.  이 멤버가 TRUE인 경우 애니메이션을 예약할 때 전환이 자동으로 제거됩니다.  그렇지 않으면 전환을 수동으로 제거해야 합니다.|  
|[CAnimationGroup::m\_bAutodestroyAnimationObjects](../Topic/CAnimationGroup::m_bAutodestroyAnimationObjects.md)|애니메이션 개체를 소멸시키는 방법을 지정합니다.  이 매개 변수가 TRUE인 경우 그룹이 소멸될 때 애니메이션 개체가 자동으로 소멸됩니다.  그렇지 않으면 애니메이션 개체를 수동으로 소멸시켜야 합니다.  기본값은 FALSE입니다.  그룹에 속하는 애니메이션 개체가 연산자를 사용하여 동적으로 새로 할당되는 경우에만 이 값을 TRUE로 설정합니다.|  
|[CAnimationGroup::m\_bAutodestroyKeyframes](../Topic/CAnimationGroup::m_bAutodestroyKeyframes.md)|키프레임을 소멸시키는 방법을 지정합니다.  이 값이 TRUE인 경우 모든 키프레임이 파괴되고 소멸되며, 그렇지 않은 경우 목록에서만 제거됩니다.  기본값은 TRUE입니다.|  
|[CAnimationGroup::m\_lstAnimationObjects](../Topic/CAnimationGroup::m_lstAnimationObjects.md)|애니메이션 개체 목록을 포함합니다.|  
|[CAnimationGroup::m\_lstKeyFrames](../Topic/CAnimationGroup::m_lstKeyFrames.md)|키프레임 목록을 포함합니다.|  
|[CAnimationGroup::m\_pStoryboard](../Topic/CAnimationGroup::m_pStoryboard.md)|애니메이션 스토리보드에 대한 점입니다.  이 포인터는 Animate를 호출한 후에만 유효합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationGroup::m\_nGroupID](../Topic/CAnimationGroup::m_nGroupID.md)|애니메이션 그룹의 고유 식별자입니다.|  
|[CAnimationGroup::m\_pParentController](../Topic/CAnimationGroup::m_pParentController.md)|이 그룹이 속해 있는 애니메이션 컨트롤러에 대한 포인터입니다.|  
  
## 설명  
 CAnimationController::AddAnimationObject를 사용하여 애니메이션 개체를 추가하면 애니메이션 컨트롤러\(CAnimationController\)에 의해 애니메이션 그룹이 자동으로 만들어집니다.  애니메이션 그룹은 일반적으로 애니메이션 그룹을 조작하는 매개 변수로 사용되는 GroupID에 의해 식별됩니다.  GroupID는 새 애니메이션 그룹에 추가되는 첫 번째 애니메이션 개체에서 가져옵니다.  CAnimationController::AnimateGroup을 호출한 후에 캡슐화된 애니메이션 스토리보드가 만들어지며 공용 멤버 m\_pStoryboard를 통해 액세스할 수 있습니다.  
  
## 상속 계층 구조  
 [CAnimationGroup](../../mfc/reference/canimationgroup-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)