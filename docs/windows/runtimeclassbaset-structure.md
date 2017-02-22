---
title: "RuntimeClassBaseT 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::RuntimeClassBaseT"
dev_langs: 
  - "C++"
ms.assetid: a62775fb-3359-4f45-9ff1-c07fa8da464b
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# RuntimeClassBaseT 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라구조체를 지원하고 코드에서 직접적으로 사용되는 것을 의도하지 않습니다.  
  
## 구문  
  
```  
template <  
   unsigned int RuntimeClassTypeT  
>  
friend struct Details::RuntimeClassBaseT;  
```  
  
#### 매개 변수  
 `RuntimeClassTypeT`  
 하나 이상의 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거자의 지정된 플래그의 필드입니다.  
  
## 설명  
 `QueryInterface` 작업에 대한 도우미 메서드를 제공하고 인터페이스 ID를 가져옵니다.  
  
## 멤버  
  
## 상속 계층  
 `RuntimeClassBaseT`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL::Details  
  
## 참고 항목  
 [Reference \(Windows Runtime Library\)](http://msdn.microsoft.com/ko-kr/00000000-0000-0000-0000-000000000000)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)