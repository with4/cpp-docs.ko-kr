---
title: "scheduler_resource_allocation_error 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::scheduler_resource_allocation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_resource_allocation_error 클래스"
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_resource_allocation_error 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 동시성 런타임에서 중요한 리소스를 얻지 못할 경우 throw되는 예외를 설명합니다.  
  
## 구문  
  
```  
class scheduler_resource_allocation_error : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[scheduler\_resource\_allocation\_error::scheduler\_resource\_allocation\_error 생성자](../Topic/scheduler_resource_allocation_error::scheduler_resource_allocation_error%20Constructor.md)|오버로드됨.  `scheduler_resource_allocation_error` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[scheduler\_resource\_allocation\_error::get\_error\_code 메서드](../Topic/scheduler_resource_allocation_error::get_error_code%20Method.md)|예외의 원인이 된 오류 코드를 반환합니다.|  
  
## 설명  
 이 예외는 일반적으로 동시성 런타임 내에서 운영 체제에 대한 호출이 실패할 때 throw됩니다.  일반적으로 Win32 메서드 `GetLastError`에 대한 호출에서 반환되는 오류 코드는 값 형식 `HRESULT`이며 `get_error_code` 메서드를 사용하여 검색할 수 있습니다.  
  
## 상속 계층  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)