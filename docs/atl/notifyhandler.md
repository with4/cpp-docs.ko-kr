---
title: NotifyHandler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f2b7e1825e7192c6a9afa105aeb3a7436f120c1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="notifyhandler"></a>NotifyHandler
세 번째 매개 변수에 의해 식별 된 함수 이름에서 `NOTIFY_HANDLER` 메시지 맵에서 매크로입니다.  
  
## <a name="syntax"></a>구문  
  
```  
 
    LRESULT 
    NotifyHandler 
 (
    int idCtrl,  
    LPNMHDR pnmh,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>매개 변수  
 `idCtrl`  
 메시지를 전송 하는 컨트롤의 식별자입니다.  
  
 *pnmh*  
 주소는 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) 알림 코드 및 추가 정보를 포함 하는 구조입니다. 일부 알림 메시지에 대 한이 매개 변수는 큰 구조체를 가리키는 **NMHDR** 첫 번째 멤버로 구조입니다.  
  
 `bHandled`  
 메시지 맵 집합 `bHandled` 를 **TRUE** 전에 *NotifyHandler* 호출 됩니다. 경우 *NotifyHandler* 메시지를 완전히 처리 하지 않는 설정 해야 `bHandled` 를 **FALSE** 를 나타내는 메시지에 추가 처리가 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메시지 처리의 결과입니다. 성공 하면 0입니다.  
  
## <a name="remarks"></a>설명  
 이 메시지 처리기를 사용 하 여 메시지 맵에서 예제를 보려면 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)   
 [메시지 맵](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

