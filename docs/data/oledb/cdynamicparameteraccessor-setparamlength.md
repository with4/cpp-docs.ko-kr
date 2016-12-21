---
title: "CDynamicParameterAccessor::SetParamLength | Microsoft Docs"
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
  - "ATL::CDynamicParameterAccessor::SetParamLength"
  - "CDynamicParameterAccessor.SetParamLength"
  - "ATL.CDynamicParameterAccessor.SetParamLength"
  - "CDynamicParameterAccessor::SetParamLength"
  - "SetParamLength"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamLength 메서드"
ms.assetid: d8e0bbfe-e1ae-4a8f-9567-584fbb0c8385
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::SetParamLength
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the length of the specified parameter stored in the buffer.  
  
## 구문  
  
```  
  
      bool SetParamLength(  
   DBORDINAL nParam,  
   DBLENGTH length  
);  
```  
  
#### 매개 변수  
 `nParam`  
 \[in\] The parameter number \(offset from 1\).  Parameter 0 is reserved for return values.  The parameter number is the index of the parameter based on its order in the SQL or stored procedure call.  See [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) for an example.  
  
 *length*  
 \[in\] The length in bytes of the specified parameter.  
  
## 설명  
 Returns **true** on success or **false** on failure.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)