---
title: "CDynamicAccessor::GetBlobHandling | Microsoft Docs"
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
  - "ATL.CDynamicAccessor.GetBlobHandling"
  - "CDynamicAccessor::GetBlobHandling"
  - "ATL::CDynamicAccessor::GetBlobHandling"
  - "GetBlobHandling"
  - "CDynamicAccessor.GetBlobHandling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBlobHandling 메서드"
ms.assetid: bbc6dda6-e132-42a3-980d-24e455cbe456
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetBlobHandling
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the BLOB handling value for the current row.  
  
## 구문  
  
```  
  
const DBBLOBHANDLINGENUM GetBlobHandling( ) const;  
  
```  
  
## 설명  
 Returns the BLOB handling value `eBlobHandling` as set by [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)