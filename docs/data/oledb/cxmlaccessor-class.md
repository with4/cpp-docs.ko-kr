---
title: "CXMLAccessor 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CXMLAccessor"
  - "CXMLAccessor"
  - "ATL.CXMLAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CXMLAccessor 클래스"
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CXMLAccessor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Allows you to access data sources as string data when you have no knowledge of the data store's schema \(underlying structure\).  
  
## 구문  
  
```  
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md)|Retrieves the column information.|  
|[GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md)|Retrieves the entire contents of a table by rows.|  
  
## 설명  
 However, `CXMLAccessor` differs from `CDynamicStringAccessorW` in that it converts all data accessed from the data store as XML\-formatted \(tagged\) data.  This is especially useful for output to XML\-aware Web pages.  The XML tag names will match the data store's column names as closely as possible.  
  
 `CDynamicAccessor` 메서드를 사용하여 열 정보를 구하십시오.  사용자는 이 열 정보를 사용하여 런타임에 동적으로 접근자를 만듭니다.  
  
 열 정보는 이 클래스에서 만들고 관리하는 버퍼에 저장됩니다.  Obtain column information using [GetXMLColumnData](../../data/oledb/cxmlaccessor-getxmlcolumndata.md) or obtain column data by rows using [GetXMLRowData](../../data/oledb/cxmlaccessor-getxmlrowdata.md).  
  
## 예제  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/CPP/cxmlaccessor-class_1.cpp)]  
  
## 요구 사항  
 **Header**: atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CDynamicStringAccessor 클래스](../../data/oledb/cdynamicstringaccessor-class.md)   
 [CDynamicStringAccessorA 클래스](../../data/oledb/cdynamicstringaccessora-class.md)   
 [CDynamicStringAccessorW 클래스](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)