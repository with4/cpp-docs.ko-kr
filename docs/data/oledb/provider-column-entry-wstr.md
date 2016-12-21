---
title: "PROVIDER_COLUMN_ENTRY_WSTR | Microsoft Docs"
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
  - "PROVIDER_COLUMN_ENTRY_WSTR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_WSTR 매크로"
ms.assetid: 70630bd5-d782-473b-9777-aebbbf5321c5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROVIDER_COLUMN_ENTRY_WSTR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a specific column supported by the provider.  
  
## 구문  
  
```  
  
PROVIDER_COLUMN_ENTRY_WSTR(  
name  
, ordinal, member )  
```  
  
#### 매개 변수  
 *name*  
 \[in\] The column name.  
  
 `ordinal`  
 \[in\] The column number.  Unless the column is a Bookmark column, the column number must not be 0.  
  
 `member`  
 \[in\] The member variable in the data class that stores the data.  
  
## 설명  
 Use this macro when the column data is a null terminated Unicode character string, [DBTYPE\_WSTR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿에 대한 매크로](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB 공급자 만들기](../../data/oledb/creating-an-ole-db-provider.md)