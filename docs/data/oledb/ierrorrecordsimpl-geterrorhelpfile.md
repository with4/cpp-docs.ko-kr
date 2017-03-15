---
title: "IErrorRecordsImpl::GetErrorHelpFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl::GetErrorHelpFile"
  - "GetErrorHelpFile"
  - "IErrorRecordsImpl.GetErrorHelpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorHelpFile 메서드"
ms.assetid: ad198f76-5bdf-4b8d-9f1a-3d38f72f31ad
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IErrorRecordsImpl::GetErrorHelpFile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gets the path name of the help file from an error record.  
  
## 구문  
  
```  
  
      LPOLESTR GetErrorHelpFile(  
   ERRORINFO& rCurError   
);  
```  
  
#### 매개 변수  
 `rCurError`  
 An `ERRORINFO` record in an **IErrorInfo** interface.  
  
## 반환 값  
 Pointer to a string that contains the path name of the help file for the error.  
  
## 요구 사항  
 **Header:** atldb.h  
  
## 참고 항목  
 [IErrorRecordsImpl 클래스](../../data/oledb/ierrorrecordsimpl-class.md)