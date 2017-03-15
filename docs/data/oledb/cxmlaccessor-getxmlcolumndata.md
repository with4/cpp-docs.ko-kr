---
title: "CXMLAccessor::GetXMLColumnData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CXMLAccessor.GetXMLColumnData"
  - "CXMLAccessor::GetXMLColumnData"
  - "CXMLAccessor.GetXMLColumnData"
  - "ATL::CXMLAccessor::GetXMLColumnData"
  - "GetXMLColumnData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetXMLColumnData 메서드"
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CXMLAccessor::GetXMLColumnData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the column type information of a table as XML\-formatted string data, by column.  
  
## 구문  
  
```  
  
      HRESULT GetXMLColumnData(   
   CSimpleStringW& strOutput    
) throw( );  
```  
  
#### 매개 변수  
 `strOutput`  
 \[out\] A reference to a string buffer containing the column type information to be retrieved.  The string is formatted with XML tag names that match the data store's column names.  
  
## 반환 값  
 One of the standard `HRESULT` values.  
  
## 설명  
 The following shows how the column type information is formatted in XML.  `type` specifies the column's data type.  Note that the data types are based on OLE DB data types, not those of the database being accessed.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CXMLAccessor 클래스](../../data/oledb/cxmlaccessor-class.md)