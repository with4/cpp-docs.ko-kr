---
title: "CSession::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CSession::Open"
  - "CSession::Open"
  - "CSession.Open"
  - "ATL.CSession.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open 메서드"
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CSession::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Opens a new session for the data source object.  
  
## 구문  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### 매개 변수  
 `ds`  
 \[in\] The data source for which the session is to be opened.  
  
 *pPropSet*  
 \[in\] A pointer to an array of [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures containing properties and values to be set.  See [Property Sets and Property Groups](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in the *OLE DB Programmer's Reference* in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ulPropSets`  
 \[in\] The number of [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures passed in the *pPropSet* argument.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 You must open the data source object using [CDataSource::Open](../../data/oledb/cdatasource-open.md) before passing it to `CSession::Open`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CSession 클래스](../../data/oledb/csession-class.md)