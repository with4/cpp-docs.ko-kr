---
title: "CDataSource::GetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::GetProperties"
  - "ATL.CDataSource.GetProperties"
  - "CDataSource.GetProperties"
  - "ATL::CDataSource::GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties 메서드"
ms.assetid: ffaecc17-9fe7-449e-94d6-43d31ad06cfc
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the property information requested for the connected data source object.  
  
## 구문  
  
```  
  
      HRESULT GetProperties(   
   ULONG ulPropIDSets,   
   const DBPROPIDSET* pPropIDSet,   
   ULONG* pulPropertySets,   
   DBPROPSET** ppPropsets    
) const throw( );  
```  
  
#### 매개 변수  
 See [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) in the *OLE DB Programmer's Reference* in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 To get a single property, use [GetProperty](../../data/oledb/cdatasource-getproperty.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)