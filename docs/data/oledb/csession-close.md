---
title: "CSession::Close | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSession::Close"
  - "ATL.CSession.Close"
  - "CSession.Close"
  - "ATL::CSession::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close 메서드"
ms.assetid: dc36c4c0-e588-4c0b-91d1-fc7dc5c8e7f4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CSession::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Closes the session, which was opened by [CSession::Open](../../data/oledb/csession-open.md).  
  
## 구문  
  
```  
  
void Close( ) throw( );  
  
```  
  
## 설명  
 Releases the **m\_spOpenRowset** pointer.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)