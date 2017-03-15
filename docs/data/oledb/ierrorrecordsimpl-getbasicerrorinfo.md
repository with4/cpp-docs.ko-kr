---
title: "IErrorRecordsImpl::GetBasicErrorInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IErrorRecordsImpl::GetBasicErrorInfo"
  - "IErrorRecordsImpl::GetBasicErrorInfo"
  - "GetBasicErrorInfo"
  - "ATL.IErrorRecordsImpl.GetBasicErrorInfo"
  - "IErrorRecordsImpl.GetBasicErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetBasicErrorInfo 메서드"
ms.assetid: d0b4dec3-f32a-4aaa-8365-524f2e7c8395
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IErrorRecordsImpl::GetBasicErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns basic information about the error, such as the return code and provider\-specific error number.  
  
## 구문  
  
```  
  
      STDMETHOD( GetBasicErrorInfo )(  
   ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo   
);  
```  
  
#### 매개 변수  
 See [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)