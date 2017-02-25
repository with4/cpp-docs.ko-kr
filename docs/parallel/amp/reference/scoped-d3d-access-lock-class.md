---
title: "scoped_d3d_access_lock 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# scoped_d3d_access_lock 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Accelerator\_view 개체에 대해 액세스 잠금 D3D RAII 래퍼.  
  
## 구문  
  
```  
class scoped_d3d_access_lock;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[scoped\_d3d\_access\_lock::scoped\_d3d\_access\_lock 생성자](../Topic/scoped_d3d_access_lock::scoped_d3d_access_lock%20Constructor.md)|오버로드됨.  `scoped_d3d_access_lock` 개체를 생성합니다.  이 개체가 범위를 벗어날 때 잠금이 해제됩니다.|  
|[scoped\_d3d\_access\_lock::~scoped\_d3d\_access\_lock 소멸자](../Topic/scoped_d3d_access_lock::~scoped_d3d_access_lock%20Destructor.md)|연결된 `accelerator_view` 개에 대한 D3D 액세스 잠금을 해제합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[scoped\_d3d\_access\_lock::operator\= 연산자](../Topic/scoped_d3d_access_lock::operator=%20Operator.md)|다른 `scoped_d3d_access_lock`에서 잠금 소유권을 가져옵니다.|  
  
## 상속 계층  
 `scoped_d3d_access_lock`  
  
## 요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** concurrency::direct3d  
  
## 참고 항목  
 [Concurrency::direct3d 네임스페이스](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)