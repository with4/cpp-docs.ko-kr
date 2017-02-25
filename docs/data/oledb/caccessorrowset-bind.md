---
title: "CAccessorRowset::Bind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CAccessorRowset.Bind"
  - "CAccessorRowset::Bind"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bind 메서드"
ms.assetid: 42a1fc86-f570-4e54-9b82-7f7141564214
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CAccessorRowset::Bind
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Creates the bindings if you specified **bBind** as false in [CCommand::Open](../../data/oledb/ccommand-open.md).  
  
## 구문  
  
```  
  
HRESULT Bind( );  
  
```  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CAccessorRowset 클래스](../../data/oledb/caccessorrowset-class.md)