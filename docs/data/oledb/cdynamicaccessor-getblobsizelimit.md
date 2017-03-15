---
title: "CDynamicAccessor::GetBlobSizeLimit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::GetBlobSizeLimit"
  - "CDynamicAccessor.GetBlobSizeLimit"
  - "CDynamicAccessor::GetBlobSizeLimit"
  - "GetBlobSizeLimit"
  - "ATL.CDynamicAccessor.GetBlobSizeLimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBlobSizeLimit 메서드"
ms.assetid: 7131e7c4-6e05-42f3-9d87-110301b672f2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetBlobSizeLimit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the maximum BLOB size in bytes.  
  
## 구문  
  
```  
  
const DBLENGTH GetBlobSizeLimit( ) const;  
  
```  
  
## 설명  
 Returns the BLOB handling value `nBlobSize` as set by [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)