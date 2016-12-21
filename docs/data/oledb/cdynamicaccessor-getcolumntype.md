---
title: "CDynamicAccessor::GetColumnType | Microsoft Docs"
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
  - "ATL.CDynamicAccessor.GetColumnType"
  - "CDynamicAccessor::GetColumnType"
  - "GetColumnType"
  - "CDynamicAccessor.GetColumnType"
  - "ATL::CDynamicAccessor::GetColumnType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnType 메서드"
ms.assetid: ac96a2e9-6049-4eb5-9718-9f5f5446b74e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetColumnType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the data type of a specified column.  
  
## 구문  
  
```  
  
      bool GetColumnType(   
   DBORDINAL nColumn,   
   DBTYPE* pType    
) const throw( );  
```  
  
#### 매개 변수  
 `nColumn`  
 \[in\] The column number.  Column numbers start with 1.  A value of 0 refers to the bookmark column, if any.  
  
 `pType`  
 \[out\] A pointer to the data type of the specified column.  
  
## 반환 값  
 Returns **true** on success or **false** on failure.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx)