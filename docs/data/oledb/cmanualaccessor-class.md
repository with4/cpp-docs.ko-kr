---
title: "CManualAccessor 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor"
  - "ATL.CManualAccessor"
  - "CManualAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CManualAccessor 클래스"
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CManualAccessor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents an accessor type designed for advanced use.  
  
## 구문  
  
```  
class CManualAccessor : public CAccessorBase  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|Adds a bind entry to the output columns.|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|Adds a parameter entry to the parameter accessor.|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|Allocates memory for the column bind structures and initializes the column data members.|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Allocates memory for the parameter bind structures and initializes the parameter data members.|  
  
## 설명  
 Using `CManualAccessor`, you can specify the parameter and output column binding by run\-time function calls.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor 클래스](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)