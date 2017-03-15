---
title: "CRowset::SetData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset<TAccessor>.SetData"
  - "SetData"
  - "ATL::CRowset::SetData"
  - "CRowset<TAccessor>.SetData"
  - "CRowset::SetData"
  - "ATL.CRowset.SetData"
  - "CRowset.SetData"
  - "CRowset<TAccessor>::SetData"
  - "ATL::CRowset<TAccessor>::SetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetData 메서드"
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::SetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets data values in one or more columns of a row.  
  
## 구문  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### 매개 변수  
 `nAccessor`  
 \[in\] The number of the accessor to use for accessing the data.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 For the `SetData` form that accepts no arguments, all accessors are used for updating.  You typically call **SetData** to set data values in columns in a row, then call [Update](../../data/oledb/crowset-update.md) to transmit those changes.  
  
 This method requires the optional interface `IRowsetChange`, which might not be supported on all providers; if this is the case, the method returns **E\_NOINTERFACE**.  You must also set **DBPROP\_IRowsetChange** to `VARIANT_TRUE` before calling **Open** on the table or command containing the rowset.  
  
 The setting operation might fail if one or more columns is not writable.  이를 방지하려면 커서 맵을 수정하십시오.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [CRowset::Update](../../data/oledb/crowset-update.md)