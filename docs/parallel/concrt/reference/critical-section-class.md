---
title: "critical_section 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::critical_section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "critical_section 클래스"
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# critical_section 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

동시성 런타임을 명시적으로 인식하는 재진입 뮤텍스입니다.  
  
## 구문  
  
```  
class critical_section;  
```  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`native_handle_type`|`critical_section` 개체에 대한 참조입니다.|  
  
### 공용 클래스  
  
|Name|설명|  
|----------|--------|  
|[critical\_section::scoped\_lock 클래스](../Topic/critical_section::scoped_lock%20Class.md)|`critical_section` 개체에 대한 예외 안전 RAII 래퍼입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[critical\_section::critical\_section 생성자](../Topic/critical_section::critical_section%20Constructor.md)|새 중요 섹션을 생성합니다.|  
|[critical\_section::~critical\_section 소멸자](../Topic/critical_section::~critical_section%20Destructor.md)|임계 영역을 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[critical\_section::lock 메서드](../Topic/critical_section::lock%20Method.md)|이 중요 섹션을 가져옵니다.|  
|[critical\_section::native\_handle 메서드](../Topic/critical_section::native_handle%20Method.md)|있는 경우 플랫폼 특정 네이티브 핸들을 반환합니다.|  
|[critical\_section::try\_lock 메서드](../Topic/critical_section::try_lock%20Method.md)|차단하지 않고 잠금을 얻으려고 시도합니다.|  
|[critical\_section::try\_lock\_for 메서드](../Topic/critical_section::try_lock_for%20Method.md)|밀리 초 단위의 특정 번호를 차단하지 않고 잠금을 획득하려고 시도합니다.|  
|[critical\_section::unlock 메서드](../Topic/critical_section::unlock%20Method.md)|임계 영역을 잠금을 해제합니다.|  
  
## 설명  
 자세한 내용은 [동기화 데이터 구조](../../../parallel/concrt/synchronization-data-structures.md)을 참조하십시오.  
  
## 상속 계층  
 `critical_section`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [reader\_writer\_lock 클래스](../../../parallel/concrt/reference/reader-writer-lock-class.md)