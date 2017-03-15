---
title: "IDBCreateCommandImpl::CreateCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBCreateCommandImpl.CreateCommand"
  - "CreateCommand"
  - "IDBCreateCommandImpl::CreateCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateCommand 메서드"
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IDBCreateCommandImpl::CreateCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Creates a new command and returns the requested interface.  
  
## 구문  
  
```  
  
      STDMETHOD(CreateCommand)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand    
);  
```  
  
#### 매개 변수  
 See [IDBCreateCommand::CreateCommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx) in the *OLE DB Programmer's Reference*.  
  
 Some parameters correspond to *OLE DB Programmer's Reference* parameters of different names, which are described in **IDBCreateCommand::CreateCommand**:  
  
|OLE DB Template parameters|*OLE DB Programmer's Reference* parameters|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IDBCreateCommandImpl 클래스](../../data/oledb/idbcreatecommandimpl-class.md)