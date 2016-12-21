---
title: "CBookmark::SetBookmark | Microsoft Docs"
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
  - "CBookmark<0>::SetBookmark"
  - "ATL.CBookmark<0>.SetBookmark"
  - "CBookmark<0>.SetBookmark"
  - "SetBookmark"
  - "ATL::CBookmark::SetBookmark"
  - "ATL::CBookmark<0>::SetBookmark"
  - "CBookmark.SetBookmark"
  - "ATL.CBookmark.SetBookmark"
  - "CBookmark::SetBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBookmark 메서드"
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBookmark::SetBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copies the bookmark value referenced by `pBuffer` to the `CBookmark` buffer and sets the buffer size to `nSize`.  
  
## 구문  
  
```  
  
      HRESULT SetBookmark(  
   DBLENGTH nSize,  
   BYTE* pBuffer   
) throw( );  
```  
  
#### 매개 변수  
 *nSize*  
 \[in\] The size of the bookmark buffer.  
  
 `pBuffer`  
 \[in\] A pointer to the byte array containing the bookmark value.  
  
## 반환 값  
 A standard `HRESULT`.  
  
## 설명  
 This function is only available in **CBookmark\<0\>**.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CBookmark 클래스](../../data/oledb/cbookmark-class.md)