---
title: "runtime_exception 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::direct3d_abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "runtime_exception 클래스"
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# runtime_exception 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

C\+\+ 가속 대용량 병렬 처리 \(AMP\) 라이브러리에서 예외에 대한 기본 형식입니다.  
  
## 구문  
  
```  
class runtime_exception : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[runtime\_exception::runtime\_exception 생성자](../Topic/runtime_exception::runtime_exception%20Constructor.md)|`runtime_exception` 클래스의 새 인스턴스를 초기화합니다.|  
|[runtime\_exception::~runtime\_exception 소멸자](../Topic/runtime_exception::~runtime_exception%20Destructor.md)|`runtime_exception` 개체를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[runtime\_exception::get\_error\_code 메서드](../Topic/runtime_exception::get_error_code%20Method.md)|예외의 원인이 된 오류 코드를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[runtime\_exception::operator\= 연산자](../Topic/runtime_exception::operator=%20Operator.md)|지정된 `runtime_exception` 개체의 내용을 여기로 복사합니다.|  
  
## 상속 계층  
 `exception`  
  
 `runtime_exception`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)