---
title: 전역 함수를 처리 하는 이벤트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85babf3155fdc94dafd5d62c2e67401e5add3663
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884001"
---
# <a name="event-handling-global-functions"></a>이벤트 처리 전역 함수
이 함수는 이벤트 처리기를 제공합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|필요에 따라 창 메시지를 디스패치 개체에 신호를 기다립니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>  AtlWaitWithMessageLoop  
 필요에 따라 창 메시지를 디스패치하는 중에 개체가 신호를 받는 동안 대기합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>매개 변수  
 *hEvent*  
 [in] 대기할 개체의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 신호를 받은 경우 TRUE를 반환 합니다.  
  
### <a name="remarks"></a>설명  
 개체의 이벤트를 발생 하 고 발생 하 고 알림을 받을 때까지 대기 하 긴 하지만 창 메시지를 대기 하는 동안 디스패치할 수를 허용 하는 경우에 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)
