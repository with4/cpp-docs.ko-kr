---
title: "CSession::Commit | Microsoft Docs"
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
  - "CSession.Commit"
  - "ATL.CSession.Commit"
  - "ATL::CSession::Commit"
  - "CSession::Commit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Commit 메서드"
ms.assetid: 1d5f56b9-000c-4bae-a975-89d3452f499f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession::Commit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

트랜잭션을 커밋합니다.  
  
## 구문  
  
```  
  
      HRESULT Commit(   
   BOOL bRetaining = FALSE,   
   DWORD grfTC = XACTTC_SYNC,   
   DWORD grfRM = 0    
) const throw( );  
```  
  
#### 매개 변수  
 *OLE DB Programmer's Reference* 에서 [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx) 를 참고하세요.  
  
## 반환 값  
 표준 `HRESULT`입니다.  
  
## 설명  
 보다 자세한 내용은, [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx)를 참고하세요.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)