---
title: "lock 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock"
  - "msclr.lock"
  - "lock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "잠금 클래스"
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This class automates taking a lock for synchronizing access to an object from multiple threads.  When constructed it acquires the lock and when destroyed it releases the lock.  
  
## 구문  
  
```  
ref class lock;  
```  
  
## 설명  
 `lock` is available only for CLR objects and can only be used in CLR code.  
  
 Internally, the lock class uses <xref:System.Threading.Monitor> to synchronize access.  See this topic for more detailed information on synchronization.  
  
## 요구 사항  
 **Header file** \<msclr\\lock.h\>  
  
 **Namespace** msclr  
  
## 참고 항목  
 [잠금](../dotnet/lock.md)   
 [lock 멤버](../dotnet/lock-members.md)