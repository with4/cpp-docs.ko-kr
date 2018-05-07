---
title: 이벤트 싱크 맵 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event sink maps [MFC]
ms.assetid: a9757eb2-5f4a-45ec-a2cd-ce5eec85b16f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ababaab7324d712457f6411ed731274ea361084b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="event-sink-maps"></a>이벤트 싱크 맵
포함 된 OLE 컨트롤 이벤트를 발생 시킬 때 컨트롤의 컨테이너 라고는 이벤트 싱크 맵"" MFC에서 제공 하는 메커니즘을 사용 하 여 이벤트를 받습니다. 이 이벤트 싱크 맵 이러한 이벤트의 매개 변수 뿐만 아니라 각 특정 이벤트에 대 한 처리기 함수를 지정합니다. 이벤트 싱크 맵에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤 컨테이너](../../mfc/activex-control-containers.md)합니다.  
  
### <a name="event-sink-maps"></a>이벤트 싱크 맵  
  
|||  
|-|-|  
|[BEGIN_EVENTSINK_MAP](#begin_eventsink_map)|이벤트 싱크 맵 정의 시작 합니다.|  
|[DECLARE_EVENTSINK_MAP](#declare_eventsink_map)|이벤트 싱크 맵을 선언합니다.|  
|[END_EVENTSINK_MAP](#end_eventsink_map)|이벤트 싱크 맵 정의 종료합니다.|  
|[ON_EVENT](#on_event)|특정 이벤트에 대 한 이벤트 처리기를 정의합니다.|  
|[ON_EVENT_RANGE](#on_event_range)|OLE 컨트롤의 집합에서 발생 하는 특정 이벤트에 대 한 이벤트 처리기를 정의 합니다.|  
|[ON_EVENT_REFLECT](#on_event_reflect)|컨트롤의 컨테이너에 의해 처리 전에 컨트롤에서 발생 하는 이벤트를 받습니다.|  
|[ON_PROPNOTIFY](#on_propnotify)|OLE 컨트롤에서 알림 속성 처리에 대 한 처리기를 정의 합니다.|  
|[ON_PROPNOTIFY_RANGE](#on_propnotify_range)|OLE 컨트롤의 집합에서 속성 알림 처리에 대 한 처리기를 정의 합니다.|  
|[ON_PROPNOTIFY_REFLECT](#on_propnotify_reflect)|컨트롤의 컨테이너에 의해 처리 전에 컨트롤에 의해 전송 속성 알림을 수신 합니다.|  
  
##  <a name="begin_eventsink_map"></a>  BEGIN_EVENTSINK_MAP  
 이벤트 싱크 맵 정의 시작 합니다.  
  
```   
BEGIN_EVENTSINK_MAP(theClass, baseClass)  
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 싱크를 매핑할 컨트롤 클래스의 이름을 지정 합니다.  
  
 `baseClass`  
 `theClass`의 기본 클래스 이름을 지정합니다.  
  
### <a name="remarks"></a>설명  
 클래스 멤버 함수를 정의 하는 구현 (.cpp) 파일에서와 이벤트 싱크 맵 시작는 `BEGIN_EVENTSINK_MAP` 매크로 다음에 알릴, 각 이벤트에 대해 매크로 항목을 추가 하 고 완료로 이벤트 싱크 맵은 `END_EVENTSINK_MAP` 매크로입니다.  
  
 이벤트 싱크 맵 및 OLE 컨트롤 컨테이너에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤 컨테이너](../../mfc/activex-control-containers.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="declare_eventsink_map"></a>  DECLARE_EVENTSINK_MAP  
 OLE 컨테이너 이벤트 컨테이너 알림을 지정 하는 이벤트 싱크 맵을 제공할 수 있습니다.  
  
```   
DECLARE_EVENTSINK_MAP()   
```  
  
### <a name="remarks"></a>설명  
 사용 하 여는 `DECLARE_EVENTSINK_MAP` 끝 클래스 선언에는 매크로입니다. 그런 다음는 합니다. 사용 하 여, 클래스에 대 한 멤버를 정의 하는 CPP 파일 함수는 `BEGIN_EVENTSINK_MAP` 매크로, 각 이벤트의 알림을 받을 수에 대해 매크로 항목 및 `END_EVENTSINK_MAP` 이벤트 싱크 목록의 끝을 선언 하는 매크로입니다.  
  
 이벤트 싱크 맵에 대 한 자세한 내용은 문서 참조 [ActiveX 컨트롤 컨테이너](../../mfc/activex-control-containers.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="end_eventsink_map"></a>  END_EVENTSINK_MAP  
 이벤트 싱크 맵 정의 끝냅니다.  
  
```   
END_EVENTSINK_MAP()   
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="on_event"></a>  ON_EVENT  
 사용 된 `ON_EVENT` 매크로 이벤트에 대 한 이벤트 처리기 함수를 정의 하는 OLE 컨트롤에 의해 발생 합니다.  
  
```   
ON_EVENT(theClass, id, dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 싱크 맵 속해 있는 클래스입니다.  
  
 `id`  
 OLE 컨트롤의 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤에 의해 발생 한 이벤트의 한 디스패치 ID입니다.  
  
 `pfnHandler`  
 이벤트를 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수에 있어야는 **BOOL** 반환 형식 및 이벤트의 매개 변수와 일치 하는 매개 변수 형식 (참조 `vtsParams`). 함수 반환 해야 **TRUE** 이벤트 었 고, 그렇지 않으면 처리를 나타내기 위해 **FALSE**합니다.  
  
 `vtsParams`  
 시퀀스 **VTS_** 이벤트에 대 한 매개 변수 유형을 지정 하는 상수입니다. 와 같은 디스패치 맵 항목에 사용 되는 동일한 상수 이들은 `DISP_FUNCTION`합니다.  
  
### <a name="remarks"></a>설명  
 `vtsParams` 인수는 공백으로 구분 된 목록에서 값의 **VTS_** 상수입니다. 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 short 정수 뒤에 포함 된 목록을 지정 합니다.는 **BOOL**합니다.  
  
 목록은 **VTS_** 상수 참조 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="on_event_range"></a>  ON_EVENT_RANGE  
 사용 하 여 `ON_EVENT_RANGE` 연속 Id 범위 내에서 컨트롤 ID를 가진 모든 OLE 컨트롤에서 발생 시킨 이벤트에 대 한 이벤트 처리기 함수를 정의 하는 매크로입니다.  
  
```   
ON_EVENT_RANGE(theClass, idFirst, idLast, dispid, pfnHandler,  vtsParams)   
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 싱크 맵 속해 있는 클래스입니다.  
  
 `idFirst`  
 범위에서 첫 번째 OLE 컨트롤의 컨트롤 ID입니다.  
  
 `idLast`  
 범위에서 마지막 OLE 컨트롤의 컨트롤 ID입니다.  
  
 `dispid`  
 컨트롤에 의해 발생 한 이벤트의 한 디스패치 ID입니다.  
  
 `pfnHandler`  
 이벤트를 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수에 있어야는 **BOOL** 반환 형식, 형식 매개 변수가 첫 번째 **UINT** (컨트롤 ID)에 대 한 및 이벤트의 매개 변수와 일치 하는 추가 매개 변수 형식 (참조 `vtsParams`). 함수 반환 해야 **TRUE** 이벤트 었 고, 그렇지 않으면 처리를 나타내기 위해 **FALSE**합니다.  
  
 `vtsParams`  
 시퀀스 **VTS_** 이벤트에 대 한 매개 변수 유형을 지정 하는 상수입니다. 첫 번째 상수 유형 이어야 **VTS_I4**, 컨트롤 id 와 같은 디스패치 맵 항목에 사용 되는 동일한 상수 이들은 `DISP_FUNCTION`합니다.  
  
### <a name="remarks"></a>설명  
 `vtsParams` 인수는 공백으로 구분 된 목록에서 값의 **VTS_** 상수입니다. 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 short 정수 뒤에 포함 된 목록을 지정 합니다.는 **BOOL**합니다.  
  
 목록은 **VTS_** 상수 참조 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 세 가지 컨트롤에 대 한 구현 MouseDown 이벤트에 대 한 이벤트 처리기를 보여 줍니다 ( `IDC_MYCTRL1` 통해 `IDC_MYCTRL3`). 이벤트 처리기 함수 `OnRangeMouseDown`, 대화 상자 클래스의 헤더 파일에서 선언 됩니다 ( `CMyDlg`)로:  
  
 [!code-cpp[NVC_MFCAutomation#12](../../mfc/codesnippet/cpp/event-sink-maps_2.h)]  
  
 아래 코드는 대화 상자 클래스의 구현 파일에 정의 됩니다.  
  
 [!code-cpp[NVC_MFCAutomation#13](../../mfc/codesnippet/cpp/event-sink-maps_3.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="on_event_reflect"></a>  ON_EVENT_REFLECT  
 `ON_EVENT_REFLECT` 매크로 사용 이벤트 싱크 맵 OLE 컨트롤의 래퍼 클래스의 경우 컨트롤의 컨테이너에 의해 처리 전에 컨트롤에서 발생 하는 이벤트를 수신 합니다.  
  
```   
ON_EVENT_REFLECT(theClass,  dispid, pfnHandler,  vtsParams) 
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 싱크 맵 속해 있는 클래스입니다.  
  
 dispid  
 컨트롤에 의해 발생 한 이벤트의 한 디스패치 ID입니다.  
  
 `pfnHandler`  
 이벤트를 처리 하는 멤버 함수에 대 한 포인터입니다. 이 함수에 있어야는 **BOOL** 반환 형식 및 이벤트의 매개 변수와 일치 하는 매개 변수 형식 (참조 `vtsParams`). 함수 반환 해야 **TRUE** 이벤트 었 고, 그렇지 않으면 처리를 나타내기 위해 **FALSE**합니다.  
  
 `vtsParams`  
 시퀀스 **VTS_** 이벤트에 대 한 매개 변수 유형을 지정 하는 상수입니다. 와 같은 디스패치 맵 항목에 사용 되는 동일한 상수 이들은 `DISP_FUNCTION`합니다.  
  
### <a name="remarks"></a>설명  
 `vtsParams` 인수는 공백으로 구분 된 목록에서 값의 **VTS_** 상수입니다.  
  
 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 short 정수 뒤에 포함 된 목록을 지정 합니다.는 **BOOL**합니다.  
  
 목록은 **VTS_** 상수 참조 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="on_propnotify"></a>  ON_PROPNOTIFY  
 사용 하 여는 `ON_PROPNOTIFY` OLE 컨트롤에서 알림 속성 처리에 대 한 이벤트 싱크 맵 항목을 정의 하는 매크로입니다.  
  
```   
ON_PROPNOTIFY(theClass, id, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 싱크 맵 속해 있는 클래스입니다.  
  
 `id`  
 OLE 컨트롤의 컨트롤 ID입니다.  
  
 `dispid`  
 알림 영역에서 관련 된 속성의 디스패치 ID입니다.  
  
 `pfnRequest`  
 처리 하는 멤버 함수에 대 한 포인터는 **OnRequestEdit** 이 속성에 대 한 알림입니다. 이 함수에 있어야는 **BOOL** 반환 형식 및 **BOOL\***  매개 변수입니다. 이 함수는 매개 변수를 설정 해야 **TRUE** 속성을 변경 하 고 **FALSE** 허용 되지 않습니다. 함수 반환 해야 **TRUE** 알림을 었 고, 그렇지 않으면 처리를 나타내기 위해 **FALSE**합니다.  
  
 `pfnChanged`  
 처리 하는 멤버 함수에 대 한 포인터는 **OnChanged** 이 속성에 대 한 알림입니다. 함수에 있어야는 **BOOL** 반환 형식 및 **UINT** 매개 변수입니다. 함수 반환 해야 **TRUE** 알림을 처리 하지 않으면 나타내는 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 `vtsParams` 인수는 공백으로 구분 된 목록에서 값의 **VTS_** 상수입니다. 공백 (쉼표가 아님)으로 구분 된 이러한 값 중 하나 이상이 함수의 매개 변수 목록을 지정 합니다. 예를 들어:  
  
 [!code-cpp[NVC_MFCAutomation#11](../../mfc/codesnippet/cpp/event-sink-maps_1.cpp)]  
  
 short 정수 뒤에 포함 된 목록을 지정 합니다.는 **BOOL**합니다.  
  
 목록은 **VTS_** 상수 참조 [EVENT_CUSTOM](event-maps.md#event_custom)합니다.  
  
##  <a name="on_propnotify_range"></a>  ON_PROPNOTIFY_RANGE  
 사용 하 여는 `ON_PROPNOTIFY_RANGE` 연속 Id 범위 내에서 컨트롤 ID를 가진 OLE 컨트롤에서 알림 속성 처리에 대 한 이벤트 싱크 맵 항목을 정의 하는 매크로입니다.  
  
```  
 
ON_PROPNOTIFY_RANGE(theClass, idFirst, idLast, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 싱크 맵 속해 있는 클래스입니다.  
  
 `idFirst`  
 범위에서 첫 번째 OLE 컨트롤의 컨트롤 ID입니다.  
  
 `idLast`  
 범위에서 마지막 OLE 컨트롤의 컨트롤 ID입니다.  
  
 `dispid`  
 알림 영역에서 관련 된 속성의 디스패치 ID입니다.  
  
 `pfnRequest`  
 처리 하는 멤버 함수에 대 한 포인터는 **OnRequestEdit** 이 속성에 대 한 알림입니다. 이 함수에 있어야는 **BOOL** 반환 형식 및 **UINT** 및 **BOOL\***  매개 변수입니다. 함수는 매개 변수를 설정 해야 **TRUE** 속성을 변경 하 고 **FALSE** 허용 되지 않습니다. 함수 반환 해야 **TRUE** 알림을 처리 하지 않으면 나타내는 **FALSE**합니다.  
  
 `pfnChanged`  
 처리 하는 멤버 함수에 대 한 포인터는 **OnChanged** 이 속성에 대 한 알림입니다. 함수에 있어야는 **BOOL** 반환 형식 및 **UINT** 매개 변수입니다. 함수 반환 해야 **TRUE** 알림을 처리 하지 않으면 나타내는 **FALSE**합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
  
##  <a name="on_propnotify_reflect"></a>  ON_PROPNOTIFY_REFLECT  
 `ON_PROPNOTIFY_REFLECT` 매크로 사용 이벤트 싱크 맵 OLE 컨트롤의 래퍼 클래스의 경우 컨트롤의 컨테이너에 의해 처리 전에 컨트롤에서 전송 하는 속성 알림을 받습니다.  
  
```  
 
ON_PROPNOTIFY_REFLECT(theClass, dispid, pfnRequest, pfnChanged)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 싱크 맵 속해 있는 클래스입니다.  
  
 `dispid`  
 알림 영역에서 관련 된 속성의 디스패치 ID입니다.  
  
 `pfnRequest`  
 처리 하는 멤버 함수에 대 한 포인터는 **OnRequestEdit** 이 속성에 대 한 알림입니다. 이 함수에 있어야는 **BOOL** 반환 형식 및 **BOOL\***  매개 변수입니다. 이 함수는 매개 변수를 설정 해야 **TRUE** 속성을 변경 하 고 **FALSE** 허용 되지 않습니다. 함수 반환 해야 **TRUE** 알림을 었 고, 그렇지 않으면 처리를 나타내기 위해 **FALSE**합니다.  
  
 `pfnChanged`  
 처리 하는 멤버 함수에 대 한 포인터는 **OnChanged** 이 속성에 대 한 알림입니다. 함수에 있어야는 **BOOL** 형식 및 매개 변수 없이 반환 합니다. 함수 반환 해야 **TRUE** 알림을 었 고, 그렇지 않으면 처리를 나타내기 위해 **FALSE**합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdisp.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)
