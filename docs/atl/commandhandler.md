---
title: CommandHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CommandHandler
dev_langs:
- C++
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 784551b090f7c0c73b96b846fcc8d74017cc1e30
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850643"
---
# <a name="commandhandler"></a>CommandHandler
`CommandHandler` 메시지 맵에 COMMAND_HANDLER 매크로의 세 번째 매개 변수로 식별 된 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
    LRESULT 
    CommandHandler 
 (
    WORD wNotifyCode,  
    WORD wID,  
    HWND hWndCtl,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>매개 변수  
 *wNotifyCode*  
 알림 코드입니다.  
  
 *wID*  
 메뉴 항목, 컨트롤 또는 액셀러레이터 키의 식별자입니다.  
  
 *hWndCtl*  
 창 컨트롤에 대 한 핸들입니다.  
  
 *bHandled*  
 메시지 맵 집합 *bHandled* 하기 전에 true `CommandHandler` 라고 합니다. 경우 `CommandHandler` 메시지를 완전히 처리 하지 않는 설정 해야 *bHandled* 에 FALSE를 메시지에 추가 처리가 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메시지 처리의 결과입니다. 성공한 경우 0입니다.  
  
## <a name="remarks"></a>설명  
 메시지 맵에서이 메시지 처리기를 사용 하 여 예제를 참조 하세요 [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)   
 [메시지 맵](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

