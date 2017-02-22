---
title: "CEnumeratorAccessor 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CEnumeratorAccessor"
  - "CEnumeratorAccessor"
  - "ATL.CEnumeratorAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumeratorAccessor 클래스"
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CEnumeratorAccessor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Used by [CEnumerator](../../data/oledb/cenumerator-class.md) to access the data from the enumerator rowset.  
  
## 구문  
  
```  
class CEnumeratorAccessor  
```  
  
## 멤버  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|A variable indicating whether the enumerator is a parent enumerator, if the row is an enumerator.|  
|[m\_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|A variable indicating whether the row describes a data source or an enumerator.|  
|[m\_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|The description of the data source or enumerator.|  
|[m\_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|The name of the data source or enumerator.|  
|[m\_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|String to pass to [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) to obtain a moniker for the data source or enumerator.|  
  
## 설명  
 This rowset consists of the data sources and enumerators visible from the current enumerator.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)