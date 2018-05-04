---
title: Windows 메시지 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::WM_FORWARDMSG
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21bb273b94f871e253ab927238c96256f46e2b3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="windows-messages-macros"></a>Windows 메시지 매크로
이 매크로 창 메시지를 전달합니다.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|사용 하 여 처리를 위해 다른 창으로 창에서 수신 된 메시지를 전달 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h 
   
##  <a name="wm_forwardmsg"></a>  WM_FORWARDMSG  
 이 매크로 처리를 위해 다른 창으로 창에서 수신 된 메시지를 전달 합니다.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>반환 값  
 0이 아니고 그렇지 않으면 메시지를 처리 하는 경우 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `WM_FORWARDMSG` 처리를 위해 다른 창으로 창에서 수신 된 메시지를 전달 하도록 합니다. LPARAM 및 WPARAM 매개 변수는 다음과 같이 사용 됩니다.  
  
|매개 변수|사용법|  
|---------------|-----------|  
|WPARAM|사용자가 정의 된 데이터|  
|LPARAM|에 대 한 포인터는 `MSG` 메시지에 대 한 정보가 포함 된 구조체|  
  
### <a name="example"></a>예제  
 다음 예에서 `m_hWndOther` 이 메시지를 수신 하는 다른 창을 나타냅니다.  
  
 [!code-cpp[NVC_ATL_Windowing#137](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)
