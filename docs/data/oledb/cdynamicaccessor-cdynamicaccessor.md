---
title: "CDynamicAccessor::CDynamicAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::CDynamicAccessor"
  - "ATL::CDynamicAccessor::CDynamicAccessor"
  - "ATL.CDynamicAccessor.CDynamicAccessor"
  - "CDynamicAccessor.CDynamicAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicAccessor 클래스, 생성자"
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::CDynamicAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Instantiates and initializes the `CDynamicAccessor` object.  
  
## 구문  
  
```  
  
      CDynamicAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000   
);  
```  
  
#### 매개 변수  
 `eBlobHandling`  
 Specifies how the binary large object \(BLOB\) data is to be handled.  The default value is **DBBLOBHANDLING\_DEFAULT**.  See [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) for a description of the **DBBLOBHANDLINGENUM** values.  
  
 `nBlobSize`  
 The maximum BLOB size in bytes; column data over this value is treated as a BLOB.  The default value is 8,000.  See [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) for details.  
  
## 설명  
 If you use the constructor to initialize the `CDynamicAccessor` object, you can specify how it will bind BLOBs.  BLOBs can contain binary data such as graphics, sound, or compiled code.  The default behavior is to treat columns more than 8,000 bytes as BLOBs and try to bind them to an `ISequentialStream` object.  However, you can specify a different value to be the BLOB size.  
  
 You can also specify how `CDynamicAccessor` handles column data that qualifies as BLOB data: it can handle BLOB data in the default manner; it can skip \(does not bind\) BLOB data; or it can bind BLOB data in provider\-allocated memory.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)