---
title: "CDataConnection::operator CDataSource&amp; | Microsoft Docs"
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
  - "CDataSource&"
  - "CDataConnection.operatorCDataSource&"
  - "operatorCDataSource&"
  - "CDataConnection::operatorCDataSource&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataSource& 연산자"
  - "연산자 & (CDataSource)"
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CDataSource&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns a reference to the contained `CDataSource` object.  
  
## 구문  
  
```  
  
operator const CDataSource&() throw( );  
  
```  
  
## 설명  
 This operator returns a reference to the contained `CDataSource` object, allowing you to pass a `CDataConnection` object where a `CDataSource` reference is expected.  
  
## 예제  
 If you have a function \(such as `func` below\) that takes a `CDataSource` reference, you can use **CDataSource&** to pass a `CDataConnection` object instead.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/CPP/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/CPP/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource\*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)