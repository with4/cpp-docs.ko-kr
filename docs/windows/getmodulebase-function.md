---
title: "GetModuleBase 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::GetModuleBase"
dev_langs: 
  - "C++"
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# GetModuleBase 함수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

참조 횟수의 [RuntimeClass](../windows/runtimeclass-class.md) 개체의 증가하고 감소하는 것을 허용하는 [ModuleBae](../windows/modulebase-class.md) 포인터를 검색합니다.  
  
## 구문  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## 반환 값  
 `ModuleBase` 개체에 대한 포인터 입니다.  
  
## 설명  
 이 함수는 내부적으로 증가 또는 감소를 사용하는 개체 참조를 계산 합니다.  
  
 이 함수는 [ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md) 및 [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md) 를 호출함으로써, 참조 횟수를 제어하는데 사용할 수 있습니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [Microsoft::WRL 네임스페이스](../windows/microsoft-wrl-namespace.md)