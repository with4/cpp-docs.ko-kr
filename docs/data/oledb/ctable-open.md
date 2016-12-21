---
title: "CTable::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CTable.Open"
  - "ATL::CTable::Open"
  - "CTable::Open"
  - "CTable.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open 메서드"
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTable::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Opens the table.  
  
## 구문  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### 매개 변수  
 `session`  
 \[in\] The session for which the table is opened.  
  
 *wszTableName*  
 \[in\] The name of the table to open, passed as a Unicode string.  
  
 *szTableName*  
 \[in\] The name of the table to open, passed as an ANSI string.  
  
 *dbid*  
 \[in\] The **DBID** of the table to open.  
  
 *pPropSet*  
 \[in\] A pointer to an array of [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures containing properties and values to be set.  See [Property Sets and Property Groups](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in the *OLE DB Programmer's Reference* in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  The default value of NULL specifies no properties.  
  
 `ulPropSets`  
 \[in\] The number of [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) structures passed in the *pPropSet* argument.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 For more details, see [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CTable 클래스](../../data/oledb/ctable-class.md)