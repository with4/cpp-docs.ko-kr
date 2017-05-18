---
title: "IAxWinHostWindow 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAxWinHostWindow
- No header/ATL::IAxWinHostWindow
- No header/ATL::AttachControl
- No header/ATL::CreateControl
- No header/ATL::CreateControlEx
- No header/ATL::QueryControl
- No header/ATL::SetExternalDispatch
- No header/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
caps.latest.revision: 21
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: ecf88a3a6b115088dd605fff2b633bff86fb086a
ms.contentlocale: ko-kr
ms.lasthandoff: 03/31/2017

---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow 인터페이스
이 인터페이스는 컨트롤 및 해당 호스트 개체를 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
interface IAxWinHostWindow : IUnknown
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|호스트 개체를 기존 컨트롤을 연결합니다.|  
|[CreateControl](#createcontrol)|컨트롤을 만들고 호스트 개체에 연결 합니다.|  
|[CreateControlEx](#createcontrolex)|컨트롤을 만듭니다., 호스트 개체에 연결 하 고 필요에 따라 이벤트 처리기를 설정 합니다.|  
|[QueryControl](#querycontrol)|호스팅된 컨트롤에 대 한 인터페이스 포인터를 반환합니다.|  
|[SetExternalDispatch](#setexternaldispatch)|설정 하는 외부 `IDispatch` 인터페이스입니다.|  
|[SetExternalUIHandler](#setexternaluihandler)|설정 하는 외부 `IDocHostUIHandlerDispatch` 인터페이스입니다.|  
  
## <a name="remarks"></a>주의  
 이 인터페이스는 ATL의 ActiveX 컨트롤 호스팅 개체에 의해 노출 됩니다. 만들기 및/또는 컨트롤 호스팅된 컨트롤에서 인터페이스를 가져올 수 또는 웹 브라우저를 호스트 하는 경우 외부 dispinterface 또는 사용에 대 한 UI 처리기를 설정 하려면 호스트 개체에 연결 하려면이 인터페이스에서 메서드를 호출 합니다.  
  
## <a name="requirements"></a>요구 사항  
 아래와 같이이 인터페이스의 정의 IDL 또는 c + +로 제공 됩니다.  
  
|정의 유형|파일|  
|---------------------|----------|  
|IDL|ATLIFace.idl|  
|C++|ATLIFace.h (ATLBase.h에도 포함)|  
  
##  <a name="attachcontrol"></a>IAxWinHostWindow::AttachControl  
 로 식별 되는 창을 사용 하 여 호스트 개체는 기존 (및 이전에 초기화) 컨트롤 연결 `hWnd`합니다.  
  
```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUnkControl*  
 [in] 에 대 한 포인터는 **IUnknown** 호스트 개체에 연결 될 컨트롤의 인터페이스입니다.  
  
 `hWnd`  
 [in] 호스팅에 사용할 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="createcontrol"></a>IAxWinHostWindow::CreateControl  
 컨트롤을 만들고 초기화를로 식별 되는 창에 호스팅합니다 `hWnd`합니다.  
  
```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpTricsData`  
 [in] 만들 컨트롤을 식별 하는 문자열입니다. (중괄호 포함 해야 함) CLSID, ProgID, URL 또는 원시 HTML 될 수 있습니다 (접두사로 **MSHTML:**).  
  
 `hWnd`  
 [in] 호스팅에 사용할 창 핸들입니다.  
  
 `pStream`  
 [in] 컨트롤에 대 한 초기화 데이터를 포함 하는 스트림에 대 한 인터페이스 포인터입니다. 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 메시지를 컨트롤에 반영 될 수 있습니다 및 기타 컨테이너 기능을 사용할 수 있도록이 인터페이스를 노출 하는 호스트 개체에서이 창을 서브클래싱 할 됩니다.  
  
 이 메서드를 호출 하는 것 [IAxWinHostWindow::CreateControlEx](#createcontrolex)합니다.  
  
 사용 허가 받은 ActiveX 컨트롤을 만들려면 참조 [IAxWinHostWindowLic::CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)합니다.  
  
##  <a name="createcontrolex"></a>IAxWinHostWindow::CreateControlEx  
 ActiveX 컨트롤을 만들고 초기화를 유사 하며 지정한 창에 호스팅합니다 [IAxWinHostWindow::CreateControl](#createcontrol)합니다.  
  
```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpTricsData`  
 [in] 만들 컨트롤을 식별 하는 문자열입니다. (중괄호 포함 해야 함) CLSID, ProgID, URL 또는 원시 HTML 될 수 있습니다 (접두사로 **MSHTML:**).  
  
 `hWnd`  
 [in] 호스팅에 사용할 창 핸들입니다.  
  
 `pStream`  
 [in] 컨트롤에 대 한 초기화 데이터를 포함 하는 스트림에 대 한 인터페이스 포인터입니다. 수 **NULL**합니다.  
  
 `ppUnk`  
 [out] 수신할 포인터의 주소는 **IUnknown** 만든된 컨트롤의 인터페이스입니다. 수 **NULL**합니다.  
  
 *riidAdvise*  
 [in] 포함 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다. 수 **IID_NULL**합니다.  
  
 *punkAdvise*  
 [in] 에 대 한 포인터는 **IUnknown** 가 지정한 포함 된 개체에 있는 연결 지점에 연결 되어 싱크 개체의 인터페이스 `iidSink`합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 와 달리는 `CreateControl` 메서드를 `CreateControlEx` 새로 생성된 된 컨트롤에 대 한 인터페이스 포인터를 수신 및 컨트롤에 의해 실행 되는 이벤트를 수신할 이벤트 싱크를 설정할 수 있습니다.  
  
 사용 허가 받은 ActiveX 컨트롤을 만들려면 참조 [IAxWinHostWindowLic::CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)합니다.  
  
##  <a name="querycontrol"></a>IAxWinHostWindow::QueryControl  
 호스팅된 컨트롤에서 제공 된 인터페이스 포인터를 반환 합니다.  
  
```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `riid`  
 [in] 인터페이스에 요청 된 컨트롤의 ID입니다.  
  
 `ppvObject`  
 [out] 생성된 된 컨트롤의 지정된 된 인터페이스를 수신할 포인터의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="setexternaldispatch"></a>IAxWinHostWindow::SetExternalDispatch  
 통해 포함 된 컨트롤에 사용할 수 있는 외부 dispinterface 설정는 [IDocHostUIHandlerDispatch::GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) 메서드.  
  
```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDisp`  
 [in] 에 대 한 포인터는 `IDispatch` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="setexternaluihandler"></a>IAxWinHostWindow::SetExternalUIHandler  
 외부를 설정 하려면이 함수 호출 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 에 대 한 인터페이스는 `CAxWindow` 개체입니다.  
  
```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDisp`  
 [in] 에 대 한 포인터는 **IDocHostUIHandlerDispatch** 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 이 함수에 대 한 호스트의 사이트를 쿼리 하는 컨트롤 (예: 웹 브라우저 컨트롤)에서 사용 하 여 `IDocHostUIHandlerDispatch` 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [IAxWinAmbientDispatch 인터페이스](../../atl/reference/iaxwinambientdispatch-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)










