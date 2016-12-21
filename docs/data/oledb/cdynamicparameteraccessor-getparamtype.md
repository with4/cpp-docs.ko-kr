---
title: "CDynamicParameterAccessor::GetParamType | Microsoft Docs"
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
  - "CDynamicParameterAccessor.GetParamType"
  - "CDynamicParameterAccessor:GetParamType"
  - "CDynamicParameterAccessor::GetParamType"
  - "ATL.CDynamicParameterAccessor.GetParamType"
  - "GetParamType"
  - "ATL::CDynamicParameterAccessor::GetParamType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamType 메서드"
ms.assetid: d9c46775-c2a6-4100-8b69-99f13c52958b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParamType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the data type of a specified parameter.  
  
## 구문  
  
```  
  
      bool GetParamType(  
   DBORDINAL nParam,  
   DBTYPE* pType   
) const throw( );  
```  
  
#### 매개 변수  
 `nParam`  
 \[in\] The parameter number \(offset from 1\).  Parameter 0 is reserved for return values.  The parameter number is the index of the parameter based on its order in the SQL or stored procedure call.  See [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) for an example.  
  
 `pType`  
 \[out\] A pointer to the variable containing the data type of the specified parameter.  
  
## 반환 값  
 Returns **true** on success or **false** on failure.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)