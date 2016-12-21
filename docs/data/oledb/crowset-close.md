---
title: "CRowset::Close | Microsoft Docs"
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
  - "CRowset::Close"
  - "ATL.CRowset.Close"
  - "CRowset<TAccessor>::Close"
  - "CRowset<TAccessor>.Close"
  - "ATL.CRowset<TAccessor>.Close"
  - "ATL::CRowset::Close"
  - "ATL::CRowset<TAccessor>::Close"
  - "CRowset.Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close 메서드"
ms.assetid: 966d779e-e148-4dc0-bbba-7cfb9fa6a16b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Close
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Releases rows and the current [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) interface.  
  
## 구문  
  
```  
  
void Close( ) throw( );  
  
```  
  
## 설명  
 This method releases all rows currently in the rowset.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CRowset 클래스](../../data/oledb/crowset-class.md)