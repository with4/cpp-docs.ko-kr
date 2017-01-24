---
title: "데이터베이스 매크로 및 전역 | Microsoft Docs"
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
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터베이스 전역[C++]"
  - "데이터베이스 매크로[C++]"
  - "전역 데이터베이스 함수[C++]"
  - "전역 함수[C++], 데이터베이스 함수"
  - "매크로[C++], MFC 데이터베이스"
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 데이터베이스 매크로 및 전역
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The macros and globals listed below apply to ODBC\-based database applications.  They are not used with DAO\-based applications.  
  
 Before MFC 4.2, the macros `AFX_SQL_ASYNC` and `AFX_SQL_SYNC` gave asynchronous operations an opportunity to yield time to other processes.  Beginning with MFC 4.2, the implementation of these macros changed because the MFC ODBC classes used only synchronous operations.  The macro `AFX_ODBC_CALL` was new to MFC 4.2.  
  
### Database Macros  
  
|||  
|-|-|  
|[AFX\_ODBC\_CALL](../Topic/AFX_ODBC_CALL.md)|Calls an ODBC API function that returns `SQL_STILL_EXECUTING`.  `AFX_ODBC_CALL` will repeatedly call the function until it no longer returns `SQL_STILL_EXECUTING`.|  
|[AFX\_SQL\_ASYNC](../Topic/AFX_SQL_ASYNC.md)|`AFX_ODBC_CALL`를 호출합니다.|  
|[AFX\_SQL\_SYNC](../Topic/AFX_SQL_SYNC.md)|Calls an ODBC API function that does not return `SQL_STILL_EXECUTING`.|  
  
### Database Globals  
  
|||  
|-|-|  
|[AfxGetHENV](../Topic/AfxGetHENV.md)|Retrieves a handle to the ODBC environment currently in use by MFC.  You can use this handle in direct ODBC calls.|  
  
## 참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)