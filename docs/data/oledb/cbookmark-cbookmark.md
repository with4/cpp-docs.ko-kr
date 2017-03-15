---
title: "CBookmark::CBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBookmark<0>.CBookmark<0>"
  - "CBookmark::CBookmark"
  - "ATL.CBookmark.CBookmark"
  - "CBookmark.CBookmark"
  - "CBookmark"
  - "ATL::CBookmark<0>::CBookmark<0>"
  - "ATL.CBookmark<0>.CBookmark<0>"
  - "CBookmark<0>::CBookmark<0>"
  - "ATL::CBookmark::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark 클래스, 생성자"
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBookmark::CBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

생성자입니다.  
  
## 구문  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### 매개 변수  
 `nSize`  
 \[in\] Size of the bookmark buffer in bytes.  
  
## 설명  
 The first function sets the buffer to **NULL** and the buffer size to 0.  The second function sets the buffer size to `nSize`, and the buffer to a byte array of `nSize` bytes.  
  
> [!NOTE]
>  This function is only available in **CBookmark\<0\>**.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CBookmark 클래스](../../data/oledb/cbookmark-class.md)