---
title: "IRowsetUpdateImpl::GetOriginalData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetUpdateImpl.GetOriginalData"
  - "IRowsetUpdateImpl.GetOriginalData"
  - "GetOriginalData"
  - "ATL::IRowsetUpdateImpl::GetOriginalData"
  - "IRowsetUpdateImpl::GetOriginalData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOriginalData 메서드"
ms.assetid: 7477b3b7-6b1b-49a7-8167-b34323f0fdcc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::GetOriginalData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gets the data most recently transmitted to or obtained from the data source, ignoring pending changes.  
  
## 구문  
  
```  
  
      STDMETHOD ( GetOriginalData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pData   
);  
```  
  
#### 매개 변수  
 See [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/en-us/library/ms709947.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IRowsetUpdateImpl 클래스](../../data/oledb/irowsetupdateimpl-class.md)