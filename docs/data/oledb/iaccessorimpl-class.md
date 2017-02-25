---
title: "IAccessorImpl 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IAccessorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAccessorImpl 클래스"
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IAccessorImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation of the [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) interface.  
  
## 구문  
  
```  
template <  
   class T,   
   class BindType = ATLBINDINGS,   
   class BindingVector = CAtlMap <   
      HACCESSOR hAccessor,   
      BindType* pBindingsStructure   
   >   
>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### 매개 변수  
 `T`  
 Your rowset or command object class.  
  
 `BindType`  
 Storage unit for binding information.  The default is the **ATLBINDINGS** structure \(see atldb.h\).  
  
 `BindingVector`  
 Storage unit for column information.  The default is [CAtlMap](../../atl/reference/catlmap-class.md) where the key element is an **HACCESSOR** value and the value element is a pointer to a `BindType` structure.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|생성자입니다.|  
  
### Interface Methods  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|기존 접근자에 참조 횟수를 추가합니다.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|바인딩 집합에서 접근자를 만듭니다.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|접근자에 있는 바인딩을 반환합니다.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|접근자를 해제합니다.|  
  
## 설명  
 This is mandatory on rowsets and commands.  OLE DB requires providers to implement an **HACCESSOR**, which is a tag to an array of [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) structures.  **HACCESSOR**s provided by `IAccessorImpl` are addresses of the `BindType` structures.  By default, `BindType` is defined as an **ATLBINDINGS** in `IAccessorImpl`'s template definition.  `BindType` provides a mechanism used by `IAccessorImpl` to track the number of elements in its **DBBINDING** array as well as a reference count and accessor flags.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)