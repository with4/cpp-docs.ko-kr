---
title: "CDynamicStringAccessor::GetString | Microsoft Docs"
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
  - "CDynamicStringAccessor.GetString"
  - "CDynamicStringAccessor::GetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetString 메서드"
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor::GetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the specified column data as a string.  
  
## 구문  
  
```  
  
      BaseType* GetString(  
   DBORDINAL nColumn  
) const throw( );  
BaseType* GetString(  
   const CHAR* pColumnName  
) const throw( );  
BaseType* GetString(  
   const WCHAR* pColumnName  
) const throw( );  
```  
  
#### 매개 변수  
 `nColumn`  
 \[in\] The column number.  Column numbers start with 1.  A value of 0 refers to the bookmark column, if any.  
  
 `pColumnName`  
 \[in\] A pointer to a character string that contains the column name.  
  
## 반환 값  
 A pointer to the string value retrieved from the specified column.  The value is of type ***BaseType***, which will be **CHAR** or **WCHAR** depending on whether \_UNICODE is defined or not.  Returns NULL if the specified column is not found.  
  
## 설명  
 The second override form takes the column name as an ANSI string.  The third override form takes the column name as a Unicode string.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicStringAccessor 클래스](../../data/oledb/cdynamicstringaccessor-class.md)