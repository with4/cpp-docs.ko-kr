---
title: "CSimpleRow::AddRefRow | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSimpleRow::AddRefRow"
  - "AddRefRow"
  - "ATL.CSimpleRow.AddRefRow"
  - "ATL::CSimpleRow::AddRefRow"
  - "CSimpleRow.AddRefRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefRow 메서드"
ms.assetid: 9bb5b7a5-79f2-4de5-852c-e9918fe67665
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CSimpleRow::AddRefRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Adds a reference count to an existing row handle in a thread\-safe manner.  
  
## 구문  
  
```  
  
DWORD AddRefRow( );  
  
```  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CSimpleRow 클래스](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)