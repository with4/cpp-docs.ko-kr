---
title: "CDBPropIDSet 클래스 | Microsoft Docs"
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
  - "CDBPropIDSet"
  - "ATL.CDBPropIDSet"
  - "ATL::CDBPropIDSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropIDSet 클래스"
ms.assetid: 52bb806c-9581-494d-9af7-50d8a4834805
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropIDSet 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Inherits from the **DBPROPIDSET** structure and adds a constructor that initializes key fields as well as the [AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md) access method.  
  
## 구문  
  
```  
class CDBPropIDSet : public tagDBPROPIDSET  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[AddPropertyID](../../data/oledb/cdbpropidset-addpropertyid.md)|Adds a property to the property ID set.|  
|[CDBPropIDSet](../../data/oledb/cdbpropidset-cdbpropidset.md)|생성자입니다.|  
|[SetGUID](../../data/oledb/cdbpropidset-setguid.md)|Sets the GUID of the property ID set.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../../data/oledb/cdbpropidset-operator-equal.md)|Assigns the contents of one property ID set to another.|  
  
## 설명  
 OLE DB consumers use **DBPROPIDSET** structures to pass an array of property IDs for which the consumer wants to get property information.  The properties identified in a single [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx) structure belong to one property set.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)