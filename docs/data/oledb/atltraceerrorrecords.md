---
title: "AtlTraceErrorRecords | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.AtlTraceErrorRecords"
  - "ATL::AtlTraceErrorRecords"
  - "AtlTraceErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlTraceErrorRecords 함수"
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# AtlTraceErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dumps OLE DB Error Record information to the dump device if an error is returned.  
  
## 구문  
  
```  
  
      inline void AtlTraceErrorRecords(   
   HRESULT hrErr = S_OK    
);  
```  
  
#### 매개 변수  
 `hErr`  
 \[in\] An `HRESULT` returned by an OLE DB Consumer Template member function.  
  
## 설명  
 If `hErr` is not `S_OK`, `AtlTraceErrorRecords` dumps OLE DB Error Record information to the dump device \(the **Debug** tab of the Output window or a file\).  The Error Record information, which is obtained from the provider, includes row number, source, description, help file, context, and GUID for each error record entry.  `AtlTraceErrorRecords` dumps this information only in debug builds.  In release builds, it is an empty stub that is optimized out.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿에 대한 매크로 및 전역 함수](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo 클래스](../../data/oledb/cdberrorinfo-class.md)