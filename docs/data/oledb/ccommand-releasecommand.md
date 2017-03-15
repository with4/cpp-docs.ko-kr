---
title: "CCommand::ReleaseCommand | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCommand.ReleaseCommand"
  - "ReleaseCommand"
  - "CCommand::ReleaseCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseCommand 메서드"
ms.assetid: 3b58230c-13d5-45c5-b43e-bb013ecc3019
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CCommand::ReleaseCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Releases the parameter accessor, then releases the command itself.  
  
## 구문  
  
```  
  
void CCommandBase::ReleaseCommand( ) throw( );  
  
```  
  
## 설명  
 `ReleaseCommand` is used in conjunction with **Close**.  See [Close](../../data/oledb/ccommand-close.md) for usage details.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)   
 [CCommand::Close](../../data/oledb/ccommand-close.md)