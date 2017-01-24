---
title: "SOCKADDR 구조체 | Microsoft Docs"
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
  - "SOCKADDR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SOCKADDR 구조체"
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SOCKADDR 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`SOCKADDR` 구조체는 Windows 소켓 통신에 참여하는 장치에 대한 인터넷 프로토콜 \(IP\) 주소를 저장하는 데에 사용됩니다.  
  
## 구문  
  
```  
  
      struct sockaddr {  
   unsigned short sa_family;  
   char sa_data[14];  
};  
```  
  
#### 매개 변수  
 *sa\_family*  
 소켓 주소 패밀리입니다.  
  
 *sa\_data*  
 다른 모든 소켓 주소 구조체의 최대 크기입니다.  
  
## 설명  
 Microsoft TCP\/IP 소켓 개발자 키트는 인터넷 주소 도메인만을 지원합니다.  주소의 각 부분의 값을 실제로 채우기 위해서는, 특별히 이 주소 형식을 위한 `SOCKADDR_IN` 데이터 구조를 사용합니다.  `SOCKADDR` 및 `SOCKADDR_IN` 데이터 구조는 같은 크기입니다.  두 구조체 형식 사이를 전환하려면 단순히 캐스팅하면 됩니다.  
  
## 요구 사항  
 **헤더:** winsock2.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR\_IN 구조체](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)   
 [CSocket::Create](../Topic/CSocket::Create.md)