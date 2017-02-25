---
title: "CBookmark 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CBookmark"
  - "ATL::CBookmark<nSize>"
  - "CBookmark"
  - "ATL.CBookmark<nSize>"
  - "ATL::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark 클래스"
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CBookmark 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Holds a bookmark value in its buffer.  
  
## 구문  
  
```  
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase  
template < >  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### 매개 변수  
 `nSize`  
 The size of the bookmark buffer in bytes.  When `nSize` is zero, the bookmark buffer will be dynamically created at run time.  
  
## 멤버  
  
### 메서드  
  
|||  
|-|-|  
|[CBookmark](../../data/oledb/cbookmark-class.md)|The constructor|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|Retrieves the pointer to the buffer.|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|Retrieves the size of the buffer in bytes.|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|Sets the bookmark value.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../../data/oledb/cbookmark-operator-equal.md)|Assigns one `CBookmark` class to another.|  
  
## 설명  
 **CBookmark\<0\>** is a template specialization of `CBookmark`; its buffer is dynamically created at run time.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)