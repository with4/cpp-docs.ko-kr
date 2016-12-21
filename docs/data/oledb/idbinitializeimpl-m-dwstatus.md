---
title: "IDBInitializeImpl::m_dwStatus | Microsoft Docs"
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
  - "ATL::IDBInitializeImpl::m_dwStatus"
  - "IDBInitializeImpl.m_dwStatus"
  - "ATL.IDBInitializeImpl.m_dwStatus"
  - "IDBInitializeImpl::m_dwStatus"
  - "IDBInitializeImpl<T>::m_dwStatus"
  - "ATL.IDBInitializeImpl<T>.m_dwStatus"
  - "ATL::IDBInitializeImpl<T>::m_dwStatus"
  - "m_dwStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_dwStatus"
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBInitializeImpl::m_dwStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Data source flags.  
  
## 구문  
  
```  
  
DWORD m_dwStatus;  
  
```  
  
## 설명  
 These flags specify or indicate the status of various attributes for the data source object.  Contains one or more of the following `enum` values:  
  
 `enum DATASOURCE_FLAGS {`  
  
 `DSF_MASK_INIT     = 0xFFFFF00F,`  
  
 `DSF_PERSIST_DIRTY = 0x00000001,`  
  
 `DSF_INITIALIZED   = 0x00000010,`  
  
 `};`  
  
|||  
|-|-|  
|**DSF\_MASK\_INIT**|A mask to enable restoration of the uninitialized state.|  
|**DSF\_PERSIST\_DIRTY**|Set if data source object requires persistence \(that is, if there have been changes\).|  
|**DSF\_INITIALIZED**|Set if data source has been initialized.|  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IDBInitializeImpl 클래스](../../data/oledb/idbinitializeimpl-class.md)   
 [IDBInitializeImpl::IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)   
 [IDBInitializeImpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)