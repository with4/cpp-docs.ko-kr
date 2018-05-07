---
title: COleControlSite 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleControlSite
- AFXOCC/COleControlSite
- AFXOCC/COleControlSite::COleControlSite
- AFXOCC/COleControlSite::BindDefaultProperty
- AFXOCC/COleControlSite::BindProperty
- AFXOCC/COleControlSite::CreateControl
- AFXOCC/COleControlSite::DestroyControl
- AFXOCC/COleControlSite::DoVerb
- AFXOCC/COleControlSite::EnableDSC
- AFXOCC/COleControlSite::EnableWindow
- AFXOCC/COleControlSite::FreezeEvents
- AFXOCC/COleControlSite::GetDefBtnCode
- AFXOCC/COleControlSite::GetDlgCtrlID
- AFXOCC/COleControlSite::GetEventIID
- AFXOCC/COleControlSite::GetExStyle
- AFXOCC/COleControlSite::GetProperty
- AFXOCC/COleControlSite::GetStyle
- AFXOCC/COleControlSite::GetWindowText
- AFXOCC/COleControlSite::InvokeHelper
- AFXOCC/COleControlSite::InvokeHelperV
- AFXOCC/COleControlSite::IsDefaultButton
- AFXOCC/COleControlSite::IsWindowEnabled
- AFXOCC/COleControlSite::ModifyStyle
- AFXOCC/COleControlSite::ModifyStyleEx
- AFXOCC/COleControlSite::MoveWindow
- AFXOCC/COleControlSite::QuickActivate
- AFXOCC/COleControlSite::SafeSetProperty
- AFXOCC/COleControlSite::SetDefaultButton
- AFXOCC/COleControlSite::SetDlgCtrlID
- AFXOCC/COleControlSite::SetFocus
- AFXOCC/COleControlSite::SetProperty
- AFXOCC/COleControlSite::SetPropertyV
- AFXOCC/COleControlSite::SetWindowPos
- AFXOCC/COleControlSite::SetWindowText
- AFXOCC/COleControlSite::ShowWindow
- AFXOCC/COleControlSite::GetControlInfo
- AFXOCC/COleControlSite::m_bIsWindowless
- AFXOCC/COleControlSite::m_ctlInfo
- AFXOCC/COleControlSite::m_dwEventSink
- AFXOCC/COleControlSite::m_dwMiscStatus
- AFXOCC/COleControlSite::m_dwPropNotifySink
- AFXOCC/COleControlSite::m_dwStyle
- AFXOCC/COleControlSite::m_hWnd
- AFXOCC/COleControlSite::m_iidEvents
- AFXOCC/COleControlSite::m_nID
- AFXOCC/COleControlSite::m_pActiveObject
- AFXOCC/COleControlSite::m_pCtrlCont
- AFXOCC/COleControlSite::m_pInPlaceObject
- AFXOCC/COleControlSite::m_pObject
- AFXOCC/COleControlSite::m_pWindowlessObject
- AFXOCC/COleControlSite::m_pWndCtrl
- AFXOCC/COleControlSite::m_rect
dev_langs:
- C++
helpviewer_keywords:
- COleControlSite [MFC], COleControlSite
- COleControlSite [MFC], BindDefaultProperty
- COleControlSite [MFC], BindProperty
- COleControlSite [MFC], CreateControl
- COleControlSite [MFC], DestroyControl
- COleControlSite [MFC], DoVerb
- COleControlSite [MFC], EnableDSC
- COleControlSite [MFC], EnableWindow
- COleControlSite [MFC], FreezeEvents
- COleControlSite [MFC], GetDefBtnCode
- COleControlSite [MFC], GetDlgCtrlID
- COleControlSite [MFC], GetEventIID
- COleControlSite [MFC], GetExStyle
- COleControlSite [MFC], GetProperty
- COleControlSite [MFC], GetStyle
- COleControlSite [MFC], GetWindowText
- COleControlSite [MFC], InvokeHelper
- COleControlSite [MFC], InvokeHelperV
- COleControlSite [MFC], IsDefaultButton
- COleControlSite [MFC], IsWindowEnabled
- COleControlSite [MFC], ModifyStyle
- COleControlSite [MFC], ModifyStyleEx
- COleControlSite [MFC], MoveWindow
- COleControlSite [MFC], QuickActivate
- COleControlSite [MFC], SafeSetProperty
- COleControlSite [MFC], SetDefaultButton
- COleControlSite [MFC], SetDlgCtrlID
- COleControlSite [MFC], SetFocus
- COleControlSite [MFC], SetProperty
- COleControlSite [MFC], SetPropertyV
- COleControlSite [MFC], SetWindowPos
- COleControlSite [MFC], SetWindowText
- COleControlSite [MFC], ShowWindow
- COleControlSite [MFC], GetControlInfo
- COleControlSite [MFC], m_bIsWindowless
- COleControlSite [MFC], m_ctlInfo
- COleControlSite [MFC], m_dwEventSink
- COleControlSite [MFC], m_dwMiscStatus
- COleControlSite [MFC], m_dwPropNotifySink
- COleControlSite [MFC], m_dwStyle
- COleControlSite [MFC], m_hWnd
- COleControlSite [MFC], m_iidEvents
- COleControlSite [MFC], m_nID
- COleControlSite [MFC], m_pActiveObject
- COleControlSite [MFC], m_pCtrlCont
- COleControlSite [MFC], m_pInPlaceObject
- COleControlSite [MFC], m_pObject
- COleControlSite [MFC], m_pWindowlessObject
- COleControlSite [MFC], m_pWndCtrl
- COleControlSite [MFC], m_rect
ms.assetid: 43970644-5eab-434a-8ba6-56d144ff1e3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4dcb17c2650bf8b56702241a0ab4e77a3e2fc48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="colecontrolsite-class"></a>COleControlSite 클래스
사용자 지정 클라이언트 측 컨트롤 인터페이스를 지원합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class COleControlSite : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[COleControlSite::COleControlSite](#colecontrolsite)|`COleControlSite` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleControlSite::BindDefaultProperty](#binddefaultproperty)|호스팅된 컨트롤의 기본 속성을 데이터 소스에 바인딩합니다.|  
|[COleControlSite::BindProperty](#bindproperty)|호스팅된 컨트롤의 속성을 데이터 소스에 바인딩합니다.|  
|[COleControlSite::CreateControl](#createcontrol)|호스트 된 ActiveX 컨트롤을 만듭니다.|  
|[COleControlSite::DestroyControl](#destroycontrol)|호스팅된 컨트롤을 제거합니다.|  
|[COleControlSite::DoVerb](#doverb)|호스팅된 컨트롤의 특정 동사를 실행합니다.|  
|[COleControlSite::EnableDSC](#enabledsc)|컨트롤 사이트에 대 한 원본을 지정 하는 데이터를 사용 하도록 설정 합니다.|  
|[COleControlSite::EnableWindow](#enablewindow)|컨트롤 사이트를 사용 하도록 설정 합니다.|  
|[COleControlSite::FreezeEvents](#freezeevents)|컨트롤 사이트에서 이벤트를 수락 하 고 하는 경우를 지정 합니다.|  
|[COleControlSite::GetDefBtnCode](#getdefbtncode)|호스팅된 컨트롤에 대 한 기본 단추 코드를 검색합니다.|  
|[COleControlSite::GetDlgCtrlID](#getdlgctrlid)|컨트롤의 식별자를 검색합니다.|  
|[COleControlSite::GetEventIID](#geteventiid)|호스팅된 컨트롤에 대 한 이벤트 인터페이스의 ID를 검색합니다.|  
|[COleControlSite::GetExStyle](#getexstyle)|컨트롤 사이트에서의 확장된 스타일을 검색합니다.|  
|[COleControlSite::GetProperty](#getproperty)|호스팅된 컨트롤의 특정 속성을 검색합니다.|  
|[COleControlSite::GetStyle](#getstyle)|컨트롤 사이트에서의 스타일을 검색합니다.|  
|[COleControlSite::GetWindowText](#getwindowtext)|호스팅된 컨트롤의 텍스트를 검색합니다.|  
|[COleControlSite::InvokeHelper](#invokehelper)|호스팅된 컨트롤의 특정 메서드를 호출 합니다.|  
|[COleControlSite::InvokeHelperV](#invokehelperv)|가변 인수 목록과 함께 호스팅된 컨트롤의 특정 메서드를 호출 합니다.|  
|[COleControlSite::IsDefaultButton](#isdefaultbutton)|컨트롤 창에서 기본 단추 인지 여부를 확인 합니다.|  
|[COleControlSite::IsWindowEnabled](#iswindowenabled)|컨트롤 사이트에서의 표시 상태를 확인합니다.|  
|[COleControlSite::ModifyStyle](#modifystyle)|현재 확장 컨트롤 사이트에서의 스타일을 수정 합니다.|  
|[COleControlSite::ModifyStyleEx](#modifystyleex)|컨트롤 사이트에서의 현재 스타일을 수정합니다.|  
|[COleControlSite::MoveWindow](#movewindow)|컨트롤 사이트에서의 위치를 변경 합니다.|  
|[COleControlSite::QuickActivate](#quickactivate)|빠른 호스팅된 컨트롤을 활성화합니다.|  
|[COleControlSite::SafeSetProperty](#safesetproperty)|기회 예외를 throw 하지 않고 컨트롤의 메서드나 속성을 설정 합니다.|  
|[COleControlSite::SetDefaultButton](#setdefaultbutton)|창에서 기본 단추로 설정합니다.|  
|[COleControlSite::SetDlgCtrlID](#setdlgctrlid)|컨트롤의 식별자를 검색합니다.|  
|[COleControlSite::SetFocus](#setfocus)|컨트롤 사이트에 포커스를 설정합니다.|  
|[COleControlSite::SetProperty](#setproperty)|호스팅된 컨트롤의 특정 속성을 설정합니다.|  
|[COleControlSite::SetPropertyV](#setpropertyv)|가변 인수 목록과 함께 호스팅된 컨트롤의 특정 속성을 설정합니다.|  
|[COleControlSite::SetWindowPos](#setwindowpos)|컨트롤 사이트에서의 위치를 설정 합니다.|  
|[COleControlSite::SetWindowText](#setwindowtext)|호스팅된 컨트롤의 텍스트를 설정 합니다.|  
|[COleControlSite::ShowWindow](#showwindow)|표시 하거나 컨트롤 사이트를 숨깁니다.|  
  
### <a name="protected-methods"></a>보호된 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[COleControlSite::GetControlInfo](#getcontrolinfo)|키보드 정보 및 니모닉 호스팅된 컨트롤에 대 한 검색합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[COleControlSite::m_bIsWindowless](#m_biswindowless)|호스팅된 컨트롤 창 없는 컨트롤 인지 여부를 확인 합니다.|  
|[COleControlSite::m_ctlInfo](#m_ctlinfo)|키보드 컨트롤에 대 한 처리에 정보를 포함 합니다.|  
|[COleControlSite::m_dwEventSink](#m_dweventsink)|컨트롤의 연결 지점의 쿠키입니다.|  
|[COleControlSite::m_dwMiscStatus](#m_dwmiscstatus)|호스팅된 컨트롤에 대 한 기타 상태입니다.|  
|[COleControlSite::m_dwPropNotifySink](#m_dwpropnotifysink)|`IPropertyNotifySink` 컨트롤의 쿠키입니다.|  
|[COleControlSite::m_dwStyle](#m_dwstyle)|호스팅된 컨트롤의 스타일입니다.|  
|[COleControlSite::m_hWnd](#m_hwnd)|컨트롤 사이트에서의 핸들입니다.|  
|[COleControlSite::m_iidEvents](#m_iidevents)|호스팅된 컨트롤에 대 한 이벤트 인터페이스의 ID입니다.|  
|[COleControlSite::m_nID](#m_nid)|호스팅된 컨트롤의 ID입니다.|  
|[COleControlSite::m_pActiveObject](#m_pactiveobject)|에 대 한 포인터는 `IOleInPlaceActiveObject` 호스팅된 컨트롤의 개체입니다.|  
|[COleControlSite::m_pCtrlCont](#m_pctrlcont)|호스팅된 컨트롤의 컨테이너입니다.|  
|[COleControlSite::m_pInPlaceObject](#m_pinplaceobject)|에 대 한 포인터는 `IOleInPlaceObject` 호스팅된 컨트롤의 개체입니다.|  
|[COleControlSite::m_pObject](#m_pobject)|에 대 한 포인터는 `IOleObjectInterface` 컨트롤의 인터페이스입니다.|  
|[COleControlSite::m_pWindowlessObject](#m_pwindowlessobject)|에 대 한 포인터는 `IOleInPlaceObjectWindowless` 컨트롤의 인터페이스입니다.|  
|[COleControlSite::m_pWndCtrl](#m_pwndctrl)|호스팅된 컨트롤에 대 한 window 개체에 대 한 포인터입니다.|  
|[COleControlSite::m_rect](#m_rect)|컨트롤 사이트에서의 차원입니다.|  
  
## <a name="remarks"></a>설명  
 이 지원은 기본적 기준인 ActiveX 컨트롤이 포함된 된 위치 및 해당 표시 사이트, 해당 모니커, 해당 사용자 인터페이스, 해당 앰비언트 속성 및 해당 컨테이너에서 제공 하는 다른 리소스의 범위에 대 한 정보를 가져옵니다. `COleControlSite` 완벽 하 게 구현는 [IOleControlSite](http://msdn.microsoft.com/library/windows/desktop/ms688502), [IOleInPlaceSite](http://msdn.microsoft.com/library/windows/desktop/ms686586), [IOleClientSite](http://msdn.microsoft.com/library/windows/desktop/ms693706), [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638),  **IBoundObjectSite**, **INotifyDBEvents**, [IRowSetNotify](../../data/oledb/irowsetnotifyimpl-class.md) 인터페이스입니다. 또한 IDispatch 인터페이스 (앰비언트 속성 및 이벤트 싱크에 대 한 지원 제공)도 구현 됩니다.  
  
 ActiveX 컨트롤 사이트 사용 하 여 프로그램을 만들려면 `COleControlSite`에서 클래스를 파생 `COleControlSite`합니다. 사용자 `CWnd`-컨테이너 (예를 들어, 대화 상자)에 대 한 파생된 클래스에서 재정의 된 **CWnd::CreateControlSite** 함수입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleControlSite`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxocc.h  
  
##  <a name="binddefaultproperty"></a>  COleControlSite::BindDefaultProperty  
 데이터 소스 컨트롤의 데이터 원본, 사용자 이름, 암호 및 SQL 속성으로 정의 된 기본 커서를 호출 하는 개체의 바인딩된 기본 단순 속성을, 형식 라이브러리에 표시 된 대로 바인딩합니다.  
  
```  
virtual void BindDefaultProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    LPCTSTR szFieldName,  
    CWnd* pDSCWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 지정 된 **DISPID** 데이터 소스 제어에 바인딩되어 있는 데이터 바인딩된 컨트롤에서 속성의 합니다.  
  
 `vtProp`  
 바인딩할 속성의 유형을 지정-예를 들어 `VT_BSTR`, **VT_VARIANT**등입니다.  
  
 `szFieldName`  
 속성이 연결 된 데이터 소스 컨트롤에서 제공 하는 커서의는 열의 이름을 지정 합니다.  
  
 `pDSCWnd`  
 에 대 한 포인터는 `CWnd`-속성이 연결 된 데이터 소스 컨트롤을 호스트 하는 파생 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 `CWnd` 이 함수를 호출 하는 개체는 데이터 바인딩된 컨트롤 이어야 합니다.  
  
##  <a name="bindproperty"></a>  COleControlSite::BindProperty  
 데이터 소스 컨트롤의 데이터 원본, 사용자 이름, 암호 및 SQL 속성으로 정의 된 기본 커서를 호출 하는 개체의 단순 바인딩된 속성에 형식 라이브러리에 표시 된 대로 바인딩합니다.  
  
```  
virtual void BindProperty(
    DISPID dwDispId,  
    CWnd* pWndDSC);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwDispId*  
 지정 된 **DISPID** 데이터 소스 제어에 바인딩되어 있는 데이터 바인딩된 컨트롤에서 속성의 합니다.  
  
 `pWndDSC`  
 에 대 한 포인터는 `CWnd`-속성이 연결 된 데이터 소스 컨트롤을 호스트 하는 파생 된 개체입니다.  
  
### <a name="remarks"></a>설명  
 `CWnd` 이 함수를 호출 하는 개체는 데이터 바인딩된 컨트롤 이어야 합니다.  
  
##  <a name="colecontrolsite"></a>  COleControlSite::COleControlSite  
 새 `COleControlSite` 개체를 생성합니다.  
  
```  
explicit COleControlSite(COleControlContainer* pCtrlCont);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCtrlCont`  
 컨트롤의 컨테이너 (AtiveX 컨트롤을 호스트 하는 창을 나타냅니다)에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 함수 호출 됩니다는 [COccManager::CreateContainer](../../mfc/reference/coccmanager-class.md#createcontainer) 함수입니다. 컨테이너의 만들기를 사용자 지정에 대 한 자세한 내용은 참조 하십시오. [COccManager::CreateSite](../../mfc/reference/coccmanager-class.md#createsite)합니다.  
  
##  <a name="createcontrol"></a>  COleControlSite::CreateControl  
 호스팅되는 ActiveX 컨트롤을 만듭니다는 `COleControlSite` 개체입니다.  
  
```  
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);

 
virtual HRESULT CreateControl(
    CWnd* pWndCtrl,  
    REFCLSID clsid,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const POINT* ppt,  
    const SIZE* psize,  
    UINT nID,  
    CFile* pPersist = NULL,  
    BOOL bStorage = FALSE,  
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWndCtrl`  
 컨트롤을 나타내는 window 개체에 대 한 포인터입니다.  
  
 `clsid`  
 컨트롤의 고유 클래스 ID입니다.  
  
 `lpszWindowName`  
 컨트롤에 표시할 텍스트에 대 한 포인터입니다. (있는 경우) winodw의 캡션 또는 텍스트 속성의 값을 설정 합니다.  
  
 `dwStyle`  
 창 스타일입니다. 사용 가능한 스타일 아래에 나열 됩니다는 **주의** 섹션.  
  
 `rect`  
 컨트롤의 크기와 위치를 지정합니다. 있습니다는 `CRect` 개체 또는 `RECT` 구조입니다.  
  
 `nID`  
 컨트롤의 자식 창 ID를 지정 합니다.  
  
 `pPersist`  
 에 대 한 포인터는 `CFile` 컨트롤에 대 한 영구 상태를 포함 합니다. 기본값은 **NULL**, 컨트롤 모든 영구 저장소에서 해당 상태를 복원 하지 않고 자체적 초기화를 나타내는입니다. 그렇지 않은 경우 **NULL**에 대 한 포인터 여야 합니다는 `CFile`-파생 된 스트림 또는 저장소의 형태로 컨트롤의 영구 데이터를 포함 하는 개체입니다. 이 데이터는 클라이언트의 이전 정품에서 저장 수 없습니다. `CFile` 다른 데이터를 포함할 수 있지만 읽기 / 쓰기 포인터에 대 한 호출의 시간에 영구 데이터의 첫 번째 바이트도 설정 되어 있어야 `CreateControl`합니다.  
  
 `bStorage`  
 나타냅니다 여부의 데이터 `pPersist` 으로 해석할지 `IStorage` 또는 `IStream` 데이터입니다. 경우에 데이터 `pPersist` 는 저장소 `bStorage` 해야 **TRUE**합니다. 경우에 데이터 `pPersist` 는 stream `bStorage` 해야 **FALSE**합니다. 기본값은 **FALSE**합니다.  
  
 `bstrLicKey`  
 선택적 라이선스 키 데이터입니다. 이 데이터는 런타임 라이선스 키를 필요로 하는 컨트롤을 만드는 경우에 필요 합니다. 컨트롤 라이선스를 지 원하는 경우 성공 하려면 컨트롤 생성에 대 한 라이선스 키를 제공 해야 합니다. 기본값은 **NULL**합니다.  
  
 `ppt`  
 에 대 한 포인터는 **지점** 컨트롤의 왼쪽 위 모퉁이 포함 하는 구조입니다. 컨트롤의 크기 값에 의해 결정 됩니다 *psize*합니다. `ppt` 및 *psize* 값의 크기를 지정 하는 선택적 메서드가 되어 opf 컨트롤 위치를 지정 합니다.  
  
 *psize*  
 에 대 한 포인터는 **크기** 컨트롤의 크기를 포함 하는 구조입니다. 왼쪽 위 모퉁이의 값에 의해 결정 됩니다 `ppt`합니다. `ppt` 및 *psize* 값의 크기를 지정 하는 선택적 메서드가 되어 opf 컨트롤 위치를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 Windows의 하위 집합만 `dwStyle` 에서 지원 되는 플래그 `CreateControl`:  
  
- **WS_VISIBLE** 처음에 표시 되는 창을 만듭니다. 컨트롤이 일반 창과 마찬가지로 즉시 표시 될 수 있는 경우에 필요 합니다.  
  
- **WS_DISABLED** 처음부터 사용할 창을 만듭니다. 사용할 수 없는 창 사용자 로부터 입력을 받을 수 없습니다. 컨트롤에는 Enabled 속성에 설정할 수 있습니다.  
  
- `WS_BORDER` 씬 줄 테두리가 있는 창을 만듭니다. 컨트롤 BorderStyle 속성에 설정할 수 있습니다.  
  
- **WS_GROUP** 컨트롤 그룹의 첫 번째 컨트롤을 지정 합니다. 사용자 방향 키를 사용 하 여 키보드 포커스를 한 컨트롤의 그룹에서에서 다음 변경할 수 있습니다. 정의 된 모든 컨트롤은 **WS_GROUP** 후 동일한 그룹에 속하는 첫 번째 컨트롤에 스타일입니다. 다음 컨트롤은 **WS_GROUP** 스타일 그룹을 종료 하 고 다음 그룹을 시작 합니다.  
  
- **WS_TABSTOP** TAB 키를 누를 때 키보드 포커스를 받을 수 있는 컨트롤을 지정 합니다. 다음 컨트롤로 키보드 포커스를 변경 TAB 키를 누를 **WS_TABSTOP** 스타일입니다.  
  
 두 번째 오버 로드를 사용 하 여 기본 크기의 컨트롤을 만들 수 있습니다.  
  
##  <a name="destroycontrol"></a>  COleControlSite::DestroyControl  
 소멸 된 `COleControlSite` 개체입니다.  
  
```  
virtual BOOL DestroyControl();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 완료 되 면 개체가 메모리에서 해제 되 고 있는 개체에 대 한 모든 포인터는 더 이상 올바르지.  
  
##  <a name="doverb"></a>  COleControlSite::DoVerb  
 지정된 된 동사를 실행합니다.  
  
```  
virtual HRESULT DoVerb(
    LONG nVerb,  
    LPMSG lpMsg = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `nVerb`  
 실행 하는 동사를 지정 합니다. 다음 중 하나를 포함할 수 있습니다.  
  
|값|의미|기호|  
|-----------|-------------|------------|  
|0|기본 동사|`OLEIVERB_PRIMARY`|  
|-1|보조 동사|(None)|  
|1|편집할 개체를 표시합니다.|`OLEIVERB_SHOW`|  
|-2|별도 창에서 항목을 편집 합니다.|`OLEIVERB_OPEN`|  
|-3|개체를 숨깁니다.|`OLEIVERB_HIDE`|  
|-4|위치에서 컨트롤을 활성화 합니다.|`OLEIVERB_UIACTIVATE`|  
|-5|컨트롤 내부를 없이 추가 사용자 인터페이스 요소를 활성화합니다.|**OLEIVERB_INPLACEACTIVATE**|  
|-7|컨트롤의 속성을 표시 합니다.|**OLEIVERB_PROPERTIES**|  
  
 `lpMsg`  
 항목을 활성화할 수를 발생 시킨 메시지에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 컨트롤을 통해 간접적으로 호출 `IOleObject` 지정된 된 동사를 실행 하는 인터페이스입니다. 이 함수 호출의 결과로 예외가 발생 하는 경우는 `HRESULT` 오류 코드가 반환 됩니다.  
  
 자세한 내용은 참조 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508) Windows sdk에서입니다.  
  
##  <a name="enabledsc"></a>  COleControlSite::EnableDSC  
 컨트롤 사이트에 대 한 원본을 지정 하는 데이터를 사용 하도록 설정 합니다.  
  
```  
virtual void EnableDSC();
```  
  
### <a name="remarks"></a>설명  
 사용 하도록 설정 하 고 컨트롤 사이트에 대 한 원본을 지정 하는 데이터를 초기화 하기 위해 프레임 워크에서 호출 됩니다. 동작 사용자 지정 하려면이 함수를 재정의 합니다.  
  
##  <a name="enablewindow"></a>  COleControlSite::EnableWindow  
 마우스 및 키보드 컨트롤 사이트에 대 한 입력을 사용 하지 않도록 설정 하거나 합니다.  
  
```  
virtual BOOL EnableWindow(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnable`  
 창에 표시할 것인지 여부를 지정 합니다: **TRUE** 그렇지 않은 경우 사용 가능 하도록 창 입력이 리디렉션되면 **FALSE**합니다.  
  
### <a name="return-value"></a>반환 값  
 창을 이전에 해제 하면 0이 아니고 그렇지 않으면 0입니다.  
  
##  <a name="freezeevents"></a>  COleControlSite::FreezeEvents  
 컨트롤 사이트에서 무시 컨트롤에서 발생 하는 이벤트 처리 여부를 지정 합니다.  
  
```  
void FreezeEvents(BOOL bFreeze);
```  
  
### <a name="parameters"></a>매개 변수  
 `bFreeze`  
 컨트롤 사이트에서 이벤트 수락을 중지하려는지를 지정합니다. 컨트롤이 이벤트를 수락 하지 않으면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 경우 `bFreeze` 은 **TRUE**, 컨트롤 사이트에서 요청 중지 fring 이벤트를 제어 합니다. 경우 `bFreeze` 은 **FALSE**, 컨트롤 사이트에서 발생 하는 이벤트를 계속 하려면 컨트롤을 요청 합니다.  
  
> [!NOTE]
>  컨트롤을 컨트롤 사이트에서 요청할 경우에 이벤트를 발생 시키고 중지 필요 하지 않습니다. 실행을 계속할 수 있지만 컨트롤 사이트에서 후속 이벤트를 모두 무시 됩니다.  
  
##  <a name="getcontrolinfo"></a>  COleControlSite::GetControlInfo  
 컨트롤의 키보드 니모닉와 키보드 동작에 대 한 정보를 검색합니다.  
  
```  
void GetControlInfo();
```  
  
### <a name="remarks"></a>설명  
 정보에 저장 됩니다 [COleControlSite::m_ctlInfo](#m_ctlinfo)합니다.  
  
##  <a name="getdefbtncode"></a>  COleControlSite::GetDefBtnCode  
 기본 누름 단추 컨트롤 인지 여부를 확인 합니다.  
  
```  
DWORD GetDefBtnCode();
```  
  
### <a name="return-value"></a>반환 값  
 다음 값 중 하나입니다.  
  
- **DLGC_DEFPUSHBUTTON** 제어 대화 상자에서 기본 단추입니다.  
  
- **DLGC_UNDEFPUSHBUTTON** 컨트롤이 대화 상자에서 기본 단추로 않습니다.  
  
- **0** 단추 컨트롤이 아닙니다.  
  
##  <a name="getdlgctrlid"></a>  COleControlSite::GetDlgCtrlID  
 컨트롤의 식별자를 검색합니다.  
  
```  
virtual int GetDlgCtrlID() const;  
```  
  
### <a name="return-value"></a>반환 값  
 대화 상자 항목 컨트롤의 식별자입니다.  
  
##  <a name="geteventiid"></a>  COleControlSite::GetEventIID  
 컨트롤의 기본 이벤트 인터페이스에 대 한 포인터를 검색합니다.  
  
```  
BOOL GetEventIID(IID* piid);
```  
  
### <a name="parameters"></a>매개 변수  
 `piid`  
 인터페이스 ID에 대 한 포인터  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다. 성공 하면 `piid` 컨트롤의 기본 이벤트 인터페이스에 대 한 인터페이스 ID를 포함 합니다.  
  
##  <a name="getexstyle"></a>  COleControlSite::GetExStyle  
 확장된 창 스타일을 검색합니다.  
  
```  
virtual DWORD GetExStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 제어 창의 스타일을 연장 합니다.  
  
### <a name="remarks"></a>설명  
 일반 스타일을 검색 하려면 [COleControlSite::GetStyle](#getstyle)합니다.  
  
##  <a name="getproperty"></a>  COleControlSite::GetProperty  
 로 지정 된 컨트롤 속성을 가져옵니다 `dwDispID`합니다.  
  
```  
virtual void GetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    void* pvProp) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 에 컨트롤의 기본 속성의 디스패치 ID를 식별 `IDispatch` 인터페이스를 검색할 수 있습니다.  
  
 `vtProp`  
 검색할 속성의 유형을 지정 합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 `pvProp`  
 속성 값을 받을 변수의 주소입니다. 지정한 형식과 일치 해야 `vtProp`합니다.  
  
### <a name="remarks"></a>설명  
 통해 반환 되는 값은 `pvProp`합니다.  
  
##  <a name="getstyle"></a>  COleControlSite::GetStyle  
 컨트롤 사이트에서의 스타일을 검색합니다.  
  
```  
virtual DWORD GetStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 창 스타일입니다.  
  
### <a name="remarks"></a>설명  
 가능한 값 목록은 참조 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles)합니다. 컨트롤 사이트에서의 확장된 스타일을 검색 하려면 [COleControlSite::GetExStyle](#getexstyle)합니다.  
  
##  <a name="getwindowtext"></a>  COleControlSite::GetWindowText  
 컨트롤의 현재 텍스트를 검색합니다.  
  
```  
virtual void GetWindowText(CString& str) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `str`  
 에 대 한 참조는 `CString` 컨트롤의 현재 텍스트를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>설명  
 컨트롤 캡션 스톡 속성을 지 원하는 경우이 값이 반환 됩니다. 캡션 스톡 속성이 지원 되지 않는 경우 Text 속성에 대 한 값이 반환 됩니다.  
  
##  <a name="invokehelper"></a>  COleControlSite::InvokeHelper  
 메서드 또는 속성으로 지정 된 호출 `dwDispID`, 의해 지정 된 컨텍스트의 `wFlags`합니다.  
  
```  
virtual void AFX_CDECL InvokeHelper(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo, ...);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 속성 또는 메서드를 컨트롤의에 대 한 디스패치 ID 식별 `IDispatch` 인터페이스를 호출 합니다.  
  
 `wFlags`  
 Idispatch:: Invoke 호출의 컨텍스트를 설명 하는 플래그입니다. 가능한 `wFlags` 값, 참조 `IDispatch::Invoke` Windows sdk에서입니다.  
  
 `vtRet`  
 반환 값 형식을 지정합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 `pvRet`  
 속성 값이나 반환 값을 받을 변수의 주소입니다. `vtRet`를 통해 지정된 형식과 일치해야 합니다.  
  
 `pbParamInfo`  
 `pbParamInfo`뒤에 매개 변수 형식을 지정하는 바이트의 null로 종료된 문자열에 대한 포인터입니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 *...*  
 `pbParamInfo`에 지정된 형식의 매개 변수에 대한 변수 목록입니다.  
  
### <a name="remarks"></a>설명  
 `pbParamInfo` 매개 변수는 메서드나 속성에 전달되는 매개 변수 형식을 지정합니다. 인수의 변수 목록은 구문 선언에서...으로 표시 됩니다.  
  
 이 함수는 매개 변수를 변환 **VARIANTARG** 값, 호출 후의 **idispatch:: Invoke** 컨트롤 대 메서드. 경우에 대 한 호출 **idispatch:: Invoke** 실패 하면이이 함수는 예외가 throw 됩니다. 상태 코드를 반환 하는 경우 **idispatch:: Invoke** 은 `DISP_E_EXCEPTION`,이 함수는 **COleDispatchException** 개체, 그렇지 않으면 throw 된 `COleException`합니다.  
  
##  <a name="invokehelperv"></a>  COleControlSite::InvokeHelperV  
 메서드 또는 속성으로 지정 된 호출 `dwDispID`, 의해 지정 된 컨텍스트의 `wFlags`합니다.  
  
```  
virtual void InvokeHelperV(
    DISPID dwDispID,  
    WORD wFlags,  
    VARTYPE vtRet,  
    void* pvRet,  
    const BYTE* pbParamInfo,  
    va_list argList);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 속성 또는 메서드를 컨트롤의에 대 한 디스패치 ID 식별 `IDispatch` 인터페이스를 호출 합니다.  
  
 `wFlags`  
 Idispatch:: Invoke 호출의 컨텍스트를 설명 하는 플래그입니다.  
  
 `vtRet`  
 반환 값 형식을 지정합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 `pvRet`  
 속성 값이나 반환 값을 받을 변수의 주소입니다. `vtRet`를 통해 지정된 형식과 일치해야 합니다.  
  
 `pbParamInfo`  
 `pbParamInfo`뒤에 매개 변수 형식을 지정하는 바이트의 null로 종료된 문자열에 대한 포인터입니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 `argList`  
 가변 인수 목록에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 `pbParamInfo` 매개 변수는 메서드나 속성에 전달되는 매개 변수 형식을 지정합니다. 사용 하 여 메서드 또는 호출 되는 속성에 대 한 추가 매개 변수를 전달할 수 있습니다는 *va_list* 매개 변수입니다.  
  
 이 함수를 호출 하 일반적으로 `COleControlSite::InvokeHelper`합니다.  
  
##  <a name="isdefaultbutton"></a>  COleControlSite::IsDefaultButton  
 컨트롤이 기본 단추 인지 여부를 확인 합니다.  
  
```  
BOOL IsDefaultButton();
```  
  
### <a name="return-value"></a>반환 값  
 컨트롤이 있는 경우 0이 아닌 창에서 기본 단추로 그렇지 않으면 0입니다.  
  
##  <a name="iswindowenabled"></a>  COleControlSite::IsWindowEnabled  
 컨트롤 사이트에서 사용 되는지 여부를 결정 합니다.  
  
```  
virtual BOOL IsWindowEnabled() const;  
```  
  
### <a name="return-value"></a>반환 값  
 0이 아니고 그렇지 않으면 0 컨트롤을 사용 합니다.  
  
### <a name="remarks"></a>설명  
 값은 컨트롤의 Enabled 스톡 속성에서 검색 됩니다.  
  
##  <a name="m_biswindowless"></a>  COleControlSite::m_bIsWindowless  
 개체 창 없는 컨트롤 인지 여부를 확인 합니다.  
  
```  
BOOL m_bIsWindowless;  
```  
  
### <a name="remarks"></a>설명  
 0이 아닌 경우 컨트롤에 창이, 그렇지 않으면 0입니다.  
  
##  <a name="m_ctlinfo"></a>  COleControlSite::m_ctlInfo  
 컨트롤에서 키보드 입력은 처리 하는 방법에 대 한 정보입니다.  
  
```  
CONTROLINFO m_ctlInfo;  
```  
  
### <a name="remarks"></a>설명  
 이 정보에 저장 되는 [한 채울 CONTROLINFO](http://msdn.microsoft.com/library/windows/desktop/ms680734) 구조입니다.  
  
##  <a name="m_dweventsink"></a>  COleControlSite::m_dwEventSink  
 컨트롤의 이벤트 싱크에 연결 포인트의 쿠키를 포함합니다.  
  
```  
DWORD m_dwEventSink;  
```  
  
##  <a name="m_dwmiscstatus"></a>  COleControlSite::m_dwMiscStatus  
 컨트롤에 대 한 기타 정보를 포함합니다.  
  
```  
DWORD m_dwMiscStatus;  
```  
  
### <a name="remarks"></a>설명  
 자세한 내용은 참조 [OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497)Windows sdk에서입니다.  
  
##  <a name="m_dwpropnotifysink"></a>  COleControlSite::m_dwPropNotifySink  
 포함 된 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 쿠키입니다.  
  
```  
DWORD m_dwPropNotifySink;  
```  
  
##  <a name="m_dwstyle"></a>  COleControlSite::m_dwStyle  
 컨트롤의 창 스타일을 포함합니다.  
  
```  
DWORD m_dwStyle;  
```  
  
##  <a name="m_hwnd"></a>  COleControlSite::m_hWnd  
 포함 된 `HWND` 컨트롤의 또는 **NULL** 컨트롤은 창 없는 경우.  
  
```  
HWND m_hWnd;  
```  
  
##  <a name="m_iidevents"></a>  COleControlSite::m_iidEvents  
 컨트롤의 기본 이벤트 싱크 인터페이스의 인터페이스 ID를 포함합니다.  
  
```  
IID m_iidEvents;  
```  
  
##  <a name="m_nid"></a>  COleControlSite::m_nID  
 컨트롤의 대화 상자 항목 ID를 포함  
  
```  
UINT m_nID;  
```  
  
##  <a name="m_pactiveobject"></a>  COleControlSite::m_pActiveObject  
 포함 된 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) 컨트롤의 인터페이스입니다.  
  
```  
LPOLEINPLACEACTIVEOBJECT m_pActiveObject;  
```  
  
##  <a name="m_pctrlcont"></a>  COleControlSite::m_pCtrlCont  
 컨트롤의 컨테이너 (폼을 나타냄)를 포함 합니다.  
  
```  
COleControlContainer* m_pCtrlCont;  
```  
  
##  <a name="m_pinplaceobject"></a>  COleControlSite::m_pInPlaceObject  
 포함 된 `IOleInPlaceObject` [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) 컨트롤의 인터페이스입니다.  
  
```  
LPOLEINPLACEOBJECT m_pInPlaceObject;  
```  
  
##  <a name="m_pobject"></a>  COleControlSite::m_pObject  
 포함 된 **IOleObjectInterface** 컨트롤의 인터페이스입니다.  
  
```  
LPOLEOBJECT m_pObject;  
```  
  
##  <a name="m_pwindowlessobject"></a>  COleControlSite::m_pWindowlessObject  
 포함 된 `IOleInPlaceObjectWindowless` [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) 컨트롤의 인터페이스입니다.  
  
```  
IOleInPlaceObjectWindowless* m_pWindowlessObject;  
```  
  
##  <a name="m_pwndctrl"></a>  COleControlSite::m_pWndCtrl  
 에 대 한 포인터는 `CWnd` 컨트롤 자체를 나타내는 개체입니다.  
  
```  
CWnd* m_pWndCtrl;  
```  
  
##  <a name="m_rect"></a>  COleControlSite::m_rect  
 컨테이너의 창 기준으로 컨트롤의 범위를 포함합니다.  
  
```  
CRect m_rect;  
```  
  
##  <a name="modifystyle"></a>  COleControlSite::ModifyStyle  
 컨트롤의 스타일을 수정합니다.  
  
```  
virtual BOOL ModifyStyle(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwRemove`  
 현재 창 스타일에서 제거할 스타일입니다.  
  
 `dwAdd`  
 현재 창 스타일에서 추가할 스타일입니다.  
  
 `nFlags`  
 플래그의 위치를 지정 하는 창입니다. 목록이 가능한 값에 대 한 참조는 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK에는 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 스타일이 변경 되 면 0이 고, 그렇지 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>설명  
 컨트롤의 재고 Enabled 속성에 대 한 설정과 일치 하도록 수정 됩니다 **WS_DISABLED**합니다. 컨트롤의 스톡 테두리 스타일 속성에 대 한 요청 된 설정과 일치 하도록 수정 됩니다 `WS_BORDER`합니다. 다른 모든 스타일 있을 경우 컨트롤의 창 핸들에 직접 적용 됩니다.  
  
 컨트롤의 창 스타일을 수정합니다. 비트 OR를 사용 하 여 추가 또는 제거 하기 위해 스타일을 결합할 수 있습니다 ( &#124; ) 연산자. 참조는 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 사용 가능한 창 스타일에 대 한 정보에 대 한 Windows SDK에는 함수입니다.  
  
 경우 `nFlags` 이 값은 0 `ModifyStyle` Win32 함수를 호출 `SetWindowPos`를 결합 하 여 창을 다시 그리고 `nFlags` 다음 4 개의 플래그와 함께:  
  
- `SWP_NOSIZE` 현재 크기를 유지합니다.  
  
- `SWP_NOMOVE` 현재 위치를 유지합니다.  
  
- `SWP_NOZORDER` 현재 Z 순서를 유지합니다.  
  
- `SWP_NOACTIVATE` 창을 활성화 하지 않습니다.  
  
 스타일의 연장 창을 수정 하려면, 호출 [ModifyStyleEx](#modifystyleex)합니다.  
  
##  <a name="modifystyleex"></a>  COleControlSite::ModifyStyleEx  
 컨트롤의 확장된 스타일을 수정합니다.  
  
```  
virtual BOOL ModifyStyleEx(
    DWORD dwRemove,  
    DWORD dwAdd,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwRemove`  
 현재 창 스타일에서 제거할 확장된 스타일입니다.  
  
 `dwAdd`  
 확장 된 스타일에서 현재 창 스타일을 추가할 수입니다.  
  
 `nFlags`  
 플래그의 위치를 지정 하는 창입니다. 목록이 가능한 값에 대 한 참조는 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows SDK에는 함수입니다.  
  
### <a name="return-value"></a>반환 값  
 스타일이 변경 되 면 0이 고, 그렇지 0이 아닌 지정 합니다.  
  
### <a name="remarks"></a>설명  
 컨트롤의 스톡 모양 속성에 대 한 설정과 일치 하도록 수정 됩니다 **WS_EX_CLIENTEDGE**합니다. 다른 모든 확장된 창 스타일 있을 경우 컨트롤의 창 핸들에 직접 적용 됩니다.  
  
 확장 컨트롤 사이트 개체의 스타일 창을 수정 합니다. 비트 OR를 사용 하 여 추가 또는 제거 하기 위해 스타일을 결합할 수 있습니다 ( &#124; ) 연산자. 참조는 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 사용 가능한 창 스타일에 대 한 정보에 대 한 Windows SDK에는 함수입니다.  
  
 경우 `nFlags` 이 값은 0 `ModifyStyleEx` Win32 함수를 호출 `SetWindowPos`를 결합 하 여 창을 다시 그리고 `nFlags` 다음 4 개의 플래그와 함께:  
  
- `SWP_NOSIZE` 현재 크기를 유지합니다.  
  
- `SWP_NOMOVE` 현재 위치를 유지합니다.  
  
- `SWP_NOZORDER` 현재 Z 순서를 유지합니다.  
  
- `SWP_NOACTIVATE` 창을 활성화 하지 않습니다.  
  
 스타일의 연장 창을 수정 하려면, 호출 [ModifyStyle](#modifystyle)합니다.  
  
##  <a name="movewindow"></a>  COleControlSite::MoveWindow  
 컨트롤의 위치를 변경합니다.  
  
```  
virtual void MoveWindow(
    int x,  
    int y,  
    int nWidth,  
    int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 창 왼쪽의 새 위치입니다.  
  
 *y*  
 창의 위쪽의 새 위치입니다.  
  
 `nWidth`  
 창의 새 너비  
  
 `nHeight`  
 창의 새 높이입니다.  
  
##  <a name="quickactivate"></a>  COleControlSite::QuickActivate  
 빠른 포함 된 컨트롤을 활성화합니다.  
  
```  
virtual BOOL QuickActivate();
```  
  
### <a name="return-value"></a>반환 값  
 0이 아니고 그렇지 않으면 0 컨트롤 사이트에서 활성화 된 경우.  
  
### <a name="remarks"></a>설명  
 사용자가 컨트롤의 생성 프로세스를 재정의 하는 경우에이 함수를 호출 해야 합니다.  
  
 `IPersist*::Load` 및 `IPersist*::InitNew` 빠른 활성화의 발생 후 메서드를 호출 해야 합니다. 컨트롤 신속 하 게 작동 하는 동안 컨테이너의 싱크에 대 한 연결을 설정 해야 합니다. 그러나 이러한 연결 될 때까지 라이브 하지 않습니다 `IPersist*::Load` 또는 `IPersist*::InitNew` 가 호출 되었습니다.  
  
##  <a name="safesetproperty"></a>  COleControlSite::SafeSetProperty  
 로 지정 된 컨트롤 속성을 설정 `dwDispID`합니다.  
  
```  
virtual BOOL AFX_CDECL SafeSetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 속성 또는 메서드를 컨트롤의에 대 한 디스패치 ID 식별 `IDispatch` 인터페이스를 설정 합니다.  
  
 `vtProp`  
 속성을 설정 해야 유형을 지정 합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 *...*  
 `vtProp`에서 지정한 유형의 단일 매개 변수  
  
### <a name="return-value"></a>반환 값  
 성공하는 경우 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  와 달리 `SetProperty` 및 `SetPropertyV`합니다 (예: 존재 하지 않는 속성을 설정 하는 동안)는 오류가 발생 하는 경우 예외가 throw 되지 않습니다.  
  
##  <a name="setdefaultbutton"></a>  COleControlSite::SetDefaultButton  
 컨트롤을 기본 단추로 설정합니다.  
  
```  
void SetDefaultButton(BOOL bDefault);
```  
  
### <a name="parameters"></a>매개 변수  
 `bDefault`  
 컨트롤에 기본 단추가; 되어야 하는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
> [!NOTE]
>  있어야는 **OLEMISC_ACTSLIKEBUTTON** 상태 비트가 설정 합니다.  
  
##  <a name="setdlgctrlid"></a>  COleControlSite::SetDlgCtrlID  
 컨트롤의 대화 항목 식별자의 값을 변경합니다.  
  
```  
virtual int SetDlgCtrlID(int nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 새 식별자 값입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 대화 상자 창의; 식별자 항목 성공 하면 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setfocus"></a>  COleControlSite::SetFocus  
 컨트롤에 포커스를 설정 합니다.  
  
```  
virtual CWnd* SetFocus();  
virtual CWnd* SetFocus(LPMSG lpmsg);
```  
  
### <a name="parameters"></a>매개 변수  
 *lpmsg*  
 에 대 한 포인터는 [MSG 구조체](../../mfc/reference/msg-structure1.md)합니다. 이 구조에 포함 된 Windows 메시지 트리거하는 `SetFocus` 현재 컨트롤 사이트에 포함 된 컨트롤에 대 한 요청입니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 포커스가 있던 창에 대 한 포인터입니다.  
  
##  <a name="setproperty"></a>  COleControlSite::SetProperty  
 로 지정 된 컨트롤 속성을 설정 `dwDispID`합니다.  
  
```  
virtual void AFX_CDECL SetProperty(
    DISPID dwDispID,  
    VARTYPE vtProp, ...);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 속성 또는 메서드를 컨트롤의에 대 한 디스패치 ID 식별 `IDispatch` 인터페이스를 설정 합니다.  
  
 `vtProp`  
 속성을 설정 해야 유형을 지정 합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 *...*  
 `vtProp`에서 지정한 유형의 단일 매개 변수  
  
### <a name="remarks"></a>설명  
 경우 `SetProperty` 에서 오류가 발생 하 게 예외가 throw 됩니다.  
  
 예외의 유형은 메서드나 속성을 설정할 수의 반환 값에 의해 결정 됩니다. 반환 값이 `DISP_E_EXCEPTION`, **COleDispatchExcpetion** throw 되 고, 그렇지 않으면는 `COleException`합니다.  
  
##  <a name="setpropertyv"></a>  COleControlSite::SetPropertyV  
 로 지정 된 컨트롤 속성을 설정 `dwDispID`합니다.  
  
```  
virtual void SetPropertyV(
    DISPID dwDispID,  
    VARTYPE vtProp,  
    va_list argList);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwDispID`  
 속성 또는 메서드를 컨트롤의에 대 한 디스패치 ID 식별 `IDispatch` 인터페이스를 설정 합니다.  
  
 `vtProp`  
 속성을 설정 해야 유형을 지정 합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [coledispatchdriver:: Invokehelper](../../mfc/reference/coledispatchdriver-class.md#invokehelper)합니다.  
  
 `argList`  
 인수 목록에 대한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 메서드 또는 호출 되는 속성에 대 한 추가 매개 변수는 passeed 수를 사용 하는 *arg_list* 매개 변수입니다. 경우 `SetProperty` 에서 오류가 발생 하 게 예외가 throw 됩니다.  
  
 예외의 유형은 메서드나 속성을 설정할 수의 반환 값에 의해 결정 됩니다. 반환 값이 `DISP_E_EXCEPTION`, **COleDispatchExcpetion** throw 되 고, 그렇지 않으면는 `COleException`합니다.  
  
##  <a name="setwindowpos"></a>  COleControlSite::SetWindowPos  
 크기, 위치 및 컨트롤 사이트에서의 Z 순서를 설정합니다.  
  
```  
virtual BOOL SetWindowPos(
    const CWnd* pWndInsertAfter,  
    int x,  
    int y,  
    int cx,  
    int cy,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWndInsertAfter`  
 창에 대 한 포인터입니다.  
  
 *x*  
 창 왼쪽의 새 위치입니다.  
  
 *y*  
 창의 위쪽의 새 위치입니다.  
  
 `cx`  
 창의 새 너비  
  
 `cy`  
 창의 새 높이입니다.  
  
 `nFlags`  
 창 크기 조정 및 위치 플래그를 지정 합니다. 가능한 값에 대 한 설명 섹션을 참조 하십시오. [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) Windows sdk에서입니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아니고 그렇지 않으면 0을 성공 하는 경우.  
  
##  <a name="setwindowtext"></a>  COleControlSite::SetWindowText  
 컨트롤 사이트에 대 한 텍스트를 설정합니다.  
  
```  
virtual void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszString`  
 새 제목 또는 컨트롤 텍스트도 사용할 수는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 이 함수는 먼저 Caption 스톡 속성을 설정 하려고 합니다. 캡션 스톡 속성이 지원 되지 않는 경우 Text 속성 대신 설정 됩니다.  
  
##  <a name="showwindow"></a>  COleControlSite::ShowWindow  
 창의 표시 상태를 설정합니다.  
  
```  
virtual BOOL ShowWindow(int nCmdShow);
```  
  
### <a name="parameters"></a>매개 변수  
 `nCmdShow`  
 컨트롤 사이트에서 표시할 방법을 지정 합니다. 다음 값 중 하나 여야 합니다.  
  
- **SW_HIDE** 이 창을 숨깁니다 하 고 다른 창에 활성화를 전달 합니다.  
  
- **SW_MINIMIZE** 창을 최소화 하 고 시스템의 목록에서 최상위 창을 활성화 합니다.  
  
- **SW_RESTORE** 활성화 하 고 창을 표시 합니다. 창이, 최대화 또는 최소화 하는 경우 Windows의 원래 크기와 위치에 복원 합니다.  
  
- **SW_SHOW** 의 현재 크기와 위치에 표시 하 고 창을 활성화 합니다.  
  
- **SW_SHOWMAXIMIZED** 창을 활성화 한 최대화 창으로 표시 됩니다.  
  
- **SW_SHOWMINIMIZED** 창을 활성화 하 고 아이콘으로 표시 합니다.  
  
- **SW_SHOWMINNOACTIVE** 창을 아이콘으로 표시 합니다. 현재 활성화 된 창에 활성 상태로 유지 됩니다.  
  
- **SW_SHOWNA** 현재 상태에서 창을 표시 합니다. 현재 활성화 된 창에 활성 상태로 유지 됩니다.  
  
- **SW_SHOWNOACTIVATE** 의 가장 최근 크기와 위치에 있는 창을 표시 합니다. 현재 활성화 된 창에 활성 상태로 유지 됩니다.  
  
- **SW_SHOWNORMAL** 활성화 하 고 창을 표시 합니다. 창이, 최대화 또는 최소화 하는 경우 Windows의 원래 크기와 위치에 복원 합니다.  
  
### <a name="return-value"></a>반환 값  
 이전에 표시 되는 창 되었으면 0이 아닌 창이 이전에 숨겨진 된 경우 0입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleControlContainer 클래스](../../mfc/reference/colecontrolcontainer-class.md)
