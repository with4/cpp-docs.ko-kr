---
title: "CSession::GetTransactionInfo | Microsoft Docs"
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
  - "GetTransactionInfo"
  - "CSession.GetTransactionInfo"
  - "ATL.CSession.GetTransactionInfo"
  - "CSession::GetTransactionInfo"
  - "ATL::CSession::GetTransactionInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetTransactionInfo 메서드"
ms.assetid: 9fa62808-3162-4b5a-8610-e1abb8cf9a71
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession::GetTransactionInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns information regarding a transaction.  
  
## 구문  
  
```  
  
      HRESULT GetTransactionInfo(   
   XACTTRANSINFO* pInfo    
) const throw( );  
```  
  
#### 매개 변수  
 See [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx) in the *OLE DB Programmer's Reference*.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 For more information, see [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)