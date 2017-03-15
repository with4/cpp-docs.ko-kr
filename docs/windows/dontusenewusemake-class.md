---
title: "DontUseNewUseMake 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DontUseNewUseMake 클래스"
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DontUseNewUseMake 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
class DontUseNewUseMake;  
```  
  
## 설명  
 런타임 클래스 에서 연산자 `new` 를 사용하는 것을 금지합니다.  [함수 만들기](../windows/make-function.md) 대신에 사용해야 합니다.  
  
## 멤버  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[DontUseNewUseMake::operator 새 연산자](../windows/dontusenewusemake-operator-new-operator.md)|연산자 `new` 를 오버로드하고 RuntimeClass에서 사용되는 것을 막습니다.|  
  
## 상속 계층  
 `DontUseNewUseMake`  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)   
 [Make 함수](../windows/make-function.md)