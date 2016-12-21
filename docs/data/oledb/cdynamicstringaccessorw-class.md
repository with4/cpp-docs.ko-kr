---
title: "CDynamicStringAccessorW 클래스 | Microsoft Docs"
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
  - "CDynamicStringAccessorW"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessorW 클래스"
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessorW 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Allows you to access a data source when you have no knowledge of the database schema \(underlying structure\).  
  
## 구문  
  
```  
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;  
```  
  
## 설명  
 They both request that the provider fetch all data accessed from the data store as string data, but `CDynamicStringAccessor` requests Unicode string data.  
  
 `CDynamicStringAccessorW` inherits **GetString** and `SetString` from `CDynamicStringAccessor`.  When you use these methods in a `CDynamicStringAccessorW` object, ***BaseType*** is **WCHAR**.  
  
## 요구 사항  
 **Header**: atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor 클래스](../../data/oledb/cdynamicstringaccessor-class.md)