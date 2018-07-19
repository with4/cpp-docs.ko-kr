---
title: MessageHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dcd02396fa76e9e68fce628783fb17bc6adab36e
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848404"
---
# <a name="messagehandler"></a>MessageHandler
`MessageHandler` 메시지 맵에서 MESSAGE_HANDLER 매크로의 두 번째 매개 변수로 식별 된 함수의 이름이입니다.  
  
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
 *uMsg*  
 메시지를 지정합니다.  
  
 *wParam*  
 추가 메시지 관련 정보입니다.  
  
 *lParam*  
 추가 메시지 관련 정보입니다.  
  
 *bHandled*  
 메시지 맵 집합 *bHandled* 하기 전에 true `MessageHandler` 라고 합니다. 경우 `MessageHandler` 메시지를 완전히 처리 하지 않는 설정 해야 *bHandled* 에 FALSE를 메시지에 추가 처리가 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메시지 처리의 결과입니다. 성공한 경우 0입니다.  
  
## <a name="remarks"></a>설명  
 메시지 맵에서이 메시지 처리기를 사용 하 여 예제를 참조 하세요 [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)   
 [메시지 맵](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

