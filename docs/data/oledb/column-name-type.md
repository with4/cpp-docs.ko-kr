---
title: "COLUMN_NAME_TYPE | Microsoft Docs"
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
  - "COLUMN_NAME_TYPE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_NAME_TYPE 매크로"
ms.assetid: 815ace8f-8ec3-4ad7-a7a0-37fa8e4bc68c
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_NAME_TYPE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a binding on the rowset to the specific column in the rowset.  Similar to [COLUMN\_NAME](../../data/oledb/column-name.md), except that this macro also takes data type.  
  
## 구문  
  
```  
  
COLUMN_NAME_TYPE(  
pszName  
,   
wType  
,   
data  
 )  
  
```  
  
#### 매개 변수  
 `pszName`  
 \[in\] A pointer to the column name.  The name must be a Unicode string.  You can accomplish this by putting an 'L' in front of the name, for example: `L"MyColumn"`.  
  
 `wType`  
 \[in\] The data type.  
  
 `data`  
 \[in\] The corresponding data member in the user record.  
  
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
 [COLUMN\_NAME\_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN\_NAME\_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN\_NAME\_LENGTH\_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN\_NAME\_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN\_NAME\_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN\_NAME\_PS\_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN\_NAME\_PS\_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN\_NAME\_PS\_LENGTH\_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN\_NAME\_TYPE\_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN\_NAME\_TYPE\_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN\_NAME\_TYPE\_STATUS](../../data/oledb/column-name-type-status.md)