---
title: NotifyHandler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72c6c992f2ec92bc11d6dd009649d503d3c0bd02
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848339"
---
# <a name="notifyhandler"></a>NotifyHandler
메시지 맵에서 NOTIFY_HANDLER 매크로의 세 번째 매개 변수로 식별 된 함수의 이름입니다.  
  
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
 *idCtrl*  
 메시지를 전송 하는 컨트롤의 식별자입니다.  
  
 *pnmh*  
 주소는 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) 알림 코드 및 추가 정보를 포함 하는 구조입니다. 일부 알림 메시지의 경우이 매개 변수가 가리키는 있는 더 큰 구조체는 `NMHDR` 첫 번째 멤버로 구조체입니다.  
  
 *bHandled*  
 메시지 맵 집합 *bHandled* 하기 전에 true *NotifyHandler* 라고 합니다. 경우 *NotifyHandler* 메시지를 완전히 처리 하지 않는 설정 해야 *bHandled* 에 **FALSE** 를 나타내는 메시지에 추가 처리가 필요 합니다.  
  
## <a name="return-value"></a>반환 값  
 메시지 처리의 결과입니다. 성공한 경우 0입니다.  
  
## <a name="remarks"></a>설명  
 메시지 맵에서이 메시지 처리기를 사용 하 여 예제를 참조 하세요 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler)).  
  
## <a name="see-also"></a>참고 항목  
 [창 구현](../atl/implementing-a-window.md)   
 [메시지 맵](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

