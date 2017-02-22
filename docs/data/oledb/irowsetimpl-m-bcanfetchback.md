---
title: "IRowsetImpl::m_bCanFetchBack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.m_bCanFetchBack"
  - "ATL::IRowsetImpl::m_bCanFetchBack"
  - "IRowsetImpl.m_bCanFetchBack"
  - "IRowsetImpl::m_bCanFetchBack"
  - "m_bCanFetchBack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bCanFetchBack"
ms.assetid: cfa007b0-7ba5-48a3-9d05-9f1916305fb7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::m_bCanFetchBack
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indicates whether a provider supports backward fetching.  
  
## 구문  
  
```  
  
unsigned m_bCanFetchBack:1;  
  
```  
  
## 설명  
 Linked to the **DBPROP\_CANFETCHBACKWARDS** property in the **DBPROPSET\_ROWSET** group.  The provider must support **DBPROP\_CANFETCHBACKWARDS** for **m\_bCanFetchBackwards** to be true.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m\_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)