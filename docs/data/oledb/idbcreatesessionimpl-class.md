---
title: "IDBCreateSessionImpl 클래스 | Microsoft Docs"
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
  - "IDBCreateSessionImpl"
  - "ATL.IDBCreateSessionImpl"
  - "ATL::IDBCreateSessionImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBCreateSessionImpl 클래스"
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBCreateSessionImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation for the [IDBCreateSession](https://msdn.microsoft.com/en-us/library/ms724076.aspx) interface.  
  
## 구문  
  
```  
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
#### 매개 변수  
 `T`  
 YOUR CLASS, DERIVED FROM  
  
 `SessionClass`  
 세션 개체입니다.  
  
## 멤버  
  
### Interface Methods  
  
|||  
|-|-|  
|[CreateSession](../../data/oledb/idbcreatesessionimpl-createsession.md)|Creates a new session from the data source object and returns the requested interface on the newly created session.|  
  
## 설명  
 A mandatory interface on data source objects.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)