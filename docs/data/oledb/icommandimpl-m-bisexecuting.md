---
title: "ICommandImpl::m_bIsExecuting | Microsoft Docs"
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
  - "ICommandImpl.m_bIsExecuting"
  - "ATL::ICommandImpl::m_bIsExecuting"
  - "m_bIsExecuting"
  - "ATL.ICommandImpl.m_bIsExecuting"
  - "ICommandImpl::m_bIsExecuting"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bIsExecuting"
ms.assetid: 1e152164-514c-4116-88a3-16984af99991
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandImpl::m_bIsExecuting
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령이 현재 실행되는지 여부를 나타냅니다.  
  
## 구문  
  
```  
  
unsigned m_bIsExecuting:1;  
  
```  
  
## 설명  
 명령 클래스의 **Execute** 실행은 이 변수를 **true** 로 설정할 수 있습니다.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [ICommandImpl 클래스](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::m\_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)