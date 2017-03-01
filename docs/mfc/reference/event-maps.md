---
title: "이벤트 맵 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event maps
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
caps.latest.revision: 15
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
translationtype: Machine Translation
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 4c4777496ce609d7c2fa20da726f211264095b6e
ms.lasthandoff: 02/24/2017

---
# <a name="event-maps"></a>이벤트 맵
컨트롤 컨테이너 (예: 키, 마우스 클릭 또는 컨트롤의 상태에 대 한 변경) 발생 하는 일부 동작 (컨트롤 개발자가 결정 됨)에 게 알림 하려는 때마다 이벤트 발생 함수를 호출 합니다. 이 함수는 관련된 이벤트를 발생 시켜 서 중요 한 몇 가지 동작이 발생 하는 컨트롤 컨테이너를 알립니다.  
  
 Microsoft Foundation Class 라이브러리는 이벤트를 발생 시키기 위한 최적화 된 프로그래밍 모델을 제공 합니다. 이 모델에서 "이벤트 맵" 특정 컨트롤에 대 한 어떤 이벤트를 발생 하는 함수를 지정 하는 데 사용 됩니다. 이벤트 맵 각 이벤트에 대 한 매크로 포함합니다. 예를 들어 이벤트 맵의 발행 주식 클릭 이벤트는 다음과 같을 수 있습니다.  
  
 [!code-cpp[NVC_MFCAxCtl #&16;](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]  
  
 **EVENT_STOCK_CLICK** 매크로 나타냅니다 컨트롤 클릭 마우스 감지 될 때마다 이벤트를 클릭 하 여 주식을 발생 합니다. 다른 스톡 이벤트 목록이 더 자세한 문서를 참조 하십시오. [ActiveX 컨트롤: 이벤트](../../mfc/mfc-activex-controls-events.md)합니다. 매크로 사용자 지정 이벤트를 나타내는 데 사용할 수 있습니다.  
  
 이벤트 맵 매크로 중요 하지만, 일반적으로 삽입 하지 않으면 이러한 직접. 즉, 속성 창을 사용 하면 이벤트와 이벤트 발생 함수를 연결할 때 소스 파일에서 이벤트 맵 항목 자동으로 만듭니다. 언제 든 지 편집 하거나 이벤트 맵 항목을 추가 하려면 속성 창을 사용할 수 있습니다.  
  
 이벤트 맵을 지원 하기 위해 MFC는 다음과 같은 매크로 제공 합니다.  
  
### <a name="event-map-declaration-and-demarcation"></a>이벤트 맵 선언 및 구분  
  
|||  
|-|-|  
|[DECLARE_EVENT_MAP](#declare_event_map)|이벤트 맵 (클래스 선언에 사용 해야 합니다) 이벤트 발생 함수에 이벤트를 매핑할 클래스에서 사용될지를 선언 합니다.|  
|[BEGIN_EVENT_MAP](#begin_event_map)|이벤트 맵 (클래스 구현에 사용 해야 합니다) 정의 시작 합니다.|  
|[END_EVENT_MAP](#end_event_map)|이벤트 맵 (클래스 구현에 사용 해야 합니다) 정의 끝냅니다.|  
  
### <a name="event-mapping-macros"></a>이벤트 매핑 매크로  
  
|||  
|-|-|  
|[EVENT_CUSTOM](#event_custom)|이벤트 발생 함수는 지정된 된 이벤트 발생을 나타냅니다.|  
|[EVENT_CUSTOM_ID](#event_custom_id)|이벤트 발생 함수는 지정 된 디스패치 ID 가진 지정된 된 이벤트를 발생을 나타냅니다.|  
  
### <a name="message-mapping-macros"></a>메시지 매핑 매크로  
  
|||  
|-|-|  
|[ON_OLEVERB](#on_oleverb)|OLE 컨트롤에서 처리 하는 사용자 지정 동사를 나타냅니다.|  
|[ON_STDOLEVERB](#on_stdoleverb)|OLE 컨트롤의 표준 동사 매핑을 재정의합니다.|  
  
##  <a name="a-namedeclareeventmapa--declareeventmap"></a><a name="declare_event_map"></a>DECLARE_EVENT_MAP  
 각 `COleControl`-프로그램의 파생된 클래스에서 컨트롤 발생 하는 이벤트를 지정 하기 위해 이벤트 맵을 제공할 수 있습니다.  
  
```   
DECLARE_EVENT_MAP()   
```  
  
### <a name="remarks"></a>주의  
 사용 하는 `DECLARE_EVENT_MAP` 클래스 선언 후에는 매크로입니다. 그런 다음 클래스 멤버 함수를 정의 하는.cpp 파일에서 사용 하는 `BEGIN_EVENT_MAP` 매크로, 각 컨트롤의 이벤트에 대해 매크로 항목 및 `END_EVENT_MAP` 이벤트 목록의 끝을 선언 하는 매크로입니다.  
  
 이벤트 맵에 대 한 자세한 내용은 문서를 참조 하십시오. [ActiveX 컨트롤: 이벤트](../../mfc/mfc-activex-controls-events.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-namebegineventmapa--begineventmap"></a><a name="begin_event_map"></a>BEGIN_EVENT_MAP  
 이벤트 맵 정의 시작합니다.  
  
```   
BEGIN_EVENT_MAP(theClass,  baseClass)  
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 이 이벤트 매핑할 컨트롤 클래스의 이름을 지정 합니다.  
  
 `baseClass`  
 `theClass`의 기본 클래스 이름을 지정합니다.  
  
### <a name="remarks"></a>주의  
 클래스 멤버 함수를 정의 하는 구현 (.cpp) 파일에서 이벤트 맵을 시작한는 `BEGIN_EVENT_MAP` 매크로, 그런 다음 각 사용자 이벤트에 대해 매크로 항목을 추가 하 고 사용 하 여 이벤트 맵을 완료는 `END_EVENT_MAP` 매크로입니다.  
  
 이벤트에 대 한 자세한 내용은 맵 및 `BEGIN_EVENT_MAP` 매크로 문서를 참조 하십시오 [ActiveX 컨트롤: 이벤트](../../mfc/mfc-activex-controls-events.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-nameendeventmapa--endeventmap"></a><a name="end_event_map"></a>END_EVENT_MAP  
 사용 된 `END_EVENT_MAP` 이벤트 맵의 정의 종료 하는 매크로입니다.  
  
```   
END_EVENT_MAP()   
```  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-nameeventcustoma--eventcustom"></a><a name="event_custom"></a>EVENT_CUSTOM  
 사용자 지정 이벤트에 대 한 이벤트 맵 항목을 정의합니다.  
  
```   
EVENT_CUSTOM(pszName, pfnFire,  vtsParams) 
```  
  
### <a name="parameters"></a>매개 변수  
 `pszName`  
 이벤트의 이름입니다.  
  
 `pfnFire`  
 함수를 실행 하는 이벤트의 이름입니다.  
  
 `vtsParams`  
 함수의 매개 변수 목록을 지정 하는 하나 이상의 상수 공백으로 구분 된 목록입니다.  
  
### <a name="remarks"></a>주의  
 `vtsParams` 매개 변수는 값을 공백으로 구분 된 목록이 **VTS_** 상수입니다. (쉼표) 공백으로 구분 하 여 이러한 값 중 하나 이상이 있는 함수의 매개 변수 목록을 지정 합니다. 예:  
  
 [!code-cpp[NVC_MFCActiveXControl #&13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 RGB 나타내는 32 비트 정수를 포함 하는 목록을 색상 값에 대 한 포인터 뒤 지정는 **IFontDisp** OLE 글꼴 개체의 인터페이스입니다.  
  
 **VTS_** 상수 및 그 의미는 다음과 같습니다.  
  
|기호|매개 변수 형식|  
|------------|--------------------|  
|**VTS_I2**|**short**|  
|**VTS_I4**|**long**|  
|**VTS_R4**|**float**|  
|**VTS_R8**|**double**|  
|**VTS_COLOR**|**OLE_COLOR**|  
|**VTS_CY**|**통화**|  
|**VTS_DATE**|**날짜**|  
|**VTS_BSTR**|**const char\***|  
|**VTS_DISPATCH**|`LPDISPATCH`|  
|**VTS_FONT**|**IFontDispatch\***|  
|**VTS_HANDLE**|`HANDLE`|  
|**VTS_SCODE**|`SCODE`|  
|**VTS_BOOL**|**BOOL**|  
|**VTS_VARIANT**|**const VARIANT\***|  
|**VTS_PVARIANT**|**VARIANT\***|  
|**VTS_UNKNOWN**|`LPUNKNOWN`|  
|**VTS_OPTEXCLUSIVE**|**OLE_OPTEXCLUSIVE**|  
|**VTS_PICTURE**|**IPictureDisp\***|  
|**VTS_TRISTATE**|**OLE_TRISTATE**|  
|**VTS_XPOS_PIXELS**|**OLE_XPOS_PIXELS**|  
|**VTS_YPOS_PIXELS**|**OLE_YPOS_PIXELS**|  
|**VTS_XSIZE_PIXELS**|**OLE_XSIZE_PIXELS**|  
|**VTS_YSIZE_PIXELS**|**OLE_YSIZE_PIXELS**|  
|**VTS_XPOS_HIMETRIC**|**OLE_XPOS_HIMETRIC**|  
|**VTS_YPOS_HIMETRIC**|**OLE_YPOS_HIMETRIC**|  
|**VTS_XSIZE_HIMETRIC**|**OLE_XSIZE_HIMETRIC**|  
|**VTS_YSIZE_HIMETRIC**|**OLE_YSIZE_HIMETRIC**|  
  
> [!NOTE]
>  추가 variant 상수 제외한 모든 variant 형식에 대해 정의 된 **VTS_FONT** 및 **VTS_PICTURE**, 가변 데이터 상수에 대 한 포인터를 제공 하는 합니다. 이러한 상수는를 사용 하 여 이름이 지정 된 **VTS_P** `constantname` 규칙입니다. 예를 들어 **VTS_PCOLOR** 에 대 한 포인터는 **VTS_COLOR** 상수입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-nameeventcustomida--eventcustomid"></a><a name="event_custom_id"></a>EVENT_CUSTOM_ID  
 이벤트 발생 하 여 지정 된 디스패치 ID에 속하는 사용자 지정 이벤트에 대 한 함수 정의 `dispid`합니다.  
  
```   
EVENT_CUSTOM_ID(
  pszName,   
  dispid,   
  pfnFire,
  vtsParams)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `pszName`  
 이벤트의 이름입니다.  
  
 `dispid`  
 이벤트를 발생 하는 경우 컨트롤에서 사용 하는 디스패치 ID입니다.  
  
 `pfnFire`  
 함수를 실행 하는 이벤트의 이름입니다.  
  
 `vtsParams`  
 이벤트가 발생 하는 경우 컨트롤 컨테이너에 전달 된 매개 변수 목록.  
  
### <a name="remarks"></a>주의  
 `vtsParams` 인수는 공백으로 구분 된 목록에서 값의 **VTS_** 상수입니다. 쉼표가 아닌 공백으로 구분 된 다음이 값 중 하나 이상을 함수의 매개 변수 목록을 지정 합니다. 예:  
  
 [!code-cpp[NVC_MFCActiveXControl #&13;](../../mfc/codesnippet/cpp/event-maps_2.cpp)]  
  
 RGB 나타내는 32 비트 정수를 포함 하는 목록을 색상 값에 대 한 포인터 뒤 지정는 **IFontDisp** OLE 글꼴 개체의 인터페이스입니다.  
  
 목록에 대해서는 **VTS_** 상수 참조 [EVENT_CUSTOM](#event_custom)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxctl.h  
  
##  <a name="a-nameonoleverba--onoleverb"></a><a name="on_oleverb"></a>ON_OLEVERB  
 이 매크로 사용자 지정 동사 컨트롤의 특정 멤버 함수에 매핑되는 메시지 맵 항목을 정의 합니다.  
  
```   
ON_OLEVERB(idsVerbName,  memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 *idsVerbName*  
 동사 이름의 문자열 리소스 ID입니다.  
  
 `memberFxn`  
 동사를 호출할 때 프레임 워크에서 호출 하는 함수입니다.  
  
### <a name="remarks"></a>주의  
 리소스 편집기 문자열 테이블에 추가 된 사용자 지정 동사 이름을 만드는 데 사용할 수 있습니다.  
  
 함수 프로토타입이 `memberFxn` 됩니다.  
  
 `BOOL memberFxn(`    
 `LPMSG` `lpMsg` `,`   
 `HWND` `hWndParent` `,`   
 `LPCRECT` `lpRect`   `);`  
  
 값은 `lpMsg`, `hWndParent`, 및 `lpRect` 매개 변수는 해당 매개 변수에서 가져온 것는 **IOleObject::DoVerb** 멤버 함수입니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxole.h  
  
##  <a name="a-nameonstdoleverba--onstdoleverb"></a><a name="on_stdoleverb"></a>ON_STDOLEVERB  
 이 매크로 사용 하 여 표준 동사의 기본 동작을 재정의 합니다.  
  
```   
ON_STDOLEVERB(iVerb,   memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `iVerb`  
 재정의 되는 동사에 대 한 표준 동사 인덱스입니다.  
  
 `memberFxn`  
 동사를 호출할 때 프레임 워크에서 호출 하는 함수입니다.  
  
### <a name="remarks"></a>주의  
 폼의 표준 동사 인덱스는 **OLEIVERB_**동작 뒤따릅니다. `OLEIVERB_SHOW``OLEIVERB_HIDE`, 및 `OLEIVERB_UIACTIVATE` 은 표준 동사 중 몇 가지 예입니다.  
  
 참조 [ON_OLEVERB](#on_oleverb) 에 대 한 설명은로 사용할 함수 프로토타입에 `memberFxn` 매개 변수입니다.  

  
### <a name="requirements"></a>요구 사항  
  **헤더** afxole.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

