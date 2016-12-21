---
title: "CSession::Abort | Microsoft Docs"
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
  - "CSession.Abort"
  - "CSession::Abort"
  - "ATL.CSession.Abort"
  - "ATL::CSession::Abort"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Abort 메서드"
ms.assetid: 02413b20-c486-451f-b4d7-73a6e8065df8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession::Abort
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

트랜잭션이 종료 됩니다.  
  
## 구문  
  
```  
  
      HRESULT Abort(   
   BOID* pboidReason = NULL,   
   BOOL bRetaining = FALSE,   
   BOOL bAsync = FALSE    
) const throw( );  
```  
  
#### 매개 변수  
 *OLE DB Programmer's Reference* 에서 [ITransaction::Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx) 를 참고하세요.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)