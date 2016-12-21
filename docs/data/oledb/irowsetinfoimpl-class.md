---
title: "IRowsetInfoImpl 클래스 | Microsoft Docs"
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
  - "ATL.IRowsetInfoImpl"
  - "IRowsetInfoImpl"
  - "ATL::IRowsetInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetInfoImpl 클래스"
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetInfoImpl 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Provides an implementation for the [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) interface.  
  
## 구문  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### 매개 변수  
 `T`  
 Your class, derived from `IRowsetInfoImpl`.  
  
 `PropClass`  
 A user\-definable property class that defaults to `T`.  
  
## 멤버  
  
### Interface Methods  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)|행 집합에서 지원하는 모든 속성의 현재 설정을 반환합니다.|  
|[GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|Returns an interface pointer to the rowset to which a bookmark applies.|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|이 행 집합을 만든 개체\(명령 또는 세션\)의 인터페이스 포인터를 반환합니다.|  
  
## 설명  
 A mandatory interface on rowsets.  This class implements the rowset properties by using the [property set map](../../data/oledb/begin-propset-map.md) defined in your command class.  Although the rowset class appears to be using the command class' property sets, the rowset is supplied with its own copy of the run\-time properties, when it is created by a command or session object.  
  
## 요구 사항  
 **Header:** altdb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)