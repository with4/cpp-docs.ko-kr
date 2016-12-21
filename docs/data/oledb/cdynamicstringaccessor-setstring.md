---
title: "CDynamicStringAccessor::SetString | Microsoft Docs"
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
  - "CDynamicStringAccessor::SetString"
  - "CDynamicStringAccessor.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString 메서드"
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor::SetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the specified column data as a string.  
  
## 구문  
  
```  
HRESULT SetString(  
   DBORDINAL nColumn,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const CHAR* pColumnName,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const WCHAR* pColumnName,  
   BaseType* data  
) throw( );  
```  
  
#### 매개 변수  
 `nColumn`  
 \[in\] The column number.  Column numbers start with 1.  The special value of 0 refers to the bookmark column, if any.  
  
 `pColumnName`  
 \[in\] A pointer to a character string that contains the column name.  
  
 `data`  
 \[in\] A pointer to the string data to be written to the specified column.  
  
## 반환 값  
 A pointer to the string value to which to set the specified column.  The value is of type `BaseType`, which will be `CHAR` or `WCHAR` depending on whether `_UNICODE` is defined or not.  
  
## 설명  
 The second override form takes the column name as an ANSI string and the third override form takes the column name as a Unicode string.  
  
 If `_SECURE_ATL` is defined to have a nonzero value, a runtime assertion failure will be generated if the input `data` string is longer than the maximum allowable length of the referenced data column.  Otherwise, the input string will be truncated if it is longer than the maximum allowable length.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicStringAccessor 클래스](../../data/oledb/cdynamicstringaccessor-class.md)