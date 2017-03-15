---
title: "CCmdTarget 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCmdTarget
dev_langs:
- C++
helpviewer_keywords:
- message maps, CCmdTarget base class
- command targets
- CCmdTarget class
- command routing, command targets
- targets, command
ms.assetid: 8883b132-2057-4ce0-a5f2-88979f8f2b13
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0b5b7617f6b3d89e454e31c9f95b5d4455569114
ms.lasthandoff: 02/24/2017

---
# <a name="ccmdtarget-class"></a>CCmdTarget 클래스
Microsoft Foundation Class 라이브러리 메시지 맵 아키텍처에 대 한 기본 클래스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CCmdTarget : public CObject  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CCmdTarget::CCmdTarget](#ccmdtarget)|`CCmdTarget` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CCmdTarget::BeginWaitCursor](#beginwaitcursor)|모래 시계 커서도 커서를 표시합니다.|  
|[CCmdTarget::DoOleVerb](#dooleverb)|OLE 동사를 수행 하 여 지정 된 동작이 발생 합니다.|  
|[CCmdTarget::EnableAutomation](#enableautomation)|에 대 한 OLE 자동화의 `CCmdTarget` 개체입니다.|  
|[CCmdTarget::EnableConnections](#enableconnections)|연결 지점을 통해 이벤트 발생을 수 있습니다.|  
|[CCmdTarget::EnableTypeLib](#enabletypelib)|개체의 형식 라이브러리를 사용 하도록 설정 합니다.|  
|[CCmdTarget::EndWaitCursor](#endwaitcursor)|이전 커서를 반환 합니다.|  
|[CCmdTarget::EnumOleVerbs](#enumoleverbs)|개체의 OLE 동사를 열거합니다.|  
|[CCmdTarget::FromIDispatch](#fromidispatch)|에 대 한 포인터를 반환 된 `CCmdTarget` 연관 된 개체는 `IDispatch` 포인터입니다.|  
|[CCmdTarget::GetDispatchIID](#getdispatchiid)|기본적인 디스패치 인터페이스 ID를 가져옵니다.|  
|[CCmdTarget::GetIDispatch](#getidispatch)|에 대 한 포인터를 반환 된 `IDispatch` 연관 된 개체는 `CCmdTarget` 개체입니다.|  
|[CCmdTarget::GetTypeInfoCount](#gettypeinfocount)|개체에서 제공 하는 형식 정보 인터페이스의 수를 검색 합니다.|  
|[CCmdTarget::GetTypeInfoOfGuid](#gettypeinfoofguid)|지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.|  
|[CCmdTarget::GetTypeLib](#gettypelib)|형식 라이브러리에 대 한 포인터를 가져옵니다.|  
|[CCmdTarget::GetTypeLibCache](#gettypelibcache)|형식 라이브러리 캐시를 가져옵니다.|  
|[CCmdTarget::IsInvokeAllowed](#isinvokeallowed)|자동화 메서드 호출을 수 있습니다.|  
|[CCmdTarget::IsResultExpected](#isresultexpected)|반환 하는 경우 자동화 기능에는&0;이 아닌 값을 반환 해야 합니다.|  
|[CCmdTarget::OnCmdMsg](#oncmdmsg)|라우팅 및 명령 메시지를 디스패치합니다.|  
|[CCmdTarget::OnFinalRelease](#onfinalrelease)|마지막 OLE 참조가 해제 된 후 정리 합니다.|  
|[CCmdTarget::RestoreWaitCursor](#restorewaitcursor)|모래 시계 커서를 복원합니다.|  
  
## <a name="remarks"></a>주의  
 메시지 맵 처리에 쓸 멤버 함수에 명령 또는 메시지를 라우팅합니다. (명령 액셀러레이터 키, 명령 단추 또는 메뉴 항목에서 메시지입니다.)  
  
 키 프레임 워크 클래스에서 파생 된 `CCmdTarget` 포함 [CView](../../mfc/reference/cview-class.md), [CWinApp](../../mfc/reference/cwinapp-class.md), [CDocument](../../mfc/reference/cdocument-class.md), [CWnd](../../mfc/reference/cwnd-class.md), 및 [CFrameWnd](../../mfc/reference/cframewnd-class.md)합니다. 메시지를 처리 하는 새 클래스를 호스팅하려는 경우 다음 중 하나에서 클래스를 파생 `CCmdTarget`-클래스를 파생 합니다. 클래스를 파생 거의 `CCmdTarget` 직접.  
  
 명령 대상에 대 한 개요 및 `OnCmdMsg` 참조 라우팅, [명령 대상](../../mfc/command-targets.md), [명령 라우팅](../../mfc/command-routing.md), 및 [메시지 매핑](../../mfc/mapping-messages.md)합니다.  
  
 `CCmdTarget`모래 시계 커서의 표시를 처리 하는 멤버 함수를 포함 합니다. 명령을 실행 하는 긴 시간 간격을 예상 되는 경우에 모래 시계 커서를 표시 합니다.  
  
 디스패치 맵, 메시지 맵 비슷합니다, OLE 자동화를 노출 하는 데 사용 됩니다 `IDispatch` 기능입니다. 이 인터페이스를 노출 하 여 다른 응용 프로그램 (예: Visual Basic의 경우)를 응용 프로그램으로 호출할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CCmdTarget`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namebeginwaitcursora--ccmdtargetbeginwaitcursor"></a><a name="beginwaitcursor"></a>CCmdTarget::BeginWaitCursor  
 명령을 실행 하는 긴 시간 간격을 예상 되는 경우 커서는 모래 시계를 표시 하려면이 함수를 호출 합니다.  
  
```  
void BeginWaitCursor();
```  
  
### <a name="remarks"></a>주의  
 있는지 보여 주기 위해 사용자는 다른 작업을 실행할 때와 같이이 함수를 호출 하는 프레임 워크는 **CDocument** 개체를 로드 또는 자체 파일에 저장 합니다.  
  
 작업 `BeginWaitCursor` 에 항상 비효율적 단일 메시지 처리기 외부에서 다른 작업으로 같은 `OnSetCursor` 처리, 커서 변경 될 수 있습니다.  
  
 호출 `EndWaitCursor` 이전 커서를 복원 하려면.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="a-nameccmdtargeta--ccmdtargetccmdtarget"></a><a name="ccmdtarget"></a>CCmdTarget::CCmdTarget  
 `CCmdTarget` 개체를 생성합니다.  
  
```  
CCmdTarget();
```  
  
##  <a name="a-namedooleverba--ccmdtargetdooleverb"></a><a name="dooleverb"></a>CCmdTarget::DoOleVerb  
 OLE 동사를 수행 하 여 지정 된 동작이 발생 합니다.  
  
```  
BOOL DoOleVerb(
    LONG iVerb,  
    LPMSG lpMsg,  
    HWND hWndParent,  
    LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `iVerb`  
 동사의 숫자 식별자입니다.  
  
 `lpMsg`  
 에 대 한 포인터는 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958) 동사를 호출 하는 이벤트 (예: 두 번 클릭)를 설명 하는 구조입니다.  
  
 `hWndParent`  
 개체가 포함된 문서 창의 핸들입니다.  
  
 `lpRect`  
 에 대 한 포인터는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 개체를 정의 하는 픽셀 단위의 좌표가 포함 된 구조체의 경계 사각형 *창은*합니다.  
  
### <a name="return-value"></a>반환 값  
 성공이 고, 그렇지 않으면 FALSE 면 TRUE입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 기본적으로 구현 [IOleObject::DoVerb](http://msdn.microsoft.com/library/windows/desktop/ms694508)합니다. 가능한 작업 열거 하는 [CCmdTarget::EnumOleVerbs](#enumoleverbs)합니다.  
  
##  <a name="a-nameenableautomationa--ccmdtargetenableautomation"></a><a name="enableautomation"></a>CCmdTarget::EnableAutomation  
 OLE 자동화 개체를 사용 하도록 설정 하려면이 함수를 호출 합니다.  
  
```  
void EnableAutomation();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 일반적으로 개체의 생성자에서 호출 하 고 디스패치 맵은 클래스에 대해 선언 된 경우에 호출 해야 합니다. 자동화에 대 한 자세한 내용은 문서를 참조 [자동화 클라이언트](../../mfc/automation-clients.md) 및 [자동화 서버](../../mfc/automation-servers.md)합니다.  
  
##  <a name="a-nameenableconnectionsa--ccmdtargetenableconnections"></a><a name="enableconnections"></a>CCmdTarget::EnableConnections  
 연결 지점을 통해 이벤트 발생을 수 있습니다.  
  
```  
void EnableConnections();
```  
  
### <a name="remarks"></a>주의  
 연결점을 사용 하려면 파생 된 클래스의 생성자에서이 함수를 호출 합니다.  
  
##  <a name="a-nameenabletypeliba--ccmdtargetenabletypelib"></a><a name="enabletypelib"></a>CCmdTarget::EnableTypeLib  
 개체의 형식 라이브러리를 사용 하도록 설정 합니다.  
  
```  
void EnableTypeLib();
```  
  
### <a name="remarks"></a>주의  
 생성자에서이 함수를 호출 하면 `CCmdTarget`-형식 정보를 제공 하는 경우 파생 된 개체입니다. 자세한 내용은 기술 자료 문서 Q185720을 참조 하십시오. "방법: MFC 자동화 서버에서 형식 정보를 제공 합니다." 기술 자료 문서 또는 MSDN 라이브러리의 Visual Studio 설명서에서 사용할 수 있는 [http://support.microsoft.com](http://support.microsoft.com/)합니다.  
  
##  <a name="a-nameendwaitcursora--ccmdtargetendwaitcursor"></a><a name="endwaitcursor"></a>CCmdTarget::EndWaitCursor  
 이 함수를 호출한 후 호출는 `BeginWaitCursor` 멤버 함수를 모래 시계 커서에서 이전 커서를 반환 합니다.  
  
```  
void EndWaitCursor();
```  
  
### <a name="remarks"></a>주의  
 프레임 워크는 또한 모래 시계 커서를 호출한 후이 멤버 함수를 호출 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
##  <a name="a-nameenumoleverbsa--ccmdtargetenumoleverbs"></a><a name="enumoleverbs"></a>CCmdTarget::EnumOleVerbs  
 개체의 OLE 동사를 열거합니다.  
  
```  
BOOL EnumOleVerbs(LPENUMOLEVERB* ppenumOleVerb);
```  
  
### <a name="parameters"></a>매개 변수  
 `ppenumOleVerb`  
 에 대 한 포인터에 대 한 포인터는 [IEnumOLEVERB](http://msdn.microsoft.com/library/windows/desktop/ms695084) 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 개체가 하나 이상 OLE 동사를 지원 합니다 (있는 경우 \* `ppenumOleVerb` 가리키는 **IEnumOLEVERB** 열거자 인터페이스)이 고, 그렇지 않으면 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 기본적으로 구현 [IOleObject::EnumVerbs](http://msdn.microsoft.com/library/windows/desktop/ms692781)합니다.  
  
##  <a name="a-namefromidispatcha--ccmdtargetfromidispatch"></a><a name="fromidispatch"></a>CCmdTarget::FromIDispatch  
 매핑할이 함수를 호출 하는 `IDispatch` 로 클래스의 자동화 멤버 함수에서 받은 포인터는 `CCmdTarget` 의 인터페이스를 구현 하는 개체는 `IDispatch` 개체입니다.  
  
```  
static CCmdTarget* PASCAL FromIDispatch(LPDISPATCH lpDispatch);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDispatch`  
 `IDispatch` 개체에 대한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CCmdTarget` 개체와 연결 된 `lpDispatch`합니다. 이 함수는 반환 **NULL** 경우는 `IDispatch` 개체는 Microsoft Foundation Class로 인식 되지 않습니다 `IDispatch` 개체입니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 결과 멤버 함수에 대 한 호출의 역 `GetIDispatch`합니다.  
  
##  <a name="a-namegetdispatchiida--ccmdtargetgetdispatchiid"></a><a name="getdispatchiid"></a>CCmdTarget::GetDispatchIID  
 기본적인 디스패치 인터페이스 ID를 가져옵니다.  
  
```  
virtual BOOL GetDispatchIID(IID* pIID);
```  
  
### <a name="parameters"></a>매개 변수  
 *pIID*  
 인터페이스 ID에 대 한 포인터 (한 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931)).  
  
### <a name="return-value"></a>반환 값  
 성공이 고, 그렇지 않으면 FALSE 면 TRUE입니다. 성공 하면 \* *pIID* 는 기본적인 디스패치 인터페이스 ID로 설정 되어  
  
### <a name="remarks"></a>주의  
 파생된 클래스에서이 멤버 함수를 재정의 해야 (재정의 되지 않으면 `GetDispatchIID` FALSE를 반환). 참조 [COleControl](../../mfc/reference/colecontrol-class.md)합니다.  
  
 자세한 내용은 기술 자료 문서 Q185720을 참조 하십시오. "방법: MFC 자동화 서버에서 형식 정보를 제공 합니다." 기술 자료 문서 또는 MSDN 라이브러리의 Visual Studio 설명서에서 사용할 수 있는 [http://support.microsoft.com](http://support.microsoft.com/)합니다.  
  
##  <a name="a-namegetidispatcha--ccmdtargetgetidispatch"></a><a name="getidispatch"></a>CCmdTarget::GetIDispatch  
 검색 하려면이 멤버 함수를 호출는 `IDispatch` 포인터 자동화 메서드로부터 그 중 하나가 반환는 `IDispatch` 포인터 또는 하나는 `IDispatch` 참조로 포인터입니다.  
  
```  
LPDISPATCH GetIDispatch(BOOL bAddRef);
```  
  
### <a name="parameters"></a>매개 변수  
 *bAddRef*  
 개체에 대 한 참조 횟수를 증가 것인지 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `IDispatch` 개체와 연결 된 포인터입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 호출 하는 개체 `EnableAutomation` 있도록 자동화를 사용 하는 생성자에서이 함수의 기본 클래스 구현에 대 한 포인터를 반환 `IDispatch` 를 통해 통신 하는 클라이언트에서 사용 되는 `IDispatch` 인터페이스입니다. 이 함수를 자동으로 호출 추가 하는 포인터에 대 한 참조를 호출 하는 데 필요한 되지 않으므로 [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)합니다.  
  
##  <a name="a-namegettypeinfocounta--ccmdtargetgettypeinfocount"></a><a name="gettypeinfocount"></a>CCmdTarget::GetTypeInfoCount  
 개체에서 제공 하는 형식 정보 인터페이스의 수를 검색 합니다.  
  
```  
virtual UINT GetTypeInfoCount();
```  
  
### <a name="return-value"></a>반환 값  
 형식 정보 인터페이스의 수입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 기본적으로 구현 [IDispatch::GetTypeInfoCount](http://msdn.microsoft.com/en-us/da876d53-cb8a-465c-a43e-c0eb272e2a12)합니다.  
  
 파생된 클래스에는 (0 또는 1)을 제공 하는 형식 정보 인터페이스의 수를 반환 하려면이 함수를 재정의 해야 합니다. 재정의 되지 않으면 **GetTypeInfoCount** 0을 반환 합니다. 를 무시 하려면는 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 도 구현 하는 매크로 `GetTypeLib` 및 `GetTypeLibCache`합니다.  
  
##  <a name="a-namegettypeinfoofguida--ccmdtargetgettypeinfoofguid"></a><a name="gettypeinfoofguid"></a>CCmdTarget::GetTypeInfoOfGuid  
 지정된 된 GUID에 해당 하는 형식 설명을 검색 합니다.  
  
```  
HRESULT GetTypeInfoOfGuid(
    LCID lcid,  
    const GUID& guid,  
    LPTYPEINFO* ppTypeInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `lcid`  
 로캘 식별자 ( `LCID`).  
  
 `guid`  
 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931) 형식 설명입니다.  
  
 `ppTypeInfo`  
 에 대 한 포인터에 대 한 포인터는 `ITypeInfo` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 호출의 성공 여부를 나타내는 HRESULT입니다. 성공 하면 * `ppTypeInfo` 형식 정보 인터페이스를 가리킵니다.  
  
##  <a name="a-namegettypeliba--ccmdtargetgettypelib"></a><a name="gettypelib"></a>CCmdTarget::GetTypeLib  
 형식 라이브러리에 대 한 포인터를 가져옵니다.  
  
```  
virtual HRESULT GetTypeLib(
    LCID lcid,  
    LPTYPELIB* ppTypeLib);
```  
  
### <a name="parameters"></a>매개 변수  
 `lcid`  
 로캘 식별자 ( `LCID`).  
  
 `ppTypeLib`  
 에 대 한 포인터에 대 한 포인터는 `ITypeLib` 인터페이스입니다.  
  
### <a name="return-value"></a>반환 값  
 호출의 성공 여부를 나타내는 HRESULT입니다. 성공 하면 * `ppTypeLib` 형식 라이브러리 인터페이스를 가리킵니다.  
  
### <a name="remarks"></a>주의  
 파생된 클래스에서이 멤버 함수를 재정의 해야 (재정의 되지 않으면 `GetTypeLib` TYPE_E_CANTLOADLIBRARY 반환). 사용 된 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 도 구현 하는 매크로 `GetTypeInfoCount` 및 `GetTypeLibCache`합니다.  
  
##  <a name="a-namegettypelibcachea--ccmdtargetgettypelibcache"></a><a name="gettypelibcache"></a>CCmdTarget::GetTypeLibCache  
 형식 라이브러리 캐시를 가져옵니다.  
  
```  
virtual CTypeLibCache* GetTypeLibCache();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 **CTypeLibCache** 개체입니다.  
  
### <a name="remarks"></a>주의  
 파생된 클래스에서이 멤버 함수를 재정의 해야 (재정의 되지 않으면 **GetTypeLibCache** NULL을 반환). 사용 된 [IMPLEMENT_OLETYPELIB](../../mfc/reference/type-library-access.md#implement_oletypelib) 도 구현 하는 매크로 `GetTypeInfoCount` 및 `GetTypeLib`합니다.  
  
##  <a name="a-nameisinvokealloweda--ccmdtargetisinvokeallowed"></a><a name="isinvokeallowed"></a>CCmdTarget::IsInvokeAllowed  
 이 함수는 MFC의 구현에 의해 호출 됩니다 **idispatch:: Invoke** 여부를 지정 된 자동화 메서드 확인 하려면 (으로 식별 `dispid`) 호출할 수 있습니다.  
  
```  
virtual BOOL IsInvokeAllowed(DISPID dispid);
```  
  
### <a name="parameters"></a>매개 변수  
 `dispid`  
 디스패치 id입니다.  
  
### <a name="return-value"></a>반환 값  
 TRUE 이면 메서드가 호출 된이 고, 그렇지 않으면 FALSE 일 수 있습니다.  
  
### <a name="remarks"></a>주의  
 경우 `IsInvokeAllowed` TRUE를 반환 **Invoke** ; 메서드를 호출 하는 진행 됩니다 그렇지 `Invoke` 이 실패 E_UNEXPECTED를 반환 합니다.  
  
 파생된 클래스에서 적절 한 값을 반환 하려면이 함수를 재정의할 수 (재정의 되지 않으면 `IsInvokeAllowed` TRUE를 반환 합니다). 특히 참조 [COleControl::IsInvokeAllowed](../../mfc/reference/colecontrol-class.md#isinvokeallowed)합니다.  
  
##  <a name="a-nameisresultexpecteda--ccmdtargetisresultexpected"></a><a name="isresultexpected"></a>CCmdTarget::IsResultExpected  
 사용 하 여 `IsResultExpected` 클라이언트 자동화 기능에 대 한 호출에서 반환 값이 필요 여부를 확인 합니다.  
  
```  
BOOL IsResultExpected();
```  
  
### <a name="return-value"></a>반환 값  
 자동화 기능 값을 반환 해야 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 MFC 사용 하 여이 정보에 대 한 호출의 결과를 결정 하 고 클라이언트를 사용 하거나 함수 호출의 결과 무시 하 고 있는지 여부에 대 한 MFC에 대 한 정보를 제공 하는 OLE 인터페이스 `IsResultExpected`합니다. 반환 값의 프로덕션 시간-또는 리소스 소모가 이면 반환 값을 계산 하기 전에이 함수를 호출 하 여 효율성을 높일 수 있습니다.  
  
 이 함수는 클라이언트를 호출한 호출 하는 경우 이러한 자동화 함수에서 하는 다른 자동화 함수에서 유효한 반환 값을 가져오도록는 한 번만 0을 반환 합니다.  
  
 `IsResultExpected`자동화 함수 호출과 진행 중인 취소할 때 호출 하는 경우&0;이 아닌 값을 반환 합니다.  
  
##  <a name="a-nameoncmdmsga--ccmdtargetoncmdmsg"></a><a name="oncmdmsg"></a>CCmdTarget::OnCmdMsg  
 라우팅 및 명령 메시지를 디스패치 및 명령 사용자 인터페이스 개체 업데이트를 처리 하는 프레임 워크에서 호출 됩니다.  
  
```  
virtual BOOL OnCmdMsg(
    UINT nID,  
    int nCode,  
    void* pExtra,  
    AFX_CMDHANDLERINFO* pHandlerInfo);
```  
  
### <a name="parameters"></a>매개 변수  
 `nID`  
 포함 명령 id입니다.  
  
 `nCode`  
 명령 알림 코드를 식별합니다. 참조 **주의** 값에 대 한 자세한 내용은 `nCode`합니다.  
  
 `pExtra`  
 값에 따라 사용 `nCode`합니다. 참조 **주의** 에 대 한 자세한 내용은 `pExtra`합니다.  
  
 `pHandlerInfo`  
 그렇지 않은 경우 **NULL**, `OnCmdMsg` 채웁니다는 **pTarget** 및 **pmf** 의 멤버는 `pHandlerInfo` 명령을 디스패치 하는 대신 구조입니다. 일반적으로이 매개 변수 여야 합니다 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 메시지가 처리 되는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이것은 프레임 워크 명령 아키텍처의 주요 구현 루틴입니다.  
  
 런타임 시 `OnCmdMsg` 또는 루트 클래스를 호출 하 여 명령 자체를 처리 하는 명령에 다른 개체에 디스패치 `CCmdTarget::OnCmdMsg`이며 실제 메시지 맵 조회를 수행 합니다. 참조에 대 한 전체 설명은 기본 명령 라우팅, [메시지 처리 및 매핑 항목](../../mfc/message-handling-and-mapping.md)합니다.  
  
 프레임 워크를 확장 하려면이 멤버 함수를 재정의 하려는 경우에 따라 표준 명령 라우팅입니다. 참조 [기술 참고 21](../../mfc/tn021-command-and-message-routing.md) 명령 라우팅 아키텍처의 고급 정보에 대 한 합니다.  
  
 재정의 하는 경우 `OnCmdMsg`, 적절 한 값을 제공 해야 `nCode`, 명령 알림 코드 및 `pExtra`의 값에 따라 `nCode`합니다. 다음 표에 해당 값을 보여 줍니다.  
  
|`nCode` 값|`pExtra` 값|  
|-------------------|--------------------|  
|CN_COMMAND|[CCmdUI](../../mfc/reference/ccmdui-class.md)*|  
|CN_EVENT|AFX_EVENT *|  
|CN_UPDATE_COMMAND_UI|CCmdUI *|  
|CN_OLECOMMAND|[COleCmdUI](../../mfc/reference/colecmdui-class.md)*|  
|CN_OLE_UNREGISTER|NULL|  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&44;](../../mfc/codesnippet/cpp/ccmdtarget-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView #&45;](../../mfc/codesnippet/cpp/ccmdtarget-class_3.cpp)]  
  
##  <a name="a-nameonfinalreleasea--ccmdtargetonfinalrelease"></a><a name="onfinalrelease"></a>CCmdTarget::OnFinalRelease  
 개체에서 마지막 OLE 참조를 놓을 때 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void OnFinalRelease();
```  
  
### <a name="remarks"></a>주의  
 이러한 상황에 대 한 특수 처리를 제공 하려면이 함수를 재정의 합니다. 기본 구현에서는 개체를 삭제 합니다.  
  
##  <a name="a-namerestorewaitcursora--ccmdtargetrestorewaitcursor"></a><a name="restorewaitcursor"></a>CCmdTarget::RestoreWaitCursor  
 시스템 커서 (예를 들어 메시지 상자는 열리고 후 긴 작업 중간에 닫힌 후) 변경 된 후 적절 한 모래 시계 커서를 복원 하려면이 함수를 호출 합니다.  
  
```  
void RestoreWaitCursor();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCDocView #&43;](../../mfc/codesnippet/cpp/ccmdtarget-class_1.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [ACDUAL MFC 샘플](../../visual-cpp-samples.md)   
 [CObject 클래스](../../mfc/reference/cobject-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CCmdUI 클래스](../../mfc/reference/ccmdui-class.md)   
 [CDocument 클래스](../../mfc/reference/cdocument-class.md)   
 [CDocTemplate 클래스](../../mfc/reference/cdoctemplate-class.md)   
 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CView 클래스](../../mfc/reference/cview-class.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [COleDispatchDriver 클래스](../../mfc/reference/coledispatchdriver-class.md)

