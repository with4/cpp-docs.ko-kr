---
title: "COLUMN_ENTRY_PS_LENGTH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_PS_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_PS_LENGTH 매크로"
ms.assetid: d63ab895-a4df-4183-ac09-cf2311222408
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_ENTRY_PS_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a binding on the rowset to the specific column in the database.  
  
## 구문  
  
```  
  
COLUMN_ENTRY_PS_LENGTH(  
nOrdinal  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
 )  
  
```  
  
#### 매개 변수  
 See [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in the *OLE DB Programmer's Reference*.  
  
 `nOrdinal`  
 \[in\] The column number, starting with one.  Bookmark corresponds to column zero.  
  
 `nPrecision`  
 \[in\] The maximum precision of the column you want to bind.  
  
 `nScale`  
 \[in\] The scale of the column you want to bind.  
  
 `data`  
 \[in\] The corresponding data member in the user record.  
  
 *length*  
 \[in\] The variable to be bound to the column length.  
  
## 설명  
 Allows you to specify the precision and scale of the column you want to bind.  This macro supports the *length* variable.  It is used in the following places:  
  
-   Between the [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) and [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md) macros.  
  
-   Between the [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) and [END\_ACCESSOR](../../data/oledb/end-accessor.md) macros.  
  
-   Between the [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) and [END\_PARAM\_MAP](../../data/oledb/end-param-map.md) macros.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)