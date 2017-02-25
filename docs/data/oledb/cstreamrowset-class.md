---
title: "CStreamRowset 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CStreamRowset<TAccessor>"
  - "ATL::CStreamRowset"
  - "CStreamRowset"
  - "ATL.CStreamRowset<TAccessor>"
  - "ATL.CStreamRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStreamRowset 클래스"
ms.assetid: a106e953-a38a-464e-8ea5-28963d9e4811
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# CStreamRowset 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Used in a `CCommand` or `CTable` declaration.  
  
## 구문  
  
```  
template <class TAccessor = CAccessorBase>  
class CStreamRowset  
```  
  
#### 매개 변수  
 `TAccessor`  
 An accessor class.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[CStreamRowset](../../data/oledb/cstreamrowset-cstreamrowset.md)|생성자입니다.  Instantiates and initializes the `CStreamRowset` object.|  
|[닫기](../../data/oledb/cstreamrowset-close.md)|Releases the [ISequentialStream](https://msdn.microsoft.com/en-us/library/ms718035.aspx) interface pointer in the class.|  
  
## 설명  
 Use `CStreamRowset` in your `CCommand` or `CTable` declaration, for example:  
  
 [!code-cpp[NVC_OLEDB_Consumer#11](../../data/oledb/codesnippet/CPP/cstreamrowset-class_1.cpp)]  
  
 또는  
  
 [!code-cpp[NVC_OLEDB_Consumer#12](../../data/oledb/codesnippet/CPP/cstreamrowset-class_2.cpp)]  
  
 `ICommand::Execute` returns an `ISequentialStream` pointer, which is stored in `m_spStream`.  You then use the **Read** method to retrieve the \(Unicode string\) data in XML format.  예를 들면 다음과 같습니다.  
  
 [!code-cpp[NVC_OLEDB_Consumer#13](../../data/oledb/codesnippet/CPP/cstreamrowset-class_3.cpp)]  
  
 SQL Server 2000 performs the XML formatting, and will return all columns and all rows of the rowset as one XML string.  
  
> [!NOTE]
>  This feature works with SQL Server 2000 only.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)