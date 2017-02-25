---
title: "LINGER 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LINGER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINGER 구조체"
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# LINGER 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

The `LINGER` structure is used for manipulating the **SO\_LINGER** and **SO\_DONTLINGER** options of `CAsyncSocket::GetSockOpt`.  
  
## 구문  
  
```  
  
      struct linger {  
   u_short l_onoff;            // option on/off  
   u_short l_linger;           // linger time  
};  
```  
  
## 설명  
 Setting the **SO\_DONTLINGER** option prevents blocking on member function **Close** while waiting for unsent data to be sent.  Setting this option is equivalent to setting **SO\_LINGER** with **l\_onoff** set to 0.  
  
## 요구 사항  
 **헤더:** winsock2.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)   
 [CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)