---
title: "IRowsetImpl::m_rgRowHandles | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl::m_rgRowHandles"
  - "IRowsetImpl.m_rgRowHandles"
  - "m_rgRowHandles"
  - "ATL::IRowsetImpl::m_rgRowHandles"
  - "ATL.IRowsetImpl.m_rgRowHandles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_rgRowHandles"
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::m_rgRowHandles
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

A map of row handles currently contained by the provider in response to `GetNextRows`.  
  
## 구문  
  
```  
  
MapClass  
 m_rgRowHandles;  
  
```  
  
## 설명  
 Row handles are removed by calling `ReleaseRows`.  See the [IRowsetImpl overview](../../data/oledb/irowsetimpl-class.md) for the definition of *MapClass*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetImpl 클래스](../../data/oledb/irowsetimpl-class.md)