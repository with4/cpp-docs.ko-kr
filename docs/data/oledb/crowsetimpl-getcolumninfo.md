---
title: "CRowsetImpl::GetColumnInfo | Microsoft Docs"
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
  - "GetColumnInfo"
  - "CRowsetImpl.GetColumnInfo"
  - "CRowsetImpl::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo 메서드"
ms.assetid: 9ef76525-f996-4c6f-81b9-68eb260350ef
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves column information for a particular client request.  
  
## 구문  
  
```  
  
      static ATLCOLUMNINFO* CRowsetBaseImpl::GetColumnInfo(  
   T* pv,  
   ULONG* pcCols   
);  
```  
  
#### 매개 변수  
 `pv`  
 \[in\] A pointer to the user's `CRowsetImpl` derived class.  
  
 `pcCols`  
 \[in\] A pointer \(output\) to the number of columns returned.  
  
## 반환 값  
 A pointer to a static **ATLCOLUMNINFO** structure.  
  
## 설명  
 This method is an advanced override.  
  
 This method is called by several base implementation classes to retrieve column information for a particular client request.  Usually, this method would be called by `IColumnsInfoImpl`.  If you override this method, you must place a version of the method in your `CRowsetImpl`\-derived class.  Because the method may be placed in a non\-templatized class, you must change `pv` to the appropriate `CRowsetImpl`\-derived class.  
  
 The following example demonstrates **GetColumnInfo's** usage.  In this example, **CMyRowset** is a `CRowsetImpl`\-derived class.  In order to override `GetColumnInfo` for all instances of this class, place the following method in the **CMyRowset** class definition:  
  
 [!CODE [NVC_OLEDB_Provider#1](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Provider#1)]  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)