---
title: "ITopologyNode 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrtrm/concurrency::ITopologyNode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyNode 구조체"
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ITopologyNode 구조체
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

리소스 관리자에 의해 정의 된 토폴로지 노드에 대한 인터페이스입니다.  노드에는 하나 이상의 실행 리소스가 포함되어 있습니다.  
  
## 구문  
  
```  
struct ITopologyNode;  
```  
  
## 멤버  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[ITopologyNode::GetExecutionResourceCount 메서드](../Topic/ITopologyNode::GetExecutionResourceCount%20Method.md)|이 노드 아래에 그룹화된 실행 리소스의 수를 반환합니다.|  
|[ITopologyNode::GetFirstExecutionResource 메서드](../Topic/ITopologyNode::GetFirstExecutionResource%20Method.md)|열거의 순서로 이 노드 아래에 그룹화 된 첫 번째 실행 리소스를 반환합니다.|  
|[ITopologyNode::GetId 메서드](../Topic/ITopologyNode::GetId%20Method.md)|이 노드에 대한 리소스 관리자의 고유 식별자를 반환합니다.|  
|[ITopologyNode::GetNext 메서드](../Topic/ITopologyNode::GetNext%20Method.md)|인터페이스 열거 순서에 따라 다음 토폴로지 노드를 반환합니다.|  
|[ITopologyNode::GetNumaNode 메서드](../Topic/ITopologyNode::GetNumaNode%20Method.md)|이 리소스 관리자 노드가 속해 있는 NUMA 노드 번호를 할당하여 반환합니다.|  
  
## 설명  
 이 인터페이스는 일반적으로 리소스 관리자에 의해 관찰된 대로 시스템 토폴로지를 이용합니다.  
  
## 상속 계층  
 `ITopologyNode`  
  
## 요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)