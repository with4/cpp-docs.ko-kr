---
title: "CAnimationVariable 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationVariable"
  - "afxanimationcontroller/CAnimationVariable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariable 클래스"
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationVariable 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

애니메이션 변수를 나타냅니다.  
  
## 구문  
  
```  
class CAnimationVariable;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAnimationVariable::CAnimationVariable](../Topic/CAnimationVariable::CAnimationVariable.md)|애니메이션 변수 개체를 생성합니다.|  
|[CAnimationVariable::~CAnimationVariable](../Topic/CAnimationVariable::~CAnimationVariable.md)|소멸자  CAnimationVariable 개체가 소멸될 때 호출됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationVariable::AddTransition](../Topic/CAnimationVariable::AddTransition.md)|전환을 추가합니다.|  
|[CAnimationVariable::ApplyTransitions](../Topic/CAnimationVariable::ApplyTransitions.md)|내부 목록에서 스토리보드로 전환을 추가합니다.|  
|[CAnimationVariable::ClearTransitions](../Topic/CAnimationVariable::ClearTransitions.md)|전환을 지웁니다.|  
|[CAnimationVariable::Create](../Topic/CAnimationVariable::Create.md)|내부 애니메이션 변수 COM 개체를 만듭니다.|  
|[CAnimationVariable::CreateTransitions](../Topic/CAnimationVariable::CreateTransitions.md)|이 애니메이션 변수에 적용할 모든 전환을 만듭니다.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](../Topic/CAnimationVariable::EnableIntegerValueChangedEvent.md)|IntegerValueChanged 이벤트를 사용하거나 사용하지 않도록 지정합니다.|  
|[CAnimationVariable::EnableValueChangedEvent](../Topic/CAnimationVariable::EnableValueChangedEvent.md)|ValueChanged 이벤트를 사용하거나 사용하지 않도록 지정합니다.|  
|[CAnimationVariable::GetDefaultValue](../Topic/CAnimationVariable::GetDefaultValue.md)|기본값을 반환합니다.|  
|[CAnimationVariable::GetParentAnimationObject](../Topic/CAnimationVariable::GetParentAnimationObject.md)|부모 애니메이션 개체를 반환합니다.|  
|[CAnimationVariable::GetValue](../Topic/CAnimationVariable::GetValue.md)|오버로드.  애니메이션 변수의 현재 값을 반환합니다.|  
|[CAnimationVariable::GetVariable](../Topic/CAnimationVariable::GetVariable.md)|IUIAnimationVariable COM 개체에 대한 포인터를 반환합니다.|  
|[CAnimationVariable::SetDefaultValue](../Topic/CAnimationVariable::SetDefaultValue.md)|기본값을 설정하고 IUIAnimationVariable COM 개체를 해제합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAnimationVariable::SetParentAnimationObject](../Topic/CAnimationVariable::SetParentAnimationObject.md)|애니메이션 변수와 애니메이션 개체 사이의 관계를 설정합니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationVariable::m\_bAutodestroyTransitions](../Topic/CAnimationVariable::m_bAutodestroyTransitions.md)|관련된 전환 개체를 삭제할지 여부를 지정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAnimationVariable::m\_dblDefaultValue](../Topic/CAnimationVariable::m_dblDefaultValue.md)|IUIAnimationVariable에 전파되는 기본값을 지정합니다.|  
|[CAnimationVariable::m\_lstTransitions](../Topic/CAnimationVariable::m_lstTransitions.md)|이 애니메이션 변수에 효과를 적용하는 전환 목록을 포함합니다.|  
|[CAnimationVariable::m\_pParentObject](../Topic/CAnimationVariable::m_pParentObject.md)|이 애니메이션 변수를 캡슐화하는 애니메이션 개체에 대한 포인터입니다.|  
|[CAnimationVariable::m\_variable](../Topic/CAnimationVariable::m_variable.md)|IUIAnimationVariable COM 개체에 대한 포인터를 저장합니다.  COM 개체를 아직 만들지 않았거나 만들지 못한 경우 NULL입니다.|  
  
## 설명  
 CAnimationVariable 클래스는 IUIAnimationVariable COM 개체를 캡슐화합니다.  또한 스토리보드에서 애니메이션 변수에 적용할 전환 목록을 보관합니다.  CAnimationVariable 개체는 애니메이션 개체에 포함되며 응용 프로그램에서 애니메이션된 값, 지점, 크기, 색 및 사각형을 나타낼 수 있습니다.  
  
## 상속 계층 구조  
 [CAnimationVariable](../../mfc/reference/canimationvariable-class.md)  
  
## 요구 사항  
 **헤더:** afxanimationcontroller.h  
  
## 참고 항목  
 [클래스](../../mfc/reference/mfc-classes.md)