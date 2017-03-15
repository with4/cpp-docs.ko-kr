---
title: "COLUMN_NAME_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_NAME_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_EX 매크로"
ms.assetid: 4f916a85-f6ae-464a-9cbe-0a56dbb274a6
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_NAME_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a binding on the rowset to the specific column in the rowset.  Similar to [COLUMN\_NAME](../../data/oledb/column-name.md), except that this macro also takes data type, size, precision, scale, column length, and column status.  
  
## 구문  
  
```  
  
COLUMN_NAME_EX(  
pszName  
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
status )  
```  
  
#### 매개 변수  
 `pszName`  
 \[in\] A pointer to the column name.  The name must be a Unicode string.  You can accomplish this by putting an 'L' in front of the name, for example: `L"MyColumn"`.  
  
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
 See [COLUMN\_NAME](../../data/oledb/column-name.md) for information on where the **COLUMN\_NAME\_\*** macros are used.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_NAME](../../data/oledb/column-name.md)   
 [COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN\_NAME\_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)