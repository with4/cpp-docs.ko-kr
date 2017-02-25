---
title: "MutexTraits 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MutexTraits 구조체"
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# MutexTraits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Mutex](../windows/mutex-class1.md)클래스의 공통적인 특성을 정의합니다.  
  
## 구문  
  
```  
struct MutexTraits : HANDLENullTraits;  
  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[MutexTraits::Unlock 메서드](../windows/mutextraits-unlock-method.md)|공유 리소스의 독점 컨트롤입니다.|  
  
## 상속 계층  
 `HANDLENullTraits`  
  
 `MutexTraits`  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [Microsoft::WRL::Wrappers::HandleTraits 네임스페이스](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)