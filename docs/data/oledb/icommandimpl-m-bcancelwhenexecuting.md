---
title: "ICommandImpl::m_bCancelWhenExecuting | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::m_bCancelWhenExecuting"
  - "ICommandImpl.m_bCancelWhenExecuting"
  - "ATL::ICommandImpl::m_bCancelWhenExecuting"
  - "m_bCancelWhenExecuting"
  - "ATL.ICommandImpl.m_bCancelWhenExecuting"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bCancelWhenExecuting"
ms.assetid: d7d33e4c-a862-4e6d-a9a1-4400bfe45b88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ICommandImpl::m_bCancelWhenExecuting
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indicates whether the command can be canceled when executing.  
  
## 구문  
  
```  
  
unsigned m_bCancelWhenExecuting:1;  
  
```  
  
## 설명  
 Defaults to **true** \(can be canceled\).  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [ICommandImpl 클래스](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::m\_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)