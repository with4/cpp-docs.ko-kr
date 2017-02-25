---
title: "COLUMN_ENTRY_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_EX 매크로"
ms.assetid: dfad1b67-51c3-4289-b89a-da42d7e8bb88
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_ENTRY_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a binding on the rowset to the specific column in the database.  
  
## 구문  
  
```  
  
COLUMN_ENTRY_EX(  
nOrdinal  
,   
wType  
,   
nLength  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
,   
status  
 )  
  
```  
  
#### 매개 변수  
 See [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) in the *OLE DB Programmer's Reference*.  
  
 `nOrdinal`  
 \[in\] The column number.  
  
 `wType`  
 \[in\] The data type.  
  
 `nLength`  
 \[in\] The data size in bytes.  
  
 `nPrecision`  
 \[in\] The maximum precision to use when getting data and `wType` is `DBTYPE_NUMERIC`.  그렇지 않으면 이 매개 변수는 무시됩니다.  
  
 `nScale`  
 \[in\] The scale to use when getting data and `wType` is `DBTYPE_NUMERIC` or **DBTYPE\_DECIMAL**.  
  
 `data`  
 \[in\] The corresponding data member in the user record.  
  
 *length*  
 \[in\] The variable to be bound to the column length.  
  
 *status*  
 \[in\] The variable to be bound to the column status.  
  
## 설명  
 The `COLUMN_ENTRY_EX` macro is used in the following places:  
  
-   Between the [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md) and [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md) macros.  
  
-   Between the [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) and [END\_ACCESSOR](../../data/oledb/end-accessor.md) macros.  
  
-   Between the [BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md) and [END\_PARAM\_MAP](../../data/oledb/end-param-map.md) macros.  
  
## 예제  
 See [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)