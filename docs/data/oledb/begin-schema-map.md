---
title: "BEGIN_SCHEMA_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_SCHEMA_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_SCHEMA_MAP 매크로"
ms.assetid: 4e751023-35bc-4efd-9018-5448dd1ad751
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# BEGIN_SCHEMA_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Denotes the beginning of a schema map.  
  
## 구문  
  
```  
  
      BEGIN_SCHEMA_MAP(  
   SchemaClass   
);  
```  
  
#### 매개 변수  
 *SchemaClass*  
 The class that contains the MAP.  Typically this will be the session class.  
  
## 설명  
 See [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] for more information about schema rowsets.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)   
 [IDBSchemaRowsetImpl 클래스](../../data/oledb/idbschemarowsetimpl-class.md)