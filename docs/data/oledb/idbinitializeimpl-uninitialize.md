---
title: "IDBInitializeImpl::Uninitialize | Microsoft Docs"
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
  - "IDBInitializeImpl.Uninitialize"
  - "Uninitialize"
  - "IDBInitializeImpl::Uninitialize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Uninitialize 메서드"
ms.assetid: ba37fc74-f84e-40b0-abb6-41bddd505269
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBInitializeImpl::Uninitialize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Places the data source object in an uninitialized state by freeing internal resources such as the property support.  
  
## 구문  
  
```  
  
      STDMETHOD(Uninitialize)(   
   void    
);  
```  
  
## 설명  
 See [IDBInitialize::Uninitialize](https://msdn.microsoft.com/en-us/library/ms719648.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IDBInitializeImpl 클래스](../../data/oledb/idbinitializeimpl-class.md)   
 [IDBInitializeImpl::Initialize](../../data/oledb/idbinitializeimpl-initialize.md)