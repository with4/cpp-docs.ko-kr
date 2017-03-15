---
title: "IErrorRecordsImpl::GetErrorParameters | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl::GetErrorParameters"
  - "ATL.IErrorRecordsImpl.GetErrorParameters"
  - "IErrorRecordsImpl.GetErrorParameters"
  - "GetErrorParameters"
  - "ATL::IErrorRecordsImpl::GetErrorParameters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorParameters 메서드"
ms.assetid: 9bafac52-399e-4e0e-8365-b9f83074cdd5
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IErrorRecordsImpl::GetErrorParameters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the error parameters.  
  
## 구문  
  
```  
  
      STDMETHOD( GetErrorParameters )(  
   ULONG ulRecordNum,  
   DISPPARAMS *pdispparams   
);  
```  
  
#### 매개 변수  
 See [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)