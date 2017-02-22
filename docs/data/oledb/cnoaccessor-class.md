---
title: "CNoAccessor 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CNoAccessor"
  - "CNoAccessor"
  - "ATL.CNoAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoAccessor 클래스"
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CNoAccessor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Can be used as a template argument \(`TAccessor`\) for template classes, such as `CCommand` and `CTable`, that require an accessor class argument.  
  
## 구문  
  
```  
class CNoAccessor  
```  
  
## 설명  
 Use `CNoAccessor` as a template argument when you do not want the class to support parameters or output columns.  
  
 `CNoAccessor` implements the following stub methods, each of which correspond to other accessor class methods:  
  
-   **BindColumns** \- Binds columns to accessors.  
  
-   `BindParameters` \- Binds the created parameters to columns.  
  
-   **Bind** \- Creates bindings.  
  
-   **Close** \- Closes the accessor.  
  
-   `ReleaseAccessors` \- Releases the accessors created by the class.  
  
-   `FreeRecordMemory` \- Frees any columns in the current record that need to be freed.  
  
-   `GetColumnInfo` \- Gets column information from the opened rowset.  
  
-   `GetNumAccessors` \- Retrieves the number of accessors created by the class.  
  
-   `IsAutoAccessor` \- Returns true if data is automatically retrieved for the accessor during a Move operation.  
  
-   `GetHAccessor` \- Retrieves the accessor handle of a specified accessor.  
  
-   `GetBuffer` \- Retrieves the pointer to the bookmark buffer.  
  
-   **NoBindOnNullRowset** \- Prevents data binding on empty rowsets.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)