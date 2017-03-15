---
title: "CBulkRowset::MoveToRatio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBulkRowset.MoveToRatio"
  - "ATL::CBulkRowset::MoveToRatio"
  - "MoveToRatio"
  - "CBulkRowset::MoveToRatio"
  - "ATL.CBulkRowset<TAccessor>.MoveToRatio"
  - "ATL::CBulkRowset<TAccessor>::MoveToRatio"
  - "ATL.CBulkRowset.MoveToRatio"
  - "CBulkRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio 메서드"
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CBulkRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fetches rows starting from a fractional position in the rowset.  
  
## 구문  
  
```  
  
      HRESULT MoveToRatio(  
   DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator   
) throw( );  
```  
  
#### 매개 변수  
 `nNumerator`  
 \[in\] The numerator used to determine the fractional position from which to fetch data.  
  
 `nDenominator`  
 \[in\] The denominator used to determine the fractional position from which to fetch data.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 `MoveToRatio` fetches the rows roughly according to the following formula:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 Where `RowsetSize` is the size of the rowset, measured in rows.  The accuracy of this formula depends on the specific provider.  For details, see [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CBulkRowset 클래스](../../data/oledb/cbulkrowset-class.md)