---
title: "CSession::StartTransaction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSession::StartTransaction"
  - "StartTransaction"
  - "ATL.CSession.StartTransaction"
  - "CSession.StartTransaction"
  - "ATL::CSession::StartTransaction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "StartTransaction 메서드"
ms.assetid: cd7bd2be-fad1-4e2b-932b-79d308efb8fb
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CSession::StartTransaction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Begins a new transaction for this session.  
  
## 구문  
  
```  
  
      HRESULT StartTransaction(  
   ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,  
   ULONG isoFlags = 0,  
   ITransactionOptions* pOtherOptions = NULL,  
   ULONG* pulTransactionLevel = NULL   
) const throw( );  
```  
  
#### 매개 변수  
 See [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx) in the *OLE DB Programmer's Reference*.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 For more information, see [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)