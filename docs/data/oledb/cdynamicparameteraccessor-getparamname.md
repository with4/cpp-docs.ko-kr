---
title: "CDynamicParameterAccessor::GetParamName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::GetParamName"
  - "ATL.CDynamicParameterAccessor.GetParamName"
  - "GetParamName"
  - "CDynamicParameterAccessor.GetParamName"
  - "ATL::CDynamicParameterAccessor::GetParamName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamName 메서드"
ms.assetid: 707c08ed-d3d0-4ce8-b23e-20b07202a3e2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::GetParamName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the name of the specified parameter.  
  
## 구문  
  
```  
  
      LPOLESTR GetParamName(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### 매개 변수  
 `nParam`  
 \[in\] The parameter number \(offset from 1\).  Parameter 0 is reserved for return values.  The parameter number is the index of the parameter based on its order in the SQL or stored procedure call.  See [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) for an example.  
  
## 반환 값  
 The name of the specified parameter.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)