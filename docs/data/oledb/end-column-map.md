---
title: "END_COLUMN_MAP | Microsoft Docs"
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
  - "END_COLUMN_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "END_COLUMN_MAP 매크로"
ms.assetid: b6418f19-84f5-49f4-84c7-67a40ed33364
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# END_COLUMN_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marks the end of the column map entries.  
  
## 구문  
  
```  
  
END_COLUMN_MAP( )  
  
```  
  
## 설명  
 It is used with a single accessor on a rowset.  The `BEGIN_COLUMN_MAP` macro is completed with the `END_COLUMN_MAP` macro.  
  
## 예제  
 See [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)