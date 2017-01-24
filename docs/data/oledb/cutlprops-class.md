---
title: "CUtlProps 클래스 | Microsoft Docs"
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
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUtlProps 클래스"
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implements properties for a variety of OLE DB property interfaces \(for example, `IDBProperties`, `IDBProperties`, and `IRowsetInfo`\).  
  
## 구문  
  
```  
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### 매개 변수  
 `T`  
 The class that contains the `BEGIN_PROPSET_MAP`.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|Gets a property from a property set.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Used to validate a value before setting a property.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Handles requests for an optional interface when a consumer calls a method on an object creation interface.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Called after setting a property to handle chained properties.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Sets a property in a property set.|  
  
## 설명  
 Most of this class is an implementation detail.  
  
 `CUtlProps` contains two members for setting properties internally: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) and [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 For more information on the macros used in a property set map, see [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md) and [END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [OLE DB 공급자 템플릿](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB 공급자 템플릿 구조](../../data/oledb/ole-db-provider-template-architecture.md)