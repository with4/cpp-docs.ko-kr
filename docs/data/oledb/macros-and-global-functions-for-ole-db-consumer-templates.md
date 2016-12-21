---
title: "OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수 | Microsoft Docs"
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
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "매크로, OLE DB 소비자 템플릿"
  - "OLE DB 소비자 템플릿, 매크로"
ms.assetid: 8765eb7b-32dd-407c-bacf-8890ef959837
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The OLE DB Consumer Templates include the following macros and global functions:  
  
### Global Functions  
  
|||  
|-|-|  
|[AtlTraceErrorRecords](../../data/oledb/atltraceerrorrecords.md)|Dumps OLE DB Error Record information to the dump device if an error is returned.|  
  
### Accessor Map Macros  
  
|||  
|-|-|  
|[BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)|Marks the beginning of an accessor entry.|  
|[BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)|Marks the beginning of the accessor map entries.|  
|[END\_ACCESSOR](../../data/oledb/end-accessor.md)|Marks the end of an accessor entry.|  
|[END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)|Marks the end of the accessor map entries.|  
  
### Column Map Macros  
  
|||  
|-|-|  
|[BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)|Marks the beginning of the column map entries in the user record class.|  
|[BLOB\_ENTRY](../../data/oledb/blob-entry.md)|Used to bind a binary large object \(BLOB\).|  
|[BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)|Reports the length of the BLOB data column.|  
|[BLOB\_ENTRY\_LENGTH\_STATUS](../../data/oledb/blob-entry-length-status.md)|Reports the length and status of the BLOB data column.|  
|[BLOB\_ENTRY\_STATUS](../../data/oledb/blob-entry-status.md)|Reports the status of the BLOB data column.|  
|[BLOB\_NAME](../../data/oledb/blob-name.md)|Used to bind a binary large object by column name.|  
|[BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)|Reports the length of the BLOB data column.|  
|[BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)|Reports the length and status of the BLOB data column.|  
|[BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)|Reports the status of the BLOB data column.|  
|[BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md)|Represents a bookmark entry on the rowset.  A bookmark entry is a special kind of column entry.|  
|[COLUMN\_ENTRY](../../data/oledb/column-entry.md)|Represents a binding to a specific column in the database.|  
|[COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)|Represents a binding to the specific column in the database.  Supports `type`, *length*, *precision*, `scale`, and *status* parameters.|  
|[COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)|Represents a binding to the specific column in the database.  Supports the *length* variable.|  
|[COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)|Represents a binding to the specific column in the database.  Supports *status* and *length* parameters.|  
|[COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)|Represents a binding to the specific column in the database.  Supports *precision* and `scale` parameters.|  
|[COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)|Represents a binding to the specific column in the database.  Supports the *length* variable, *precision* and `scale` parameters.|  
|[COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../../data/oledb/column-entry-ps-length-status.md)|Represents a binding to the specific column in the database.  Supports *status* and *length* variables, *precision* and `scale` parameters.|  
|[COLUMN\_ENTRY\_PS\_STATUS](../../data/oledb/column-entry-ps-status.md)|Represents a binding to the specific column in the database.  Supports the *status* variable, *precision* and `scale` parameters.|  
|[COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)|Represents a binding to the specific column in the database.  Supports the *status* variable.|  
|[COLUMN\_ENTRY\_TYPE](../../data/oledb/column-entry-type.md)|Represents a binding to a specific column in the database.  Supports `type` parameter.|  
|[COLUMN\_ENTRY\_TYPE\_SIZE](../../data/oledb/column-entry-type-size.md)|Represents a binding to the specific column in the database.  Supports `type` and `size` parameters.|  
|[COLUMN\_NAME](../../data/oledb/column-name.md)|Represents a binding to a specific column in the database by name.|  
|[COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)|Represents a binding to a specific column in the database by name.  Supports specification of data type, size, precision, scale, column length, and column status.|  
|[COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)|Represents a binding to a specific column in the database by name.  Supports specification of column length.|  
|[COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)|Represents a binding to a specific column in the database by name.  Supports specification of column length and status.|  
|[COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)|Represents a binding to a specific column in the database by name.  Supports specification of precision and scale.|  
|[COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)|Represents a binding to a specific column in the database by name.  Supports specification of precision, scale, and column length.|  
|[COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)|Represents a binding to a specific column in the database by name.  Supports specification of precision, scale, column length, and column status.|  
|[COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)|Represents a binding to a specific column in the database by name.  Supports specification of precision, scale, and column status.|  
|[COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)|Represents a binding to a specific column in the database by name.  Supports specification of column status.|  
|[COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)|Represents a binding to a specific column in the database by name.  Supports specification of data type.|  
|[COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)|Represents a binding to a specific column in the database by name.  Supports specification of data type, precision, and scale.|  
|[COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)|Represents a binding to a specific column in the database by name.  Supports specification of data type and size.|  
|[COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)|Represents a binding to a specific column in the database by name.  Supports specification of data type and column status.|  
|[END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)|Marks the end of the column map entries.|  
  
### Command Macros  
  
|||  
|-|-|  
|[DEFINE\_COMMAND](../../data/oledb/define-command.md)|Specifies the command that will be used to create the rowset when using the [CCommand](../../data/oledb/ccommand-class.md) class.  Accepts only string types matching the specified application type \(ANSI or Unicode\).  It is recommended that you use [DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md) instead of `DEFINE_COMMAND`.|  
|[DEFINE\_COMMAND\_EX](../../data/oledb/define-command-ex.md)|Specifies the command that will be used to create the rowset when using the [CCommand](../../data/oledb/ccommand-class.md) class.  Supports ANSI and Unicode applications.|  
  
### Parameter Map Macros  
  
|||  
|-|-|  
|[BEGIN\_PARAM\_MAP](../../data/oledb/begin-param-map.md)|Marks the beginning of the parameter map entries in the user record class.|  
|[END\_PARAM\_MAP](../../data/oledb/end-param-map.md)|Marks the end of the parameter map entries.|  
|[SET\_PARAM\_TYPE](../../data/oledb/set-param-type.md)|Specifies `COLUMN_ENTRY` macros that follow the `SET_PARAM_TYPE` macro as input, output, or input\/output.|  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)