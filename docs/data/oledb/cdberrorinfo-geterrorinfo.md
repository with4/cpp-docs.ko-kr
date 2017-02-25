---
title: "CDBErrorInfo::GetErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetErrorInfo"
  - "ATL.CDBErrorInfo.GetErrorInfo"
  - "CDBErrorInfo.GetErrorInfo"
  - "ATL::CDBErrorInfo::GetErrorInfo"
  - "CDBErrorInfo::GetErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorInfo 메서드"
ms.assetid: 234e1f02-c307-4666-b3ce-2a4d62407fa1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDBErrorInfo::GetErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calls [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) to return an [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) interface pointer to the specified record.  
  
## 구문  
  
```  
  
      HRESULT GetErrorInfo(   
   ULONG ulRecordNum,   
   LCID lcid,   
   IErrorInfo** ppErrorInfo    
) const throw( );  
```  
  
#### 매개 변수  
 See [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) in the *OLE DB Programmer's Reference*.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)