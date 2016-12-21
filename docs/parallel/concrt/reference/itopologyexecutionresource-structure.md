---
title: "ITopologyExecutionResource 구조체 | Microsoft Docs"
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
  - "concrtrm/concurrency::ITopologyExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyExecutionResource 구조체"
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ITopologyExecutionResource 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

리소스 관리자에 의해 정의된 실행 리소스에 대한 인터페이스입니다.  
  
## 구문  
  
```  
struct ITopologyExecutionResource;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ITopologyExecutionResource::GetId 메서드](../Topic/ITopologyExecutionResource::GetId%20Method.md)|이 실행 리소스에 대한 리소스 관리자의 고유 식별자를 반환합니다.|  
|[ITopologyExecutionResource::GetNext 메서드](../Topic/ITopologyExecutionResource::GetNext%20Method.md)|열거 순서에서 다음 실행 리소스에 인터페이스를 반환 합니다.|  
  
## 설명  
 이 인터페이스는 일반적으로 리소스 관리자에 의해 관찰된 대로 시스템 토폴로지를 이용합니다.  
  
## 상속 계층  
 `ITopologyExecutionResource`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)