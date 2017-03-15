---
title: "CDataConnection::operator bool(OLE DB) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection::operatorBOOL"
  - "ATL::CDataConnection::operatorBOOL"
  - "CDataConnection.operatorBOOL"
  - "ATL.CDataConnection.operatorBOOL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BOOL 연산자"
  - "operator bool"
ms.assetid: e0791faf-2ed2-4dbb-9e68-3b9b5da2b7a7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::operator bool(OLE DB)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Determines whether the current session is open or not.  
  
## 구문  
  
```  
  
operator bool( ) throw( );  
  
```  
  
## 설명  
 Returns a `bool` \(C\+\+ data type\) value.  **true** means the current session is open; **false** means the current session is closed.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator BOOL](../../data/oledb/cdataconnection-operator-bool.md)