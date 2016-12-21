---
title: "CDynamicAccessor::GetBookmark | Microsoft Docs"
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
  - "CDynamicAccessor.GetBookmark"
  - "GetBookmark"
  - "CDynamicAccessor::GetBookmark"
  - "ATL.CDynamicAccessor.GetBookmark"
  - "ATL::CDynamicAccessor::GetBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBookmark 메서드"
ms.assetid: 6d0a2970-0c62-4a34-bac7-149d8e990f81
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the bookmark for the current row.  
  
## 구문  
  
```  
  
      HRESULT GetBookmark(   
   CBookmark< >* pBookmark    
) const throw( );  
```  
  
#### 매개 변수  
 `pBookmark`  
 \[out\] A pointer to the [CBookmark](../../data/oledb/cbookmark-class.md) object.  
  
## 반환 값  
 One of the standard `HRESULT` values.  
  
## 설명  
 You need to set **DBPROP\_IRowsetLocate** to `VARIANT_TRUE` to retrieve a bookmark.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDynamicAccessor 클래스](../../data/oledb/cdynamicaccessor-class.md)