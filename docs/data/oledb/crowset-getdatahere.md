---
title: "CRowset::GetDataHere | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>::GetDataHere"
  - "CRowset<TAccessor>.GetDataHere"
  - "CRowset.GetDataHere"
  - "GetDataHere"
  - "CRowset::GetDataHere"
  - "ATL::CRowset::GetDataHere"
  - "ATL::CRowset<TAccessor>::GetDataHere"
  - "ATL.CRowset<TAccessor>.GetDataHere"
  - "ATL.CRowset.GetDataHere"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDataHere 메서드"
ms.assetid: 2fe2a987-1c4c-4299-876e-0591caf63af4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::GetDataHere
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves data from the current row and places it into the specified buffer.  
  
## 구문  
  
```  
  
      HRESULT GetDataHere(   
   int nAccessor,   
   void* pBuffer    
) throw( );  
```  
  
#### 매개 변수  
 `nAccessor`  
 \[in\] The index number of the accessor to use for accessing the data.  
  
 `pBuffer`  
 \[out\] A buffer into which to place the data for the current record.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 For an example of how to use this function, see the [MultiRead sample](../../top/visual-cpp-samples.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)   
 [CRowset::GetData](../../data/oledb/crowset-getdata.md)