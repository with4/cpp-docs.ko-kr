---
title: "SCHEMA_ENTRY | Microsoft Docs"
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
  - "SCHEMA_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SCHEMA_ENTRY 매크로"
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SCHEMA_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Associates a GUID with a class.  
  
## 구문  
  
```  
  
      SCHEMA_ENTRY(  
   guid,  
   rowsetClass   
);   
```  
  
#### 매개 변수  
 `guid`  
 A schema rowset GUID.  See [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in the *OLE DB Programmer's Reference* for a list of schema rowsets and their GUIDs.  
  
 *rowsetClass*  
 The class that will be created to represent the schema rowset.  
  
## 설명  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) can then query the map for a list of GUIDs, or it can create a rowset if it is given a GUID.  The schema rowset `IDBSchemaRowsetImpl` creates is similar to a standard `CRowsetImpl`\-derived class, except it must provide an **Execute** method that has the following signature:  
  
 `HRESULT Execute (LONG* pcRowsAffected, ULONG cRestrictions,`  
  
 `const VARIANT* rgRestrictions)`  
  
 This **Execute** function populates the rowset's data.  The ATL Project Wizard creates, as described in [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in the *OLE DB Programmer's Reference*, three initial schema rowsets in the project for each of the three mandatory OLE DB schemas:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA\_COLUMNS**  
  
-   **DBSCHEMA\_PROVIDER\_TYPES**  
  
 The wizard also adds three corresponding entries in the schema map.  See [Creating an OLE DB Template Provider](../../data/oledb/creating-an-ole-db-provider.md) for more information about using the wizard to create a provider.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)