---
title: "SOCKADDR_IN 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a1283740c0abb0538e5912efa11500c46b45bb9f
ms.lasthandoff: 04/04/2017

---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN 구조체
인터넷 주소 패밀리에는 `SOCKADDR_IN` 구조를 사용 하 여 Windows 소켓 소켓을 연결 하는 데 로컬 또는 원격 끝점 주소를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct sockaddr_in{  
    short sin_family;  
    unsigned short sin_port;  
struct in_addr sin_addr;  
    char sin_zero[8];  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *sin_family*  
 주소 집합 (있어야 **AF_INET**).  
  
 *sin_port*  
 IP 포트입니다.  
  
 *sin_addr*  
 IP 주소입니다.  
  
 *sin_zero*  
 크기가 같은 구조를 패딩 `SOCKADDR`합니다.  
  
## <a name="remarks"></a>주의  
 이의 형태는 `SOCKADDR` 인터넷 주소 패밀리에 특정 구조체이 고으로 캐스팅 될 수 `SOCKADDR`합니다.  
  
 이 구조체의 IP 주소 구성 요소가 형식 **IN_ADDR**합니다. **IN_ADDR** 구조 WINSOCK Windows 소켓 헤더 파일에 정의 되어 있습니다. 다음과 같이 H:  
  
```  
struct in_addr {
    union {
        struct {  
            unsigned char s_b1, s_b2, s_b3, s_b4;  
        } S_un_b;  
        struct {  
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;  
};  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winsock2.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR 구조체](../../mfc/reference/sockaddr-structure.md)

