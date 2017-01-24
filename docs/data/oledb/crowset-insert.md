---
title: "CRowset::Insert | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.Insert"
  - "CRowset.Insert"
  - "CRowset<TAccessor>.Insert"
  - "CRowset<TAccessor>::Insert"
  - "ATL::CRowset<TAccessor>::Insert"
  - "ATL.CRowset.Insert"
  - "CRowset::Insert"
  - "ATL::CRowset::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Insert 메서드"
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Insert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Creates and initializes a new row using data from the accessor.  
  
## 구문  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### 매개 변수  
 `nAccessor`  
 \[in\] The number of the accessor to use for inserting the data.  
  
 *bGetHRow*  
 \[in\] Indicates whether the handle for the inserted row is retrieved.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method requires the optional interface `IRowsetChange`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetChange** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
 Insert might fail if one or more columns is not writable.  이를 방지하려면 커서 맵을 수정하십시오.  
  
## 예제  
 The following example shows how to access a data source through a rowset and then insert a string using a table in that rowset.  
  
 First, create a table class by inserting a New ATL Object into your project.  For example, right\-click the project in the Workspace pane and select **New ATL Object**.  From the **Data Access** category, select **Consumer**.  Create a consumer object of type **Table**. \(Selecting **Table** creates a rowset directly from the table; selecting **Command** creates a rowset through a SQL command.\) Select a data source, specifying a table through which to access that data source.  If you call your consumer object **CCustomerTable**, you would then implement your insertion code as follows:  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/CPP/crowset-insert_1.cpp)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)