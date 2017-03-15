---
title: "IOpenRowsetImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOpenRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOpenRowsetImpl 클래스"
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# IOpenRowsetImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides implementation for the `IOpenRowset` interface.  
  
## 구문  
  
```  
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### 매개 변수  
 `SessionClass`  
 Your class, derived from `IOpenRowsetImpl`.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Creates a rowset object.  Not called directly by user.|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|Opens and returns a rowset that includes all rows from a single base table or index. \(Not in ATLDB.H\)|  
  
## 설명  
 The [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) interface is mandatory for a session object.  It opens and returns a rowset that includes all rows from a single base table or index.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)