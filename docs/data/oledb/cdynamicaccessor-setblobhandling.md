---
title: "CDynamicAccessor::SetBlobHandling | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetBlobHandling"
  - "CDynamicAccessor.SetBlobHandling"
  - "ATL::CDynamicAccessor::SetBlobHandling"
  - "SetBlobHandling"
  - "ATL.CDynamicAccessor.SetBlobHandling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobHandling 메서드"
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetBlobHandling
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the BLOB handling value for the current row.  
  
## 구문  
  
```  
  
      bool SetBlobHandling(  
   DBBLOBHANDLINGENUM eBlobHandling   
);  
```  
  
#### 매개 변수  
 `eBlobHandling`  
 Specifies how the BLOB data is to be handled.  It can take the following values:  
  
-   **DBBLOBHANDLING\_DEFAULT**: Handle column data larger than `nBlobSize` \(as set by `SetBlobSizeLimit`\) as BLOB data and retrieve it through an `ISequentialStream` or `IStream` object.  This option will attempt to bind every column containing data larger than `nBlobSize` or listed as **DBTYPE\_IUNKNOWN** as BLOB data.  
  
-   **DBBLOBHANDLING\_NOSTREAMS**: Handle column data larger than `nBlobSize` \(as set by `SetBlobSizeLimit`\) as BLOB data and retrieve it through reference in provider\-allocated, consumer\-owned memory.  This option is useful for tables that have more than one BLOB column, and the provider supports only one `ISequentialStream` object per accessor.  
  
-   **DBBLOBHANDLING\_SKIP**: Skip \(do not bind\) columns qualifying as containing BLOBs \(the accessor will not bind or retrieve the column value but it will still retrieve the column status and length\).  
  
## 설명  
 You should call `SetBlobHandling` before calling **Open**.  
  
 The constructor method [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) sets the BLOB handling value to **DBBLOBHANDLING\_DEFAULT**.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)