---
title: "CSession 클래스 | Microsoft Docs"
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
  - "CSession"
  - "ATL::CSession"
  - "ATL.CSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession 클래스"
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSession 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents a single database access session.  
  
## 구문  
  
```  
class CSession  
```  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[중단](../../data/oledb/csession-abort.md)|Cancels \(terminates\) the transaction.|  
|[닫기](../../data/oledb/csession-close.md)|Closes the session.|  
|[커밋](../../data/oledb/csession-commit.md)|트랜잭션을 커밋합니다.|  
|[GetTransactionInfo](../../data/oledb/csession-gettransactioninfo.md)|Returns information regarding a transaction.|  
|[를 엽니다.](../../data/oledb/csession-open.md)|Opens a new session for the data source object.|  
|[StartTransaction](../../data/oledb/csession-starttransaction.md)|Begins a new transaction for this session.|  
  
## 설명  
 One or more sessions can be associated with each provider connection \(data source\), which is represented by a [CDataSource](../../data/oledb/cdatasource-class.md) object.  To create a new `CSession` for a `CDataSource`, call [CSession::Open](../../data/oledb/csession-open.md).  To begin a database transaction, `CSession` provides the `StartTransaction` method.  Once a transaction is started, you can commit to it using the **Commit** method, or cancel it using the **Abort** method.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [CatDB](../../top/visual-cpp-samples.md)   
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)