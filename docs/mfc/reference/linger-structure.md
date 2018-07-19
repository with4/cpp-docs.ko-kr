---
title: LINGER 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LINGER
dev_langs:
- C++
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 53601afdd562f29ccd4bce9db76811e610940b7a
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37339373"
---
# <a name="linger-structure"></a>LINGER 구조체
합니다 `LINGER` 조작의 SO_LINGER 및 SO_DONTLINGER 옵션에 대 한 구조는 `CAsyncSocket::GetSockOpt`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>설명  
 멤버 함수에서 차단 방지 SO_DONTLINGER 옵션 설정 `Close` 보내지 않은 데이터를 보내도록 대기 중입니다. 이 옵션을 설정 하는 것으로 SO_LINGER `l_onoff` 0으로 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winsock2.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

