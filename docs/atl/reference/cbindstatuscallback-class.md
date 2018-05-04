---
title: CBindStatusCallback 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
dev_langs:
- C++
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43a51b98710ea92f153581945007f21864dca6f4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="cbindstatuscallback-class"></a>CBindStatusCallback 클래스
이 클래스는 `IBindStatusCallback` 인터페이스를 구현합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 데이터를 수신할 때 호출 될 함수를 포함 하 여 클래스입니다.  
  
 *nBindFlags*  
 반환 되는 바인딩 플래그 지정 [GetBindInfo](#getbindinfo)합니다. 기본 구현은 비동기적 바인딩을 가져오거나 설정, 데이터/개체의 최신 버전을 검색 및 디스크 캐시에 검색 된 데이터를 저장 하지 않습니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|생성자입니다.|  
|[CBindStatusCallback:: ~ CBindStatusCallback](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|다운로드 프로세스를 시작 하는 정적 메서드를 만듭니다는 `CBindStatusCallback` 개체 및 호출 `StartAsyncDownload`합니다.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|만들려는 바인딩 종류에 대 한 요청 정보를 비동기 모니커에서 호출 됩니다.|  
|[CBindStatusCallback::GetPriority](#getpriority)|비동기 모니커 바인딩 작업의 우선 순위를 가져오려는 호출 됩니다. ATL 구현은 `E_NOTIMPL`합니다.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|사용할 수 있도록 응용 프로그램에 데이터를 제공 하기 위해 호출 합니다. 데이터를 읽고 데이터를 사용 하기 위해 전달 된 함수를 호출 합니다.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|리소스가 부족 한 때 호출 됩니다. ATL 구현은 `S_OK`합니다.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|응용 프로그램에 대 한 개체 인터페이스 포인터를 전달 하는 비동기 모니커에서 호출 됩니다. ATL 구현은 `S_OK`합니다.|  
|[CBindStatusCallback::OnProgress](#onprogress)|데이터 다운로드 프로세스의 진행률을 나타내기 위해 호출 됩니다. ATL 구현은 `S_OK`합니다.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|바인딩 시작 될 때 호출 됩니다.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|비동기 데이터 전송을 중지 될 때 호출 됩니다.|  
|[CBindStatusCallback::StartAsyncDownload](#startasyncdownload)|사용할 수 있는 바이트를 초기화 합니다. 0 바이트를 읽을 개체를 만듭니다 푸시 형 스트림 URL 및 호출에서 `OnDataAvailable` 될 때마다 데이터를 사용할 수 있습니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|읽을 수 있는 바이트 수입니다.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|읽은 총 바이트 수입니다.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|함수에 대 한 포인터에는 데이터를 사용할 때 호출 됩니다.|  
|[CBindStatusCallback::m_pT](#m_pt)|비동기 데이터 전송을 요청 된 개체에 대 한 포인터입니다.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|에 대 한 포인터는 [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) 현재 바인딩 작업에 대 한 인터페이스입니다.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|에 대 한 포인터는 `IBinding` 현재 바인딩 작업에 대 한 인터페이스입니다.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|에 대 한 포인터는 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) 사용할 URL에 대 한 인터페이스입니다.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|에 대 한 포인터는 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 데이터 전송에 대 한 인터페이스입니다.|  
  
## <a name="remarks"></a>설명  
 `CBindStatusCallback` 클래스는 `IBindStatusCallback` 인터페이스를 구현합니다. `IBindStatusCallback` 비동기 데이터 전송에서 알림을 받을 수 있도록 응용 프로그램에서 구현 되어야 합니다. 시스템에서 제공 하는 비동기 모니커를 사용 하 여 `IBindStatusCallback` 하 고 개체에서 메서드를 비동기 데이터에 대 한 정보를 주고받으며 전송 합니다.  
  
 일반적으로 `CBindStatusCallback` 개체는 특정 바인딩 작업과 연결 합니다. 예를 들어는 [비동기](../../visual-cpp-samples.md) 샘플에서는 URL 속성을 설정할 때 만듭니다는 `CBindStatusCallback` 개체에 대 한 호출에서 `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing#86](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 콜백 함수를 사용 하는 비동기 모니커 `OnData` 를 데이터가 있는 경우 응용 프로그램을 호출 합니다. 비동기 모니커는 시스템에서 제공 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>  CBindStatusCallback::CBindStatusCallback  
 생성자입니다.  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>설명  
 비동기 데이터 전송에 관한 알림을 받을 개체를 만듭니다. 일반적으로 각 바인딩 작업에 대 한 하나의 개체가 생성 됩니다.  
  
 또한 생성자 [m_pT](#m_pt) 및 [m_pFunc](#m_pfunc) 를 **NULL**합니다.  
  
##  <a name="dtor"></a>  CBindStatusCallback:: ~ CBindStatusCallback  
 소멸자입니다.  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="download"></a>  CBindStatusCallback::Download  
 만듭니다는 `CBindStatusCallback` 개체와 호출 `StartAsyncDownload` 지정된 된 URL에서 비동기적으로 데이터를 다운로드를 시작 합니다.  
  
```
static HRESULT Download(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pT*  
 [in] 비동기 데이터 전송을 요청 하는 개체에 대 한 포인터입니다. `CBindStatusCallback` 개체는이 개체의이 클래스에 템플릿 화 됩니다.  
  
 *pFunc*  
 [in] 읽을 수 있는 데이터를 수신 하는 함수에 대 한 포인터입니다. 함수 형식의 개체의 클래스의 멤버인 `T`합니다. 참조 [StartAsyncDownload](#startasyncdownload) 구문 및 예에 대 한 합니다.  
  
 `bstrURL`  
 [in] 데이터를 가져올 URL입니다. 유효한 모든 URL 또는 파일 이름일 수 있습니다. 일 수 없습니다 **NULL**합니다. 예를 들어:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** 컨테이너의 합니다. **NULL** 기본적으로 합니다.  
  
 `bRelative`  
 [in] 상대 또는 절대 URL이 있는지 여부를 나타내는 플래그입니다. **FALSE** 기본적으로 의미 URL이 절대 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 통해 개체에 전송 될 때마다 데이터를 사용할 수 `OnDataAvailable`합니다. `OnDataAvailable` 데이터를 읽고에서 가리키는 함수를 호출 *pFunc* (예: 데이터를 저장 하거나 인쇄 하 여 화면에).  
  
##  <a name="getbindinfo"></a>  CBindStatusCallback::GetBindInfo  
 모니커에 바인딩하는 방법을 알려 주도록 호출 됩니다.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>매개 변수  
 *pgrfBSCF*  
 [out] 에 대 한 포인터 **BINDF** 바인딩 작업 해야 발생 하는 방식을 나타내는 열거형 값입니다. 기본적으로 다음 열거형 값으로 설정 합니다.  
  
 **BINDF_ASYNCHRONOUS** 비동기 다운로드 합니다.  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable` 반환 **E_PENDING** 때 데이터를 아직 데이터가 있을 때까지 차단 하는 대신 사용할 수 있습니다.  
  
 **BINDF_GETNEWESTVERSION** 바인딩 작업에서 최신 버전의 데이터를 검색 해야 합니다.  
  
 **BINDF_NOWRITECACHE** 바인드 디스크 캐시는 검색 된 데이터를 저장 하지 마십시오.  
  
 *pbindinfo*  
 [out에서] 에 대 한 포인터는 **바인드** 구조 개체 바인딩 적용 되려면를 하는 방법에 대 한 자세한 정보를 제공 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 바인딩을 비동기적 데이터 밀어넣기 모델을 사용 하도록 설정 합니다. 데이터 푸시 모델에서 모니커 비동기 바인드 드라이브 하 고 지속적으로 새 데이터를 사용할 수 있는 경우 클라이언트에 알립니다.  
  
##  <a name="getpriority"></a>  CBindStatusCallback::GetPriority  
 비동기 모니커 바인딩 작업의 우선 순위를 가져오려는 호출 됩니다.  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>매개 변수  
 *pnPriority*  
 [out] 주소는 **긴** 성공할 경우 우선 순위를 수신 하는 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOTIMPL**합니다.  
  
##  <a name="m_dwavailabletoread"></a>  CBindStatusCallback::m_dwAvailableToRead  
 용도를 읽을 수 있는 바이트 수를 저장 합니다.  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>설명  
 0으로 초기화 된 `StartAsyncDownload`합니다.  
  
##  <a name="m_dwtotalread"></a>  CBindStatusCallback::m_dwTotalRead  
 바이트의 누적 합계 비동기 데이터 전송을 읽습니다.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>설명  
 될 때마다 증가 `OnDataAvailable` 실제로 읽는 바이트 수에 의해 호출 됩니다. 0으로 초기화 된 `StartAsyncDownload`합니다.  
  
##  <a name="m_pfunc"></a>  CBindStatusCallback::m_pFunc  
 함수에서 가리키는 `m_pFunc` 호출한 `OnDataAvailable` (예: 데이터를 저장 하거나 인쇄 하 여 화면에) 사용 가능한 데이터를 읽은 후 합니다.  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>설명  
 함수에서 가리키는 `m_pFunc` 개체의 클래스의 멤버 이며 다음 구문을 가집니다.  
  
```  
void Function_Name(  
   CBindStatusCallback<T>* pbsc,  
   BYTE* pBytes,  
   DWORD dwSize  
   );  
```  
  
##  <a name="m_pt"></a>  CBindStatusCallback::m_pT  
 비동기 데이터 전송을 요청 하는 개체에 대 한 포인터입니다.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>설명  
 `CBindStatusCallback` 개체는이 개체의이 클래스에 템플릿 화 됩니다.  
  
##  <a name="m_spbindctx"></a>  CBindStatusCallback::m_spBindCtx  
 에 대 한 포인터는 [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) 바인딩 컨텍스트 (특정 모니커 바인딩 작업에 대 한 정보를 저장 하는 개체)에 대 한 액세스를 제공 하는 인터페이스입니다.  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>설명  
 초기화 된 `StartAsyncDownload`합니다.  
  
##  <a name="m_spbinding"></a>  CBindStatusCallback::m_spBinding  
 에 대 한 포인터는 `IBinding` 현재 바인딩 작업의 인터페이스입니다.  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>설명  
 초기화 된 `OnStartBinding` 에 출시 및 `OnStopBinding`합니다.  
  
##  <a name="m_spmoniker"></a>  CBindStatusCallback::m_spMoniker  
 에 대 한 포인터는 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) 사용할 URL에 대 한 인터페이스입니다.  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>설명  
 초기화 된 `StartAsyncDownload`합니다.  
  
##  <a name="m_spstream"></a>  CBindStatusCallback::m_spStream  
 에 대 한 포인터는 [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 현재 바인딩 작업의 인터페이스입니다.  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>설명  
 초기화 된 `OnDataAvailable` 에서 **STGMEDIUM** 경우 구조는 **BCSF** 플래그는 **BCSF_FIRSTDATANOTIFICATION** 면이 해제 하 고는 **BCSF**  플래그는 **BCSF_LASTDATANOTIFICATION**합니다.  
  
##  <a name="ondataavailable"></a>  CBindStatusCallback::OnDataAvailable  
 비동기 모니커 시스템 제공 호출 `OnDataAvailable` 를 사용할 수 있도록 데이터 개체를 제공 하도록 합니다.  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>매개 변수  
 *grfBSCF*  
 [in] A **BSCF** 열거형 값입니다. 다음 중 하나 이상이: **BSCF_FIRSTDATANOTIFICATION**, **BSCF_INTERMEDIARYDATANOTIFICATION**, 또는 **BSCF_LASTDATANOTIFICATION**합니다.  
  
 `dwSize`  
 [in] 바인딩의 시작 된 이후에 사용할 수 있는 데이터의 바이트 단위로 누적 시간입니다. 데이터의 양을 관련이 또는 특정 어떠한을 사용할 수 있게 나타내는 0을 수 있습니다.  
  
 *pformatetc*  
 [in] 에 대 한 포인터는 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) 사용 가능한 데이터의 형식을 포함 하는 구조입니다. 서식 없음 이면 수 **CF_NULL**합니다.  
  
 *pstgmed*  
 [in] 에 대 한 포인터는 [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269) 현재 사용할 수 있는 실제 데이터를 보유 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 `OnDataAvailable` 데이터를 읽고 (예: 데이터를 저장 하거나 인쇄 하 여 화면에) 개체의 클래스의 메서드를 호출 합니다. 참조 [CBindStatusCallback::StartAsyncDownload](#startasyncdownload) 대 한 자세한 내용은 합니다.  
  
##  <a name="onlowresource"></a>  CBindStatusCallback::OnLowResource  
 리소스가 부족 한 때 호출 됩니다.  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwReserved`  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
##  <a name="onobjectavailable"></a>  CBindStatusCallback::OnObjectAvailable  
 응용 프로그램에 대 한 개체 인터페이스 포인터를 전달 하는 비동기 모니커에서 호출 됩니다.  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>매개 변수  
 `riid`  
 요청된 된 인터페이스의 인터페이스 식별자입니다. 사용되지 않습니다.  
  
 `punk`  
 주소는 IUnknown 인터페이스입니다. 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
##  <a name="onprogress"></a>  CBindStatusCallback::OnProgress  
 데이터 다운로드 프로세스의 진행률을 나타내기 위해 호출 됩니다.  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>매개 변수  
 `ulProgress`  
 부호 없는 정수 (long)입니다. 사용되지 않습니다.  
  
 `ulProgressMax`  
 부호 없는 정수 (long) 사용 되지 않습니다.  
  
 `ulStatusCode`  
 부호 없는 정수 (long)입니다. 사용되지 않습니다.  
  
 `szStatusText`  
 주소는 문자열 값입니다. 사용되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
##  <a name="onstartbinding"></a>  CBindStatusCallback::OnStartBinding  
 데이터 멤버를 설정 [m_spBinding](#m_spbinding) 에 `IBinding` 에서 포인터 `pBinding`합니다.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwReserved`  
 나중에 사용하기 위해 예약되어 있습니다.  
  
 `pBinding`  
 [in] 현재 IBinding 인터페이스의 주소가 작업에 바인딩합니다. 이 NULL이 될 수 없습니다. 클라이언트는 바인딩 개체에 대 한 참조를 유지 하려면이 포인터에서 AddRef를 호출 해야 합니다.  
  
##  <a name="onstopbinding"></a>  CBindStatusCallback::OnStopBinding  
 릴리스는 `IBinding` 데이터 멤버의 포인터 [m_spBinding](#m_spbinding)합니다.  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>매개 변수  
 `hresult`  
 바인딩 작업에서 반환 된 상태 코드입니다.  
  
 szStatusText  
 사용 되지 않은 문자열 값의 주소입니다.  
  
### <a name="remarks"></a>설명  
 시스템 제공 비동기 모니커 바인딩 작업의 끝을 나타내는에서 호출 됩니다.  
  
##  <a name="startasyncdownload"></a>  CBindStatusCallback::StartAsyncDownload  
 지정된 된 URL에서 비동기적으로 데이터를 다운로드를 시작 합니다.  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pT*  
 [in] 비동기 데이터 전송을 요청 하는 개체에 대 한 포인터입니다. `CBindStatusCallback` 개체는이 개체의이 클래스에 템플릿 화 됩니다.  
  
 *pFunc*  
 [in] 읽는 중인 데이터를 수신 하는 함수에 대 한 포인터입니다. 함수 형식의 개체의 클래스의 멤버인 `T`합니다. 참조 **주의** 구문 및 예에 대 한 합니다.  
  
 `bstrURL`  
 [in] 데이터를 가져올 URL입니다. 유효한 모든 URL 또는 파일 이름일 수 있습니다. 일 수 없습니다 **NULL**합니다. 예를 들어:  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] **IUnknown** 컨테이너의 합니다. **NULL** 기본적으로 합니다.  
  
 `bRelative`  
 [in] 상대 또는 절대 URL이 있는지 여부를 나타내는 플래그입니다. **FALSE** 기본적으로 의미 URL이 절대 주소입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 중 하나 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 통해 개체에 전송 될 때마다 데이터를 사용할 수 `OnDataAvailable`합니다. `OnDataAvailable` 데이터를 읽고에서 가리키는 함수를 호출 *pFunc* (예: 데이터를 저장 하거나 인쇄 하 여 화면에).  
  
 함수에서 가리키는 *pFunc* 개체의 클래스의 멤버 이며 다음 구문을 가집니다.  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD` `dwSize`  
  
 `);`  
  
 다음 예제에서 (에서 가져온는 [비동기](../../visual-cpp-samples.md) 샘플)를 함수 `OnData` 텍스트 상자에 수신된 된 데이터를 씁니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing#87](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
