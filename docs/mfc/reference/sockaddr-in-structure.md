---
title: "SOCKADDR_IN 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SOCKADDR_IN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SOCKADDR_IN 구조체"
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# SOCKADDR_IN 구조체
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

인터넷 주소 제품군에서 `SOCKADDR_IN` 구조체는 Windows 소켓이 소켓을 연결할 로컬 또는 원격 끝점 주소를 지정하는 데 사용됩니다.  
  
## 구문  
  
```  
  
      struct sockaddr_in{  
   short sin_family;  
   unsigned short sin_port;  
   struct in_addr sin_addr;  
   char sin_zero[8];  
};  
```  
  
#### 매개 변수  
 *sin\_family*  
 주소 패밀리\(**AF\_INET**여야 함\)  
  
 *sin\_port*  
 IP 포트  
  
 *sin\_addr*  
 IP 주소.  
  
 *sin\_zero*  
 구조체를 `SOCKADDR`과 동일한 크기로 만들기 위한 패딩  
  
## 설명  
 인터넷 주소 제품군과 관련된 `SOCKADDR` 구조의 양식이며, `SOCKADDR`로 캐스팅할 수 있습니다.  
  
 이 구조체의 IP 주소 구성 요소는 **IN\_ADDR** 형식입니다.  **IN\_ADDR** 구조는 Windows 소켓 헤더 파일 WINSOCK.H에서 다음과 같이 정의됩니다.  
  
 `struct   in_addr {`  
  
 `union   {`  
  
 `struct{`  
  
 `unsigned  char   s_b1,`  
  
 `s_b2,`  
  
 `s_b3,`  
  
 `s_b4;`  
  
 `}  S_un_b;`  
  
 `struct  {`  
  
 `unsigned  short  s_w1,`  
  
 `s_w2;`  
  
 `}  S_un_w;`  
  
 `unsigned long  S_addr;`  
  
 `} S_un;`  
  
 `};`  
  
## 요구 사항  
 **헤더:** winsock2.h  
  
## 참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR 구조체](../../mfc/reference/sockaddr-structure.md)