---
title: "CAccessorBase::ReleaseAccessors | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAccessorBase::ReleaseAccessors"
  - "CAccessorBase.ReleaseAccessors"
  - "ReleaseAccessors"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAccessors 메서드"
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorBase::ReleaseAccessors
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Releases the accessors created by the class.  
  
## 구문  
  
```  
  
      HRESULT ReleaseAccessors(  
   IUnknown* pUnk   
);  
```  
  
#### 매개 변수  
 *pUnk*  
 \[in\] A pointer to an **IUnknown** interface for the COM object for which the accessors have been created.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 Called from [CAccessorRowset::Close](../../data/oledb/caccessorrowset-close.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CAccessorBase 클래스](../../data/oledb/caccessorbase-class.md)