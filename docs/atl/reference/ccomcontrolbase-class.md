---
title: "CComControlBase 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComControlBase
- ATLCTL/ATL::CComControlBase
- ATLCTL/ATL::CComControlBase::AppearanceType
- ATLCTL/ATL::CComControlBase::CComControlBase
- ATLCTL/ATL::CComControlBase::ControlQueryInterface
- ATLCTL/ATL::CComControlBase::DoesVerbActivate
- ATLCTL/ATL::CComControlBase::DoesVerbUIActivate
- ATLCTL/ATL::CComControlBase::DoVerbProperties
- ATLCTL/ATL::CComControlBase::FireViewChange
- ATLCTL/ATL::CComControlBase::GetAmbientAppearance
- ATLCTL/ATL::CComControlBase::GetAmbientAutoClip
- ATLCTL/ATL::CComControlBase::GetAmbientBackColor
- ATLCTL/ATL::CComControlBase::GetAmbientCharSet
- ATLCTL/ATL::CComControlBase::GetAmbientCodePage
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayAsDefault
- ATLCTL/ATL::CComControlBase::GetAmbientDisplayName
- ATLCTL/ATL::CComControlBase::GetAmbientFont
- ATLCTL/ATL::CComControlBase::GetAmbientFontDisp
- ATLCTL/ATL::CComControlBase::GetAmbientForeColor
- ATLCTL/ATL::CComControlBase::GetAmbientLocaleID
- ATLCTL/ATL::CComControlBase::GetAmbientMessageReflect
- ATLCTL/ATL::CComControlBase::GetAmbientPalette
- ATLCTL/ATL::CComControlBase::GetAmbientProperty
- ATLCTL/ATL::CComControlBase::GetAmbientRightToLeft
- ATLCTL/ATL::CComControlBase::GetAmbientScaleUnits
- ATLCTL/ATL::CComControlBase::GetAmbientShowGrabHandles
- ATLCTL/ATL::CComControlBase::GetAmbientShowHatching
- ATLCTL/ATL::CComControlBase::GetAmbientSupportsMnemonics
- ATLCTL/ATL::CComControlBase::GetAmbientTextAlign
- ATLCTL/ATL::CComControlBase::GetAmbientTopToBottom
- ATLCTL/ATL::CComControlBase::GetAmbientUIDead
- ATLCTL/ATL::CComControlBase::GetAmbientUserMode
- ATLCTL/ATL::CComControlBase::GetDirty
- ATLCTL/ATL::CComControlBase::GetZoomInfo
- ATLCTL/ATL::CComControlBase::InPlaceActivate
- ATLCTL/ATL::CComControlBase::InternalGetSite
- ATLCTL/ATL::CComControlBase::OnDraw
- ATLCTL/ATL::CComControlBase::OnDrawAdvanced
- ATLCTL/ATL::CComControlBase::OnKillFocus
- ATLCTL/ATL::CComControlBase::OnMouseActivate
- ATLCTL/ATL::CComControlBase::OnPaint
- ATLCTL/ATL::CComControlBase::OnSetFocus
- ATLCTL/ATL::CComControlBase::PreTranslateAccelerator
- ATLCTL/ATL::CComControlBase::SendOnClose
- ATLCTL/ATL::CComControlBase::SendOnDataChange
- ATLCTL/ATL::CComControlBase::SendOnRename
- ATLCTL/ATL::CComControlBase::SendOnSave
- ATLCTL/ATL::CComControlBase::SendOnViewChange
- ATLCTL/ATL::CComControlBase::SetControlFocus
- ATLCTL/ATL::CComControlBase::SetDirty
- ATLCTL/ATL::CComControlBase::m_bAutoSize
- ATLCTL/ATL::CComControlBase::m_bDrawFromNatural
- ATLCTL/ATL::CComControlBase::m_bDrawGetDataInHimetric
- ATLCTL/ATL::CComControlBase::m_bInPlaceActive
- ATLCTL/ATL::CComControlBase::m_bInPlaceSiteEx
- ATLCTL/ATL::CComControlBase::m_bNegotiatedWnd
- ATLCTL/ATL::CComControlBase::m_bRecomposeOnResize
- ATLCTL/ATL::CComControlBase::m_bRequiresSave
- ATLCTL/ATL::CComControlBase::m_bResizeNatural
- ATLCTL/ATL::CComControlBase::m_bUIActive
- ATLCTL/ATL::CComControlBase::m_bUsingWindowRgn
- ATLCTL/ATL::CComControlBase::m_bWasOnceWindowless
- ATLCTL/ATL::CComControlBase::m_bWindowOnly
- ATLCTL/ATL::CComControlBase::m_bWndLess
- ATLCTL/ATL::CComControlBase::m_hWndCD
- ATLCTL/ATL::CComControlBase::m_nFreezeEvents
- ATLCTL/ATL::CComControlBase::m_rcPos
- ATLCTL/ATL::CComControlBase::m_sizeExtent
- ATLCTL/ATL::CComControlBase::m_sizeNatural
- ATLCTL/ATL::CComControlBase::m_spAdviseSink
- ATLCTL/ATL::CComControlBase::m_spAmbientDispatch
- ATLCTL/ATL::CComControlBase::m_spClientSite
- ATLCTL/ATL::CComControlBase::m_spDataAdviseHolder
- ATLCTL/ATL::CComControlBase::m_spInPlaceSite
- ATLCTL/ATL::CComControlBase::m_spOleAdviseHolder
dev_langs:
- C++
helpviewer_keywords:
- CComControlBase class
ms.assetid: 3d1bf022-acf2-4092-8283-ff8cee6332f3
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 988528a3658dee930df2cac6fd1a4add87302509
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontrolbase-class"></a>CComControlBase 클래스
이 클래스는 만들고 ATL 컨트롤을 관리 하기 위한 메서드를 제공 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class ATL_NO_VTABLE CComControlBase
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-typedefs"></a>공용 Typedefs  
  
