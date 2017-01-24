---
title: "CRowsetImpl::GetCommandFromID | Microsoft Docs"
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
  - "CRowsetImpl::GetCommandFromID"
  - "GetCommandFromID"
  - "CRowsetImpl.GetCommandFromID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandFromID 메서드"
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::GetCommandFromID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Checks to see if either or both parameters contain string values, and if so, copies the string values to the data members [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) and [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## 구문  
  
```  
  
      HRESULT CRowsetBaseImpl::GetCommandFromID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### 매개 변수  
 `pTableID`  
 \[in\] A pointer to the **DBID** representing the Table ID.  
  
 `pIndexID`  
 \[in\] A pointer to the **DBID** representing the Index ID.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method is called through a static upcast by `CRowsetImpl` to populate the data members [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) and [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  By default, this method checks to see if either or both parameters contain string values.  If they contain string values, this method copies the string values to the data members.  By placing a method with this signature in your `CRowsetImpl`\-derived class, your method will be called instead of the base implementation.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)