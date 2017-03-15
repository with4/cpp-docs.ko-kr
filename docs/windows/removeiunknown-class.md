---
title: "RemoveIUnknown 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::RemoveIUnknown"
dev_langs: 
  - "C++"
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RemoveIUnknown 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   typename T  
>  
struct RemoveIUnknown;  
  
template <  
   typename T  
>  
class RemoveIUnknown : public T;  
```  
  
#### 매개 변수  
 `T`  
 A 클래스  
  
## 설명  
 형식에 기초한 `IUnknown` 과 동등한 형식을 만들지만, 비가상적인 `QueryInterface`, `AddRef` 및 `Release` 을 갖습니다.  
  
 기본적으로 COM 메서드는 가상 `QueryInterface`, `AddRef` 을 제공하고, 메서드를 릴리스합니다.  그러나 `ComPtr` 은 가상 메서드의 오버 헤드가 필요하지 않습니다.  `RemoveIUnknown` 는 사적이고, 비가상적인 `QueryInterface`, `AddRef`, 및 `Release` 메서드를 제공함으로써 오버헤드를 제거합니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`ReturnType`|탬플릿 매개변수 `T` 와 동등한 형식에 대한 동의어지만, 비가상 IUnknown 멤버를 갖습니다.|  
  
## 상속 계층  
 `T`  
  
 `RemoveIUnknown`  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)