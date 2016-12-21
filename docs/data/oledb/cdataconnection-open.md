---
title: "CDataConnection::Open | Microsoft Docs"
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
  - "CDataConnection.Open"
  - "ATL.CDataConnection.Open"
  - "CDataConnection::Open"
  - "ATL::CDataConnection::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open 메서드"
ms.assetid: 2c6f0c01-4954-43ba-973e-861ac8e82892
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Opens a connection to a data source using an initialization string.  
  
## 구문  
  
```  
  
      HRESULT Open(   
   LPCOLESTR szInitString    
) throw( );  
```  
  
#### 매개 변수  
 *szInitString*  
 \[in\] The initialization string for the data source.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)