---
title: "CCommand::Prepare | Microsoft Docs"
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
  - "CCommand.Prepare"
  - "CCommand::Prepare"
  - "Prepare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Prepare 메서드"
ms.assetid: f0e473fc-2f7a-4d29-96c2-1328dc21e702
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Prepare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Validates and optimizes the current command.  
  
## 구문  
  
```  
  
      HRESULT CCommandBase::Prepare(  
   ULONG cExpectedRuns = 0   
) throw( );  
```  
  
#### 매개 변수  
 *cExpectedRuns*  
 \[in\] The number of times you expect to execute the command.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This method wraps the OLE DB method [ICommandPrepare::Prepare](https://msdn.microsoft.com/en-us/library/ms718370.aspx).  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)