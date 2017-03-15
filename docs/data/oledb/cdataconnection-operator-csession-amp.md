---
title: "CDataConnection::operator CSession&amp; | Microsoft Docs"
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
  - "CSession&"
  - "CDataConnection::operatorCSession&"
  - "CDataConnection.operatorCSession&"
  - "operatorCSession&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession& 연산자"
  - "연산자 CSession&"
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Returns a reference to the contained `CSession` object.  
  
## 구문  
  
```  
  
operator const CSession&();  
  
```  
  
## 설명  
 This operator returns a reference to the contained `CSession` object, allowing you to pass a `CDataConnection` object where a `CSession` reference is expected.  
  
## 예제  
 If you have a function \(such as `func` below\) that takes a `CSession` reference, you can use **CSession&** to pass a `CDataConnection` object instead.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/CPP/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/CPP/cdataconnection-operator-csession-amp_2.cpp)]  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession\*](../../data/oledb/cdataconnection-operator-csession-star.md)