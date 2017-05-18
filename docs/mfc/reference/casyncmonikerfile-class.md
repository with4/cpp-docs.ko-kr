---
title: "CAsyncMonikerFile 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::CAsyncMonikerFile
- AFXOLE/CAsyncMonikerFile::Close
- AFXOLE/CAsyncMonikerFile::GetBinding
- AFXOLE/CAsyncMonikerFile::GetFormatEtc
- AFXOLE/CAsyncMonikerFile::Open
- AFXOLE/CAsyncMonikerFile::CreateBindStatusCallback
- AFXOLE/CAsyncMonikerFile::GetBindInfo
- AFXOLE/CAsyncMonikerFile::GetPriority
- AFXOLE/CAsyncMonikerFile::OnDataAvailable
- AFXOLE/CAsyncMonikerFile::OnLowResource
- AFXOLE/CAsyncMonikerFile::OnProgress
- AFXOLE/CAsyncMonikerFile::OnStartBinding
- AFXOLE/CAsyncMonikerFile::OnStopBinding
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- monikers [C++], MFC
- asynchronous controls [C++]
- CAsyncMonikerFile class
- IMoniker interface, binding
ms.assetid: 17378b66-a49a-4b67-88e3-7756ad26a2fc
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 47ba3137b5d0d38aa59e9d627101de8350eebd50
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="casyncmonikerfile-class"></a>CAsyncMonikerFile 클래스
ActiveX 컨트롤(이전의 OLE 컨트롤)에서 비동기 모니커를 사용할 수 있도록 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CAsyncMonikerFile : public CMonikerFile  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncMonikerFile::CAsyncMonikerFile](#casyncmonikerfile)|`CAsyncMonikerFile` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncMonikerFile::Close](#close)|닫고 모든 리소스를 해제 합니다.|  
|[CAsyncMonikerFile::GetBinding](#getbinding)|바인딩 비동기 전송에 대 한 포인터를 검색 합니다.|  
|[CAsyncMonikerFile::GetFormatEtc](#getformatetc)|스트림의 데이터의 형식을 검색합니다.|  
|[CAsyncMonikerFile::Open](#open)|비동기적으로 파일을 엽니다.|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|구현 하는 COM 개체를 만듭니다. `IBindStatusCallback`합니다.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|만들려는 바인딩 종류에 대 한 요청 정보로 OLE 시스템 라이브러리에 의해 호출 됩니다.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|바인딩의 우선 순위를 가져오려는 OLE 시스템 라이브러리에 의해 호출 됩니다.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|클라이언트에 사용할 수 있도록 비동기 바인딩 작업 중 데이터를 제공 하기 위해 호출 합니다.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|리소스가 부족 한 때 호출 됩니다.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|데이터 다운로드 프로세스의 진행률을 나타내기 위해 호출 됩니다.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|바인딩 시작 될 때 호출 됩니다.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|비동기 전송이 중지 될 때 호출 됩니다.|  
  
## <a name="remarks"></a>설명  
 파생 된 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)를 차례로에서 파생 된 [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` 사용 하 여는 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) URL에서 파일을 비동기적으로 로드를 포함 하 여 모든 데이터 스트림의 비동기적으로 액세스 하려면 인터페이스입니다. 파일에는 ActiveX 컨트롤의 데이터 경로 속성 일 수 있습니다.  
  
 비동기 모니커는 기본적으로 인터넷 사용 응용 프로그램 및 ActiveX 컨트롤에서 파일을 전송 하는 동안 응답성이 뛰어난 사용자 인터페이스를 제공 하는 데 사용 됩니다. 사용 하는 것이 가장 대표적인 예 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) 에 ActiveX 컨트롤에 대 한 비동기 속성을 제공 합니다. `CDataPathProperty` 개체는 반복 해 서 긴 속성 교환 과정 동안 새 데이터의 가용성을 나타내기 위해 콜백을 가져올 수 있습니다.  
  
 인터넷 응용 프로그램에서 비동기 모니커 및 ActiveX 컨트롤을 사용 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 합니다.  
  
- [인터넷 첫 번째 단계: 비동기 모니커](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
- [인터넷 첫 번째 단계: ActiveX 컨트롤](../../mfc/activex-controls-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 `CAsyncMonikerFile`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxole.h  
  
##  <a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile  
 `CAsyncMonikerFile` 개체를 생성합니다.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>주의  
 생성 하지 않습니다는 `IBindHost` 인터페이스입니다. `IBindHost`제공 하는 경우에 사용 되는 **열려** 멤버 함수입니다.  
  
 에 대 한 설명은 `IBindHost` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="close"></a>CAsyncMonikerFile::Close  
 닫고 모든 리소스를 해제 하려면이 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 열려 있지 않은 또는 이미 닫힌 파일에 대해 호출할 수 있습니다.  
  
##  <a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback  
 구현 하는 COM 개체를 만듭니다. `IBindStatusCallback`합니다.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkControlling`  
 제어 알 수 없음에 대 한 포인터 (외부 **IUnknown**) 또는 **NULL** 집계를 사용 하는 경우.  
  
### <a name="return-value"></a>반환 값  
 경우 `pUnkControlling` 않습니다 **NULL**, 내부 예외에 대 한 포인터를 반환 하는 함수 **IUnknown** 지 원하는 새로운 COM 개체에 `IBindStatusCallback`합니다. 경우 `pUnkControlling` 은 **NULL**, 함수 반환에 대 한 포인터는 **IUnknown** 지 원하는 새로운 COM 개체에 `IBindStatusCallback`합니다.  
  
### <a name="remarks"></a>주의  
 `CAsyncMonikerFile`구현 하는 COM 개체가 필요 `IBindStatusCallback`합니다. MFC는 이러한 개체를 구현 하며 집계할 수 있습니다. 재정의할 수 `CreateBindStatusCallback` 고유한 COM 개체를 반환 합니다. COM 개체를 호출 하 여 MFC 구현을 집계할 수 `CreateBindStatusCallback` 와 COM 개체의 제어 알 수 없음. COM 개체를 사용 하 여 구현 된 `CCmdTarget` COM 지원 제어 알 수 없는 사용 하면 검색 수 **CCmdTarget::GetControllingUnknown**합니다.  
  
 또는 COM 개체를 호출 하 여 MFC의 구현에 위임할 수 **CreateBindStatusCallback (NULL)**합니다.  
  
 [CAsyncMonikerFile::Open](#open) 호출 `CreateBindStatusCallback`합니다.  
  
 비동기 모니커 및 비동기 바인딩에 대 한 자세한 내용은 참조는 [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) 인터페이스 및 [비동기 바인딩 방법 및 저장소 작업](http://msdn.microsoft.com/library/windows/desktop/aa379152)합니다. 집계의 논의 알려면 [집계](http://msdn.microsoft.com/library/windows/desktop/ms686558)합니다. 모든 세 항목이에 포함 되어는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo  
 바인딩할은 원하는 비동기 모니커를 확인 하는 비동기 모니커의 클라이언트에서 호출 됩니다.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 설정을 검색 **IBindStatusCallBack**합니다. 에 대 한 설명은 `IBindStatusCallback` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 바인딩의 비동기 저장 매체 (스트림)를 사용 하 고 데이터 밀어넣기 모델을 사용 하도록 설정 합니다. 바인딩의 동작을 변경 하려는 경우이 함수를 재정의 합니다.  
  
 이 작업을 위한 한 가지 이유 데이터 끌어오기 모델을 사용 하 여 데이터를 밀어 넣기 모델 대신 바인딩할 수 있습니다. 데이터 끌어오기 모델에서는 클라이언트 드라이브 바인딩 작업 하 고 모니커를 읽을 때 클라이언트에 데이터만 제공 합니다. 데이터 푸시 모델에서 모니커 비동기 바인드 드라이브 하 고 지속적으로 새 데이터를 사용할 수 있는 경우 클라이언트에 알립니다.  
  
##  <a name="getbinding"></a>CAsyncMonikerFile::GetBinding  
 바인딩 비동기 전송에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `IBinding` 비동기 전송이 시작 될 때 제공 하는 인터페이스입니다. 반환 **NULL** 어떤 이유로 든 전송을 만들 수 없는 경우 비동기적으로 합니다.  
  
### <a name="remarks"></a>주의  
 데이터 전송 프로세스를 통해 제어를 수 있습니다는 `IBinding` 와 상호 작용할, 예를 들어 **IBinding::Abort**, **IBinding::Pause**, 및 **IBinding::Resume**합니다.  
  
 에 대 한 설명은 `IBinding` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc  
 스트림의 데이터의 형식을 검색 하려면이 함수를 호출 합니다.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows 구조에 대 한 포인터 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 현재 열린된 스트림에 대 한 합니다. 반환 **NULL** 모니커 바인딩되지 않은, 비동기, 없는 경우 또는 비동기 작업이 시작 되지 않은 경우.  
  
##  <a name="getpriority"></a>CAsyncMonikerFile::GetPriority  
 바인딩 프로세스 스레드에 대해 지정 되는 바인딩 작업에 대 한 우선 순위를 수신 하기 시작 비동기 모니커 클라이언트에서 호출 합니다.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>반환 값  
 우선 순위는 비동기 전송 수행 됩니다. 표준 스레드 우선 순위 플래그 중 하나가: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**, **THREAD_PRIORITY_IDLE**, **THREAD_PRIORITY_LOWEST**, **THREAD_PRIORITY_NORMAL**, 및 **THREAD_PRIORITY_TIME_CRITICAL**합니다. Windows 함수를 참조 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) 에 대 한 설명은 다음이 값입니다.  
  
### <a name="remarks"></a>설명  
 `GetPriority`호출할 수 없습니다 직접 합니다. **THREAD_PRIORITY_NORMAL** 기본 구현에 의해 반환 됩니다.  
  
##  <a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable  
 비동기 모니커 호출 `OnDataAvailable` 하기를 사용할 수 있도록 클라이언트에 데이터를 제공, 비동기 동안 바인딩할 작업 합니다.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwSize`  
 바인딩의 시작 된 이후에 사용할 수 있는 데이터의 바이트 단위로 누적 시간입니다. 데이터의 크기를 해당 작업과 관련 있는지 또는 특정 어떠한을 사용할 수 있게 나타내는 0을 수 있습니다.  
  
 *bscfFlag*  
 A **BSCF** 열거형 값입니다. 다음 값 중 하나 이상을 하나일 수 있습니다.  
  
- **BSCF_FIRSTDATANOTIFICATION** 첫 번째 호출 식별 `OnDataAvailable` 지정 된 바인딩 작업에 대 한 합니다.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** 식별에 대 한 중간 호출 `OnDataAvailable` 바인딩 작업에 대 한 합니다.  
  
- **BSCF_LASTDATANOTIFICATION** 를 마지막으로 호출한 식별 `OnDataAvailable` 바인딩 작업에 대 한 합니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 샘플 구현 보려면 다음 예제를 참조 하십시오.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWinInet # 5](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource  
 리소스가 부족 한지 모니커에서 호출 됩니다.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>설명  
 기본 구현 호출 `GetBinding( )-> Abort( )`합니다.  
  
##  <a name="onprogress"></a>CAsyncMonikerFile::OnProgress  
 반복, 일반적으로 시간이 오래 걸리는 작업 하는 동안 적절 한 간격으로이 바인딩 작업의 현재 진행률을 표시 하 여 모니커에서 호출 됩니다.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>매개 변수  
 `ulProgress`  
 에 표시 된 예상된 최대값을 기준으로 바인드 작업의 현재 진행률을 나타내는 `ulProgressMax`합니다.  
  
 `ulProgressMax`  
 변수의 예상된 최대값을 나타냅니다 `ulProgress` 기간에 대 한 호출에 대 한 `OnProgress` 이 작업에 대 한 합니다.  
  
 `ulStatusCode`  
 바인딩 작업의 진행률에 대 한 추가 정보를 제공합니다. 유효한 값을 가져옵니다는 `BINDSTATUS` 열거형입니다. 가능한 값에 대 한 설명을 참조 하세요.  
  
 `szStatusText`  
 값에 따라 현재 진행 상태에 대 한 내용은 `ulStatusCode`합니다. 가능한 값에 대 한 설명을 참조 하세요.  
  
### <a name="remarks"></a>설명  
 에 가능한 값 `ulStatusCode` (및 `szStatusText` 각 값에 대 한) 됩니다.  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 바인딩 작업에서 개체 또는에 바인딩되는 저장소를 포함 하는 리소스를 찾고 있습니다. `szStatusText` 검색이 수행 되는 리소스의 표시 이름을 제공 (예: "www.microsoft.com")에 대 한 합니다.  
  
 **BINDSTATUS_CONNECTING**  
 바인딩 작업에 바인딩되는 저장소 또는 개체를 보유 하는 리소스를 연결 합니다. `szStatusText` (예: IP 주소)에 연결 하는 리소스의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_SENDINGREQUEST**  
 바인딩 작업은 개체 또는에 바인딩되는 저장 요청입니다. `szStatusText` 개체 (예를 들어 파일 이름)의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_REDIRECTING**  
 바인딩 작업을 다른 데이터 위치로 리디렉션 되었습니다. `szStatusText` 새 데이터 위치로의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 바인딩 작업이 캐시 된 복사본에서 요청 된 개체 또는 저장소를 검색 합니다. The `szStatusText` is **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 개체 또는 저장소에 연결 되 고 수신 바인딩 작업을 시작 했습니다. `szStatusText` 데이터 위치의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 개체 또는에 바인딩되는 저장소를 수신할 바인드 작업이 계속 됩니다. `szStatusText` 데이터 위치의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 개체 또는 저장소에 연결 되 고 수신 바인딩 작업을 완료 했습니다. `szStatusText` 데이터 위치의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 에 바인딩되는 개체의 인스턴스를 만들 수에 대 한 됩니다. `szStatusText` 원하는 경우에서 클라이언트 바인딩 작업을 취소할 수 있도록 하는 문자열 형식으로 새 개체의 CLSID를 제공 합니다.  
  
##  <a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding  
 바인딩 시작 될 때 작업을 수행 하 여 파생된 클래스에서이 함수를 재정의 합니다.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>설명  
 이 함수는 모니커가 다시 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding  
 모니커 바인딩 작업의 끝에 의해 호출 됩니다.  
  
```  
virtual void OnStopBinding(HRESULT hresult, LPCTSTR szError);
```  
  
### <a name="parameters"></a>매개 변수  
 `hresult`  
 `HRESULT` 오류 또는 경고 값입니다.  
  
 *szErrort*  
 오류를 설명 하는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 전송이 중지 될 때 동작을 수행 하려면이 함수를 재정의 합니다. 기본적으로 함수 해제 `IBinding`합니다.  
  
 에 대 한 설명은 `IBinding` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="open"></a>CAsyncMonikerFile::Open  
 이 파일을 비동기적으로 함수를 호출 합니다.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IBindHost* pBindHost,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IServiceProvider* pServiceProvider,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    LPCTSTR lpszURL,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
 
virtual BOOL Open(
    IMoniker* pMoniker,
    IUnknown* pUnknown,
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszURL`  
 비동기적으로 열 파일에 대 한 포인터입니다. 가능한 URL 또는 파일 이름에는 파일 수 있습니다.  
  
 `pError`  
 파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.  
  
 `pMoniker`  
 비동기 모니커 인터페이스에 대 한 포인터 `IMoniker`,으로 검색할 수 있는 문서의 모니커를 조합한 결과인 정확한 모니커 **IOleClientSite::GetMoniker (** *OLEWHICHMK_CONTAINER* **)**, 및 경로 이름에서 생성 하는 모니커입니다. 컨트롤을 바인딩하려면이 모니커를 사용할 수 있지만 이것이 컨트롤을 저장 해야 모니커 아닙니다.  
  
 *pBindHost*  
 에 대 한 포인터는 `IBindHost` 잠재적으로 상대 경로 이름에서 모니커를 만드는 데 사용할 수는 인터페이스입니다. 바인딩 호스트 유효 하지 않거나 모니커를 제공 하지 않습니다, 호출의 기본값은 **열기 (** `lpszFileName` **,**`pError`**)**합니다. 에 대 한 설명은 `IBindHost` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `pServiceProvider`  
 에 대 한 포인터는 `IServiceProvider` 인터페이스입니다. 서비스 공급자가 잘못 되었거나 서비스를 제공 하지 못하면 경우 `IBindHost`, 기본적으로 호출 **열기 (** `lpszFileName` **,**`pError`**)**합니다.  
  
 *pUnknown*  
 에 대 한 포인터는 **IUnknown** 인터페이스입니다. 경우 `IServiceProvider` 발견 되 면에 대 한 함수 쿼리 `IBindHost`합니다. 서비스 공급자가 잘못 되었거나 서비스를 제공 하지 못하면 경우 `IBindHost`, 기본적으로 호출 **열기 (** `lpszFileName` **,**`pError`**)**합니다.  
  
### <a name="return-value"></a>반환 값  
 파일을 성공적으로 열 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 호출 하는 바인딩 프로세스를 시작합니다.  
  
 URL 또는 파일 이름을 사용할 수 있습니다는 `lpszURL` 매개 변수입니다. 예:  
  
 [!code-cpp[NVC_MFCWinInet # 6](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 - 또는  
  
 [!code-cpp[NVC_MFCWinInet # 7](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CMonikerFile 클래스](../../mfc/reference/cmonikerfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMonikerFile 클래스](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)

