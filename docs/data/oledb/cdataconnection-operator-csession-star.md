---
title: "CDataConnection::operator CSession* | Microsoft Docs"
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
  - "CDataConnection.operatorCSession*"
  - "CDataConnection::operatorCSession*"
  - "operatorCSession*"
  - "CSession*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession* 연산자"
  - "연산자 CSession*"
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession*
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

포함된 `CSession` 개체에 대한 포인터를 반환합니다.  
  
## 구문  
  
```  
  
operator const CSession*() throw( );  
  
```  
  
## 설명  
 이 연산자는 `CSession` 포인터가 예상될 때 `CDataConnection` 개체를 전달 할 수 있도록 포함 된 `CSession` 포인터를 반환합니다.  
  
## 예제  
 사용 예제는 [operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md) 를 참조하십시오.  
  
## 요구 사항  
 **헤더:** atldbcli.h  
  
## 참고 항목  
 [CDataConnection 클래스](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)