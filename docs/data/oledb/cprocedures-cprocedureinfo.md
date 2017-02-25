---
title: "CProcedures, CProcedureInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CProcedures"
  - "m_szCatalog"
  - "CProcedureInfo"
  - "m_szSchema"
  - "m_szDefinition"
  - "m_szName"
  - "m_nType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProcedureInfo 매개 변수 클래스"
  - "CProcedures typedef 클래스"
  - "DESCRIPTION 클래스 데이터 멤버"
  - "m_nType"
  - "m_szCatalog"
  - "m_szDefinition"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
ms.assetid: d0c7375e-ee0c-441d-aae6-6108150860a0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CProcedures, CProcedureInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Call the typedef class **CProcedures** to implement its parameter class **CProcedureInfo**.  
  
## 설명  
 See [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) for more information on using typedef classes.  
  
 This class identifies the procedures, defined in the catalog, that are owned by a given user.  
  
 The following table lists the class data members and their corresponding OLE DB Columns.  See [PROCEDURES Rowset](https://msdn.microsoft.com/en-us/library/ms724021.aspx) in the *OLE DB Programmer's Reference* for more information about the schema and columns.  
  
|Data members|OLE DB columns|  
|------------------|--------------------|  
|m\_szCatalog|PROCEDURE\_CATALOG|  
|m\_szSchema|PROCEDURE\_SCHEMA|  
|m\_szName|PROCEDURE\_NAME|  
|m\_nType|PROCEDURE\_TYPE|  
|m\_szDefinition|PROCEDURE\_DEFINITION|  
|m\_szDescription|DESCRIPTION|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)