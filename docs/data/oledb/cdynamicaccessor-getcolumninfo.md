---
title: "CDynamicAccessor::GetColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetColumnInfo"
  - "ATL.CDynamicAccessor.GetColumnInfo"
  - "ATL::CDynamicAccessor::GetColumnInfo"
  - "CDynamicAccessor.GetColumnInfo"
  - "CDynamicAccessor::GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo 메서드"
ms.assetid: 7f2102ea-b7cc-4714-812f-3ca2857f4b9a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

대부분의 소비자에 필요한 열 메타데이터를 반환합니다.  
  
## 구문  
  
```  
  
      HRESULT GetColumnInfo(   
   IRowset* pRowset,   
   DBORDINAL* pColumns,   
   DBCOLUMNINFO** ppColumnInfo,   
   OLECHAR** ppStringsBuffer    
) throw( );  
```  
  
#### 매개 변수  
 `pRowset`  
 \[in\] A pointer to the [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) interface.  
  
 *pColumns*  
 \[out\] A pointer to memory in which to return the number of columns in the rowset; this number includes the bookmark column, if there is one.  
  
 *ppColumnInfo*  
 \[out\] A pointer to memory in which to return an array of **DBCOLUMNINFO** structures.  See "DBCOLUMNINFO Structures" in [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in the *OLE DB Programmer's Reference*.  
  
 `ppStringsBuffer`  
 \[out\] A pointer to memory in which to return a pointer to storage for all string values \(names used either within *columnid* or for *pwszName*\) within a single allocation block.  
  
## 반환 값  
 One of the standard `HRESULT` values.  
  
## 설명  
 See [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in the *OLE DB Programmer's Reference* for information on the data types **DBORDINAL**, **DBCOLUMNINFO**, and **OLECHAR**.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)