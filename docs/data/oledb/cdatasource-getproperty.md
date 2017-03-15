---
title: "CDataSource::GetProperty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::GetProperty"
  - "ATL.CDataSource.GetProperty"
  - "CDataSource.GetProperty"
  - "CDataSource::GetProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperty 메서드"
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataSource::GetProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the value of a specified property for the connected data source object.  
  
## 구문  
  
```  
  
      HRESULT GetProperty(   
   const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant    
) const throw( );  
```  
  
#### 매개 변수  
 `guid`  
 \[in\] A GUID identifying the property set for which to return the property.  
  
 `propid`  
 \[in\] Property ID for the property to return.  
  
 *pVariant*  
 \[out\] A pointer to the variant where **GetProperty** returns the value of the property.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 To get multiple properties, use [GetProperties](../../data/oledb/cdatasource-getproperties.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)