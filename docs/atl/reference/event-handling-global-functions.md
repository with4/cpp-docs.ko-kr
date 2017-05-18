---
title: "전역 함수를 처리 하는 이벤트 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- event handling, global functions
- global functions, event handling
ms.assetid: fd674470-3def-47c3-be1c-894fa85f13e8
caps.latest.revision: 20
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4bf2a8b0211361f5d5d2bf0f996e978638631116
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="event-handling-global-functions"></a>이벤트 처리에 대 한 전역 함수
이 함수는 이벤트 처리기를 제공합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수에서 실행 되는 응용 프로그램에서 사용할 수는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]합니다.  
  
|||  
|-|-|  
|[AtlWaitWithMessageLoop](#atlwaitwithmessageloop)|한편 필요에 따라 창 메시지를 디스패치 개체가 신호를 받는 동안 대기 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

##  <a name="atlwaitwithmessageloop"></a>AtlWaitWithMessageLoop  
 필요에 따라 창 메시지를 디스패치하는 중에 개체가 신호를 받는 동안 대기합니다.  
  
> [!IMPORTANT]
>  이 함수에서 실행 되는 응용 프로그램에서 사용할 수 없습니다는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]합니다.  
  
```
BOOL AtlWaitWithMessageLoop(HANDLE hEvent);
```  
  
### <a name="parameters"></a>매개 변수  
 `hEvent`  
 [in] 대기 하는 개체의 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 개체가 신호를 받은 경우.  
  
### <a name="remarks"></a>주의  
 개체의 이벤트를 수행 하 고 발생 하 고, 알림을 받을 때까지 대기 하 긴 하지만 창 메시지를 대기 하는 동안 디스패치할 수 있도록 하는 경우에 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)

