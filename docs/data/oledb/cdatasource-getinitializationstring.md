---
title: "CDataSource::GetInitializationString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::GetInitializationString"
  - "CDataSource.GetInitializationString"
  - "GetInitializationString"
  - "CDataSource::GetInitializationString"
  - "ATL.CDataSource.GetInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInitializationString 메서드"
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataSource::GetInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retrieves the initialization string of a data source that is currently open.  
  
## 구문  
  
```  
  
      HRESULT GetInitializationString(   
   BSTR* pInitializationString,   
   bool bIncludePassword = false    
) throw( );  
```  
  
#### 매개 변수  
 *pInitializationString*  
 \[out\] A pointer to the initialization string.  
  
 *bIncludePassword*  
 \[in\] **true** if string includes a password; otherwise **false**.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 The resulting initialization string can be used to later reopen this data source connection.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataSource 클래스](../../data/oledb/cdatasource-class.md)