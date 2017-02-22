---
title: "CCommand::Unprepare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Unprepare"
  - "CCommand.Unprepare"
  - "CCommand::Unprepare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unprepare 메서드"
ms.assetid: 4fe59988-fe51-4c7c-a156-72b68e3d642b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CCommand::Unprepare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Discards the current command execution plan.  
  
## 구문  
  
```  
  
HRESULT CCommandBase::Unprepare( ) throw( );  
  
```  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method wraps the OLE DB method [ICommandPrepare::Unprepare](https://msdn.microsoft.com/en-us/library/ms719635.aspx).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)