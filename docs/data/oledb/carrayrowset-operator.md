---
title: "CArrayRowset::operator | Microsoft Docs"
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
  - "CArrayRowset::operator[]"
  - "CArrayRowset.operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연산자 [], 배열"
  - "[] 연산자"
  - "operator[], 배열"
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArrayRowset::operator
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides array\-like syntax for accessing a row in the rowset.  
  
## 구문  
  
```  
  
      TAccessor  
      & operator[](int nRow);  
```  
  
#### 매개 변수  
 `TAccessor`  
 A templated parameter that specifies the type of accessor stored in the rowset.  
  
 `nRow`  
 \[in\] Number of the row \(array element\) you want to access.  
  
## 반환 값  
 The contents of the requested row.  
  
## 설명  
 If `nRow` exceeds the number of rows in the rowset, an exception is thrown.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CArrayRowset 클래스](../../data/oledb/carrayrowset-class.md)