---
title: "DHTML 이벤트 맵 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.macros.shared
dev_langs:
- C++
helpviewer_keywords:
- event map macros
- DHTML, event map macros
- macros, DHTML event map
- DHTML events, event map
- DHTML events
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
caps.latest.revision: 14
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
ms.openlocfilehash: 8be59b52e06241651a2f605ab949efffd0e010d3
ms.lasthandoff: 02/24/2017

---
# <a name="dhtml-event-maps"></a>DHTML 이벤트 맵
DHTML 이벤트를 처리 하는 다음과 같은 매크로 사용할 수 있습니다.  
  
## <a name="dhtml-event-map-macros"></a>DHTML 이벤트 맵 매크로  
 다음 매크로 사용 하 여에 DHTML 이벤트를 처리할 수 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-클래스를 파생 합니다.  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|DHTML 이벤트 맵의 시작을 표시 합니다.|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|DHTML 이벤트 맵의 시작을 표시 합니다.|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|DHTML 이벤트 맵을 선언합니다.|  
|[DHTML_EVENT](#dhtml_event)|단일 HTML 요소에 대 한 문서 수준에서 이벤트를 처리 하는 데 사용 합니다.|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|ActiveX 컨트롤에 의해 발생 한 이벤트를 처리 하는 데 사용 합니다.|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|CSS 클래스를 특정 모든 HTML 요소에 대 한 문서 수준에서 이벤트를 처리 하는 데 사용 합니다.|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|요소 수준에서 이벤트를 처리 하는 데 사용 합니다.|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|처리 하는 데는 **onafterupdate** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|처리 하는 데는 **onbeforeupdate** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|처리 하는 데는 **onblur** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|처리 하는 데는 `onchange` HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|처리 하는 데는 **onclick** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|처리 하는 데는 **ondataavailable** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|처리 하는 데는 **ondatasetchanged** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|처리 하는 데는 **ondatasetcomplete** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|처리 하는 데는 **ondblclick** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|처리 하는 데는 **ondragstart** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|처리 하는 데는 **onerrorupdate** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|처리 하는 데는 **onfilterchange** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|처리 하는 데는 **onfocus** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|처리 하는 데는 `onhelp` HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|처리 하는 데는 **onkeydown** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|처리 하는 데는 **onkeypress** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|처리 하는 데는 **onkeyup** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|처리 하는 데는 **onmousedown** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|처리 하는 데는 `onmousemove` HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|처리 하는 데는 **onmouseout** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|처리 하는 데는 **onmouseover** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|처리 하는 데는 **onmouseup** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|처리 하는 데는 **onresize** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|처리 하는 데는 **onrowenter** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|처리 하는 데는 **onrowexit** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|처리 하는 데는 **onselectstart** HTML 요소에서 이벤트 발생 합니다.|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|특정 HTML 태그가 있는 모든 요소에 대 한 문서 수준에서 이벤트를 처리 하는 데 사용 합니다.|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|DHTML 이벤트 맵의 끝을 표시 합니다.|  
  
## <a name="url-event-map-macros"></a>URL 이벤트 맵 매크로  
 다음 매크로 사용 하 여에 DHTML 이벤트를 처리할 수 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-클래스를 파생 합니다.  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵 시작을 표시 합니다.|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|포함 된 DHTML 이벤트 맵 시작을 표시 합니다.|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|URL 이벤트 항목 맵은의 시작을 표시 합니다.|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵을 선언합니다.|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|다중 페이지 DHTML 및 URL 이벤트 맵의 끝을 표시 합니다.|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|포함 된 DHTML 이벤트 맵 끝을 표시 합니다.|  
|[END_URL_ENTRIES](#end_url_entries)|URL 이벤트 항목 맵은의 끝을 표시 합니다.|  
|[URL_EVENT_ENTRY](#url_event_entry)|다중 페이지 대화 상자에 있는 페이지를 URL 또는 HTML 리소스를 매핑합니다.|  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapa--begindhtmleventmap"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP  
 DHTML 이벤트 맵으로 식별 되는 클래스에 대 한 소스 파일에 배치 되었을 때의 시작을 표시 `className`합니다.  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>매개 변수  
 `className`  
 DHTML 이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 포함 된 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 클래스 정의 내에서 매크로입니다.  
  
### <a name="remarks"></a>주의  
 DHTML 이벤트 맵 정보를 제공 하는 클래스에 추가 **CDHtmlDialog** 클래스의 처리기 함수는 웹 페이지의 ActiveX 컨트롤 또는 HTML 요소에 의해 발생 하는 경로 이벤트를 사용할 수 있습니다.  
  
 위치는 `BEGIN_DHTML_EVENT_MAP` 클래스의 구현 (.cpp) 파일에 매크로 뒤 `DHTML_EVENT` 이벤트에 대 한 매크로 클래스를 처리 하는 (예를 들어 `DHTML_EVENT_ONMOUSEOVER` mouseover 이벤트에 대 한). 사용 된 [END_DHTML_EVENT_MAP](#end_dhtml_event_map) 이벤트 맵의 끝을 표시 하는 매크로입니다. 이러한 매크로 다음과 같은 함수를 구현합니다.  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapinlinea--begindhtmleventmapinline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE  
 DHTML 이벤트 맵에 대 한 클래스 정의 내에서 시작을 표시 `className`합니다.  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>매개 변수  
 `className`  
 DHTML 이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) 포함 된 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 클래스 정의 내에서 매크로입니다.  
  
### <a name="remarks"></a>주의  
 DHTML 이벤트 맵 정보를 제공 하는 클래스에 추가 **CDHtmlDialog** 클래스의 처리기 함수는 웹 페이지의 ActiveX 컨트롤 또는 HTML 요소에 의해 발생 하는 경로 이벤트를 사용할 수 있습니다.  
  
 위치는 `BEGIN_DHTML_EVENT_MAP` 클래스의 정의 (.h) 파일에 매크로 뒤 `DHTML_EVENT` 이벤트에 대 한 매크로 클래스를 처리 하는 (예를 들어 `DHTML_EVENT_ONMOUSEOVER` mouseover 이벤트에 대 한). 사용 된 [END_DHTML_EVENT_MAP_INLINE](http://msdn.microsoft.com/library/0cfec092-20ee-49f3-bc38-56d6a5572db2) 이벤트 맵의 끝을 표시 하는 매크로입니다. 이러한 매크로 다음과 같은 함수를 구현합니다.  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  

  
##  <a name="a-namedeclaredhtmleventmapa--declaredhtmleventmap"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP  
 클래스 정의에 DHTML 이벤트 맵을 선언합니다.  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>주의  
 이 매크로의 정의에 사용할 수는 [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-클래스를 파생 합니다.  
  
 사용 하 여 [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) 또는 [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) 맵을 구현 하려면.  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) 다음 함수를 선언 합니다.  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventa--dhtmlevent"></a><a name="dhtml_event"></a>DHTML_EVENT  
 (문서 수준)으로 식별 하는 이벤트를 처리 `dispid` 로 식별 되는 HTML 요소에 의해 시작 된 `elemName`합니다.  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `dispid`  
 이벤트를 처리의 DISPID를 지정 합니다.  
  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 유지 또는 **NULL** 문서 이벤트를 처리 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventaxcontrola--dhtmleventaxcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL  
 로 식별 되는 이벤트를 처리 `dispid` 식별 된 ActiveX 컨트롤에 의해 발생 `controlName`합니다.  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>매개 변수  
 `dispid`  
 처리할 이벤트의 발송 ID입니다.  
  
 `controlName`  
 `LPCWSTR` 이벤트를 발생 하는 컨트롤의 HTML ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventclassa--dhtmleventclass"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS  
 (문서 수준)으로 식별 하는 이벤트를 처리 `dispid` 로 식별 되는 CSS 클래스와 모든 HTML 요소에 의해 시작 된 `elemName`합니다.  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `dispid`  
 처리할 이벤트의 발송 ID입니다.  
  
 `elemName`  
 `LPCWSTR` 이벤트 소싱 HTML 요소의 CSS 클래스를 포함 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventelementa--dhtmleventelement"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT  
 처리 (으로 식별 되는 요소에서 `elemName`)로 식별 되는 이벤트 `dispid`합니다.  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>매개 변수  
 `dispid`  
 처리할 이벤트의 발송 ID입니다.  
  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
 이 매크로 사용 하 여 nonbubbling 이벤트 처리를 하는 경우 이벤트의 원본으로 식별 된 요소가 됩니다 `elemName`합니다.  
  
 이 매크로 버블링 이벤트를 처리 하기를 사용 하는 경우 요소에서 식별할 `elemName` 이벤트의 소스를 되지 않을 수 있습니다 (소스에 포함 된 요소 수 `elemName`).  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonafterupdatea--dhtmleventonafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE  
 (문서 수준)에서 처리는 **onafterupdate** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonbeforeupdatea--dhtmleventonbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE  
 (문서 수준)에서 처리는 **onbeforeupdate** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonblura--dhtmleventonblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR  
 (요소 수준)에서 처리는 **onblur** 이벤트입니다. Nonbubbling 이벤트입니다.  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonchangea--dhtmleventonchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE  
 (요소 수준)에서 처리는 `onchange` 이벤트입니다. Nonbubbling 이벤트입니다.  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonclicka--dhtmleventonclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK  
 (문서 수준)에서 처리는 **onclick** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventondataavailablea--dhtmleventondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE  
 (문서 수준)에서 처리는 **ondataavailable** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetchangeda--dhtmleventondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED  
 (문서 수준)에서 처리는 **ondatasetchanged** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetcompletea--dhtmleventondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE  
 (문서 수준)에서 처리는 **ondatasetcomplete** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventondblclicka--dhtmleventondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK  
 (문서 수준)에서 처리는 **ondblclick** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventondragstarta--dhtmleventondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART  
 (문서 수준)에서 처리는 **ondragstart** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonerrorupdatea--dhtmleventonerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE  
 (문서 수준)에서 처리는 **onerrorupdate** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfilterchangea--dhtmleventonfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE  
 (문서 수준)에서 처리는 **onfilterchange** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfocusa--dhtmleventonfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS  
 (요소 수준)에서 처리는 **onfocus** 이벤트입니다. Nonbubbling 이벤트입니다.  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonhelpa--dhtmleventonhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP  
 (문서 수준)에서 처리는 `onhelp` 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeydowna--dhtmleventonkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN  
 (문서 수준)에서 처리는 **onkeydown** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeypressa--dhtmleventonkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS  
 (문서 수준)에서 처리는 **onkeypress** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeyupa--dhtmleventonkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP  
 (문서 수준)에서 처리는 **onkeyup** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousedowna--dhtmleventonmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN  
 (문서 수준)에서 처리는 **onmousedown** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousemovea--dhtmleventonmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE  
 (문서 수준)에서 처리는 `onmousemove` 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseouta--dhtmleventonmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT  
 (문서 수준)에서 처리는 **onmouseout** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseovera--dhtmleventonmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER  
 (문서 수준)에서 처리는 **onmouseover** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseupa--dhtmleventonmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP  
 (문서 수준)에서 처리는 **onmouseup** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonresizea--dhtmleventonresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE  
 (요소 수준)에서 처리는 **onresize** 이벤트입니다. Nonbubbling 이벤트입니다.  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowentera--dhtmleventonrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER  
 (문서 수준)에서 처리는 **onrowenter** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowexita--dhtmleventonrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT  
 (문서 수준)에서 처리는 **onrowexit** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventonselectstarta--dhtmleventonselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART  
 (문서 수준)에서 처리는 **onselectstart** 로 식별 되는 HTML 요소에 의해 이벤트가 생성 된 `elemName`합니다.  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `elemName`  
 `LPCWSTR` 이벤트 원본을 지정 하는 HTML 요소의 ID를 보유 합니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedhtmleventtaga--dhtmleventtag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG  
 (문서 수준)으로 식별 하는 이벤트를 처리 `dispid` 로 식별 되는 HTML 태그가 있는 모든 HTML 요소에 의해 시작 된 `elemName`합니다.  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>매개 변수  
 `dispid`  
 처리할 이벤트의 발송 ID입니다.  
  
 `elemName`  
 이벤트 소싱 HTML 요소의 HTML 태그입니다.  
  
 `memberFxn`  
 이벤트 처리기 함수입니다.  
  
### <a name="remarks"></a>주의  
 이 매크로 사용 하 여 항목을 추가 하는 [DHTML 이벤트 맵](#begin_dhtml_event_map_inline) 클래스에 있습니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-nameenddhtmleventmapa--enddhtmleventmap"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP  
 DHTML 이벤트 맵의 끝을 표시 합니다.  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>주의  
 와 함께에서 사용 해야 [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namebegindhtmlurleventmapa--begindhtmlurleventmap"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP  
 다중 페이지 대화 상자에서 DHTML 및 URL 이벤트 맵 정의 시작 합니다.  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>주의  
 Put `BEGIN_DHTML_URL_EVENT_MAP` 의 구현 파일에서 프로그램 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-클래스를 파생 합니다. 와 그 뒤 [DHTML 이벤트 맵 포함](#begin_embed_dhtml_event_map) 및 [URL 항목](#begin_url_entries)를 닫은 후 다음으로 [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)합니다. 포함 된 [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) 클래스 정의 내에서 매크로입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&196;](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namebeginembeddhtmleventmapa--beginembeddhtmleventmap"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP  
 다중 페이지 대화 상자에 포함 된 DHTML 이벤트 맵 정의 시작 합니다.  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `className`  
 이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. 포함 된 DHTML 이벤트 맵 내에 있어야 합니다. 한 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)).  
  
 *맵 이름*  
 이 이벤트 매핑할 페이지를 지정 합니다. 이 일치 *맵 이름* 에 [URL_EVENT_ENTRY](#url_event_entry) 실제로 URL 또는 HTML 리소스를 정의 하는 매크로입니다.  
  
### <a name="remarks"></a>주의  
 다중 페이지 DHTML 대화 상자는 DHTML 이벤트를 발생 시킬 수 있으며 각 하는 여러 HTML 페이지로 구성 되기 때문에 포함 된 이벤트 맵 이벤트 처리기에서 페이지 별로 매핑할 하는 데 사용 됩니다.  
  
 DHTML 및 URL 이벤트 맵 내에서 포함 된 이벤트 맵 이루어져는 `BEGIN_EMBED_DHTML_EVENT_MAP` 매크로 뒤 [DHTML_EVENT](dhtml-event-maps.md#dhtml_event) 매크로 및 [END_EMBED_DHTML_EVENT_MAP](dhtml-event-maps.md#end_embed_dhtml_event_map) 매크로입니다.  
  
 각 포함 된 이벤트 맵에 해당 필요 [URL 이벤트 항목](#url_event_entry) 매핑할 *맵 이름* (에 지정 된 `BEGIN_EMBED_DHTML_EVENT_MAP`) URL 또는 HTML 리소스입니다.  
  
### <a name="example"></a>예제  
 예제를 참조 하십시오 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namebeginurlentriesa--beginurlentries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES  
 다중 페이지 대화 상자에서 URL 이벤트 항목 맵 정의를 시작합니다.  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `className`  
 URL 이벤트 항목 맵을 포함하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. URL 이벤트 항목 맵은 내에 있어야 합니다. 한 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)).  
  
### <a name="remarks"></a>주의  
 Url 또는 HTML을 매핑할 URL 이벤트 항목이 사용 됩니다 다중 페이지 DHTML 대화 상자는 여러 HTML 페이지로 구성 때문에 리소스를 해당 [DHTML 이벤트 맵 포함](#begin_embed_dhtml_event_map)합니다. Put `URL_EVENT_ENTRY` 매크로 사이 `BEGIN_URL_ENTRIES` 및 [END_URL_ENTRIES](#end_url_entries) 매크로입니다.  
  
### <a name="example"></a>예제  
 예제를 참조 하십시오 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-namedeclaredhtmlurleventmapa--declaredhtmlurleventmap"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP  
 클래스 정의에 DHTML 및 URL 이벤트 맵을 선언합니다.  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>주의  
 이 매크로의 정의에 사용할 수는 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-클래스를 파생 합니다.  
  
 DHTML 및 URL 이벤트 맵 포함 [DHTML 이벤트 맵 포함](#begin_embed_dhtml_event_map) 및 [URL 이벤트 항목이](#begin_url_entries) DHTML 이벤트 페이지 별로 대 한 처리기에 매핑됩니다. 사용 하 여 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) 맵을 구현 하려면.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-nameenddhtmlurleventmapa--enddhtmlurleventmap"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP  
 DHTML 및 URL 이벤트 맵 끝을 표시 합니다.  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>매개 변수  
 `className`  
 이벤트 맵을 포함 하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. 이것은 일치 해야 `className` 해당 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) 매크로입니다.  
  
### <a name="example"></a>예제  
 예제를 참조 하십시오 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-nameendembeddhtmleventmapa--endembeddhtmleventmap"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP  
 포함 된 DHTML 이벤트 맵 끝을 표시 합니다.  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>예제  
 예제를 참조 하십시오 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-nameendurlentriesa--endurlentries"></a><a name="end_url_entries"></a>END_URL_ENTRIES  
 URL 이벤트 항목 맵은의 끝을 표시 합니다.  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>예제  
 예제를 참조 하십시오 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
  
##  <a name="a-nameurlevententrya--urlevententry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY  
 다중 페이지 대화 상자에 있는 페이지를 URL 또는 HTML 리소스를 매핑합니다.  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>매개 변수  
 `className`  
 URL 이벤트 항목 맵을 포함하는 클래스의 이름입니다. 이 클래스에 직접 또는 간접적으로에서 파생 되어야 [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)합니다. URL 이벤트 항목 맵은 내에 있어야 합니다. 한 [DHTML 및 URL 이벤트 맵](#begin_dhtml_url_event_map)).  
  
 *url*  
 페이지에 대 한 URL 또는 HTML 리소스입니다.  
  
 *맵 이름*  
 URL이 인 페이지 지정 *url*합니다. 이 일치 *맵 이름* 에 [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) 이 페이지에서 이벤트를 매핑하는 매크로입니다.  
  
### <a name="remarks"></a>주의  
 페이지가 HTML 리소스인 경우 *url* 리소스의 ID 번호 (즉, "123", 하지 123 또는 ID_HTMLRES1)의 문자열 표현 이어야 합니다.  
  
 페이지 식별자 *맵 이름*를 연결 하는 데 사용 하는 임의의 기호 URL 이벤트 항목 맵에 DHTML 이벤트 맵 포함 됩니다. 이 작업은 제한에 DHTML 및 URL 이벤트 맵 범위에 있습니다.  
  
### <a name="example"></a>예제  
 예제를 참조 하십시오 [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)합니다.  

  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdhtml.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)

