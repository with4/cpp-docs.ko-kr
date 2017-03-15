---
title: "CAsyncMonikerFile 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAsyncMonikerFile
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: eb8727e6fe884c98fe010beab072fb7268f2e2c4
ms.lasthandoff: 02/24/2017

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
|[CAsyncMonikerFile::CreateBindStatusCallback](#createbindstatuscallback)|구현 하는 COM 개체를 만듭니다 `IBindStatusCallback`합니다.|  
|[CAsyncMonikerFile::GetBindInfo](#getbindinfo)|만들려는 바인딩 종류에 대 한 요청 정보를 OLE 시스템 라이브러리에서 호출 됩니다.|  
|[CAsyncMonikerFile::GetPriority](#getpriority)|바인딩에의 우선 순위를 가져오려는 OLE 시스템 라이브러리에서 호출 됩니다.|  
|[CAsyncMonikerFile::OnDataAvailable](#ondataavailable)|클라이언트에 사용할 수 있도록 비동기 바인딩 작업 중에 데이터를 제공 하기 위해 호출 합니다.|  
|[CAsyncMonikerFile::OnLowResource](#onlowresource)|리소스가 부족 한 때 호출 됩니다.|  
|[CAsyncMonikerFile::OnProgress](#onprogress)|데이터 다운로드 프로세스의 진행률을 나타내기 위해 호출 됩니다.|  
|[CAsyncMonikerFile::OnStartBinding](#onstartbinding)|시작 하는 바인딩 때 호출 됩니다.|  
|[CAsyncMonikerFile::OnStopBinding](#onstopbinding)|비동기 전송이 중지 될 때 호출 됩니다.|  
  
## <a name="remarks"></a>주의  
 파생 된 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md), 차례로에서 파생 된 [COleStreamFile](../../mfc/reference/colestreamfile-class.md), `CAsyncMonikerFile` 사용 하는 [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) URL에서 파일을 비동기적으로 로드를 포함 하 여 데이터 스트림을 비동기적으로 액세스 하려면 인터페이스입니다. 파일에는 ActiveX 컨트롤의 데이터 경로 속성 일 수 있습니다.  
  
 비동기 모니커는 주로 인터넷 사용 응용 프로그램과 ActiveX 컨트롤에서 파일을 전송 하는 동안 응답성이 뛰어난 사용자 인터페이스를 제공 하는 데 사용 됩니다. 사용 하는 것이 가장 대표적인 예 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md) 에 ActiveX 컨트롤에 대 한 비동기 속성을 제공 합니다. `CDataPathProperty` 개체 반복적으로 시간이 많이 걸리는 속성 교환 프로세스 동안 새 데이터의 가용성을 나타내기 위해 콜백을 받습니다.  
  
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
  
##  <a name="a-namecasyncmonikerfilea--casyncmonikerfilecasyncmonikerfile"></a><a name="casyncmonikerfile"></a>CAsyncMonikerFile::CAsyncMonikerFile  
 `CAsyncMonikerFile` 개체를 생성합니다.  
  
```  
CAsyncMonikerFile();
```  
  
### <a name="remarks"></a>주의  
 문제가 발생 하지 않는 `IBindHost` 인터페이스입니다. `IBindHost`제공 하는 경우에 사용 되는 **열려** 멤버 함수입니다.  
  
 에 대 한 설명은 `IBindHost` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameclosea--casyncmonikerfileclose"></a><a name="close"></a>CAsyncMonikerFile::Close  
 닫고 모든 리소스를 해제 하려면이 함수를 호출 합니다.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>주의  
 열려 있지 않은 형식 또는 폐쇄형 이미 파일에서 호출할 수 있습니다.  
  
##  <a name="a-namecreatebindstatuscallbacka--casyncmonikerfilecreatebindstatuscallback"></a><a name="createbindstatuscallback"></a>CAsyncMonikerFile::CreateBindStatusCallback  
 구현 하는 COM 개체를 만듭니다 `IBindStatusCallback`합니다.  
  
```  
virtual IUnknown* CreateBindStatusCallback(IUnknown* pUnkControlling);
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkControlling`  
 제어 알 수 없음에 대 한 포인터 (외부 **IUnknown**) 또는 **NULL** 집계 사용 하지 않는 경우.  
  
### <a name="return-value"></a>반환 값  
 경우 `pUnkControlling` 없는 **NULL**, 내부 예외에 대 한 포인터를 반환 하는 함수 **IUnknown** 지 원하는 새로운 COM 개체에 `IBindStatusCallback`합니다. 경우 `pUnkControlling` 는 **NULL**, 함수 반환에 대 한 포인터는 **IUnknown** 지 원하는 새로운 COM 개체에 `IBindStatusCallback`합니다.  
  
### <a name="remarks"></a>주의  
 `CAsyncMonikerFile`구현 하는 COM 개체가 필요 `IBindStatusCallback`합니다. MFC는 이러한 개체를 구현 되며 집계할 수 있습니다. 재정의할 수 `CreateBindStatusCallback` 고유한 COM 개체를 반환 합니다. COM 개체를 호출 하 여 MFC의 구현을 집계할 수 `CreateBindStatusCallback` COM 개체의 제어 unknown입니다. 사용 하 여 구현 된 COM 개체는 `CCmdTarget` COM 지원을 제어 알 수 없는 사용 하면 검색 수 **CCmdTarget::GetControllingUnknown**합니다.  
  
 호출 하 여 COM 개체 MFC의 구현에 위임 하는 반면 **CreateBindStatusCallback (NULL)**합니다.  
  
 [CAsyncMonikerFile::Open](#open) 호출 `CreateBindStatusCallback`합니다.  
  
 비동기 모니커 및 비동기 바인딩에 대 한 자세한 내용은 참조는 [IBindStatusCallback](http://msdn.microsoft.com/library/ie/ms775060) 인터페이스 및 [비동기 바인딩 방법 및 저장소 작업](http://msdn.microsoft.com/library/windows/desktop/aa379152)합니다. 집계의 논의 참조 하십시오. [집계](http://msdn.microsoft.com/library/windows/desktop/ms686558)합니다. 모든 세 개 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetbindinfoa--casyncmonikerfilegetbindinfo"></a><a name="getbindinfo"></a>CAsyncMonikerFile::GetBindInfo  
 바인딩할 원하는 비동기 모니커를 구별 하는 비동기 모니커의 클라이언트에서 호출 됩니다.  
  
```  
virtual DWORD GetBindInfo() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 설정을 검색 **IBindStatusCallBack**합니다. 에 대 한 설명은 `IBindStatusCallback` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 비동기적 저장 매체 (스트림)를 사용 하 고 데이터 밀어넣기 모델을 사용 하도록 바인딩을 설정 합니다. 바인딩 동작을 변경 하려는 경우이 함수를 재정의 합니다.  
  
 이 작업을 수행 하는 한 가지 이유는 데이터 밀어넣기 모델 대신 데이터 끌어오기 모델을 사용 하 여 바인딩할 것입니다. 데이터 끌어오기 모델에서 클라이언트 바인딩 작업을 구동 하 고 모니커를 읽을 때 클라이언트에 데이터만 제공 합니다. 데이터 밀어넣기 모델에서는 모니커 비동기 바인딩 작업을 구동 하 고 지속적으로 새 데이터를 사용할 때마다 클라이언트에 알립니다.  
  
##  <a name="a-namegetbindinga--casyncmonikerfilegetbinding"></a><a name="getbinding"></a>CAsyncMonikerFile::GetBinding  
 바인딩 비동기 전송에 대 한 포인터를 검색 하려면이 함수를 호출 합니다.  
  
```  
IBinding* GetBinding() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `IBinding` 비동기 전송이 시작 될 때 제공 하는 인터페이스입니다. 반환 **NULL** 어떤 이유로 든 전송을 만들 수 없는 경우 비동기적으로 합니다.  
  
### <a name="remarks"></a>주의  
 이렇게 하면 데이터 전송 프로세스를 통해 제어는 `IBinding` 상호 작용, 예를 들어, **IBinding::Abort**, **IBinding::Pause**, 및 **IBinding::Resume**합니다.  
  
 에 대 한 설명은 `IBinding` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namegetformatetca--casyncmonikerfilegetformatetc"></a><a name="getformatetc"></a>CAsyncMonikerFile::GetFormatEtc  
 스트림의 데이터의 형식을 검색 하려면이 함수를 호출 합니다.  
  
```  
FORMATETC* GetFormatEtc() const;  
```  
  
### <a name="return-value"></a>반환 값  
 Windows 구조에 대 한 포인터 [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 현재 열려 있는 스트림에 대 한 합니다. 반환 **NULL** 모니커 바인딩되지 않은, 비동기, 없는 경우 또는 비동기 작업이 시작 되지 않은 경우.  
  
##  <a name="a-namegetprioritya--casyncmonikerfilegetpriority"></a><a name="getpriority"></a>CAsyncMonikerFile::GetPriority  
 바인딩 프로세스 스레드에 대해 지정 되는 바인딩 작업에 대 한 우선 순위를 수신 하기 시작 된 비동기 모니커의 클라이언트에서 호출 합니다.  
  
```  
virtual LONG GetPriority() const;  
```  
  
### <a name="return-value"></a>반환 값  
 우선 순위는 비동기 전송 수행 됩니다. 표준 스레드 우선 순위 플래그 중 하나: **THREAD_PRIORITY_ABOVE_NORMAL**, **THREAD_PRIORITY_BELOW_NORMAL**, **THREAD_PRIORITY_HIGHEST**, **THREAD_PRIORITY_IDLE**, **THREAD_PRIORITY_LOWEST**, **THREAD_PRIORITY_NORMAL**, 및 **THREAD_PRIORITY_TIME_CRITICAL**합니다. Windows 함수를 참조 하십시오. [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) 에 대 한 설명은 다음이 값입니다.  
  
### <a name="remarks"></a>주의  
 `GetPriority`직접 호출 합니다. **THREAD_PRIORITY_NORMAL** 기본 구현에 의해 반환 됩니다.  
  
##  <a name="a-nameondataavailablea--casyncmonikerfileondataavailable"></a><a name="ondataavailable"></a>CAsyncMonikerFile::OnDataAvailable  
 호출 하는 비동기 모니커 `OnDataAvailable` 를 제공 하려면 데이터를 클라이언트를 사용할 수 있도록 하는 동안 비동기 바인딩 작업 합니다.  
  
```  
virtual void OnDataAvailable(DWORD dwSize, DWORD bscfFlag);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwSize`  
 바인딩의 시작 된 이후에 사용할 수 있는 데이터의 바이트 단위로 누적 시간입니다. 데이터의 양이 해당 작업과 관련 없는 또는 특정 양이 없는 출시를 나타내는&0;을 수 있습니다.  
  
 *bscfFlag*  
 A **BSCF** 열거형 값입니다. 다음 값 중 하나 이상이 될 수 있습니다.  
  
- **BSCF_FIRSTDATANOTIFICATION** 첫 번째 호출 식별 `OnDataAvailable` 주어진된 바인딩 작업에 대 한 합니다.  
  
- **BSCF_INTERMEDIATEDATANOTIFICATION** 식별에 대 한 중간 호출 `OnDataAvailable` 바인딩 작업에 대 한 합니다.  
  
- **BSCF_LASTDATANOTIFICATION** 를 마지막으로 호출한 식별 `OnDataAvailable` 바인딩 작업에 대 한 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 샘플 구현 보려면 다음 예제를 참조 하십시오.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWinInet #&5;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_1.cpp)]  
  
##  <a name="a-nameonlowresourcea--casyncmonikerfileonlowresource"></a><a name="onlowresource"></a>CAsyncMonikerFile::OnLowResource  
 리소스 부족 한 경우 모니커에 의해 호출 됩니다.  
  
```  
virtual void OnLowResource();
```  
  
### <a name="remarks"></a>주의  
 기본 구현 호출 하 여 `GetBinding( )-> Abort( )`합니다.  
  
##  <a name="a-nameonprogressa--casyncmonikerfileonprogress"></a><a name="onprogress"></a>CAsyncMonikerFile::OnProgress  
 긴 작업 동안 적절 한 시기에 일반적으로이 바인딩 작업의 현재 진행률을 표시 하는 반복 해 서 모니커에 의해 호출 됩니다.  
  
```  
virtual void OnProgress(
    ULONG ulProgress,  
    ULONG ulProgressMax,  
    ULONG ulStatusCode,  
    LPCTSTR szStatusText);
```  
  
### <a name="parameters"></a>매개 변수  
 `ulProgress`  
 에 표시 된 예상된 최대값을 기준으로 바인딩 작업의 현재 진행률을 나타내는 `ulProgressMax`합니다.  
  
 `ulProgressMax`  
 예상된 최대값을 나타냅니다 `ulProgress` 에 대 한 호출 기간 동안 `OnProgress` 이 작업에 대 한 합니다.  
  
 `ulStatusCode`  
 바인딩 작업의 진행률에 대 한 추가 정보를 제공합니다. 유효한 값은에서 가져온는 `BINDSTATUS` 열거형입니다. 가능한 값에 대 한 설명을 참조 하십시오.  
  
 `szStatusText`  
 값에 따라 현재 진행 상태에 대 한 내용은 `ulStatusCode`합니다. 가능한 값에 대 한 설명을 참조 하십시오.  
  
### <a name="remarks"></a>주의  
 가능한 값 `ulStatusCode` (및 `szStatusText` 각 값에 대해) 됩니다.  
  
 **BINDSTATUS_FINDINGRESOURCE**  
 바인딩 작업에서 개체 또는에 바인딩되는 저장소를 보유 하는 리소스를 찾고 있습니다. `szStatusText` 검색이 수행 되는 리소스의 표시 이름을 제공 (예: "www.microsoft.com")에 대 한 합니다.  
  
 **BINDSTATUS_CONNECTING**  
 바인드에 바인딩되는 저장소 또는 개체를 보유 하는 리소스에 연결 합니다. `szStatusText` (예: IP 주소)에 연결 되는 리소스의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_SENDINGREQUEST**  
 개체 또는 저장소에 바인딩되는 바인딩 작업을 요청 합니다. `szStatusText` 개체 (예를 들어, 파일 이름)의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_REDIRECTING**  
 바인딩 작업을 다른 데이터 위치로 리디렉션 되었습니다. `szStatusText` 새 데이터 위치로의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_USINGCACHEDCOPY**  
 바인드가 캐시 된 복사본에서 요청 된 개체 또는 저장소를 검색 합니다. The `szStatusText` is **NULL**.  
  
 **BINDSTATUS_BEGINDOWNLOADDATA**  
 바인드에 바인딩되는 저장소 개체를 받는 시작 했습니다. `szStatusText` 데이터 위치의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_DOWNLOADINGDATA**  
 또는를 받을 때 개체에 바인딩되는 저장소 바인딩 작업이 계속 됩니다. `szStatusText` 데이터 위치의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_ENDDOWNLOADDATA**  
 바인드를 완전히 받지 개체 또는에 바인딩되는 저장소. `szStatusText` 데이터 위치의 표시 이름을 제공 합니다.  
  
 **BINDSTATUS_CLASSIDAVAILABLE**  
 에 바인딩되는 개체의 인스턴스를 방금 만들어야 합니다. `szStatusText` 필요한 경우 클라이언트가 바인딩 작업을 취소할 수 있도록 하는 문자열 형식으로 새 개체의 CLSID를 제공 합니다.  
  
##  <a name="a-nameonstartbindinga--casyncmonikerfileonstartbinding"></a><a name="onstartbinding"></a>CAsyncMonikerFile::OnStartBinding  
 바인딩을 시작 하는 경우 작업을 수행 하 여 파생된 클래스에서이 함수를 재정의 합니다.  
  
```  
virtual void OnStartBinding();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 모니커가 다시 호출 됩니다. 기본 구현은 아무 작업도 수행하지 않습니다.  
  
##  <a name="a-nameonstopbindinga--casyncmonikerfileonstopbinding"></a><a name="onstopbinding"></a>CAsyncMonikerFile::OnStopBinding  
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
 전송이 중지 될 때 작업을 수행 하려면이 함수를 재정의 합니다. 기본적으로 함수를 해제 `IBinding`합니다.  
  
 에 대 한 설명은 `IBinding` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameopena--casyncmonikerfileopen"></a><a name="open"></a>CAsyncMonikerFile::Open  
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
 비동기적으로 열 파일에 대 한 포인터입니다. 유효한 URL 또는 파일 이름 파일 수 있습니다.  
  
 `pError`  
 파일 예외에 대 한 포인터입니다. 오류가 발생 한 원인에 설정 됩니다.  
  
 `pMoniker`  
 비동기 모니커 인터페이스에 대 한 포인터 `IMoniker`, 정확 하 게 되는 모니커를 조합해 서으로 검색할 수 있는 문서의 모니커를 **IOleClientSite::GetMoniker (** *OLEWHICHMK_CONTAINER* **)**, 및 경로 이름에서 생성 하는 모니커입니다. 컨트롤을 바인딩하려면이 모니커를 사용할 수 있지만이 모니커 컨트롤을 저장 해야 합니다.  
  
 *pBindHost*  
 에 대 한 포인터는 `IBindHost` 잠재적으로 상대 경로 이름을에서 모니커를 만드는 데 사용할는 인터페이스입니다. 바인딩 호스트 유효 하지 않거나 모니커를 제공 하지 않습니다, 호출 기본값으로 **열기 (** `lpszFileName` **,**`pError`**)**합니다. 에 대 한 설명은 `IBindHost` 인터페이스를 참조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `pServiceProvider`  
 에 대 한 포인터는 `IServiceProvider` 인터페이스입니다. 서비스 공급자가 잘못 되었거나 서비스를 제공 하기에 실패 하는 경우 `IBindHost`, 호출 기본값으로 **열기 (** `lpszFileName` **,**`pError`**)**합니다.  
  
 *pUnknown*  
 에 대 한 포인터는 **IUnknown** 인터페이스입니다. 경우 `IServiceProvider` 발견 되 면에 대 한 함수 쿼리 `IBindHost`합니다. 서비스 공급자가 잘못 되었거나 서비스를 제공 하기에 실패 하는 경우 `IBindHost`, 호출 기본값으로 **열기 (** `lpszFileName` **,**`pError`**)**합니다.  
  
### <a name="return-value"></a>반환 값  
 파일을 성공적으로 열 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 호출 하는 바인딩 프로세스를 시작 합니다.  
  
 URL 또는 파일 이름을 사용할 수는 `lpszURL` 매개 변수입니다. 예:  
  
 [!code-cpp[NVC_MFCWinInet #&6;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_2.cpp)]  
  
 -또는-  
  
 [!code-cpp[NVC_MFCWinInet #&7;](../../mfc/codesnippet/cpp/casyncmonikerfile-class_3.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [CMonikerFile 클래스](../../mfc/reference/cmonikerfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMonikerFile 클래스](../../mfc/reference/cmonikerfile-class.md)   
 [CDataPathProperty 클래스](../../mfc/reference/cdatapathproperty-class.md)

