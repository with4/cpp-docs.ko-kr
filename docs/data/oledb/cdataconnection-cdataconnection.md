---
title: "CDataConnection::CDataConnection | Microsoft Docs"
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
  - "CDataConnection.CDataConnection"
  - "ATL.CDataConnection.CDataConnection"
  - "CDataConnection::CDataConnection"
  - "ATL::CDataConnection::CDataConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataConnection 클래스, 생성자"
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::CDataConnection
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Instantiates and initializes a `CDataConnection` object.  
  
## 구문  
  
```  
  
      CDataConnection();   
CDataConnection(  
   const CDataConnection &ds  
);  
```  
  
#### 매개 변수  
 `ds`  
 \[in\] A reference to an existing data connection.  
  
## 설명  
 The first override creates a new `CDataConnection` object with default settings.  
  
 The second override creates a new `CDataConnection` object with settings equivalent to the data connection object you specify.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)