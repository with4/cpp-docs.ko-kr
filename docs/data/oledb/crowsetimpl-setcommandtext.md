---
title: "CRowsetImpl::SetCommandText | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.SetCommandText"
  - "CRowsetImpl::SetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommandText 메서드"
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::SetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Validates and stores the **DBID**s in the two strings \([m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) and [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\).  
  
## 구문  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
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
 The **SetCommentText** method is called by `CreateRowset`, a static templatized method of `IOpenRowsetImpl`.  
  
 This method delegates its work by calling [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) and [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) through an upcasted pointer.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)