---
title: CAxWindow 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow
- ATLWIN/ATL::CAxWindow
- ATLWIN/ATL::AttachControl
- ATLWIN/ATL::CreateControl
- ATLWIN/ATL::CreateControlEx
- ATLWIN/ATL::GetWndClassName
- ATLWIN/ATL::QueryControl
- ATLWIN/ATL::QueryHost
- ATLWIN/ATL::SetExternalDispatch
- ATLWIN/ATL::SetExternalUIHandler
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow class
- ATL, hosting ActiveX controls
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 052e7ad2bfa8cc03c4eadd4926dbd84c4fd60223
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="caxwindow-class"></a>CAxWindow 클래스
이 클래스는 ActiveX 컨트롤을 호스팅하는 창 조작 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CAxWindow : public CWindow
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AttachControl](#attachcontrol)|기존 ActiveX 컨트롤을 연결 된 `CAxWindow` 개체입니다.|  
|[CAxWindow](#caxwindow)|`CAxWindow` 개체를 생성합니다.|  
|[CreateControl](#createcontrol)|ActiveX 컨트롤을 만들고 초기화를 호스팅하는 `CAxWindow` 창.|  
|[CreateControlEx](#createcontrolex)|ActiveX 컨트롤을 만들고 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.|  
|[GetWndClassName](#getwndclassname)|(정적) 미리 정의 된 클래스 이름을 검색 하는 `CAxWindow` 개체입니다.|  
|[QueryControl](#querycontrol)|검색 된 **IUnknown** 호스팅된 ActiveX 컨트롤의 합니다.|  
|[QueryHost](#queryhost)|검색 된 **IUnknown** 의 포인터는 `CAxWindow` 개체입니다.|  
|[SetExternalDispatch](#setexternaldispatch)|사용 하는 외부 디스패치 인터페이스 설정는 `CAxWindow` 개체입니다.|  
|[SetExternalUIHandler](#setexternaluihandler)|설정 하는 외부 **IDocHostUIHandler** 에서 사용 하는 인터페이스는 `CAxWindow` 개체입니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator =](#operator_eq)|할당 된 **HWND** 기존의 **CAxWindow** 개체입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 ActiveX 컨트롤을 호스팅하는 창을 조작 하기 위한 메서드를 제공 합니다. 제공한 호스트 하는 " **AtlAxWin80"** 를 래핑하는 `CAxWindow`합니다.  
  
 클래스 `CAxWindow` 의 특수화로 구현 됩니다는 `CAxWindowT` 클래스입니다. 이 특수화로 선언 됩니다.  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 기본 클래스를 변경 해야 하는 경우 사용할 수 있습니다 `CAxWindowT` 하 고 템플릿 인수로 새 기본 클래스를 지정 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlwin.h  
  
##  <a name="attachcontrol"></a>  CAxWindow::AttachControl  
 이미 존재 하지 하나 및 지정된 된 컨트롤을 호스트에 연결 하는 경우 새 호스트 개체를 만듭니다.  
  
```
HRESULT AttachControl(
    IUnknown* pControl,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 [in] 에 대 한 포인터는 **IUnknown** 컨트롤의 합니다.  
  
 `ppUnkContainer`  
 [out] 에 대 한 포인터는 **IUnknown** 호스트의 (의 **AxWin** 개체).  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 연결 되는 컨트롤 개체를 호출 하기 전에 올바르게 초기화 해야 `AttachControl`합니다.  
  
##  <a name="caxwindow"></a>  CAxWindow::CAxWindow  
 생성 된 `CAxWindow` 기존 창 개체 핸들을 사용 하 여 개체입니다.  
  
```
CAxWindow(HWND hWnd = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 기존 창 개체에 대 한 핸들입니다.  
  
##  <a name="createcontrol"></a>  CAxWindow::CreateControl  
 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.  
  
```
HRESULT CreateControl(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);

HRESULT CreateControl(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 컨트롤을 만들 수는 문자열에 대 한 포인터입니다. 다음 방법 중 하나에 포맷 해야 합니다.  
  
-   ProgID "MSCAL 예:. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID  
  
-   와 같은 URL "http://www.microsoft.com"  
  
-   와 같은 액티브 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"  
  
-   와 같은 HTML 조각을 "MSHTML:\<HTML >\<본문 > 텍스트의 줄\</본문 >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML 스트림에 있는 것으로 지정 하는 HTML 부분 앞에 야 합니다. ProgID 및 CLSID Windows Mobile 플랫폼에서 사용할 수 있습니다. Windows CE 플랫폼을 포함, CE IE 지원에 대 한 지원과 함께 Windows Mobile 이외의 ProgID를 포함 한 모든 형식의 CLSID, URL에 대 한 참조 액티브 문서 및 html 조각입니다.  
  
 `pStream`  
 [in] 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. 수 **NULL**합니다.  
  
 `ppUnkContainer`  
 [out] 수신할 포인터의 주소는 **IUnknown** 컨테이너의 합니다. 수 **NULL**합니다.  
  
 `dwResID`  
 HTML 리소스의 리소스 ID입니다. WebBrowser 컨트롤이 만들어지고 지정된 된 리소스와 함께 로드 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 HTML 컨트롤 생성 되어 식별 되는 리소스에 바인딩된이 메서드의 두 번째 버전을 사용 하는 경우 `dwResID`합니다.  
  
 이 메서드는 호출할 때와 동일한 결과 얻을 수 있습니다:  
  
 [!code-cpp[NVC_ATL_Windowing#42](../../atl/codesnippet/cpp/caxwindow-class_1.cpp)]  
  
 참조 [CAxWindow2T::CreateControlLic](../../atl/reference/caxwindow2t-class.md#createcontrollic) 만들기, 초기화 및 사용 허가 받은 ActiveX 컨트롤을 호스트 합니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CreateControl`합니다.  
  
##  <a name="createcontrolex"></a>  CAxWindow::CreateControlEx  
 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.  
  
```
HRESULT CreateControlEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);

HRESULT CreateControlEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 컨트롤을 만들 수는 문자열에 대 한 포인터입니다. 다음 방법 중 하나에 포맷 해야 합니다.  
  
-   ProgID "MSCAL 예:. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID  
  
-   와 같은 URL "http://www.microsoft.com"  
  
-   와 같은 액티브 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"  
  
-   와 같은 HTML 조각을 "MSHTML:\<HTML >\<본문 > 텍스트의 줄\</본문 >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML 스트림에 있는 것으로 지정 하는 HTML 부분 앞에 야 합니다. ProgID 및 CLSID Windows Mobile 플랫폼에서 사용할 수 있습니다. Windows CE 플랫폼을 포함, CE IE 지원에 대 한 지원과 함께 Windows Mobile 이외의 ProgID를 포함 한 모든 형식의 CLSID, URL에 대 한 참조 액티브 문서 및 html 조각입니다.  
  
 `pStream`  
 [in] 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. 수 **NULL**합니다.  
  
 `ppUnkContainer`  
 [out] 수신할 포인터의 주소는 **IUnknown** 컨테이너의 합니다. 수 **NULL**합니다.  
  
 `ppUnkControl`  
 [out] 수신할 포인터의 주소는 **IUnknown** 컨트롤의 합니다. 수 **NULL**합니다.  
  
 `iidSink`  
 [in] 포함 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다. 수 **IID_NULL**합니다.  
  
 *punkSink*  
 [in] 에 대 한 포인터는 **IUnknown** 가 지정한 포함 된 개체에 있는 연결 지점에 연결 되어 싱크 개체의 인터페이스 `iidSink`합니다.  
  
 `dwResID`  
 [in] HTML 리소스의 리소스 ID입니다. WebBrowser 컨트롤이 만들어지고 지정된 된 리소스와 함께 로드 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 [CAxWindow::CreateControl](#createcontrol), 하지만 메서드는 달리 `CreateControlEx` 새로 생성된 된 컨트롤에 대 한 인터페이스 포인터를 수신 및 컨트롤에 의해 실행 되는 이벤트를 수신할 이벤트 싱크를 설정할 수 있습니다.  
  
 참조 [CAxWindow2T::CreateControlLicEx](../../atl/reference/caxwindow2t-class.md#createcontrollicex) 만들기, 초기화 및 사용 허가 받은 ActiveX 컨트롤을 호스트 합니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 사용 하는 샘플에 대 한 `CreateControlEx`합니다.  
  
##  <a name="getwndclassname"></a>  CAxWindow::GetWndClassName  
 창 클래스의 이름을 검색합니다.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>반환 값  
 라이센스가 없는 ActiveX 컨트롤을 호스팅할 수 있는 창 클래스의 이름을 포함 하는 문자열에 대 한 포인터입니다.  
  
##  <a name="operator_eq"></a>  CAxWindow::operator =  
 할당 된 `HWND` 기존의 `CAxWindow` 개체입니다.  
  
```
CAxWindow<TBase>& operator=(HWND hWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `hWnd`  
 기존 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 현재 `CAxWindow` 개체에 대한 참조를 반환합니다.  
  
##  <a name="querycontrol"></a>  CAxWindow::QueryControl  
 호스팅된 컨트롤의 지정된 된 인터페이스를 검색합니다.  
  
```
HRESULT QueryControl(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryControl(Q** ppUnk);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 컨트롤의 인터페이스의 IID를 지정합니다.  
  
 `ppUnk`  
 [out] 컨트롤의 인터페이스에 대 한 포인터입니다. 이 메서드는 서식 파일 버전에 있을 필요는 없습니다 참조 ID에 대 한으로 형식화 된 인터페이스는 연결 된 UUID 통해 전달 됩니다.  
  
 `Q`  
 [in] 에 대 한 쿼리 되는 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="queryhost"></a>  CAxWindow::QueryHost  
 호스트의 지정된 된 인터페이스를 반환합니다.  
  
```
HRESULT QueryHost(REFIID iid, void** ppUnk);
template <class  Q>
HRESULT QueryHost(Q** ppUnk);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 컨트롤의 인터페이스의 IID를 지정합니다.  
  
 `ppUnk`  
 [out] 호스트에서 인터페이스에 대 한 포인터입니다. 이 메서드는 서식 파일 버전에 있을 필요는 없습니다 참조 ID에 대 한으로 형식화 된 인터페이스는 연결 된 UUID 통해 전달 됩니다.  
  
 `Q`  
 [in] 에 대 한 쿼리 되는 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 호스트의이 인터페이스에 의해 구현 창 호스팅 코드의 기본 기능에 대 한 액세스를 허용 **AxWin**합니다.  
  
##  <a name="setexternaldispatch"></a>  CAxWindow::SetExternalDispatch  
 설정에 대 한 외부 디스패치 인터페이스는 `CAxWindow` 개체입니다.  
  
```
HRESULT SetExternalDispatch(IDispatch* pDisp);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDisp`  
 [in] 에 대 한 포인터는 `IDispatch` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="setexternaluihandler"></a>  CAxWindow::SetExternalUIHandler  
 설정 하는 외부 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 에 대 한 인터페이스는 `CAxWindow` 개체입니다.  
  
```
HRESULT SetExternalUIHandler(IDocHostUIHandlerDispatch* pUIHandler);
```  
  
### <a name="parameters"></a>매개 변수  
 *pUIHandler*  
 [in] 에 대 한 포인터는 **IDocHostUIHandlerDispatch** 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 외부 `IDocHostUIHandlerDispatch` 인터페이스에 대 한 호스트의 사이트를 쿼리 하는 컨트롤에서 사용 되는 `IDocHostUIHandlerDispatch` 인터페이스입니다. WebBrowser 컨트롤은이 작업을 수행 하는 컨트롤입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATLCON 샘플](../../visual-cpp-samples.md)   
 [CWindow 클래스](../../atl/reference/cwindow-class.md)   
 [합성 컨트롤 기본 사항](../../atl/atl-composite-control-fundamentals.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [컨트롤 포함 FAQ](../../atl/atl-control-containment-faq.md)

