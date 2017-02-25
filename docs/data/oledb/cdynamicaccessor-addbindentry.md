---
title: "CDynamicAccessor::AddBindEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::AddBindEntry"
  - "AddBindEntry"
  - "CDynamicAccessor.AddBindEntry"
  - "CDynamicAccessor::AddBindEntry"
  - "ATL.CDynamicAccessor.AddBindEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddBindEntry 메서드"
ms.assetid: 8f139376-7db3-4193-ba3b-63fe938ffa79
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::AddBindEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Adds a bind entry to the output columns.  
  
## 구문  
  
```  
  
      HRESULT AddBindEntry(   
   const DBCOLUMNINFO& info    
) throw( );  
```  
  
#### 매개 변수  
 `info`  
 \[in\] A **DBCOLUMNINFO** structure containing column information.  See "DBCOLUMNINFO Structures" in [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in the *OLE DB Programmer's Reference*.  
  
## 반환 값  
 One of the standard `HRESULT` values.  
  
## 설명  
 Use this method when overriding the default accessor created with `CDynamicAccessor` \(see [How Do I Fetch Data?](../../data/oledb/fetching-data.md)\).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)