---
title: "COLUMN_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY 매크로"
ms.assetid: a10aef29-6d70-49ec-b572-5b5c4abe1b46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# COLUMN_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a binding on the rowset to the specific column in the rowset.  
  
## 구문  
  
```  
  
COLUMN_ENTRY(  
nOrdinal  
,   
data  
 )  
  
```  
  
#### 매개 변수  
 See [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in the *OLE DB Programmer's Reference*.  
  
 `nOrdinal`  
 \[in\] The column number.  
  
 `data`  
 \[in\] The corresponding data member in the user record.  
  
## 설명  
 The `COLUMN_ENTRY` macro is used in the following places:  
  
-   Between the [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) and [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md) macros.  
  
-   Between the [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) and [END\_ACCESSOR](../../data/oledb/end-accessor.md) macros.  
  
-   Between the [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) and [END\_PARAM\_MAP](../../data/oledb/end-param-map.md) macros.  
  
## 예제  
 See the examples in the macro topics, [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) and [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [COLUMN\_ENTRY\_TYPE](../../data/oledb/column-entry-type.md)   
 [COLUMN\_ENTRY\_TYPE\_SIZE](../../data/oledb/column-entry-type-size.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)