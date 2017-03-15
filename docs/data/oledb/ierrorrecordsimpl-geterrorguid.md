---
title: "IErrorRecordsImpl::GetErrorGUID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetErrorGUID"
  - "IErrorRecordsImpl.GetErrorGUID"
  - "IErrorRecordsImpl::GetErrorGUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorGUID 메서드"
ms.assetid: 42c00755-50e5-401a-8246-adef9de5ced2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IErrorRecordsImpl::GetErrorGUID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gets the error GUID from an error record.  
  
## 구문  
  
```  
  
      REFGUID GetErrorGUID(  
   ERRORINFO& rCurError   
);  
```  
  
#### 매개 변수  
 `rCurError`  
 An `ERRORINFO` record in an **IErrorInfo** interface.  
  
## 반환 값  
 A reference to a GUID for the error.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)