---
title: "CRowset::GetOriginalData | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.GetOriginalData"
  - "CRowset<TAccessor>::GetOriginalData"
  - "GetOriginalData"
  - "ATL::CRowset<TAccessor>::GetOriginalData"
  - "ATL.CRowset.GetOriginalData"
  - "CRowset::GetOriginalData"
  - "ATL::CRowset::GetOriginalData"
  - "CRowset.GetOriginalData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOriginalData 메서드"
ms.assetid: 5b69d30e-34f4-41a4-a82d-cd175be88d53
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::GetOriginalData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calls **IRowsetUpdate::GetOriginalData** to retrieve the data most recently fetched from or transmitted to the data source.  
  
## 구문  
  
```  
  
HRESULT GetOriginalData( ) throw( );  
  
```  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method retrieves the data most recently fetched from or transmitted to the data source; it does not retrieve values based on pending changes.  
  
 This method requires the optional interface `IRowsetUpdate`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetUpdate** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/en-us/library/ms709947.aspx)