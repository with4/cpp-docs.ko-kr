---
title: "CRowsetImpl::NameFromDBID | Microsoft Docs"
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
  - "CRowsetImpl.NameFromDBID"
  - "CRowsetImpl::NameFromDBID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NameFromDBID 메서드"
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::NameFromDBID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extracts a string from a **DBID** and copies it to the `bstr` passed in.  
  
## 구문  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### 매개 변수  
 *pDBID*  
 \[in\] A pointer to the **DBID** from which to extract a string.  
  
 `bstr`  
 \[in\] A [CComBSTR](../../atl/reference/ccombstr-class.md) reference to place a copy of the **DBID** string.  
  
 `bIndex`  
 \[in\] **true** if an index **DBID**; **false** if a table **DBID**.  
  
## 반환 값  
 A standard `HRESULT`.  Depending on whether the **DBID** is a table or an index \(denoted by `bIndex`\), the method will either return **DB\_E\_NOINDEX** or **DB\_E\_NOTABLE**.  
  
## 설명  
 This method is called by the `CRowsetImpl` implementations of [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) and [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [CRowsetImpl 클래스](../../data/oledb/crowsetimpl-class.md)