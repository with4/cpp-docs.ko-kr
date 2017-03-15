---
title: "ChainInterfaces::CastToUnknown 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::ChainInterfaces::CastToUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToUnknown 메서드"
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ChainInterfaces::CastToUnknown 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

IUnknown 에대한 포인터에 대한 `I0` 템플릿 매개변수에 의해 정의된 형식의 인터페이스 포인터를 캐스팅합니다.  
  
## 구문  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## 반환 값  
 IUnknown 대한 포인터  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ChainInterfaces 구조체](../windows/chaininterfaces-structure.md)