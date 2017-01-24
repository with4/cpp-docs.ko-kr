---
title: "HTTP 기초 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HTTP 요청, 반환 코드"
  - "HTTP, 반환 코드"
  - "반환 코드"
ms.assetid: 5b7421bf-42c8-4f3a-8566-8ff5957f58cc
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HTTP 기초
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

When writing an internet application, you often examine and add to the information in HTTP header.  Return codes indicate the success or failure of the requested event.  Several common return codes are listed in the following table.  
  
|Return Code|의미|  
|-----------------|--------|  
|200|URL located, transmission follows|  
|400|Unintelligible request|  
|404|Requested URL not found|  
|405|Server does not support requested method|  
|500|Unknown server error|  
|503|Service unavailable|  
  
 The HTTP responses are grouped as shown in the following table.  
  
|그룹|의미|  
|--------|--------|  
|200–299|성공|  
|300–399|정보|  
|400–499|Request error|  
|500–599|Server error|  
  
 The Hypertext Transfer Protocol \(HTTP\) is an application\-level protocol for hypermedia information systems.  For more information about HTTP, and how Web browsers and servers communicate, see the Hypertext Transfer Protocol \(HTTP\) specification:  
  
 [http:\/\/www.w3.org\/pub\/WWW\/Protocols\/](http://www.w3.org/pub/WWW/Protocols/)  
  
## 참고 항목  
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)