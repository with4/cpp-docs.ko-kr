---
title: "PROVIDER_COLUMN_ENTRY_TYPE_LENGTH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_TYPE_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_TYPE_LENGTH 매크로"
ms.assetid: a60b1a8b-0903-4ff4-91ec-ed62126449fb
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# PROVIDER_COLUMN_ENTRY_TYPE_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a specific column supported by the provider.  
  
## 구문  
  
```  
  
PROVIDER_COLUMN_ENTRY_TYPE_LENGTH(  
name  
, ordinal, dbtype, size, member )  
```  
  
#### 매개 변수  
 *name*  
  
 \[in\] The column name.  
  
 `ordinal`  
 \[in\] The column number.  Unless the column is a Bookmark column, the column number must not be 0.  
  
 `dbtype`  
 \[in\] The data type in [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
 `size`  
 \[in\] The column size in bytes.  
  
 `member`  
 \[in\] The member variable in the data class that stores the data.  
  
## 설명  
 Similar to [PROVIDER\_COLUMN\_ENTRY\_LENGTH](../../data/oledb/provider-column-entry-length.md) but also allows you to specify the column's data type as well as size.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)