---
title: "RuntimeClassFlags 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClassFlags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClassFlags 구조체"
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClassFlags 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[RuntimeClass](../windows/runtimeclass-class.md)의 인스턴스에 대한 형식을 포함합니다.  
  
## 구문  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### 매개 변수  
 `flags`  
 [RuntimeClassType 열거형](../windows/runtimeclasstype-enumeration.md) 값입니다.  
  
## 멤버  
  
### 공용 상수  
  
|Name|설명|  
|----------|--------|  
|[RuntimeClassFlags::value 상수](../windows/runtimeclassflags-value-constant.md)|[RuntimeClassType 열거형](../windows/runtimeclasstype-enumeration.md) 값을 포함합니다.|  
  
## 상속 계층  
 `RuntimeClassFlags`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)