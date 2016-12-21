---
title: "CDynamicAccessor::GetColumnName | Microsoft Docs"
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
  - "ATL::CDynamicAccessor::GetColumnName"
  - "GetColumnName"
  - "ATL.CDynamicAccessor.GetColumnName"
  - "CDynamicAccessor::GetColumnName"
  - "CDynamicAccessor.GetColumnName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnName 메서드"
ms.assetid: 96a7452a-1f5b-41e9-ab37-88dac026f961
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetColumnName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the name of the specified column.  
  
## 구문  
  
```  
  
      LPOLESTR GetColumnName(   
   DBORDINAL nColumn    
) const throw( );  
```  
  
#### 매개 변수  
 `nColumn`  
 \[in\] The column number.  Column numbers start with 1.  A value of 0 refers to the bookmark column, if any.  
  
## 반환 값  
 지정된 열의 이름입니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)