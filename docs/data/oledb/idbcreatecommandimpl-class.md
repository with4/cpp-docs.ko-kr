---
title: "IDBCreateCommandImpl 클래스 | Microsoft Docs"
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
  - "ATL::IDBCreateCommandImpl"
  - "IDBCreateCommandImpl"
  - "ATL.IDBCreateCommandImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBCreateCommandImpl 클래스"
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBCreateCommandImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation of the [IDBCreateCommand](https://msdn.microsoft.com/en-us/library/ms711625.aspx) interface.  
  
## 구문  
  
```  
template <class T, class CommandClass >  
class ATL_NO_VTABLE IDBCreateCommandImpl   
   : public IDBCreateCommand  
```  
  
#### 매개 변수  
 `T`  
 The session object derived from `IDBCreateCommandImpl`.  
  
 `CommandClass`  
 Your command class.  
  
## 멤버  
  
### Interface Methods  
  
|||  
|-|-|  
|[CreateCommand](../../data/oledb/idbcreatecommandimpl-createcommand.md)|Creates a new command.|  
  
## 설명  
 An optional interface on the session object to obtain a new command.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)