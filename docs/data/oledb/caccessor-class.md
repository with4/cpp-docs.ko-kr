---
title: "CAccessor 클래스 | Microsoft Docs"
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
  - "ATL.CAccessor<T>"
  - "ATL::CAccessor"
  - "CAccessor"
  - "ATL::CAccessor<T>"
  - "ATL.CAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessor 클래스"
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessor 클래스
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Represents one of the accessor types.  
  
## 구문  
  
```  
  
      template < class   
      T  
       >  
class CAccessor : public CAccessorBase, public T  
```  
  
#### 매개 변수  
 `T`  
 The user record class.  
  
## 설명  
 It is used when a record is statically bound to a data source.  The record contains the buffer.  This class supports multiple accessors on a rowset.  
  
 Use this accessor type when you know the structure and the type of the database.  
  
 If your accessor contains fields that point to memory \(such as a `BSTR` or interface\) that must be freed, call the member function [CAccessorRowset::FreeRecordMemory](../../data/oledb/caccessorrowset-freerecordmemory.md) before the next record is read.  
  
## 요구 사항  
 **Header:** atldbcli.h  
  
## 참고 항목  
 [OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)