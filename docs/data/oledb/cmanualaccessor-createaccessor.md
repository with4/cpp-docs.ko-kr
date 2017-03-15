---
title: "CManualAccessor::CreateAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::CreateAccessor"
  - "CreateAccessor"
  - "ATL.CManualAccessor.CreateAccessor"
  - "CManualAccessor.CreateAccessor"
  - "CManualAccessor::CreateAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateAccessor 메서드"
ms.assetid: 594c8d6d-b49a-4818-a9a5-81c8115d4e42
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CManualAccessor::CreateAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Allocates memory for the column bind structures and initializes the column data members.  
  
## 구문  
  
```  
  
      HRESULT CreateAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### 매개 변수  
 `nBindEntries`  
 \[in\] Number of columns.  This number should match the number of calls to the [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) function.  
  
 `pBuffer`  
 \[in\] A pointer to the buffer where the output columns are stored.  
  
 `nBufferSize`  
 \[in\] The size of the buffer in bytes.  
  
## 반환 값  
 One of the standard `HRESULT` values.  
  
## 설명  
 Call this function before you call the `CManualAccessor::AddBindEntry` function.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CManualAccessor 클래스](../../data/oledb/cmanualaccessor-class.md)   
 [DBViewer sample](../../top/visual-cpp-samples.md)