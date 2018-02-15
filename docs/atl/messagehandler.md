---
title: MessageHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7247868f85a30cbecef416c690f181f068f7eaf2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="messagehandler"></a>MessageHandler
**MessageHandler** 의 두 번째 매개 변수에 의해 식별 된 함수 이름에서 `MESSAGE_HANDLER` 메시지 맵에서 매크로입니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
    LRESULT 
    MessageHandler 
 (
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>매개 변수  
 `uMsg`  
 메시지를 지정 합니다.  
  
 `wParam`  
 추가 메시지 관련 정보입니다.  
  
 `lParam`  
 추가 메시지 관련 정보입니다.  
  
 `bHandled`  
 메시지 맵 집합 `bHandled` 를 **TRUE** 전에 `MessageHandler` 호출 됩니다. 경우 `MessageHandler` 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 를 **FALSE** 를 나타내는 메시지에 추가 처리가 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메시지 처리의 결과입니다. 성공 하면 0입니다.  
  
## <a name="remarks"></a>설명  
 이 메시지 처리기를 사용 하 여 메시지 맵에서 예제를 보려면 [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)   
 [메시지 맵](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

