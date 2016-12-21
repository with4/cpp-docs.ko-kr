---
title: "accelerator_view_removed 클래스 | Microsoft Docs"
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
  - "amprt/Concurrency::accelerator_view_removed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "amprt/Concurrency::accelerator_view_removed 클래스"
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# accelerator_view_removed 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Windows 시간 초과 검색 및 복구 메커니즘으로 인해 내부 DirectX 호출이 실패할 때 throw되는 예외입니다.  
  
## 구문  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[accelerator\_view\_removed::accelerator\_view\_removed 생성자](../Topic/accelerator_view_removed::accelerator_view_removed%20Constructor.md)|`accelerator_view_removed` 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[accelerator\_view\_removed::get\_view\_removed\_reason 메서드](../Topic/accelerator_view_removed::get_view_removed_reason%20Method.md)|HRESULT 오류 코드 반환은 `accelerator_view` 개체의 제거의 원인을 나타냅니다.|  
  
## 상속 계층  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [Concurrency 네임스페이스\(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)