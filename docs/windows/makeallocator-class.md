---
title: "MakeAllocator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAllocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MakeAllocator 클래스"
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# MakeAllocator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,   
   T)> , T)> class MakeAllocator;  
  
template<  
   typename T  
>  
class MakeAllocator<T, false>;  
  
template<  
   typename T  
>  
class MakeAllocator<T, true>;  
```  
  
#### 매개 변수  
 `T`  
 형식 이름입니다.  
  
 `hasWeakReferenceSupport`  
 `true` 개체에 메모리를 할당을 지원하는 약한 참조; `false` 개체에 메모리를 할당하는 약한 참조를 지원하지 않습니다.  
  
## 설명  
 약한 참조를 지원하지 않는 또는 활성화할 수 있는 클래스에 대한 메모리를 할당합니다.  
  
 사용자 정의 메모리 할당 모델을 구 하는 MakeAllocator 클래스를 재정의합니다.  
  
 MakeAllocator 개체를 생하는 동안 throw 되는 경우 메모리 누수를 방지하기 위해 일반적으로 사용됩니다.  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[MakeAllocator::MakeAllocator 생성자](../windows/makeallocator-makeallocator-constructor.md)|MakeAllocator 클래스의 새 인스턴스를 초기화합니다.|  
|[MakeAllocator::~MakeAllocator 소멸자](../windows/makeallocator-tilde-makeallocator-destructor.md)|MakeAlloator 클래스의 현재 인스턴스를 초기화하지 않습니다.\(소멸시킵니다.\)|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[MakeAllocator::Allocate 메서드](../windows/makeallocator-allocate-method.md)|메모리를 할당하고 현재 MakeAllocator 개체와 연결합니다.|  
|[MakeAllocator::Detach 메서드](../windows/makeallocator-detach-method.md)|현재 MakeAllocator 개체로부터 [할당](../windows/makeallocator-allocate-method.md) 메서드에 의해 할당된 메모리를 분리합니다.|  
  
## 상속 계층  
 `MakeAllocator`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)