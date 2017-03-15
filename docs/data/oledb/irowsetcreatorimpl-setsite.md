---
title: "IRowsetCreatorImpl::SetSite | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetCreatorImpl.SetSite"
  - "IRowsetCreatorImpl<T>::SetSite"
  - "IRowsetCreatorImpl::SetSite"
  - "SetSite"
  - "ATL.IRowsetCreatorImpl.SetSite"
  - "ATL::IRowsetCreatorImpl<T>::SetSite"
  - "ATL::IRowsetCreatorImpl::SetSite"
  - "ATL.IRowsetCreatorImpl<T>.SetSite"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetSite 메서드"
ms.assetid: e92e63d5-93e4-4ee0-9ef7-bb6583cc8091
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetCreatorImpl::SetSite
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the site that contains the rowset object.  For more information, see [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  
  
## 구문  
  
```  
  
      STDMETHOD( SetSite )(  
   IUnknown* pCreator   
);  
```  
  
#### 매개 변수  
 `pCreator`  
 \[in\] Pointer to the **IUnknown** interface pointer of the site managing the rowset object.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 In addition, `IRowsetCreatorImpl::SetSite` enables the OLE DB **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS** properties.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetCreatorImpl 클래스](../../data/oledb/irowsetcreatorimpl-class.md)