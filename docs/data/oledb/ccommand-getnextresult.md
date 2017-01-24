---
title: "CCommand::GetNextResult | Microsoft Docs"
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
  - "ATL::CCommand::GetNextResult"
  - "CCommand::GetNextResult"
  - "GetNextResult"
  - "CCommand.GetNextResult"
  - "ATL.CCommand.GetNextResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetNextResult 메서드"
ms.assetid: 63df9b55-9490-45c4-934a-879c5c2725d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::GetNextResult
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fetches the next result set if one is available.  
  
## 구문  
  
```  
  
      HRESULT GetNextResult(  
   DBROWCOUNT* pulRowsAffected,  
   bool bBind = true   
) throw( );  
```  
  
#### 매개 변수  
 *pulRowsAffected*  
 \[in\/out\] A pointer to memory where the count of rows affected by a command is returned.  
  
 `bBind`  
 \[in\] Specifies whether to bind the command automatically after being executed.  The default is **true**, which causes the command to be bound automatically.  Setting `bBind` to **false** prevents the automatic binding of the command so that you can bind manually. \(Manual binding is of particular interest to OLAP users.\)  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 If a result set has been previously fetched, this function releases the previous result set and unbinds the columns.  If `bBind` is **true**, it binds the new columns.  
  
 You should call this function only if you have specified multiple results by setting the `CCommand` template parameter *TMultiple*\=`CMultipleResults`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CCommand 클래스](../../data/oledb/ccommand-class.md)