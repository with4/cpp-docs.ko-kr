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
ms.openlocfilehash: f19ab7e05b4e27a3b00576339d0b60b37bdba4a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374346"
---
# <a name="linger-structure"></a>LINGER 구조체
`LINGER` 구조 조작에 사용 되는 **SO_LINGER** 및 **SO_DONTLINGER** 의 옵션 `CAsyncSocket::GetSockOpt`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>설명  
 설정의 **SO_DONTLINGER** 옵션 멤버 함수에 대 한 차단을 방지 **닫기** 보내지 않은 데이터를 보낼 수를 기다리는 동안 합니다. 이 옵션을 설정 하는 것이 설정에 해당 하 **SO_LINGER** 와 **l_onoff** 0으로 설정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winsock2.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

