---
title: "CRowsetImpl::ValidateCommandID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.ValidateCommandID"
  - "CRowsetImpl::ValidateCommandID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ValidateCommandID 메서드"
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::ValidateCommandID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Checks to see if either or both **DBID**s contain string values, and if so, copies them to its data members [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) and [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## 구문  
  
```  
  
      HRESULT CRowsetBaseImpl::ValidateCommandID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### 매개 변수  
 `pTableID`  
 \[in\] A pointer to the **DBID** representing the table ID.  
  
 `pIndexID`  
 \[in\] A pointer to the **DBID** representing the index ID.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method is called through a static upcast by `CRowsetImpl` to populate its data members [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) and [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  By default, this method checks to see if either or both **DBID**s contain string values, and if so, copies them to its data members.  By placing a method with this signature in your `CRowsetImpl`\-derived class, your method will be called instead of the base implementation.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)