|이름|설명|  
|----------|-----------------|  
|[CComControlBase::AppearanceType](#appearancetype)|필요한 경우 재정의할 프로그램 `m_nAppearance` 스톡 속성은 형식의 `short`합니다.|  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComControlBase::CComControlBase](#ccomcontrolbase)|생성자입니다.|  
|[CComControlBase:: ~ CComControlBase](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComControlBase::ControlQueryInterface](#controlqueryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|  
|[CComControlBase::DoesVerbActivate](#doesverbactivate)|검사는 `iVerb` 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 컨트롤의 사용자 인터페이스를 활성화 하는 중 하나 ( `iVerb` equals `OLEIVERB_UIACTIVATE`), 컨트롤을 두 번 클릭할 때 수행할 동작을 정의 ( `iVerb` equals `OLEIVERB_PRIMARY`), 컨트롤을 표시 ( `iVerb` equals `OLEIVERB_SHOW`), 컨트롤을 활성화 하거나 ( `iVerb` equals **OLEIVERB_INPLACEACTIVATE**).|  
|[CComControlBase::DoesVerbUIActivate](#doesverbuiactivate)|검사는 `iVerb` 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 컨트롤의 사용자 인터페이스를 활성화 하 고 반환 **TRUE**합니다.|  
|[CComControlBase::DoVerbProperties](#doverbproperties)|컨트롤의 속성 페이지를 표시합니다.|  
|[CComControlBase::FireViewChange](#fireviewchange)|컨트롤의 뷰가 변경 되는 등록 된 advise 싱크 또는 컨테이너 컨트롤 다시 그리기를 구별 하는이 메서드를 호출 합니다.|  
|[CComControlBase::GetAmbientAppearance](#getambientappearance)|검색 **DISPID_AMBIENT_APPEARANCE**, 컨트롤 설정 현재 모양을: 0 평면 음영 및 3D에 대 한 1입니다.|  
|[CComControlBase::GetAmbientAutoClip](#getambientautoclip)|검색 **DISPID_AMBIENT_AUTOCLIP**, 컨테이너 컨트롤 표시 영역의 자동 캡처를 지원 하는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientBackColor](#getambientbackcolor)|검색 **DISPID_AMBIENT_BACKCOLOR**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 배경색입니다.|  
|[CComControlBase::GetAmbientCharSet](#getambientcharset)|검색 **DISPID_AMBIENT_CHARSET**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 문자 집합입니다.|  
|[CComControlBase::GetAmbientCodePage](#getambientcodepage)|검색 **DISPID_AMBIENT_CODEPAGE**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 문자 집합입니다.|  
|[CComControlBase::GetAmbientDisplayAsDefault](#getambientdisplayasdefault)|검색 **DISPID_AMBIENT_DISPLAYASDEFAULT**를 하는 플래그 **TRUE** 경우 컨테이너는 컨트롤을 기본 단추로이 사이트에 표시 하 고 따라서 button 컨트롤을 그릴 자체 두꺼운 프레임이 합니다.|  
|[CComControlBase::GetAmbientDisplayName](#getambientdisplayname)|검색 **DISPID_AMBIENT_DISPLAYNAME**, 컨테이너에 컨트롤에 제공 된 이름입니다.|  
|[CComControlBase::GetAmbientFont](#getambientfont)|검색 된 컨테이너에 대 한 포인터의 앰비언트 `IFont` 인터페이스입니다.|  
|[CComControlBase::GetAmbientFontDisp](#getambientfontdisp)|검색 된 컨테이너에 대 한 포인터의 앰비언트 **IFontDisp** 디스패치 인터페이스입니다.|  
|[CComControlBase::GetAmbientForeColor](#getambientforecolor)|검색 **DISPID_AMBIENT_FORECOLOR**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 전경색입니다.|  
|[CComControlBase::GetAmbientLocaleID](#getambientlocaleid)|검색 **DISPID_AMBIENT_LOCALEID**, 컨테이너에서 사용 되는 언어의 식별자입니다.|  
|[CComControlBase::GetAmbientMessageReflect](#getambientmessagereflect)|검색 **DISPID_AMBIENT_MESSAGEREFLECT**, 컨테이너를 창 메시지를 수신 하려고 하는지 여부를 나타내는 플래그 (예: `WM_DRAWITEM`) 이벤트로 합니다.|  
|[CComControlBase::GetAmbientPalette](#getambientpalette)|검색 **DISPID_AMBIENT_PALETTE**계정에 컨테이너 액세스에 사용 되는 `HPALETTE`합니다.|  
|[CComControlBase::GetAmbientProperty](#getambientproperty)|지정 된 컨테이너 속성을 검색 `id`합니다.|  
|[CComControlBase::GetAmbientRightToLeft](#getambientrighttoleft)|검색 **DISPID_AMBIENT_RIGHTTOLEFT**, 콘텐츠는 컨테이너에 의해 표시 되는 방향입니다.|  
|[CComControlBase::GetAmbientScaleUnits](#getambientscaleunits)|검색 **DISPID_AMBIENT_SCALEUNITS**, 컨테이너의 앰비언트 단위 (예: 인치 또는 센티미터로) 표시에 레이블을 지정 합니다.|  
|[CComControlBase::GetAmbientShowGrabHandles](#getambientshowgrabhandles)|검색 **DISPID_AMBIENT_SHOWGRABHANDLES**, 컨테이너 활성화 된 경우 자신에 대 한 잡기 핸들을 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientShowHatching](#getambientshowhatching)|검색 **DISPID_AMBIENT_SHOWHATCHING**, 컨테이너의 UI 활성화 되어 있을 때 교차 무늬 패턴으로 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientSupportsMnemonics](#getambientsupportsmnemonics)|검색 **DISPID_AMBIENT_SUPPORTSMNEMONICS**, 컨테이너 키보드 니모닉을 지원 하는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientTextAlign](#getambienttextalign)|검색 **DISPID_AMBIENT_TEXTALIGN**, 컨테이너에서 지 원하는 기본 텍스트 맞춤: 일반 맞춤 (번호 오른쪽으로 텍스트를 왼쪽)에 대 한 0, 1 왼쪽 맞춤, 가운데 맞춤에 대 한 2 및 3 오른쪽 맞춤에 대 한 합니다.|  
|[CComControlBase::GetAmbientTopToBottom](#getambienttoptobottom)|검색 **DISPID_AMBIENT_TOPTOBOTTOM**, 콘텐츠는 컨테이너에 의해 표시 되는 방향입니다.|  
|[CComControlBase::GetAmbientUIDead](#getambientuidead)|검색 **DISPID_AMBIENT_UIDEAD**, 컨테이너가 컨트롤을 사용자 인터페이스 작업에 응답 하는지 여부를 나타내는 플래그입니다.|  
|[CComControlBase::GetAmbientUserMode](#getambientusermode)|검색 **DISPID_AMBIENT_USERMODE**, 컨테이너 실행 모드 인지 여부를 나타내는 플래그 ( **TRUE**) 또는 디자인 모드 ( **FALSE**).|  
|[CComControlBase::GetDirty](#getdirty)|데이터 멤버의 값을 반환 `m_bRequiresSave`합니다.|  
|[CComControlBase::GetZoomInfo](#getzoominfo)|X 및 y 검색 분자와 분모의 확대/축소 비율의 값에 대 한 컨트롤이 활성화에 대 한 전체 편집 합니다.|  
|[CComControlBase::InPlaceActivate](#inplaceactivate)|동사에 상태로 비활성 상태에서 전환 하면 컨트롤이 `iVerb` 나타냅니다.|  
|[CComControlBase::InternalGetSite](#internalgetsite)|컨트롤 사이트에서 식별 된 인터페이스 포인터에 대 한 쿼리를이 메서드를 호출 합니다.|  
|[CComControlBase::OnDraw](#ondraw)|컨트롤을 그리는 데이 메서드를 재정의 합니다.|  
|[CComControlBase::OnDrawAdvanced](#ondrawadvanced)|기본 **OnDrawAdvanced** 드로잉에 대 한 정규화 된 장치 컨텍스트를 준비 이면 호출 하는 컨트롤 클래스의 `OnDraw` 메서드.|  
|[CComControlBase::OnKillFocus](#onkillfocus)|확인 컨트롤에 내부 활성화는 및 유효한 컨트롤 사이트가 한 다음 컨트롤에서 포커스를 잃었을 컨테이너에 게 알립니다.|  
|[CComControlBase::OnMouseActivate](#onmouseactivate)|UI 사용자 모드에 다음 컨트롤을 활성화를 확인 합니다.|  
|[CComControlBase::OnPaint](#onpaint)|그리기에 대 한 컨테이너를 준비, 컨트롤의 클라이언트 영역을 가져온 다음 호출 하는 컨트롤 클래스의 `OnDraw` 메서드.|  
|[CComControlBase::OnSetFocus](#onsetfocus)|컨트롤에 내부 활성화는 유효한 컨트롤 사이트가 후 컨테이너 컨트롤에 알립니다 함을 확인에 포커스가 있습니다.|  
|[CComControlBase::PreTranslateAccelerator](#pretranslateaccelerator)|고유한 키보드 액셀러레이터 처리기를 제공 하려면이 메서드를 재정의 합니다.|  
|[CComControlBase::SendOnClose](#sendonclose)|모든 자문 싱크를 등록 된 컨트롤이 닫 혔 advise 소유자에 게 알립니다.|  
|[CComControlBase::SendOnDataChange](#sendondatachange)|모든 자문 싱크를 등록 된 컨트롤 데이터가 변경 되었음을 advise 소유자에 게 알립니다.|  
|[CComControlBase::SendOnRename](#sendonrename)|모든 자문 싱크를 등록 된 컨트롤에는 새 모니커 advise 소유자에 게 알립니다.|  
|[CComControlBase::SendOnSave](#sendonsave)|모든 자문 싱크를 등록 된 컨트롤이 저장 된 advise 소유자에 게 알립니다.|  
|[CComControlBase::SendOnViewChange](#sendonviewchange)|등록 된 모든 자문 싱크에 컨트롤의 뷰 변경 되었음을 알립니다.|  
|[CComControlBase::SetControlFocus](#setcontrolfocus)|설정 하거나 컨트롤에서 키보드 포커스를 제거 합니다.|  
|[CComControlBase::SetDirty](#setdirty)|데이터 멤버를 설정 `m_bRequiresSave` 값에 `bDirty`합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComControlBase::m_bAutoSize](#m_bautosize)|컨트롤에는 다른 크기 일 수 없습니다 나타내는 플래그입니다.|  
|[CComControlBase::m_bDrawFromNatural](#m_bdrawfromnatural)|함을 나타내는 플래그 `IDataObjectImpl::GetData` 및 `CComControlBase::GetZoomInfo` 에서 컨트롤 크기를 설정 해야 `m_sizeNatural` 아닌 `m_sizeExtent`합니다.|  
|[CComControlBase::m_bDrawGetDataInHimetric](#m_bdrawgetdatainhimetric)|함을 나타내는 플래그 `IDataObjectImpl::GetData` 그릴 때 HIMETRIC 단위 및 픽셀이 아닌 사용 해야 합니다.|  
|[CComControlBase::m_bInPlaceActive](#m_binplaceactive)|이 컨트롤의 내부 활성화를 나타내는 플래그입니다.|  
|[CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex)|컨테이너에서 지 원하는 나타내는 플래그는 **IOleInPlaceSiteEx** 인터페이스와 OCX96 및 깜박임 창 없는 컨트롤 등의 기능을 제어 합니다.|  
|[CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd)|컨트롤 (예: 깜박임 및 창 없는 컨트롤), OCX96 제어 기능에 대 한 지원에 대 한 컨테이너와 협상에 여부 및 기간 이동 또는 창 없는 컨트롤 인지를 나타내는 플래그입니다.|  
|[CComControlBase::m_bRecomposeOnResize](#m_brecomposeonresize)|컨트롤 컨테이너 컨트롤의 표시 크기를 변경 하는 경우에 표시를 다시 구성 하기 위해가 나타내는 플래그입니다.|  
|[CComControlBase::m_bRequiresSave](#m_brequiressave)|컨트롤은 마지막으로 저장 된 이후 변경 되었음을 나타내는 플래그입니다.|  
|[CComControlBase::m_bResizeNatural](#m_bresizenatural)|컨트롤의 자연 스러운 범위가 (배율이 지정 되지 않은 실제 크기)의 크기를 조정 하려면가 나타내는 플래그 컨테이너 컨트롤의 표시 크기를 변경 하는 경우.|  
|[CComControlBase::m_bUIActive](#m_buiactive)|도구 모음, 메뉴 등의 컨트롤의 사용자 인터페이스를 나타내는 플래그는 활성 상태입니다.|  
|[CComControlBase::m_bUsingWindowRgn](#m_busingwindowrgn)|컨트롤 컨테이너 공급 창 영역을 사용 하는 나타내는 플래그입니다.|  
|[CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless)|컨트롤, 창 없는 되었습니다 있지만 수 있거나 없을 수도 있습니다 창 없는 이제 나타내는 플래그입니다.|  
|[CComControlBase::m_bWindowOnly](#m_bwindowonly)|컨테이너 창 없는 컨트롤을 지 원하는 경우에 컨트롤을 창 있는 되어야 여부를 나타내는 플래그입니다.|  
|[CComControlBase::m_bWndLess](#m_bwndless)|창 없는 컨트롤을 나타내는 플래그입니다.|  
|[CComControlBase::m_hWndCD](#m_hwndcd)|컨트롤과 연결 된 창 핸들에 대 한 참조를 포함 합니다.|  
|[CComControlBase::m_nFreezeEvents](#m_nfreezeevents)|횟수 개수 컨테이너가 이벤트 (이벤트에 대 한 동의)의 중간는 재개 하지 않고 이벤트 (이벤트 수락을 거부 했습니다) 고정 합니다.|  
|[CComControlBase::m_rcPos](#m_rcpos)|컨테이너의 좌표로 표시 되는 컨트롤의 위치 (픽셀)에서입니다.|  
|[CComControlBase::m_sizeExtent](#m_sizeextent)|특정 디스플레이 대 한 HIMETRIC 단위 (각 단위는 0.01 밀리미터는) 컨트롤의 범위입니다.|  
|[CComControlBase::m_sizeNatural](#m_sizenatural)|HIMETRIC 단위 (각 단위는 0.01 밀리미터는) 컨트롤의 실제 크기입니다.|  
|[CComControlBase::m_spAdviseSink](#m_spadvisesink)|컨테이너에서 권장 하는 연결에 대 한 직접 포인터 (컨테이너의 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).|  
|[CComControlBase::m_spAmbientDispatch](#m_spambientdispatch)|A `CComDispatchDriver` 를 검색 하 고 컨테이너의 속성을 설정할 수 있는 개체는 `IDispatch` 포인터입니다.|  
|[CComControlBase::m_spClientSite](#m_spclientsite)|컨테이너 내의 컨트롤의 클라이언트 사이트에 대 한 포인터입니다.|  
|[CComControlBase::m_spDataAdviseHolder](#m_spdataadviseholder)|어드바이스 싱크 및 데이터 개체 간의 자문 연결을 유지 하는 표준 방법을 제공 합니다.|  
|[CComControlBase::m_spInPlaceSite](#m_spinplacesite)|컨테이너의에 대 한 포인터 [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), 또는 [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) 인터페이스 포인터입니다.|  
|[CComControlBase::m_spOleAdviseHolder](#m_spoleadviseholder)|자문 연결을 유지 하는 방법의 표준 구현을 제공 합니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 만들고 ATL 컨트롤을 관리 하기 위한 메서드를 제공 합니다. [CComControl 클래스](../../atl/reference/ccomcontrol-class.md) 에서 파생 되며 `CComControlBase`합니다. ATL 컨트롤 마법사를 사용 하 여 표준 컨트롤 또는 DHTML 컨트롤을 만들 때 마법사는 자동으로에서 파생 `CComControlBase`합니다.  
  
 컨트롤을 만드는 방법에 대 한 자세한 내용은 참조는 [ATL 자습서](../../atl/active-template-library-atl-tutorial.md)합니다. ATL 프로젝트 마법사에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="appearancetype"></a>CComControlBase::AppearanceType  
 필요한 경우 재정의할 프로그램 **m_nAppearance** 스톡 속성은 형식의 **짧은**합니다.  
  
```
typedef short AppearanceType;
```  
  
### <a name="remarks"></a>주의  
 ATL 컨트롤 마법사 추가 **m_nAppearance** 스톡 짧은 형식의 속성입니다. 재정의 `AppearanceType` 다른 데이터 형식을 사용 하는 경우.  
  
##  <a name="ccomcontrolbase"></a>CComControlBase::CComControlBase  
 생성자입니다.  
  
```
CComControlBase(HWND& h);
```  
  
### <a name="parameters"></a>매개 변수  
 `h`  
 컨트롤과 연결 된 창 핸들입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤 크기를 HIMETRIC 단위 5080 X 5080를 초기화 합니다 ("2" X 2)를 초기화 하 고는 `CComControlBase` 데이터 멤버 값을 **NULL** 또는 **FALSE**합니다.  
  
##  <a name="dtor"></a>CComControlBase:: ~ CComControlBase  
 소멸자입니다.  
  
```
~CComControlBase();
```  
  
### <a name="remarks"></a>주의  
 컨트롤이 창 있는 경우 `~CComControlBase` 를 호출 하 여 소멸 [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682)합니다.  
  
##  <a name="controlqueryinterface"></a>CComControlBase::ControlQueryInterface  
 요청된 인터페이스에 대한 포인터를 검색합니다.  
  
```
virtual HRESULT ControlQueryInterface(const IID& iid,
    void** ppv);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 요청 된 인터페이스의 GUID입니다.  
  
 `ppv`  
 로 식별 되는 인터페이스 포인터에 대 한 포인터 `iid`, 또는 **NULL** 인터페이스를 찾을 수 없는 경우.  
  
### <a name="remarks"></a>주의  
 에서는 COM 맵 테이블의 인터페이스만 처리 됩니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#15;](../../atl/codesnippet/cpp/ccomcontrolbase-class_1.cpp)]  
  
##  <a name="doesverbactivate"></a>CComControlBase::DoesVerbActivate  
 검사는 `iVerb` 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 컨트롤의 사용자 인터페이스를 활성화 하는 중 하나 ( `iVerb` equals `OLEIVERB_UIACTIVATE`), 컨트롤을 두 번 클릭할 때 수행할 동작을 정의 ( `iVerb` equals `OLEIVERB_PRIMARY`), 컨트롤을 표시 ( `iVerb` equals `OLEIVERB_SHOW`), 컨트롤을 활성화 하거나 ( `iVerb` equals **OLEIVERB_INPLACEACTIVATE**).  
  
```
BOOL DoesVerbActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>매개 변수  
 `iVerb`  
 값의 동작을 수행 하도록 나타내는 `DoVerb`합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 경우 `iVerb` equals `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, 또는 **OLEIVERB_INPLACEACTIVATE**고, 그렇지 않으면 반환 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 사용자 고유의 활성화 동사를 정의 하려면이 메서드를 재정의할 수 있습니다.  
  
##  <a name="doesverbuiactivate"></a>CComControlBase::DoesVerbUIActivate  
 검사는 `iVerb` 매개 변수에서 사용 하는 `IOleObjectImpl::DoVerb` 컨트롤의 사용자 인터페이스를 활성화 하 고 반환 **TRUE**합니다.  
  
```
BOOL DoesVerbUIActivate(LONG iVerb);
```  
  
### <a name="parameters"></a>매개 변수  
 `iVerb`  
 값의 동작을 수행 하도록 나타내는 `DoVerb`합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 경우 `iVerb` equals `OLEIVERB_UIACTIVATE`, `OLEIVERB_PRIMARY`, `OLEIVERB_SHOW`, 또는 **OLEIVERB_INPLACEACTIVATE**합니다. 그렇지 않으면 메서드가 반환 **FALSE**합니다.  
  
##  <a name="doverbproperties"></a>CComControlBase::DoVerbProperties  
 컨트롤의 속성 페이지를 표시합니다.  
  
```
HRESULT DoVerbProperties(LPCRECT /* prcPosRect */, HWND hwndParent);
```  
  
### <a name="parameters"></a>매개 변수  
 `prcPosRec`  
 예약됨.  
  
 *창은*  
 컨트롤이 포함 된 창 핸들입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#19;](../../atl/codesnippet/cpp/ccomcontrolbase-class_2.cpp)]  
  
 [!code-cpp[NVC_ATL_COM&#20;](../../atl/codesnippet/cpp/ccomcontrolbase-class_3.h)]  
  
##  <a name="fireviewchange"></a>CComControlBase::FireViewChange  
 컨트롤의 뷰가 변경 되는 등록 된 advise 싱크 또는 컨테이너 컨트롤 다시 그리기를 구별 하는이 메서드를 호출 합니다.  
  
```
HRESULT FireViewChange();
```  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤이 활성화 된 경우 (컨트롤 클래스 데이터 멤버 [CComControlBase::m_bInPlaceActive](#m_binplaceactive) 는 **TRUE**), 전체 컨트롤을 다시 그리도록 하려면 컨테이너에 알립니다. 컨트롤이 활성 상태인 경우 컨트롤의 등록 된 알립니다 어드바이스 싱크 (컨트롤 클래스 데이터 멤버를 통해 [CComControlBase::m_spAdviseSink](#m_spadvisesink)) 컨트롤의 뷰 변경 되었습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[#21 NVC_ATL_COM](../../atl/codesnippet/cpp/ccomcontrolbase-class_4.cpp)]  
  
##  <a name="getambientappearance"></a>CComControlBase::GetAmbientAppearance  
 검색 **DISPID_AMBIENT_APPEARANCE**, 컨트롤 설정 현재 모양을: 0 평면 음영 및 3D에 대 한 1입니다.  
  
```
HRESULT GetAmbientAppearance(short& nAppearance);
```  
  
### <a name="parameters"></a>매개 변수  
 `nAppearance`  
 속성은 **DISPID_AMBIENT_APPEARANCE**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[#22 NVC_ATL_COM](../../atl/codesnippet/cpp/ccomcontrolbase-class_5.h)]  
  
##  <a name="getambientautoclip"></a>CComControlBase::GetAmbientAutoClip  
 검색 **DISPID_AMBIENT_AUTOCLIP**, 컨테이너 컨트롤 표시 영역의 자동 캡처를 지원 하는지 여부를 나타내는 플래그입니다.  
  
```
HRESULT GetAmbientAutoClip(BOOL& bAutoClip);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAutoClip*  
 속성은 **DISPID_AMBIENT_AUTOCLIP**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientbackcolor"></a>CComControlBase::GetAmbientBackColor  
 검색 **DISPID_AMBIENT_BACKCOLOR**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 배경색입니다.  
  
```
HRESULT GetAmbientBackColor(OLE_COLOR& BackColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *BackColor*  
 속성은 **DISPID_AMBIENT_BACKCOLOR**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientcharset"></a>CComControlBase::GetAmbientCharSet  
 검색 **DISPID_AMBIENT_CHARSET**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 문자 집합입니다.  
  
```
HRESULT GetAmbientCharSet(BSTR& bstrCharSet);
```  
  
### <a name="parameters"></a>매개 변수  
 *bstrCharSet*  
 속성은 **DISPID_AMBIENT_CHARSET**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="getambientcodepage"></a>CComControlBase::GetAmbientCodePage  
 검색 **DISPID_AMBIENT_CODEPAGE**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 코드 페이지입니다.  
  
```
HRESULT GetAmbientCodePage(ULONG& ulCodePage);
```  
  
### <a name="parameters"></a>매개 변수  
 *ulCodePage*  
 속성은 **DISPID_AMBIENT_CODEPAGE**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="getambientdisplayasdefault"></a>CComControlBase::GetAmbientDisplayAsDefault  
 검색 **DISPID_AMBIENT_DISPLAYASDEFAULT**를 하는 플래그 **TRUE** 경우 컨테이너는 컨트롤을 기본 단추로이 사이트에 표시 하 고 따라서 button 컨트롤을 그릴 자체 두꺼운 프레임이 합니다.  
  
```
HRESULT GetAmbientDisplayAsDefault(BOOL& bDisplayAsDefault);
```  
  
### <a name="parameters"></a>매개 변수  
 `bDisplayAsDefault`  
 속성은 **DISPID_AMBIENT_DISPLAYASDEFAULT**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientdisplayname"></a>CComControlBase::GetAmbientDisplayName  
 검색 **DISPID_AMBIENT_DISPLAYNAME**, 컨테이너에 컨트롤에 제공 된 이름입니다.  
  
```
HRESULT GetAmbientDisplayName(BSTR& bstrDisplayName);
```  
  
### <a name="parameters"></a>매개 변수  
 *bstrDisplayName*  
 속성은 **DISPID_AMBIENT_DISPLAYNAME**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientfont"></a>CComControlBase::GetAmbientFont  
 검색 된 컨테이너에 대 한 포인터의 앰비언트 `IFont` 인터페이스입니다.  
  
```
HRESULT GetAmbientFont(IFont** ppFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppFont`  
 컨테이너에 대 한 포인터의 앰비언트 [IFont](http://msdn.microsoft.com/library/windows/desktop/ms680673) 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 속성이 있으면 **NULL**, 포인터가 **NULL**합니다. 포인터가 없으면 **NULL**, 호출자는 포인터를 해제 해야 합니다.  
  
##  <a name="getambientfontdisp"></a>CComControlBase::GetAmbientFontDisp  
 검색 된 컨테이너에 대 한 포인터의 앰비언트 **IFontDisp** 디스패치 인터페이스입니다.  
  
```
HRESULT GetAmbientFontDisp(IFontDisp** ppFont);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppFont`  
 컨테이너에 대 한 포인터의 앰비언트 [IFontDisp](http://msdn.microsoft.com/library/windows/desktop/ms692695) 디스패치 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 속성이 있으면 **NULL**, 포인터가 **NULL**합니다. 포인터가 없으면 **NULL**, 호출자는 포인터를 해제 해야 합니다.  
  
##  <a name="getambientforecolor"></a>CComControlBase::GetAmbientForeColor  
 검색 **DISPID_AMBIENT_FORECOLOR**, 컨테이너에 의해 정의 된 모든 컨트롤에 대 한 앰비언트 전경색입니다.  
  
```
HRESULT GetAmbientForeColor(OLE_COLOR& ForeColor);
```  
  
### <a name="parameters"></a>매개 변수  
 *전경색*  
 속성은 **DISPID_AMBIENT_FORECOLOR**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientlocaleid"></a>CComControlBase::GetAmbientLocaleID  
 검색 **DISPID_AMBIENT_LOCALEID**, 컨테이너에서 사용 되는 언어의 식별자입니다.  
  
```
HRESULT GetAmbientLocaleID(LCID& lcid);
```  
  
### <a name="parameters"></a>매개 변수  
 `lcid`  
 속성은 **DISPID_AMBIENT_LOCALEID**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 컨트롤이 다른 언어에 해당 사용자 인터페이스에 맞게이 식별자를 사용할 수 있습니다.  
  
##  <a name="getambientmessagereflect"></a>CComControlBase::GetAmbientMessageReflect  
 검색 **DISPID_AMBIENT_MESSAGEREFLECT**, 컨테이너를 창 메시지를 수신 하려고 하는지 여부를 나타내는 플래그 (예: `WM_DRAWITEM`) 이벤트로 합니다.  
  
```
HRESULT GetAmbientMessageReflect(BOOL& bMessageReflect);
```  
  
### <a name="parameters"></a>매개 변수  
 `bMessageReflect`  
 속성은 **DISPID_AMBIENT_MESSAGEREFLECT**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientpalette"></a>CComControlBase::GetAmbientPalette  
 검색 **DISPID_AMBIENT_PALETTE**계정에 컨테이너 액세스에 사용 되는 `HPALETTE`합니다.  
  
```
HRESULT GetAmbientPalette(HPALETTE& hPalette);
```  
  
### <a name="parameters"></a>매개 변수  
 `hPalette`  
 속성은 **DISPID_AMBIENT_PALETTE**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientproperty"></a>CComControlBase::GetAmbientProperty  
 지정 된 컨테이너 속성을 검색 `dispid`합니다.  
  
```
HRESULT GetAmbientProperty(DISPID dispid, VARIANT& var);
```  
  
### <a name="parameters"></a>매개 변수  
 `dispid`  
 검색할 컨테이너 속성의 식별자입니다.  
  
 `var`  
 속성을 받을 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 ATL에서 예를 들어 특정 속성을 검색 하는 도우미 함수 집합이 제공 [CComControlBase::GetAmbientBackColor](#getambientbackcolor)합니다. 사용할 수 있는 적절 한 메서드가 없는 경우 사용 하 여 `GetAmbientProperty`합니다.  
  
##  <a name="getambientrighttoleft"></a>CComControlBase::GetAmbientRightToLeft  
 검색 **DISPID_AMBIENT_RIGHTTOLEFT**, 콘텐츠는 컨테이너에 의해 표시 되는 방향입니다.  
  
```
HRESULT GetAmbientRightToLeft(BOOL& bRightToLeft);
```  
  
### <a name="parameters"></a>매개 변수  
 *bRightToLeft*  
 속성은 **DISPID_AMBIENT_RIGHTTOLEFT**합니다. 로 설정 **TRUE** 콘텐츠 오른쪽에서 왼쪽으로 표시 되 면 **FALSE** 왼쪽에서 오른쪽으로 표시 되어 있는 경우.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="getambientscaleunits"></a>CComControlBase::GetAmbientScaleUnits  
 검색 **DISPID_AMBIENT_SCALEUNITS**, 컨테이너의 앰비언트 단위 (예: 인치 또는 센티미터로) 표시에 레이블을 지정 합니다.  
  
```
HRESULT GetAmbientScaleUnits(BSTR& bstrScaleUnits);
```  
  
### <a name="parameters"></a>매개 변수  
 *bstrScaleUnits*  
 속성은 **DISPID_AMBIENT_SCALEUNITS**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientshowgrabhandles"></a>CComControlBase::GetAmbientShowGrabHandles  
 검색 **DISPID_AMBIENT_SHOWGRABHANDLES**, 컨테이너 활성화 된 경우 자신에 대 한 잡기 핸들을 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그입니다.  
  
```
HRESULT GetAmbientShowGrabHandles(BOOL& bShowGrabHandles);
```  
  
### <a name="parameters"></a>매개 변수  
 *bShowGrabHandles*  
 속성은 **DISPID_AMBIENT_SHOWGRABHANDLES**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientshowhatching"></a>CComControlBase::GetAmbientShowHatching  
 검색 **DISPID_AMBIENT_SHOWHATCHING**, 컨테이너 컨트롤의 사용자 인터페이스 활성화 되어 있을 때 교차 무늬 패턴으로 표시 하도록 컨트롤을 허용 하는지 여부를 나타내는 플래그입니다.  
  
```
HRESULT GetAmbientShowHatching(BOOL& bShowHatching);
```  
  
### <a name="parameters"></a>매개 변수  
 *bShowHatching*  
 속성은 **DISPID_AMBIENT_SHOWHATCHING**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambientsupportsmnemonics"></a>CComControlBase::GetAmbientSupportsMnemonics  
 검색 **DISPID_AMBIENT_SUPPORTSMNEMONICS**, 컨테이너 키보드 니모닉을 지원 하는지 여부를 나타내는 플래그입니다.  
  
```
HRESULT GetAmbientSupportsMnemonics(BOOL& bSupportsMnemonics);
```  
  
### <a name="parameters"></a>매개 변수  
 *bSupportsMnemonics*  
 속성은 **DISPID_AMBIENT_SUPPORTSMNEMONICS**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambienttextalign"></a>CComControlBase::GetAmbientTextAlign  
 검색 **DISPID_AMBIENT_TEXTALIGN**, 컨테이너에서 지 원하는 기본 텍스트 맞춤: 일반 맞춤 (번호 오른쪽으로 텍스트를 왼쪽)에 대 한 0, 1 왼쪽 맞춤, 가운데 맞춤에 대 한 2 및 3 오른쪽 맞춤에 대 한 합니다.  
  
```
HRESULT GetAmbientTextAlign(short& nTextAlign);
```  
  
### <a name="parameters"></a>매개 변수  
 *nTextAlign*  
 속성은 **DISPID_AMBIENT_TEXTALIGN**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getambienttoptobottom"></a>CComControlBase::GetAmbientTopToBottom  
 검색 **DISPID_AMBIENT_TOPTOBOTTOM**, 콘텐츠는 컨테이너에 의해 표시 되는 방향입니다.  
  
```
HRESULT GetAmbientTopToBottom(BOOL& bTopToBottom);
```  
  
### <a name="parameters"></a>매개 변수  
 *bTopToBottom*  
 속성은 **DISPID_AMBIENT_TOPTOBOTTOM**합니다. 로 설정 **TRUE** 텍스트 표시 되 면 위쪽에서 아래쪽으로 **FALSE** 표시 되 면 아래쪽에서 위쪽입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="getambientuidead"></a>CComControlBase::GetAmbientUIDead  
 검색 **DISPID_AMBIENT_UIDEAD**, 컨테이너가 컨트롤을 사용자 인터페이스 작업에 응답 하는지 여부를 나타내는 플래그입니다.  
  
```
HRESULT GetAmbientUIDead(BOOL& bUIDead);
```  
  
### <a name="parameters"></a>매개 변수  
 *bUIDead*  
 속성은 **DISPID_AMBIENT_UIDEAD**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 경우 **TRUE**, 컨트롤이 응답 하지 않아야 합니다. 이 플래그에 관계 없이 적용 되는 **DISPID_AMBIENT_USERMODE** 플래그입니다. 참조 [CComControlBase::GetAmbientUserMode](#getambientusermode)합니다.  
  
##  <a name="getambientusermode"></a>CComControlBase::GetAmbientUserMode  
 검색 **DISPID_AMBIENT_USERMODE**, 컨테이너 실행 모드 인지 여부를 나타내는 플래그 ( **TRUE**) 또는 디자인 모드 ( **FALSE**).  
  
```
HRESULT GetAmbientUserMode(BOOL& bUserMode);
```  
  
### <a name="parameters"></a>매개 변수  
 `bUserMode`  
 속성은 **DISPID_AMBIENT_USERMODE**합니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
##  <a name="getdirty"></a>CComControlBase::GetDirty  
 데이터 멤버의 값을 반환 `m_bRequiresSave`합니다.  
  
```
BOOL GetDirty();
```  
  
### <a name="return-value"></a>반환 값  
 데이터 멤버의 값을 반환 [m_bRequiresSave](#m_brequiressave)합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여이 값은 설정 [CComControlBase::SetDirty](#setdirty)합니다.  
  
##  <a name="getzoominfo"></a>CComControlBase::GetZoomInfo  
 X 및 y 검색 분자와 분모의 확대/축소 비율의 값에 대 한 컨트롤이 활성화에 대 한 전체 편집 합니다.  
  
```
void GetZoomInfo(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>매개 변수  
 `di`  
 확대/축소 비율의 분자와 분모를 보유 하는 구조입니다. 자세한 내용은 참조 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md)합니다.  
  
### <a name="remarks"></a>주의  
 확대/축소 비율은 현재 범위를 컨트롤의 기본 크기의 비율입니다.  
  
##  <a name="inplaceactivate"></a>CComControlBase::InPlaceActivate  
 동사에 상태로 비활성 상태에서 전환 하면 컨트롤이 `iVerb` 나타냅니다.  
  
```
HRESULT InPlaceActivate(LONG iVerb, const RECT* prcPosRect = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `iVerb`  
 값의 동작을 수행 하도록 나타내는 [IOleObjectImpl::DoVerb](../../atl/reference/ioleobjectimpl-class.md#doverb)합니다.  
  
 *prcPosRect*  
 전체 컨트롤의 위치에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 HRESULT 값 중 하나입니다.  
  
### <a name="remarks"></a>주의  
 정품 인증을 하기 전에이 메서드 있는지 확인 컨트롤 클라이언트 사이트에, 표시 되는 컨트롤의 크기를 확인 한 부모 창에서 컨트롤의 위치를 가져옵니다. 컨트롤이 활성화 되 면이 메서드는 컨트롤의 사용자 인터페이스를 활성화 하 고 컨트롤을 표시 하려면 컨테이너를 알려줍니다.  
  
 이 메서드는 또한 검색 된 `IOleInPlaceSite`, **IOleInPlaceSiteEx**, 또는 **IOleInPlaceSiteWindowless** 컨트롤에 대 한 인터페이스 포인터 컨트롤 클래스의 데이터 멤버에 저장 하 고 [CComControlBase::m_spInPlaceSite](#m_spinplacesite). 컨트롤 클래스 데이터 멤버 [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex), [CComControlBase::m_bWndLess](#m_bwndless), [CComControlBase::m_bWasOnceWindowless](#m_bwasoncewindowless), 및 [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) 적절 하 게 true로 설정 됩니다.  
  
##  <a name="internalgetsite"></a>CComControlBase::InternalGetSite  
 컨트롤 사이트에서 식별 된 인터페이스 포인터에 대 한 쿼리를이 메서드를 호출 합니다.  
  
```
HRESULT InternalGetSite(REFIID riid, void** ppUnkSite);
```  
  
### <a name="parameters"></a>매개 변수  
 `riid`  
 반환 되는 인터페이스 포인터의 IID `ppUnkSite`합니다.  
  
 `ppUnkSite`  
 요청 된 인터페이스 포인터를 받는 포인터 변수의 주소 `riid`합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 사이트에서 요청 된 인터페이스를 지 원하는 경우 `riid`, 방법으로 포인터가 반환 됩니다 `ppUnkSite`합니다. 그렇지 않으면 `ppUnkSite` NULL로 설정 됩니다.  
  
##  <a name="m_bautosize"></a>CComControlBase::m_bAutoSize  
 컨트롤에는 다른 크기 일 수 없습니다 나타내는 플래그입니다.  
  
```
unsigned m_bAutoSize:1;
```  
  
### <a name="remarks"></a>주의  
 이 플래그는 확인자 `IOleObjectImpl::SetExtent` 하며, **TRUE**, 함수 반환 하 **E_FAIL**합니다.  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 추가 하는 경우는 **자동 크기** 옵션에 [스톡 속성](../../atl/reference/stock-properties-atl-control-wizard.md) ATL 컨트롤 마법사, 마법사의 탭 자동으로 컨트롤 클래스에서이 데이터 멤버를 만들고, put 만들고 속성 및 지원에 대 한 get 메서드 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 는 속성이 변경 될 때 컨테이너를 자동으로 알릴 수 있습니다.  
  
##  <a name="m_bdrawfromnatural"></a>CComControlBase::m_bDrawFromNatural  
 함을 나타내는 플래그 `IDataObjectImpl::GetData` 및 `CComControlBase::GetZoomInfo` 에서 컨트롤 크기를 설정 해야 `m_sizeNatural` 아닌 `m_sizeExtent`합니다.  
  
```
unsigned m_bDrawFromNatural:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_bdrawgetdatainhimetric"></a>CComControlBase::m_bDrawGetDataInHimetric  
 함을 나타내는 플래그 `IDataObjectImpl::GetData` 그릴 때 HIMETRIC 단위 및 픽셀이 아닌 사용 해야 합니다.  
  
```
unsigned m_bDrawGetDataInHimetric:1;
```  
  
### <a name="remarks"></a>주의  
 각 논리 HIMETRIC 단위는 0.01 m m입니다.  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_binplaceactive"></a>CComControlBase::m_bInPlaceActive  
 이 컨트롤의 내부 활성화를 나타내는 플래그입니다.  
  
```
unsigned m_bInPlaceActive:1;
```  
  
### <a name="remarks"></a>주의  
 즉 컨트롤이 표시 되 고 해당 창에서 해당 하는 경우 표시 되지만 해당 메뉴와 도구 모음이 활성화 될 수 있습니다. `m_bUIActive` 플래그 등 메뉴, 컨트롤의 사용자 인터페이스에도 작동을 나타냅니다.  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_binplacesiteex"></a>CComControlBase::m_bInPlaceSiteEx  
 컨테이너에서 지 원하는 나타내는 플래그는 **IOleInPlaceSiteEx** 인터페이스와 OCX96 및 깜박임 창 없는 컨트롤 등의 기능을 제어 합니다.  
  
```
unsigned m_bInPlaceSiteEx:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 데이터 멤버 `m_spInPlaceSite` 가리키는 [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), 또는 [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) 값에 따라 인터페이스는 `m_bWndLess` 및 `m_bInPlaceSiteEx` 플래그입니다. (데이터 멤버 `m_bNegotiatedWnd` 해야 **TRUE** 에 대 한는 `m_spInPlaceSite` 유효에 대 한 포인터입니다.)  
  
 경우 `m_bWndLess` 는 **FALSE** 및 `m_bInPlaceSiteEx` 는 **TRUE**, `m_spInPlaceSite` 는 **IOleInPlaceSiteEx** 인터페이스 포인터입니다. 참조 [m_spInPlaceSite](#m_spinplacesite) 이러한 세 가지 데이터 멤버 간의 관계를 보여 주는 표입니다.  
  
##  <a name="m_bnegotiatedwnd"></a>CComControlBase::m_bNegotiatedWnd  
 컨트롤 (예: 깜박임 및 창 없는 컨트롤), OCX96 제어 기능에 대 한 지원에 대 한 컨테이너와 협상에 여부 및 기간 이동 또는 창 없는 컨트롤 인지를 나타내는 플래그입니다.  
  
```
unsigned m_bNegotiatedWnd:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 `m_bNegotiatedWnd` 플래그 여야 **TRUE** 에 대 한는 `m_spInPlaceSite` 유효에 대 한 포인터입니다.  
  
##  <a name="m_brecomposeonresize"></a>CComControlBase::m_bRecomposeOnResize  
 컨트롤 컨테이너 컨트롤의 표시 크기를 변경 하는 경우에 표시를 다시 구성 하기 위해가 나타내는 플래그입니다.  
  
```
unsigned m_bRecomposeOnResize:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 이 플래그는 확인자 [IOleObjectImpl::SetExtent](../../atl/reference/ioleobjectimpl-class.md#setextent) 하며, **TRUE**, `SetExtent` 변경 내용 보기의 컨테이너에 알립니다. 이 플래그를 설정 하는 경우는 **OLEMISC_RECOMPOSEONRESIZE** 에 비트는 [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) 열거형 설정 해야 합니다.  
  
##  <a name="m_brequiressave"></a>CComControlBase::m_bRequiresSave  
 컨트롤은 마지막으로 저장 된 이후 변경 되었음을 나타내는 플래그입니다.  
  
```
unsigned m_bRequiresSave:1;
```  
  
### <a name="remarks"></a>주의  
 값 `m_bRequiresSave` 로 설정할 수 있습니다 [CComControlBase::SetDirty](#setdirty) 와 검색 및 [CComControlBase::GetDirty](#getdirty)합니다.  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_bresizenatural"></a>CComControlBase::m_bResizeNatural  
 컨트롤의 자연 스러운 범위가 (배율이 지정 되지 않은 실제 크기)의 크기를 조정 하려면가 나타내는 플래그 컨테이너 컨트롤의 표시 크기를 변경 하는 경우.  
  
```
unsigned m_bResizeNatural:1;
```  
  
### <a name="remarks"></a>주의  
 이 플래그는 확인자 `IOleObjectImpl::SetExtent` 하며, **TRUE**, 크기에 전달 된 `SetExtent` 에 할당 된 `m_sizeNatural`합니다.  
  
 로 전달 된 크기 `SetExtent` 은 항상 할당 `m_sizeExtent`의 값에 관계 없이 `m_bResizeNatural`합니다.  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_buiactive"></a>CComControlBase::m_bUIActive  
 도구 모음, 메뉴 등의 컨트롤의 사용자 인터페이스를 나타내는 플래그는 활성 상태입니다.  
  
```
unsigned m_bUIActive:1;
```  
  
### <a name="remarks"></a>주의  
 `m_bInPlaceActive` 플래그 활성, 하지만 하는 것에 컨트롤을 나타냅니다. 사용자 인터페이스 활성화 되어 있습니다.  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_busingwindowrgn"></a>CComControlBase::m_bUsingWindowRgn  
 컨트롤 컨테이너 공급 창 영역을 사용 하는 나타내는 플래그입니다.  
  
```
unsigned m_bUsingWindowRgn:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_bwasoncewindowless"></a>CComControlBase::m_bWasOnceWindowless  
 컨트롤, 창 없는 되었습니다 있지만 수 있거나 없을 수도 있습니다 창 없는 이제 나타내는 플래그입니다.  
  
```
unsigned m_bWasOnceWindowless:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_bwindowonly"></a>CComControlBase::m_bWindowOnly  
 컨테이너 창 없는 컨트롤을 지 원하는 경우에 컨트롤을 창 있는 되어야 여부를 나타내는 플래그입니다.  
  
```
unsigned m_bWindowOnly:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_bwndless"></a>CComControlBase::m_bWndLess  
 창 없는 컨트롤을 나타내는 플래그입니다.  
  
```
unsigned m_bWndLess:1;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 데이터 멤버 `m_spInPlaceSite` 가리키는 [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), 또는 [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) 값에 따라 인터페이스는 `m_bWndLess` 및 [CComControlBase::m_bInPlaceSiteEx](#m_binplacesiteex) 플래그입니다. (데이터 멤버 [CComControlBase::m_bNegotiatedWnd](#m_bnegotiatedwnd) 해야 **TRUE** 에 대 한는 [CComControlBase::m_spInPlaceSite](#m_spinplacesite) 유효에 대 한 포인터입니다.)  
  
 경우 `m_bWndLess` 는 **TRUE**, `m_spInPlaceSite` 는 **IOleInPlaceSiteWindowless** 인터페이스 포인터입니다. 참조 [CComControlBase::m_spInPlaceSite](#m_spinplacesite) 이러한 데이터 멤버의 전체 관계를 보여 주는 표입니다.  
  
##  <a name="m_hwndcd"></a>CComControlBase::m_hWndCD  
 컨트롤과 연결 된 창 핸들에 대 한 참조를 포함 합니다.  
  
```
HWND& m_hWndCD;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_nfreezeevents"></a>CComControlBase::m_nFreezeEvents  
 횟수 개수 컨테이너가 이벤트 (이벤트에 대 한 동의)의 중간는 재개 하지 않고 이벤트 (이벤트 수락을 거부 했습니다) 고정 합니다.  
  
```
short m_nFreezeEvents;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_rcpos"></a>CComControlBase::m_rcPos  
 컨테이너의 좌표로 표시 되는 컨트롤의 위치 (픽셀)에서입니다.  
  
```
RECT m_rcPos;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_sizeextent"></a>CComControlBase::m_sizeExtent  
 특정 디스플레이 대 한 HIMETRIC 단위 (각 단위는 0.01 밀리미터는) 컨트롤의 범위입니다.  
  
```
SIZE m_sizeExtent;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 이 크기는 표시 하 여 확장 합니다. 컨트롤의 실제 크기에 지정 된는 `m_sizeNatural` 데이터 멤버 고정 됩니다.  
  
 전역 함수로 픽셀 크기를 변환할 수 있습니다 [AtlHiMetricToPixel](http://msdn.microsoft.com/library/00c3af58-7298-4082-9a2e-5b68a8cec6fd)합니다.  
  
##  <a name="m_sizenatural"></a>CComControlBase::m_sizeNatural  
 HIMETRIC 단위 (각 단위는 0.01 밀리미터는) 컨트롤의 실제 크기입니다.  
  
```
SIZE m_sizeNatural;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 크기는 동안이 크기가 고정 되어 `m_sizeExtent` 표시 크기를 조정 합니다.  
  
 전역 함수로 픽셀 크기를 변환할 수 있습니다 [AtlHiMetricToPixel](http://msdn.microsoft.com/library/00c3af58-7298-4082-9a2e-5b68a8cec6fd)합니다.  
  
##  <a name="m_spadvisesink"></a>CComControlBase::m_spAdviseSink  
 컨테이너에서 권장 하는 연결에 대 한 직접 포인터 (컨테이너의 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513)).  
  
```
CComPtr<IAdviseSink>
    m_spAdviseSink;
```     
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_spambientdispatch"></a>CComControlBase::m_spAmbientDispatch  
 A `CComDispatchDriver` 를 검색 하 고 개체의 속성을 설정할 수 있는 개체는 `IDispatch` 포인터입니다.  
  
```
CComDispatchDriver m_spAmbientDispatch;
```  
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_spclientsite"></a>CComControlBase::m_spClientSite  
 컨테이너 내의 컨트롤의 클라이언트 사이트에 대 한 포인터입니다.  
  
```
CComPtr<IOleClientSite>
    m_spClientSite;
```     
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
##  <a name="m_spdataadviseholder"></a>CComControlBase::m_spDataAdviseHolder  
 어드바이스 싱크 및 데이터 개체 간의 자문 연결을 유지 하는 표준 방법을 제공 합니다.  
  
```
CComPtr<IDataAdviseHolder>
    m_spDataAdviseHolder;
```     
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 데이터 개체는 데이터를 전송할 수 있는 구현 하는 컨트롤 [IDataObject](http://msdn.microsoft.com/library/windows/desktop/ms688421), 해당 메서드 데이터의 형식 및 전송 매체를 지정 합니다.  
  
 인터페이스 `m_spDataAdviseHolder` 구현 하는 [IDataObject::DAdvise](http://msdn.microsoft.com/library/windows/desktop/ms692579) 및 [IDataObject::DUnadvise](http://msdn.microsoft.com/library/windows/desktop/ms692448) 메서드를 설정 하 고 컨테이너에 대 한 자문 연결을 삭제 합니다. 컨트롤의 컨테이너를 지원 하 여 advise 싱크를 구현 해야는 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) 인터페이스입니다.  
  
##  <a name="m_spinplacesite"></a>CComControlBase::m_spInPlaceSite  
 컨테이너의에 대 한 포인터 [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleInPlaceSiteEx](http://msdn.microsoft.com/library/windows/desktop/ms693461), 또는 [IOleInPlaceSiteWindowless](http://msdn.microsoft.com/library/windows/desktop/ms682300) 인터페이스 포인터입니다.  
  
```
CComPtr<IOleInPlaceSiteWindowless>
    m_spInPlaceSite;
```     
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 `m_spInPlaceSite` 포인터가 유효한 경우에만 [m_bNegotiatedWnd](#m_bnegotiatedwnd) 플래그는 **TRUE**합니다.  
  
 다음 표에서 표시 방법을 `m_spInPlaceSite` 포인터 형식에 따라 달라 집니다는 [m_bWndLess](#m_bwndless) 및 [m_bInPlaceSiteEx](#m_binplacesiteex) 데이터 멤버 플래그:  
  
|m_spInPlaceSite 유형|m_bWndLess 값|m_bInPlaceSiteEx 값|  
|---------------------------|-----------------------|-----------------------------|  
|**IOleInPlaceSiteWindowless**|**TRUE**|**True 이면** 또는 **FALSE**|  
|**IOleInPlaceSiteEx**|**FALSE**|**TRUE**|  
|`IOleInPlaceSite`|**FALSE**|**FALSE**|  
  
##  <a name="m_spoleadviseholder"></a>CComControlBase::m_spOleAdviseHolder  
 자문 연결을 유지 하는 방법의 표준 구현을 제공 합니다.  
  
```
CComPtr<IOleAdviseHolder>
    m_spOleAdviseHolder;
```     
  
### <a name="remarks"></a>주의  
  
> [!NOTE]
>  컨트롤 클래스 내에서이 데이터 멤버를 사용 하려면 컨트롤 클래스의 데이터 멤버로 선언 해야 있습니다. 사용자 컨트롤 클래스 기본 클래스의 공용 구조체 내에서 선언 되기 때문에이 데이터 멤버 기본 클래스에서 상속 하지 않습니다.  
  
 인터페이스 `m_spOleAdviseHolder` 구현 하는 [IOleObject::Advise](http://msdn.microsoft.com/library/windows/desktop/ms686573) 및 [IOleObject::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms693749) 메서드를 설정 하 고 컨테이너에 대 한 자문 연결을 삭제 합니다. 컨트롤의 컨테이너를 지원 하 여 advise 싱크를 구현 해야는 [IAdviseSink](http://msdn.microsoft.com/library/windows/desktop/ms692513) 인터페이스입니다.  
  
##  <a name="ondraw"></a>CComControlBase::OnDraw  
 컨트롤을 그리는 데이 메서드를 재정의 합니다.  
  
```
virtual HRESULT OnDraw(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>매개 변수  
 `di`  
 에 대 한 참조는 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) 컨트롤 범위 그리기 측면은 같은 그리기 정보를 포함 하는 구조 또는 그리기 최적화 되어 있는지 여부.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 기본 `OnDraw` 삭제 또는 장치 컨텍스트를 복원 하거나에 설정 된 플래그에 따라 아무 것도 수행 [CComControlBase::OnDrawAdvanced](#ondrawadvanced)합니다.  
  
 `OnDraw` 메서드가 ATL 컨트롤 마법사와 컨트롤을 만들 때 자동으로 사용자 컨트롤 클래스에 추가 됩니다. 마법사의 기본 `OnDraw` "ATL 8.0" 레이블이 있는 사각형을 그립니다.  
  
### <a name="example"></a>예제  
 예를 참조 [CComControlBase::GetAmbientAppearance](#getambientappearance)합니다.  
  
##  <a name="ondrawadvanced"></a>CComControlBase::OnDrawAdvanced  
 기본 `OnDrawAdvanced` 드로잉에 대 한 정규화 된 장치 컨텍스트를 준비 이면 호출 하는 컨트롤 클래스의 `OnDraw` 메서드.  
  
```
virtual HRESULT OnDrawAdvanced(ATL_DRAWINFO& di);
```  
  
### <a name="parameters"></a>매개 변수  
 `di`  
 에 대 한 참조는 [ATL_DRAWINFO](../../atl/reference/atl-drawinfo-structure.md) 컨트롤 범위 그리기 측면은 같은 그리기 정보를 포함 하는 구조 또는 그리기 최적화 되어 있는지 여부.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 이 정규화 하지 않고 컨테이너에 의해 전달 된 장치 컨텍스트에 적용 하려면이 메서드를 재정의 합니다.  
  
 참조 [CComControlBase::OnDraw](#ondraw) 대 한 자세한 내용은 합니다.  
  
##  <a name="onkillfocus"></a>CComControlBase::OnKillFocus  
 확인 컨트롤에 내부 활성화는 및 유효한 컨트롤 사이트가 한 다음 컨트롤에서 포커스를 잃었을 컨테이너에 게 알립니다.  
  
```
LRESULT OnKillFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMsg`  
 예약됨.  
  
 `wParam`  
 예약됨.  
  
 `lParam`  
 예약됨.  
  
 `bHandled`  
 창 메시지 성공적으로 처리 되었는지 여부를 나타내는 플래그입니다. 기본값은 `FALSE`입니다.  
  
### <a name="return-value"></a>반환 값  
 항상 1을 반환 합니다.  
  
##  <a name="onmouseactivate"></a>CComControlBase::OnMouseActivate  
 UI 사용자 모드에 다음 컨트롤을 활성화를 확인 합니다.  
  
```
LRESULT OnMouseActivate(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMsg`  
 예약됨.  
  
 `wParam`  
 예약됨.  
  
 `lParam`  
 예약됨.  
  
 `bHandled`  
 창 메시지 성공적으로 처리 되었는지 여부를 나타내는 플래그입니다. 기본값은 `FALSE`입니다.  
  
### <a name="return-value"></a>반환 값  
 항상 1을 반환 합니다.  
  
##  <a name="onpaint"></a>CComControlBase::OnPaint  
 그리기에 대 한 컨테이너를 준비, 컨트롤의 클라이언트 영역을 가져온 다음 호출 하는 컨트롤 클래스의 `OnDrawAdvanced` 메서드.  
  
```
LRESULT OnPaint(UINT /* nMsg */,
    WPARAM wParam,
    LPARAM /* lParam */,
    BOOL& /* lResult */);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMsg`  
 예약됨.  
  
 `wParam`  
 기존 HDC 합니다.  
  
 `lParam`  
 예약됨.  
  
 `lResult`  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 항상&0;을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 경우 `wParam` NULL이 아니면 `OnPaint` 가정 하는 유효한 HDC을 유지 하 고 대신 사용 하 여 [CComControlBase::m_hWndCD](#m_hwndcd)합니다.  
  
##  <a name="onsetfocus"></a>CComControlBase::OnSetFocus  
 컨트롤에 내부 활성화는 유효한 컨트롤 사이트가 후 컨테이너 컨트롤에 알립니다 함을 확인에 포커스가 있습니다.  
  
```
LRESULT OnSetFocus(UINT /* nMsg */,
    WPARAM /* wParam */,
    LPARAM /* lParam */,
    BOOL& bHandled);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMsg`  
 예약됨.  
  
 `wParam`  
 예약됨.  
  
 `lParam`  
 예약됨.  
  
 `bHandled`  
 창 메시지 성공적으로 처리 되었는지 여부를 나타내는 플래그입니다. 기본값은 `FALSE`입니다.  
  
### <a name="return-value"></a>반환 값  
 항상 1을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 컨트롤에서 포커스를 받았을 컨테이너에 알림을 보냅니다.  
  
##  <a name="pretranslateaccelerator"></a>CComControlBase::PreTranslateAccelerator  
 고유한 키보드 액셀러레이터 처리기를 제공 하려면이 메서드를 재정의 합니다.  
  
```
BOOL PreTranslateAccelerator(LPMSG /* pMsg */,
    HRESULT& /* hRet */);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMsg`  
 예약됨.  
  
 *hRet*  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 기본적으로 반환 **FALSE**합니다.  
  
##  <a name="sendonclose"></a>CComControlBase::SendOnClose  
 모든 자문 싱크를 등록 된 컨트롤이 닫 혔 advise 소유자에 게 알립니다.  
  
```
HRESULT SendOnClose();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 컨트롤에 해당 자문 싱크를 닫았는지 알림을 보냅니다.  
  
##  <a name="sendondatachange"></a>CComControlBase::SendOnDataChange  
 모든 자문 싱크를 등록 된 컨트롤 데이터가 변경 되었음을 advise 소유자에 게 알립니다.  
  
```
HRESULT SendOnDataChange(DWORD advf = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *advf*  
 통지 플래그를 지정 하는 방법에 대 한 호출 [IAdviseSink::OnDataChange](http://msdn.microsoft.com/library/windows/desktop/ms687283) 이루어집니다. 값은에서 [ADVF](http://msdn.microsoft.com/library/windows/desktop/ms693742) 열거 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="sendonrename"></a>CComControlBase::SendOnRename  
 모든 자문 싱크를 등록 된 컨트롤에는 새 모니커 advise 소유자에 게 알립니다.  
  
```
HRESULT SendOnRename(IMoniker* pmk);
```  
  
### <a name="parameters"></a>매개 변수  
 *pmk*  
 컨트롤의 새 모니커에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 컨트롤에 대 한 moniker 변경 되었음을 나타내는 알림을 보냅니다.  
  
##  <a name="sendonsave"></a>CComControlBase::SendOnSave  
 모든 자문 싱크를 등록 된 컨트롤이 저장 된 advise 소유자에 게 알립니다.  
  
```
HRESULT SendOnSave();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 컨트롤의 데이터를 방금 저장에 알림을 보냅니다.  
  
##  <a name="sendonviewchange"></a>CComControlBase::SendOnViewChange  
 등록 된 모든 자문 싱크에 컨트롤의 뷰 변경 되었음을 알립니다.  
  
```
HRESULT SendOnViewChange(DWORD dwAspect, LONG lindex = -1);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwAspect`  
 모양 또는 컨트롤의 뷰입니다.  
  
 *색인입니다.*  
 변경 된 보기의 일부입니다. -1만 유효합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 `SendOnViewChange`호출 [IAdviseSink::OnViewChange](http://msdn.microsoft.com/library/windows/desktop/ms694337)합니다. 유일한 값 *색인입니다.* 관심 전체 보기 인지 여부를 나타내는-1은 현재 지원 합니다.  
  
##  <a name="setcontrolfocus"></a>CComControlBase::SetControlFocus  
 설정 하거나 컨트롤에서 키보드 포커스를 제거 합니다.  
  
```
BOOL SetControlFocus(BOOL bGrab);
```  
  
### <a name="parameters"></a>매개 변수  
 *bGrab*  
 경우 **TRUE**, 호출 컨트롤에 키보드 포커스를 설정 합니다. 경우 **FALSE**, 포커스를가지고 제공 호출 컨트롤에서 키보드 포커스를 제거 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 컨트롤에 포커스를 성공적으로 수신 하는 경우, 그러지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 창 있는 컨트롤을 Windows API 함수에 대 한 [SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms646312) 호출 됩니다. 창 없는 컨트롤에 대 한 [IOleInPlaceSiteWindowless::SetFocus](http://msdn.microsoft.com/library/windows/desktop/ms679745) 호출 됩니다. 이 호출을 통해 창 없는 컨트롤 키보드 포커스 및 창 메시지에 응답할 수 있습니다.  
  
##  <a name="setdirty"></a>CComControlBase::SetDirty  
 데이터 멤버를 설정 `m_bRequiresSave` 값에 `bDirty`합니다.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>매개 변수  
 `bDirty`  
 데이터 멤버의 값 [CComControlBase::m_bRequiresSave](#m_brequiressave)합니다.  
  
### <a name="remarks"></a>주의  
 **SetDirty(TRUE)** 컨트롤 마지막으로 저장 된 이후 변경 된 것을 플래그를 호출 해야 합니다. 값 `m_bRequiresSave` 사용 하 여 검색 [CComControlBase::GetDirty](#getdirty)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComControl 클래스](../../atl/reference/ccomcontrol-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

