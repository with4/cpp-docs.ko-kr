---
title: "IErrorRecordsImpl::GetRecordCount | Microsoft Docs"
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
  - "IErrorRecordsImpl::GetRecordCount"
  - "ATL::IErrorRecordsImpl::GetRecordCount"
  - "IErrorRecordsImpl.GetRecordCount"
  - "ATL.IErrorRecordsImpl.GetRecordCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRecordCount 메서드"
ms.assetid: 44388bc3-1c64-4491-a1c5-28f3497ef040
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl::GetRecordCount
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns the number of records in the OLE DB record object.  
  
## 구문  
  
```  
  
      STDMETHOD( GetRecordCount )(  
   ULONG *pcRecords   
);  
```  
  
#### 매개 변수  
 See [IErrorRecords::GetRecordCount](https://msdn.microsoft.com/en-us/library/ms722724.aspx) in the *OLE DB Programmer's Reference*.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)