---
title: "IRowsetCreatorImpl 클래스 | Microsoft Docs"
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
  - "ATL::IRowsetCreatorImpl"
  - "ATL.IRowsetCreatorImpl"
  - "ATL::IRowsetCreatorImpl<T>"
  - "ATL.IRowsetCreatorImpl<T>"
  - "IRowsetCreatorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetCreatorImpl 클래스"
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetCreatorImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Performs the same functions as `IObjectWithSite` but also enables the OLE DB properties **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## 구문  
  
```  
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### 매개 변수  
 `T`  
 A class derived from **IRowsetCreator**.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|Sets the site that contains the rowset object.|  
  
## 설명  
 This class inherits from [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) and overrides [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  When a provider command or session object creates a rowset, it calls `QueryInterface` on the rowset object looking for `IObjectWithSite` and calls `SetSite` passing the rowset object's **IUnkown** interface as the site interface.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)