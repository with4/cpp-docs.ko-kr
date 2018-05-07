---
title: 복합 컨트롤 전역 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c62d5056f28460644084296598ae865c6ff5f48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="composite-control-global-functions"></a>복합 컨트롤 전역 함수
이러한 함수를 작성, 호스팅 및 ActiveX 컨트롤 라이센스 획득 하 고 대화 상자 만들기에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|사용자가 제공한 대화 상자 템플릿에서 모달 대화 상자를 만듭니다. 대화 상자가 나타나면 ActiveX 컨트롤을 포함할 수 있습니다.|  
|[AtlAxCreateDialog](#atlaxcreatedialog)|사용자가 제공한 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다. 대화 상자가 나타나면 ActiveX 컨트롤을 포함할 수 있습니다.|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|ActiveX 컨트롤을 만듭니다. 초기화 하며 지정한 창에 호스팅합니다 및 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|사용 허가 받은 ActiveX 컨트롤을 만듭니다. 초기화 하며 지정한 창에 호스팅합니다 및 컨트롤에서 인터페이스 포인터 (또는 포인터)를 검색 합니다.|  
|[AtlAxAttachControl](#atlaxattachcontrol)|지정한 창에 이전에 만든 컨트롤을 연결합니다.|  
|[AtlAxGetHost](#atlaxgethost)|지정 된 창 (있는 경우), 컨테이너에 직접 인터페이스 포인터를 가져오는 데 핸들이 제공 합니다.|  
|[AtlAxGetControl](#atlaxgetcontrol)|지정 된 창 (있는 경우), 내부에 포함 된 컨트롤에 직접 인터페이스 포인터를 가져오는 데 핸들이 제공 합니다.|  
|[AtlSetChildSite](#atlsetchildsite)|초기화는 **IUnknown** 자식 사이트의 합니다.|  
|[AtlAxWinInit](#atlaxwininit)|AxWin 개체에 대 한 호스팅 코드를 초기화합니다.|  
|[AtlAxWinTerm](#atlaxwinterm)|호스팅 코드 AxWin 개체에 대 한 초기화를 취소 합니다.|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|개체의 기본 소스 인터페이스에 대 한 정보를 반환합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlhost.h  

##  <a name="atlaxdialogbox"></a>  AtlAxDialogBox  
 사용자가 제공한 대화 상자 템플릿에서 모달 대화 상자를 만듭니다.  
   
```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstance`  
 [in] 인 실행 파일 대화 상자 템플릿에 포함 된 모듈의 인스턴스를 식별 합니다.  
  
 `lpTemplateName`  
 [in] 대화 상자 템플릿을 식별합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터 또는 대화 상자 템플릿의 리소스 식별자를 지정 하는 정수 값입니다. 리소스 식별자를 지정 하는 매개 변수, 상위 단어로 0 이어야 합니다. 및 해당 하위 단어는 식별자가 있어야 합니다. 사용할 수는 [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) 매크로이 값을 생성 합니다.  
  
 `hWndParent`  
 [in] 대화 상자를 소유 하는 창을 식별 합니다.  
  
 `lpDialogProc`  
 [in] 대화 상자 프로시저를 가리킵니다. 대화 상자 프로시저에 대 한 자세한 내용은 참조 [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469)합니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 **lParam** 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 사용 하려면 **AtlAxDialogBox** ActiveX 컨트롤을 포함 하는 대화 상자 템플릿을 사용 하 여 올바른 지정 **CLSID**, **APPID** 또는 URL 문자열의 *텍스트* 필드는 **제어** "AtlAxWin80"와 함께 대화 상자 리소스의 섹션은 *클래스 이름* 동일한 섹션에서 필드입니다. 다음에서는 어떤 유효한 **제어** 섹션 아래와 같습니다:  
  
```  
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,  
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100  
```  
  
 리소스 스크립트 편집에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 리소스 스크립트 파일을 텍스트 형식으로 열기](../../windows/how-to-open-a-resource-script-file-in-text-format.md)합니다. 리소스 정의 제어문에 대 한 자세한 내용은 참조 하십시오. [공통 제어 매개 변수](http://msdn.microsoft.com/library/windows/desktop/aa380902) Windows SDK에서 *: SDK 도구*합니다.  
  
 일반적으로 대화 상자에 대 한 자세한 내용은 참조 [대화 상자](http://msdn.microsoft.com/library/windows/desktop/ms645452) 및 [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) Windows sdk에서입니다.  
  
##  <a name="atlaxcreatedialog"></a>  AtlAxCreateDialog  
 사용자가 제공한 대화 상자 템플릿에서 모덜리스 대화 상자를 만듭니다.  
  
```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstance`  
 [in] 인 실행 파일 대화 상자 템플릿에 포함 된 모듈의 인스턴스를 식별 합니다.  
  
 `lpTemplateName`  
 [in] 대화 상자 템플릿을 식별합니다. 이 매개 변수는 대화 상자 템플릿의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터 또는 대화 상자 템플릿의 리소스 식별자를 지정 하는 정수 값입니다. 리소스 식별자를 지정 하는 매개 변수, 상위 단어로 0 이어야 합니다. 및 해당 하위 단어는 식별자가 있어야 합니다. 사용할 수는 [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) 매크로이 값을 생성 합니다.  
  
 `hWndParent`  
 [in] 대화 상자를 소유 하는 창을 식별 합니다.  
  
 `lpDialogProc`  
 [in] 대화 상자 프로시저를 가리킵니다. 대화 상자 프로시저에 대 한 자세한 내용은 참조 [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469)합니다.  
  
 `dwInitParam`  
 [in] 대화 상자에 전달할 값을 지정 된 **lParam** 의 매개 변수는 **WM_INITDIALOG** 메시지입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 대화 상자가 나타나면 ActiveX 컨트롤을 포함할 수 있습니다.  
  
 참조 [CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434) 및 [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) in the Windows SDK입니다.  
  
##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl  
 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.  
  

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 컨트롤에 전달 하는 문자열에 대 한 포인터입니다. 다음 방법 중 하나에 포맷 해야 합니다.  
  
-   ProgID "MSCAL 예:. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID  
  
-   와 같은 URL "http://www.microsoft.com"  
  
-   와 같은 액티브 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"  
  
-   와 같은 HTML 조각을 "MSHTML:\<HTML >\<본문 > 텍스트의 줄\</본문 >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML 스트림에 있는 것으로 지정 하는 HTML 부분 앞에 야 합니다.  
  
 `hWnd`  
 [in] 컨트롤이 연결 된 창으로 처리 합니다.  
  
 `pStream`  
 [in] 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. 수 **NULL**합니다.  
  
 `ppUnkContainer`  
 [out] 수신할 포인터의 주소는 **IUnknown** 컨테이너의 합니다. 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 이 전역 함수를 호출할 때와 동일한 결과 사용 [AtlAxCreateControlEx](#atlaxcreatecontrolex)( `lpszName` **,** `hWnd` **,** `pStream` **, NULL, NULL, NULL, NULL** );.  
  
 사용 허가 받은 ActiveX 컨트롤을 만들려면 참조 [AtlAxCreateControlLic](#atlaxcreatecontrollic)합니다.  
  
##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx  
 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다. 새 컨트롤에 대한 인터페이스 포인터와 이벤트 싱크를 만들 수도 있습니다.  
  
```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 컨트롤에 전달 하는 문자열에 대 한 포인터입니다. 다음 방법 중 하나에 포맷 해야 합니다.  
  
-   ProgID "MSCAL 예:. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID  
  
-   와 같은 URL "http://www.microsoft.com"  
  
-   와 같은 액티브 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"  
  
-   와 같은 HTML 조각을 "MSHTML:\<HTML >\<본문 > 텍스트의 줄\</본문 >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML 스트림에 있는 것으로 지정 하는 HTML 부분 앞에 야 합니다.  
  
 `hWnd`  
 [in] 컨트롤이 연결 된 창으로 처리 합니다.  
  
 `pStream`  
 [in] 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. 수 **NULL**합니다.  
  
 `ppUnkContainer`  
 [out] 수신할 포인터의 주소는 **IUnknown** 컨테이너의 합니다. 수 **NULL**합니다.  
  
 `ppUnkControl`  
 [out] 수신할 포인터의 주소는 **IUnknown** 만든된 컨트롤의 합니다. 수 **NULL**합니다.  
  
 `iidSink`  
 포함 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다.  
  
 *punkSink*  
 에 대 한 포인터는 **IUnknown** 로 지정 된 연결점에 연결할 싱크 개체의 인터페이스 `iidSink` 에 포함 된 개체가 만들어진 후에 성공적으로 포함된 된 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 `AtlAxCreateControlEx` 유사한 [AtlAxCreateControl](#atlaxcreatecontrol) 하지만 새로 만든된 컨트롤에 대 한 인터페이스 포인터를 받아서 컨트롤에 의해 실행 되는 이벤트를 수신할 이벤트 싱크를 설정할 수 있습니다.  
  
 사용 허가 받은 ActiveX 컨트롤을 만들려면 참조 [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)합니다.  
  
##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic  
 사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다.  

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 컨트롤에 전달 하는 문자열에 대 한 포인터입니다. 다음 방법 중 하나에 포맷 해야 합니다.  
  
-   ProgID "MSCAL 예:. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID  
  
-   와 같은 URL "http://www.microsoft.com"  
  
-   와 같은 액티브 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"  
  
-   와 같은 HTML 조각을 "MSHTML:\<HTML >\<본문 > 텍스트의 줄\</본문 >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML 스트림에 있는 것으로 지정 하는 HTML 부분 앞에 야 합니다.  
  
 `hWnd`  
 컨트롤이 연결 된 창으로 처리 합니다.  
  
 `pStream`  
 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. 수 **NULL**합니다.  
  
 `ppUnkContainer`  
 수신할 포인터의 주소는 **IUnknown** 컨테이너의 합니다. 수 **NULL**합니다.  
  
 `bstrLic`  
 컨트롤에 대 한 라이선스를 포함 하는 BSTR입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 샘플을 사용 하는 방법에 대 한 `AtlAxCreateControlLic`합니다.  
  
##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx  
 사용 허가를 받은 ActiveX 컨트롤을 만들고 초기화하며 지정한 창에 호스팅합니다. 새 컨트롤에 대한 인터페이스 포인터와 이벤트 싱크를 만들 수도 있습니다.  
  
```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 컨트롤에 전달 하는 문자열에 대 한 포인터입니다. 다음 방법 중 하나에 포맷 해야 합니다.  
  
-   ProgID "MSCAL 예:. Calendar.7 "  
  
-   "{8E27C92B-1264-101C-8A2F-040224009C02}"와 같은 CLSID  
  
-   와 같은 URL "http://www.microsoft.com"  
  
-   와 같은 액티브 문서에 대 한 참조 "file://\\\Documents\MyDoc.doc"  
  
-   와 같은 HTML 조각을 "MSHTML:\<HTML >\<본문 > 텍스트의 줄\</본문 >\</HTML >"  
  
    > [!NOTE]
    >  "MSHTML:" MSHTML 스트림에 있는 것으로 지정 하는 HTML 부분 앞에 야 합니다.  
  
 `hWnd`  
 컨트롤이 연결 된 창으로 처리 합니다.  
  
 `pStream`  
 컨트롤의 속성을 초기화 하는 데 사용 되는 스트림에 대 한 포인터입니다. 수 **NULL**합니다.  
  
 `ppUnkContainer`  
 수신할 포인터의 주소는 **IUnknown** 컨테이너의 합니다. 수 **NULL**합니다.  
  
 `ppUnkControl`  
 [out] 수신할 포인터의 주소는 **IUnknown** 만든된 컨트롤의 합니다. 수 **NULL**합니다.  
  
 `iidSink`  
 포함 된 개체에는 송신 인터페이스의 인터페이스 식별자입니다.  
  
 *punkSink*  
 에 대 한 포인터는 **IUnknown** 로 지정 된 연결점에 연결할 싱크 개체의 인터페이스 `iidSink` 에 포함 된 개체가 만들어진 후에 성공적으로 포함된 된 개체입니다.  
  
 `bstrLic`  
 컨트롤에 대 한 라이선스를 포함 하는 BSTR입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 `AtlAxCreateControlLicEx` 유사한 [AtlAxCreateControlLic](#atlaxcreatecontrollic) 하지만 새로 만든된 컨트롤에 대 한 인터페이스 포인터를 받아서 컨트롤에 의해 실행 되는 이벤트를 수신할 이벤트 싱크를 설정할 수 있습니다.  
  
### <a name="example"></a>예제  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 샘플을 사용 하는 방법에 대 한 `AtlAxCreateControlLicEx`합니다.  
  
##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl  
 지정한 창에 이전에 만든 컨트롤을 연결합니다.  
  
```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>매개 변수  
 `pControl`  
 [in] 에 대 한 포인터는 **IUnknown** 컨트롤의 합니다.  
  
 `hWnd`  
 [in] 컨트롤을 호스트 하는 창에 대 한 핸들입니다.  
  
 `ppUnkContainer`  
 [out] 에 대 한 포인터에 대 한 포인터는 **IUnknown** 컨테이너 개체의 합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 [AtlAxCreateControlEx](#atlaxcreatecontrolex) 및 [AtlAxCreateControl](#atlaxcreatecontrol) 을 동시에 만들고 컨트롤을 연결 합니다.  
  
> [!NOTE]
>  연결 되는 컨트롤 개체를 호출 하기 전에 올바르게 초기화 해야 `AtlAxAttachControl`합니다.  
  
##  <a name="atlaxgethost"></a>  AtlAxGetHost  
 핸들이 제공되는 지정된 창(있는 경우)의 컨테이너에 직접 인터페이스 포인터를 가져옵니다.  
  
```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>매개 변수  
 `h`  
 [in] 컨트롤을 호스팅하는 창 핸들입니다.  
  
 `pp`  
 [out] **IUnknown** 컨트롤의 컨테이너입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl  
 핸들이 제공되는 지정된 창 내에 포함된 컨트롤에 직접 인터페이스 포인터를 가져옵니다.  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>매개 변수  
 `h`  
 [in] 컨트롤을 호스팅하는 창 핸들입니다.  
  
 `pp`  
 [out] **IUnknown** 호스팅되는 컨트롤의 합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="atlsetchildsite"></a>  AtlSetChildSite  
 자식 개체의 사이트를 설정 하려면이 함수 호출의 **IUnknown** 부모 개체의 합니다.  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>매개 변수  
 *punkChild*  
 [in] 에 대 한 포인터는 **IUnknown** 자식의 인터페이스입니다.  
  
 `punkParent`  
 [in] 에 대 한 포인터는 **IUnknown** 부모의 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
##  <a name="atlaxwininit"></a>  AtlAxWinInit  
 이 함수를 ATL의 컨트롤 호스팅 코드를 등록 하 여 초기화 된 **"AtlAxWin80"** 및 **"AtlAxWinLic80"** 창 클래스 몇 가지 사용자 지정 창 메시지와 함께 합니다.  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤 호스팅 코드의 초기화에 성공 하면 0이 아닌 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 ATL 컨트롤 호스팅 API를 사용 하기 전에이 함수를 호출 해야 합니다. 이 함수를 호출한 다음는 **"AtlAxWin"** 창 클래스에 대 한 호출에서 사용할 수 있습니다 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 또는 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)Windows SDK에 설명 된 대로 합니다.  

##  <a name="atlaxwinterm"></a>  AtlAxWinTerm  
 이 함수 ATL의 컨트롤 호스팅 코드를 등록 취소 하 여 초기화를 취소는 **"AtlAxWin80"** 및 **"AtlAxWinLic80"** 창 클래스입니다.  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>반환 값  
 항상 반환 **TRUE**합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 호출 [UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) Windows SDK에 설명 된 대로 합니다.  
  
 이 함수를 호출한 경우 모든 기존 호스트 창을 제거 된 후 정리 호출 [AtlAxWinInit](#atlaxwininit) 호스트 창을 만들 더 이상 필요 합니다. 이 함수를 호출 하지 않으면, 창 클래스는 등록을 취소할 자동으로 프로세스가 종료 될 때입니다.  
  
##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface  
 개체의 기본 소스 인터페이스에 대한 정보를 검색하려면 이 함수를 호출합니다.  
  
```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```  
  
### <a name="parameters"></a>매개 변수  
 `punkObj`  
 [in] 정보는 반환 될 개체에 대 한 포인터입니다.  
  
 `plibid`  
 [out] 소스 인터페이스의 정의 포함 하는 형식 라이브러리의 LIBID에 대 한 포인터입니다.  
  
 `piid`  
 [out] 개체의 기본 소스 인터페이스의 인터페이스 ID에 대 한 포인터입니다.  
  
 *pdwMajor*  
 [out] 소스 인터페이스의 정의 포함 하는 형식 라이브러리의 주 버전 번호에 대 한 포인터입니다.  
  
 *pdwMinor*  
 [out] 소스 인터페이스의 정의 포함 하는 형식 라이브러리의 부 버전 번호에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 `AtlGetObjectSourceInterface` 인터페이스 ID의 LIBID 함께 및 주요 기본 소스 인터페이스를 사용 하 고 해당 인터페이스를 설명 하는 형식 라이브러리의 부 버전 번호를 제공할 수 있습니다.  
  
> [!NOTE]
>  가 나타내는 개체가 성공적으로 요청된 된 정보를 검색 하려면이 함수에 대해 `punkObj` 구현 해야 `IDispatch` (통해 형식 정보를 반환 하 고 **IDispatch::GetTypeInfo**)와 해야 합니다 구현 `IProvideClassInfo2` 또는 `IPersist`합니다. 소스 인터페이스에 대 한 형식 정보에 대 한 형식 정보와 동일한 형식 라이브러리에 있어야 합니다. `IDispatch`합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 이벤트 싱크 클래스를 정의 하는 방법을 보여 줍니다. `CEasySink`에 전달할 수 있는 템플릿 인수 개수를 줄여 주는 `IDispEventImpl` 완전 essentials에 합니다. `EasyAdvise` 및 `EasyUnadvise` 사용 `AtlGetObjectSourceInterface` 초기화 하는 [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) 호출 하기 전에 멤버 [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) 또는 [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise)합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)   
 [복합 컨트롤 매크로](../../atl/reference/composite-control-macros.md)
