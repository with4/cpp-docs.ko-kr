---
title: "CReferentialConstraints, CReferentialConstraintInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szUniqueName"
  - "m_szCatalog"
  - "DELETE_RULE"
  - "m_szUniqueCatalog"
  - "CONSTRAINT_NAME"
  - "CReferentialConstraintInfo"
  - "MATCH_OPTION"
  - "m_szSchema"
  - "m_szDeleteRule"
  - "m_szUpdateRule"
  - "m_szUniqueSchema"
  - "CReferentialConstraints"
  - "m_szName"
  - "CONSTRAINT_CATALOG"
  - "m_szMatchOption"
  - "CONSTRAINT_SCHEMA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "CReferentialConstraintInfo 매개 변수 클래스"
  - "CReferentialConstraints typedef 클래스"
  - "DELETE_RULE"
  - "DESCRIPTION 클래스 데이터 멤버"
  - "m_szCatalog"
  - "m_szDeleteRule"
  - "m_szDescription"
  - "m_szMatchOption"
  - "m_szName"
  - "m_szSchema"
  - "m_szUniqueCatalog"
  - "m_szUniqueName"
  - "m_szUniqueSchema"
  - "m_szUpdateRule"
  - "MATCH_OPTION"
ms.assetid: 5d485358-be29-41c2-b0ce-19e023598e73
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CReferentialConstraints, CReferentialConstraintInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Call the typedef class **CReferentialConstraints** to implement its parameter class **CReferentialConstraintInfo**.  
  
## 설명  
 See [Schema Rowset Classes and Typedef Classes](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) for more information on using typedef classes.  
  
 This class identifies the referential constraints, defined in the catalog, that are owned by a given user.  
  
 The following table lists the class data members and their corresponding OLE DB Columns.  See [REFERENTIAL\_CONSTRAINTS Rowset](https://msdn.microsoft.com/en-us/library/ms719737.aspx) in the *OLE DB Programmer's Reference* for more information about the schema and columns.  
  
|Data members|OLE DB columns|  
|------------------|--------------------|  
|m\_szCatalog|CONSTRAINT\_CATALOG|  
|m\_szSchema|CONSTRAINT\_SCHEMA|  
|m\_szName|CONSTRAINT\_NAME|  
|m\_szUniqueCatalog|UNIQUE\_CONSTRAINT\_CATALOG|  
|m\_szUniqueSchema|UNIQUE\_CONSTRAINT\_SCHEMA|  
|m\_szUniqueName|UNIQUE\_CONSTRAINT\_NAME|  
|m\_szMatchOption|MATCH\_OPTION|  
|m\_szUpdateRule|UPDATE\_RULE|  
|m\_szDeleteRule|DELETE\_RULE|  
|m\_szDescription|DESCRIPTION|  
  
## 요구 사항  
 **Header:** atldbsch.h  
  
## 참고 항목  
 [CRestrictions 클래스](../../data/oledb/crestrictions-class.md)