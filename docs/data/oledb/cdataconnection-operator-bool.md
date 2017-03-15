---
title: "CDataConnection::operator BOOL | Microsoft Docs"
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
ms.assetid: ad0bea7f-61ff-47f7-8127-32a31e3e9b9d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::operator BOOL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Determines whether the current session is open or not.  
  
## 구문  
  
```  
  
operator BOOL( ) throw( );  
  
```  
  
## 설명  
 Returns **BOOL** \(MFC typedef\) value.  **TRUE** means the current session is open; **FALSE** means the current session is closed.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator bool](../../data/oledb/cdataconnection-operator-bool-ole-db.md)