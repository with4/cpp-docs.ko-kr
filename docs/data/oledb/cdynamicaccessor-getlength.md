---
title: "CDynamicAccessor::GetLength | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor.GetLength"
  - "ATL.CDynamicAccessor.GetLength"
  - "CDynamicAccessor::GetLength"
  - "ATL::CDynamicAccessor::GetLength"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetLength 메서드"
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetLength
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the length of the specified column.  
  
## 구문  
  
```  
  
      bool GetLength(   
   DBORDINAL nColumn,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const CHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const WCHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
```  
  
#### 매개 변수  
 `nColumn`  
 \[in\] The column number.  Column numbers start with 1.  A value of 0 refers to the bookmark column, if any.  
  
 `pColumnName`  
 \[in\] A pointer to a character string containing the column name.  
  
 `pLength`  
 \[out\] A pointer to the integer containing the length of the column in bytes.  
  
## 반환 값  
 Returns **true** if the specified column is found.  Otherwise, this function returns **false**.  
  
## 설명  
 The first override takes the column number, and the second and third overrides take the column name in ANSI or Unicode format, respectively.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)