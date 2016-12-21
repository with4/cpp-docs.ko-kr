---
title: "HandleT 클래스 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HandleT 클래스"
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

개체에 대한 핸들을 나타냅니다.  
  
## 구문  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### 매개 변수  
 `HandleTraits`  
 핸들의 일반적인 특징을 정의하는 [HandleTraits](../windows/handletraits-structure.md) 구조체의 인스턴스.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`Traits`|이 `HandleTraits` 의 동의어입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[HandleT::HandleT 생성자](../windows/handlet-handlet-constructor.md)|핸들 클래스의 새 인스턴스를 초기화합니다.|  
|[HandleT::~HandleT 소멸자](../windows/handlet-tilde-handlet-destructor.md)|HandleT 클래스의 인스턴스를 초기화하지 않습니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[HandleT::Attach 메서드](../windows/handlet-attach-method.md)|현재 HandleT 개체와 지정된 된 핸들에 연결합니다.|  
|[HandleT::Close 메서드](../windows/handlet-close-method.md)|현재 HandleT 개체를 닫습니다.|  
|[HandleT::Detach 메서드](../windows/handlet-detach-method.md)|현재 HandleT 개체의 기본 핸들에서을 분리합니다.|  
|[HandleT::Get 메서드](../windows/handlet-get-method.md)|내부 핸들의 값을 가져옵니다.|  
|[HandleT::IsValid 메서드](../windows/handlet-isvalid-method.md)|현재 HandleT 개체 핸들이 있는지 여부를 나타냅니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[HandleT::InternalClose 메서드](../windows/handlet-internalclose-method.md)|현재 HandleT 개체를 닫습니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[HandleT::operator\= 연산자](../windows/handlet-operator-assign-operator.md)|현재 HandleT 개체에 지정된 된 HandleT 개체의 값을 이동합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[HandleT::handle\_ Data 멤버](../windows/handlet-handle-data-member.md)|HandleT 개체로 표시 되는 핸들을 포함합니다.|  
  
## 상속 계층  
 `HandleT`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers 네임스페이스](../windows/microsoft-wrl-wrappers-namespace.md)