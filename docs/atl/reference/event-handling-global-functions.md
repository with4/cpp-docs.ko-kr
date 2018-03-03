---
title: "전역 함수를 처리 하는 이벤트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlWaitWithMessageLoop
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6670ef283d24f57b407ad70693421feae427855f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling-global-functions"></a>이벤트 처리 전역 함수
이 함수는 이벤트 처리기를 제공합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|필요에 따라 창 메시지를 디스패치 한편 신호를 받을 개체에 대 한 대기 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 필요에 따라 창 메시지를 디스패치하는 중에 개체가 신호를 받는 동안 대기합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>매개 변수  
 `hEvent`  
 [in] 에 대 한 대기 하는 개체의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 개체가 신호를 받은 경우.  
  
### <a name="remarks"></a>설명  
 개체의 이벤트가 발생 하지 않으며 발생 하 고 알림을 받을 때까지 대기 하려고 하지만 창 메시지를 대기 하는 동안 디스패치할 수를 허용 하는 경우에 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)
