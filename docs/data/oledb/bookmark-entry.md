---
title: "BOOKMARK_ENTRY | Microsoft Docs"
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
  - "BOOKMARK_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BOOKMARK_ENTRY 매크로"
ms.assetid: ec8222f5-9d90-46cb-989e-23f24465083f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BOOKMARK_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Binds the bookmark column.  
  
## 구문  
  
```  
  
BOOKMARK_ENTRY(  
variable  
 )  
  
```  
  
#### 매개 변수  
 *variable*  
 \[in\] The variable to be bound to the bookmark column.  
  
## 예제  
 [!CODE [NVC_OLEDB_Consumer#17](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#17)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CBookmark 클래스](../../data/oledb/cbookmark-class.md)   
 [DBPROP\_BOOKMARKS](https://msdn.microsoft.com/en-us/library/ms709728.aspx)