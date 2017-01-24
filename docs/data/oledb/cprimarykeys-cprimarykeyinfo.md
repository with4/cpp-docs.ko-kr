---
title: "CPrimaryKeys, CPrimaryKeyInfo | Microsoft Docs"
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
  - "m_nOrdinal"
  - "m_szTableSchema"
  - "m_nColumnPropID"
  - "CPrimaryKeys"
  - "COLUMN_GUID"
  - "CPrimaryKeyInfo"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "ORDINAL"
  - "m_szTableName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "CPrimaryKeyInfo 매개 변수 클래스"
  - "CPrimaryKeys typedef 클래스"
  - "m_guidColumn"
  - "m_nColumnPropID"
  - "m_nOrdinal"
  - "m_szColumnName"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "ORDINAL 데이터 멤버"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: c27b97a4-a156-4f66-89e3-95f85d7d6281
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CPrimaryKeys, CPrimaryKeyInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Call the typedef class **CPrimaryKeys** to implement its parameter class **CPrimaryKeyInfo**.  
  
## 설명  
 See [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) for more information on using typedef classes.  
  
 This class identifies the primary key columns defined in the catalog by a given user.  
  
 The following table lists the class data members and their corresponding OLE DB Columns.  See [PRIMARY\_KEYS Rowset](https://msdn.microsoft.com/en-us/library/ms714362.aspx) in the *OLE DB Programmer's Reference* for more information about the schema and columns.  
  
|Data members|OLE DB columns|  
|------------------|--------------------|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_nOrdinal|ORDINAL|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)