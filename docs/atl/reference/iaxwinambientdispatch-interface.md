---
title: IAxWinAmbientDispatch 인터페이스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
dev_langs:
- C++
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d082faf4c25f76fd7a98cc897760adc424ffb49e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch 인터페이스
이 인터페이스는 호스트 된 컨트롤 또는 컨테이너의 특성을 지정 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
interface IAxWinAmbientDispatch : IDispatch
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[get_AllowContextMenu](#get_allowcontextmenu)|**컨텍스트 메뉴 사용** 속성 호스팅된 컨트롤 상황에 맞는 메뉴를 표시할 수 있는지 여부를 지정 합니다.|  
|[get_AllowShowUI](#get_allowshowui)|**AllowShowUI** 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스를 표시할 수 있는지 여부를 지정 합니다.|  
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|**AllowWindowlessActivation** 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.|  
|[get_BackColor](#get_backcolor)|`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.|  
|[get_DisplayAsDefault](#get_displayasdefault)|**DisplayAsDefault** 기본 컨트롤 인지 알아보려면 제어 기능을 제공 하는 앰비언트 속성입니다.|  
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|**DocHostDoubleClickFlags** 속성 때 수행 해야 하는 두 번 클릭에 대 한 응답에서 작업을 지정 합니다.|  
|[get_DocHostFlags](#get_dochostflags)|**DocHostFlags** 속성 개체의 사용자 인터페이스 기능을 지정 합니다.|  
|[get_Font](#get_font)|**글꼴** 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.|  
|[get_ForeColor](#get_forecolor)|`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.|  
|[get_LocaleID](#get_localeid)|**LocaleID** 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.|  
|[get_MessageReflect](#get_messagereflect)|**MessageReflect** 앰비언트 속성 컨테이너는 호스팅된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.|  
|[get_OptionKeyPath](#get_optionkeypath)|**OptionKeyPath** 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.|  
|[get_ShowGrabHandles](#get_showgrabhandles)|**ShowGrabHandles** 앰비언트 속성이 경우 것 그릴지 자체 잡기 핸들을 사용한 찾을 컨트롤을 찾을 수 있습니다.|  
|[get_ShowHatching](#get_showhatching)|**ShowHatching** 앰비언트 속성이 무늬 자체 그리기 해야 하는 경우 찾을 컨트롤을 찾을 수 있습니다.|  
|[get_UserMode](#get_usermode)|**UserMode** 속성 컨테이너의 앰비언트 사용자 모드를 지정 합니다.|  
|[put_AllowContextMenu](#put_allowcontextmenu)|**컨텍스트 메뉴 사용** 속성 호스팅된 컨트롤 상황에 맞는 메뉴를 표시할 수 있는지 여부를 지정 합니다.|  
|[put_AllowShowUI](#put_allowshowui)|**AllowShowUI** 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스를 표시할 수 있는지 여부를 지정 합니다.|  
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|**AllowWindowlessActivation** 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.|  
|[put_BackColor](#put_backcolor)|`BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.|  
|[put_DisplayAsDefault](#put_displayasdefault)|**DisplayAsDefault** 기본 컨트롤 인지 알아보려면 제어 기능을 제공 하는 앰비언트 속성입니다.|  
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|**DocHostDoubleClickFlags** 속성 때 수행 해야 하는 두 번 클릭에 대 한 응답에서 작업을 지정 합니다.|  
|[put_DocHostFlags](#put_dochostflags)|**DocHostFlags** 속성 개체의 사용자 인터페이스 기능을 지정 합니다.|  
|[put_Font](#put_font)|**글꼴** 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.|  
|[put_ForeColor](#put_forecolor)|`ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.|  
|[put_LocaleID](#put_localeid)|**LocaleID** 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.|  
|[put_MessageReflect](#put_messagereflect)|**MessageReflect** 앰비언트 속성 컨테이너는 호스팅된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.|  
|[put_OptionKeyPath](#put_optionkeypath)|**OptionKeyPath** 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.|  
|[put_UserMode](#put_usermode)|**UserMode** 속성 컨테이너의 앰비언트 사용자 모드를 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 ATL의 ActiveX 컨트롤 호스팅 개체에 의해 노출 됩니다. 호스팅된 컨트롤에 사용할 수 있는 앰비언트 속성을 설정 하거나 컨테이너의 동작의 기타 측면을 지정 하려면이 인터페이스에서 메서드를 호출 합니다. 제공 되는 속성을 보완 하기 위해 `IAxWinAmbientDispatch`를 사용 하 여 [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)합니다.  
  
 [AXHost](https://msdn.microsoft.com/library/system.windows.forms.axhost.aspx) 에 대 한 형식 정보를 로드 하려고 `IAxWinAmbientDispatch` 및 `IAxWinAmbientDispatchEx` 코드를 포함 하는 형식 라이브러리에서.  
  
 ATL90.dll를 연결할 경우 **AXHost** DLL의 형식 라이브러리에서 형식 정보를 로드 합니다.  
  
 참조 [ActiveX 컨트롤 ATL를 사용 하 여 AXHost 호스팅](../../atl/hosting-activex-controls-using-atl-axhost.md) 내용을 확인 합니다.  
  
## <a name="requirements"></a>요구 사항  
 이 인터페이스의 정의 아래 표에 나와 있는 것 처럼 다양 한 폼에서에서 사용할 수 있습니다.  
  
|정의 유형|파일|  
|---------------------|----------|  
|IDL|atliface.idl|  
|형식 라이브러리|ATL.dll|  
|C++|atliface.h (ATLBase.h에도 포함)|  
  
##  <a name="get_allowcontextmenu"></a>  IAxWinAmbientDispatch::get_AllowContextMenu  
 **컨텍스트 메뉴 사용** 속성 호스팅된 컨트롤 상황에 맞는 메뉴를 표시할 수 있는지 여부를 지정 합니다.  
  
```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbAllowContextMenu*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_allowshowui"></a>  IAxWinAmbientDispatch::get_AllowShowUI  
 **AllowShowUI** 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스를 표시할 수 있는지 여부를 지정 합니다.  
  
```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbAllowShowUI*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **VARIANT_FALSE** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::get_AllowWindowlessActivation  
 **AllowWindowlessActivation** 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.  
  
```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbAllowWindowless*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_backcolor"></a>  IAxWinAmbientDispatch::get_BackColor  
 `BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.  
  
```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```  
  
### <a name="parameters"></a>매개 변수  
 *pclrBackground*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **COLOR_BTNFACE** 또는 **COLOR_WINDOW** (에 따라 호스트 창의 부모 인지 여부는 대화 상자)이이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_displayasdefault"></a>  IAxWinAmbientDispatch::get_DisplayAsDefault  
 **DisplayAsDefault** 기본 컨트롤 인지 알아보려면 제어 기능을 제공 하는 앰비언트 속성입니다.  
  
```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbDisplayAsDefault*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **VARIANT_FALSE** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::get_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags** 속성 때 수행 해야 하는 두 번 클릭에 대 한 응답에서 작업을 지정 합니다.  
  
```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 *pdwDocHostDoubleClickFlags*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **DOCHOSTUIDBLCLK_DEFAULT** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_dochostflags"></a>  IAxWinAmbientDispatch::get_DocHostFlags  
 **DocHostFlags** 속성 개체의 사용자 인터페이스 기능을 지정 합니다.  
  
```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 *pdwDocHostFlags*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **DOCHOSTUIFLAG_NO3DBORDER** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_font"></a>  IAxWinAmbientDispatch::get_Font  
 **글꼴** 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.  
  
```
STDMETHOD(get_Font)(IFontDisp** pFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFont`  
 [out] 주소는 **IFontDisp** 이 속성의 현재 값을 수신 하는 데 사용 되는 인터페이스 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을이 속성의 값을 기본값으로 기본 GUI 글꼴 또는 시스템 글꼴을 사용합니다.  
  
##  <a name="get_forecolor"></a>  IAxWinAmbientDispatch::get_ForeColor  
 `ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.  
  
```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```  
  
### <a name="parameters"></a>매개 변수  
 *pclrForeground*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 속성의 값을 기본값으로 시스템 창 텍스트 색을 사용 하는 ATL 호스트 개체 구현 합니다.  
  
##  <a name="get_localeid"></a>  IAxWinAmbientDispatch::get_LocaleID  
 **LocaleID** 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.  
  
```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```  
  
### <a name="parameters"></a>매개 변수  
 *plcidLocaleID*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 속성의 값을 기본값으로 사용자의 기본 로캘을 사용 하는 ATL 호스트 개체 구현 합니다.  
  
 이 메서드로 앰비언트 LocalID를 검색할 수 있는, 즉, 프로그램의 LocaleID 컨트롤 사용량입니다. LocaleID 것을 알고 있다면 조각과 위성 DLL 또는 리소스 파일에서 로드 하는 코드 로캘별 캡션, 오류 메시지 텍스트를 호출할 수 있습니다.  
  
##  <a name="get_messagereflect"></a>  IAxWinAmbientDispatch::get_MessageReflect  
 **MessageReflect** 앰비언트 속성 컨테이너는 호스팅된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.  
  
```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbMessageReflect*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="get_optionkeypath"></a>  IAxWinAmbientDispatch::get_OptionKeyPath  
 **OptionKeyPath** 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.  
  
```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbstrOptionKeyPath*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="get_showgrabhandles"></a>  IAxWinAmbientDispatch::get_ShowGrabHandles  
 **ShowGrabHandles** 앰비언트 속성이 경우 것 그릴지 자체 잡기 핸들을 사용한 찾을 컨트롤을 찾을 수 있습니다.  
  
```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbShowGrabHandles*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현 시 항상 반환 **VARIANT_FALSE** 이 속성의 값으로.  
  
##  <a name="get_showhatching"></a>  IAxWinAmbientDispatch::get_ShowHatching  
 **ShowHatching** 앰비언트 속성이 무늬 자체 그리기 해야 하는 경우 찾을 컨트롤을 찾을 수 있습니다.  
  
```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbShowHatching*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현 시 항상 반환 **VARIANT_FALSE** 이 속성의 값으로.  
  
##  <a name="get_usermode"></a>  IAxWinAmbientDispatch::get_UserMode  
 **UserMode** 속성 컨테이너의 앰비언트 사용자 모드를 지정 합니다.  
  
```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```  
  
### <a name="parameters"></a>매개 변수  
 *pbUserMode*  
 [out] 이 속성의 현재 값을 받을 변수의 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_allowcontextmenu"></a>  IAxWinAmbientDispatch::put_AllowContextMenu  
 **컨텍스트 메뉴 사용** 속성 호스팅된 컨트롤 상황에 맞는 메뉴를 표시할 수 있는지 여부를 지정 합니다.  
  
```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAllowContextMenu*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_allowshowui"></a>  IAxWinAmbientDispatch::put_AllowShowUI  
 **AllowShowUI** 속성 호스팅된 컨트롤의 고유한 사용자 인터페이스를 표시할 수 있는지 여부를 지정 합니다.  
  
```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAllowShowUI*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **VARIANT_FALSE** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_allowwindowlessactivation"></a>  IAxWinAmbientDispatch::put_AllowWindowlessActivation  
 **AllowWindowlessActivation** 속성 컨테이너 창 없는 활성화를 허용 되는지 여부를 지정 합니다.  
  
```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAllowWindowless*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_backcolor"></a>  IAxWinAmbientDispatch::put_BackColor  
 `BackColor` 속성 컨테이너의 앰비언트 배경색을 지정 합니다.  
  
```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```  
  
### <a name="parameters"></a>매개 변수  
 *clrBackground*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **COLOR_BTNFACE** 또는 **COLOR_WINDOW** (에 따라 호스트 창의 부모 인지 여부는 대화 상자)이이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_displayasdefault"></a>  IAxWinAmbientDispatch::put_DisplayAsDefault  
 **DisplayAsDefault** 기본 컨트롤 인지 알아보려면 제어 기능을 제공 하는 앰비언트 속성입니다.  
  
```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```  
  
### <a name="parameters"></a>매개 변수  
 `bDisplayAsDefault`  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **VARIANT_FALSE** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_dochostdoubleclickflags"></a>  IAxWinAmbientDispatch::put_DocHostDoubleClickFlags  
 **DocHostDoubleClickFlags** 속성 때 수행 해야 하는 두 번 클릭에 대 한 응답에서 작업을 지정 합니다.  
  
```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwDocHostDoubleClickFlags*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **DOCHOSTUIDBLCLK_DEFAULT** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_dochostflags"></a>  IAxWinAmbientDispatch::put_DocHostFlags  
 **DocHostFlags** 속성 개체의 사용자 인터페이스 기능을 지정 합니다.  
  
```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwDocHostFlags*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 **DOCHOSTUIFLAG_NO3DBORDER** 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_font"></a>  IAxWinAmbientDispatch::put_Font  
 **글꼴** 속성 컨테이너의 앰비언트 글꼴을 지정 합니다.  
  
```
STDMETHOD(put_Font)(IFontDisp* pFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `pFont`  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을이 속성의 값을 기본값으로 기본 GUI 글꼴 또는 시스템 글꼴을 사용합니다.  
  
##  <a name="put_forecolor"></a>  IAxWinAmbientDispatch::put_ForeColor  
 `ForeColor` 속성 컨테이너의 앰비언트 전경색을 지정 합니다.  
  
```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```  
  
### <a name="parameters"></a>매개 변수  
 *clrForeground*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 속성의 값을 기본값으로 시스템 창 텍스트 색을 사용 하는 ATL 호스트 개체 구현 합니다.  
  
##  <a name="put_localeid"></a>  IAxWinAmbientDispatch::put_LocaleID  
 **LocaleID** 속성 컨테이너의 앰비언트 로캘 ID를 지정 합니다.  
  
```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```  
  
### <a name="parameters"></a>매개 변수  
 *lcidLocaleID*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 속성의 값을 기본값으로 사용자의 기본 로캘을 사용 하는 ATL 호스트 개체 구현 합니다.  
  
##  <a name="put_messagereflect"></a>  IAxWinAmbientDispatch::put_MessageReflect  
 **MessageReflect** 앰비언트 속성 컨테이너는 호스팅된 컨트롤에 메시지를 반영 하는지 여부를 지정 합니다.  
  
```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```  
  
### <a name="parameters"></a>매개 변수  
 `bMessageReflect`  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
##  <a name="put_optionkeypath"></a>  IAxWinAmbientDispatch::put_OptionKeyPath  
 **OptionKeyPath** 속성 사용자 설정으로 레지스트리 키의 경로 지정 합니다.  
  
```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```  
  
### <a name="parameters"></a>매개 변수  
 *bstrOptionKeyPath*  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="put_usermode"></a>  IAxWinAmbientDispatch::put_UserMode  
 **UserMode** 속성 컨테이너의 앰비언트 사용자 모드를 지정 합니다.  
  
```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `bUserMode`  
 [in] 이 속성의 새 값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 ATL 호스트 개체 구현을 사용 하 여 `VARIANT_TRUE` 이 속성의 값을 기본값으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IAxWinAmbientDispatchEx 인터페이스](../../atl/reference/iaxwinambientdispatchex-interface.md)   
 [IAxWinHostWindow 인터페이스](../../atl/reference/iaxwinhostwindow-interface.md)   
 [CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)   
 [AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)









