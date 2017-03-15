---
title: "IRowsetInfoImpl::GetSpecification | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetInfoImpl::GetSpecification"
  - "ATL.IRowsetInfoImpl.GetSpecification"
  - "IRowsetInfoImpl.GetSpecification"
  - "GetSpecification"
  - "ATL::IRowsetInfoImpl::GetSpecification"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSpecification 메서드"
ms.assetid: 8e14289d-9cca-4df7-a9e0-f4ef03c61e30
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetInfoImpl::GetSpecification
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 행 집합을 만든 개체\(명령 또는 세션\)의 인터페이스 포인터를 반환합니다.  
  
## 구문  
  
```  
  
      STDMETHOD ( GetSpecification )(  
   REFIID riid,  
   IUnknown** ppSpecification   
);  
```  
  
#### 매개 변수  
 See [IRowsetInfo::GetSpecification](https://msdn.microsoft.com/en-us/library/ms716746.aspx) in the *OLE DB Programmer's Reference*.  
  
## 설명  
 Use this method with [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md) to retrieve properties from the data source object.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetInfoImpl 클래스](../../data/oledb/irowsetinfoimpl-class.md)   
 [IRowsetInfoImpl::GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [IRowsetInfoImpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)