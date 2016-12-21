---
title: "CDynamicAccessor::SetStatus | Microsoft Docs"
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
  - "CDynamicAccessor::SetStatus"
  - "ATL::CDynamicAccessor::SetStatus"
  - "CDynamicAccessor.SetStatus"
  - "ATL.CDynamicAccessor.SetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetStatus 메서드"
ms.assetid: 6db82694-e87d-4bf8-a7e3-5765cf6abff9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::SetStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sets the status of the specified column.  
  
## 구문  
  
```  
  
      bool SetStatus(   
   DBORDINAL nColumn,   
   DBSTATUS status    
) throw( );  
bool SetStatus(   
   const CHAR* pColumnName,   
   DBSTATUS status    
) throw( );  
bool SetStatus(   
   const WCHAR* pColumnName,   
   DBSTATUS status    
) throw( );  
```  
  
#### 매개 변수  
 `nColumn`  
 \[in\] The column number.  Column numbers start with 1.  A value of 0 refers to the bookmark column, if any.  
  
 *status*  
 \[in\] The column status.  See [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in the *OLE DB Programmer's Reference* for more information.  
  
 `pColumnName`  
 \[in\] A pointer to a character string containing the column name.  
  
## 반환 값  
 Returns **true** if the specified column status is set successfully.  Otherwise, this function returns **false**.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetStatus](../../data/oledb/cdynamicaccessor-getstatus.md)