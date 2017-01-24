---
title: "scheduler_worker_creation_error 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::scheduler_worker_creation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_worker_creation_error 클래스"
ms.assetid: 4aec1c3e-c32a-41b2-899d-2d898f23b3c7
caps.latest.revision: 9
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scheduler_worker_creation_error 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 동시성 런타임에서 작업자 실행 컨텍스트를 만드는데 실패한 오류로 인해 throw 되는 예외를 설명합니다.  
  
## 구문  
  
```  
class scheduler_worker_creation_error : public scheduler_resource_allocation_error;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[scheduler\_worker\_creation\_error::scheduler\_worker\_creation\_error 생성자](../Topic/scheduler_worker_creation_error::scheduler_worker_creation_error%20Constructor.md)|오버로드됨.  `scheduler_worker_creation_error` 개체를 생성합니다.|  
  
## 설명  
 동시성 런타임 내에서 실행 컨텍스트를 만들 수있는 운영 체제에 대한 호출이 실패 할 때 이 예외는 일반적으로 발생합니다.  실행 컨텍스트는 동시성 런타임에서 작업을 실행 하는 스레드입니다.  일반적으로 Win32 메서드 `GetLastError`에 대한 호출에서 반환되는 오류 코드는 값 형식 `HRESULT`이며 `get_error_code` 기본 클래스 메서드를 통해 검색할 수 있습니다.  
  
## 상속 계층  
 `exception`  
  
 [scheduler\_resource\_allocation\_error](../../../parallel/concrt/reference/scheduler-resource-allocation-error-class.md)  
  
 `scheduler_worker_creation_error`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)