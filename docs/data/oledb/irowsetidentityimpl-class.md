---
title: "IRowsetIdentityImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetIdentityImpl"
  - "ATL.IRowsetIdentityImpl"
  - "IRowsetIdentityImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetIdentityImpl 클래스"
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IRowsetIdentityImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implements the OLE DB [IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx) interface, which enables testing for row identity.  
  
## 구문  
  
```  
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
#### 매개 변수  
 `T`  
 A class derived from `IRowsetIdentityImpl`.  
  
 `RowClass`  
 The storage unit for the **HROW**.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[IsSameRow](../../data/oledb/irowsetidentityimpl-issamerow.md)|Compares two row handles to see if they refer to the same row.|  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)