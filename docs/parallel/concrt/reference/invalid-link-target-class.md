---
title: "invalid_link_target 클래스 | Microsoft Docs"
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
  - "concrt/concurrency::invalid_link_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_link_target 클래스"
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_link_target 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 메시징 블록의 `link_target` 메서드가 호출되며 메시징 블록이 대상에 연결할 수 없을 때 throw되는 예외를 설명합니다.  이는 메시징 블록이 허용하는 링크 수를 초과하거나 특정 대상이 같은 소스에 두 번 연결을 시도한 결과일 수 있습니다.  
  
## 구문  
  
```  
class invalid_link_target : public std::exception;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[invalid\_link\_target::invalid\_link\_target 생성자](../Topic/invalid_link_target::invalid_link_target%20Constructor.md)|오버로드됨.  `invalid_link_target` 개체를 생성합니다.|  
  
## 상속 계층  
 `exception`  
  
 `invalid_link_target`  
  
## 요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)