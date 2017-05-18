---
title: "SOCKADDR 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR structure
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 28984fcc5614a5f901a01ffdeff4ea5f360f63fc
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="sockaddr-structure"></a>SOCKADDR 구조체
`SOCKADDR` 구조체는 Windows 소켓 통신에 참여하는 컴퓨터에 대한 IP(인터넷 프로토콜) 주소를 저장하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct sockaddr {  
    unsigned short sa_family;  
    char sa_data[14];  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *sa_family*  
 소켓 주소 패밀리입니다.  
  
 *sa_data*  
 다른 모든 소켓 주소 구조체의 최대 크기입니다.  
  
## <a name="remarks"></a>주의  
 Microsoft TCP/IP 소켓 개발자 키트는 인터넷 주소 도메인만 지원합니다. 주소의 각 부분에 대한 값을 실제로 채우려면 특별히 이 주소 형식을 위한 `SOCKADDR_IN` 데이터 구조를 사용합니다. `SOCKADDR` 및 `SOCKADDR_IN` 데이터 구조는 동일한 크기입니다. 두 구조체 형식 사이를 전환하려면 캐스팅만 하면 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winsock2.h  
  
## <a name="see-also"></a>참고 항목  
 [구조, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR_IN 구조체](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)


