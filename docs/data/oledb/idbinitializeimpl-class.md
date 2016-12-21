---
title: "IDBInitializeImpl 클래스 | Microsoft Docs"
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
  - "ATL.IDBInitializeImpl<T>"
  - "ATL::IDBInitializeImpl<T>"
  - "IDBInitializeImpl"
  - "ATL::IDBInitializeImpl"
  - "ATL.IDBInitializeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDBInitializeImpl 클래스"
ms.assetid: e4182f81-0443-44f5-a0d3-e7e075d6f883
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBInitializeImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation for the [IDBInitialize](https://msdn.microsoft.com/en-us/library/ms713706.aspx) interface.  
  
## 구문  
  
```  
template <class T>  
class ATL_NO_VTABLE IDBInitializeImpl : public IDBInitialize  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from `IDBInitializeImpl`.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)|생성자입니다.|  
  
### Interface Methods  
  
|||  
|-|-|  
|[초기화](../../data/oledb/idbinitializeimpl-initialize.md)|Starts the provider.|  
|[Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)|Stops the provider.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_dwStatus](../../data/oledb/idbinitializeimpl-m-dwstatus.md)|Data source flags.|  
|[m\_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md)|A pointer to implementation of DB Properties information.|  
  
## 설명  
 A mandatory interface on data source objects and optional interface on enumerators.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)