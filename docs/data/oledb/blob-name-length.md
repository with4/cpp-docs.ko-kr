---
title: "BLOB_NAME_LENGTH | Microsoft Docs"
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
  - "BLOB_NAME_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME_LENGTH 매크로"
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_NAME_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Used with `BEGIN_COLUMN_MAP` and `END_COLUMN_MAP` to bind a binary large object \([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Similar to [BLOB\_NAME](../../data/oledb/blob-name.md), except that this macro also gets the length in bytes of the BLOB data column.  
  
## 구문  
  
```  
  
BLOB_NAME_LENGTH(  
pszName  
,   
IID  
,   
flags  
,   
data  
,   
length )  
```  
  
#### 매개 변수  
 `pszName`  
 \[in\] A pointer to the column name.  The name must be a Unicode string.  You can accomplish this by putting an 'L' in front of the name, for example: `L"MyColumn"`.  
  
 *IID*  
 \[in\] Interface GUID, such as **IDD\_ISequentialStream**, used to retrieve the BLOB.  
  
 `flags`  
 \[in\] Storage\-mode flags as defined by the OLE Structured Storage model \(for example, **STGM\_READ**\).  
  
 `data`  
 \[in\] The corresponding data member in the user record.  
  
 *length*  
 \[out\] The \(actual\) length in bytes of the BLOB column.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME](../../data/oledb/blob-name.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../../data/oledb/blob-name-status.md)