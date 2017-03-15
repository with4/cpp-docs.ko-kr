---
title: "CDBPropSet 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropSet"
  - "ATL.CDBPropSet"
  - "ATL::CDBPropSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropSet 클래스"
ms.assetid: 54190149-c277-4679-b81a-ef484d4d1c00
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CDBPropSet 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inherits from the **DBPROPSET** structure and adds a constructor that initializes key fields as well as the `AddProperty` access method.  
  
## 구문  
  
```  
class CDBPropSet : public tagDBPROPSET  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[AddProperty](../../data/oledb/cdbpropset-addproperty.md)|Adds a property to the property set.|  
|[CDBPropSet](../../data/oledb/cdbpropset-cdbpropset.md)|생성자입니다.|  
|[SetGUID](../../data/oledb/cdbpropset-setguid.md)|Sets the **guidPropertySet** field of the **DBPROPSET** structure.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../../data/oledb/cdbpropset-operator-equal.md)|Assigns the contents of one property set to another.|  
  
## 설명  
 OLE DB providers and consumers use **DBPROPSET** structures to pass arrays of `DBPROP` structures.  Each `DBPROP` structure represents a single property that can be set.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CDBPropIDSet 클래스](../../data/oledb/cdbpropidset-class.md)   
 [DBPROPSET Structure](https://msdn.microsoft.com/en-us/library/ms714367.aspx)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)