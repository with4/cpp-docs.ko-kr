---
title: "CDynamicParameterAccessor::SetParamString | Microsoft Docs"
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
  - "ATL.CDynamicParameterAccessor.SetParamString"
  - "ATL::CDynamicParameterAccessor::SetParamString"
  - "SetParamString"
  - "CDynamicParameterAccessor::SetParamString"
  - "CDynamicParameterAccessor.SetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamString 메서드"
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::SetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the string data of the specified parameter stored in the buffer.  
  
## 구문  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### 매개 변수  
 `nParam`  
 \[in\] The parameter number \(offset from 1\).  Parameter 0 is reserved for return values.  The parameter number is the index of the parameter based on its order in the SQL or stored procedure call.  See [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) for an example.  
  
 `pString`  
 \[in\] A pointer to the ANSI \(**CHAR**\) or Unicode \(**WCHAR**\) string data of the specified parameter.  See `DBSTATUS` in oledb.h.  
  
 *status*  
 \[in\] The `DBSTATUS` status of the specified parameter.  For information on `DBSTATUS` values, see [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in the *OLE DB Programmer's Reference*, or search for `DBSTATUS` in oledb.h.  
  
## 설명  
 Returns **true** on success or **false** on failure.  
  
 `SetParamString` will fail if you try to set a string that is larger than the maximum size specified for `pString`.  
  
 Use `SetParamString` to set string parameter data in the buffer.  Use [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) to set nonstring parameter data in the buffer.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicParameterAccessor 클래스](../../data/oledb/cdynamicparameteraccessor-class.md)