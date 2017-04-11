---
title: "디버깅 및 오류 보고 함수를 전역 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 6c328c82c5e2ef5ff6f413d4eb3f1b62e2b693d8
ms.lasthandoff: 03/31/2017

---
# <a name="debugging-and-error-reporting-global-functions"></a>디버깅 및 오류 보고 함수를 전역
이러한 함수는 유용한 디버깅 및 추적 기능을 제공 합니다.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)|반환 된 `GetLastError` HRESULT 값의 형태로 오류 코드입니다.|  
|[AtlHresultFromWin32](debugging-and-error-reporting-global-functions.md#atlhresultfromwin32)|Win32 오류 코드 HRESULT로 변환합니다.|  
|[AtlReportError](debugging-and-error-reporting-global-functions.md#atlreporterror)|설정 **IErrorInfo** 클라이언트에 오류 세부 정보를 제공 합니다.|  
|[Atlthrow 변형이](debugging-and-error-reporting-global-functions.md#atlthrow)|`CAtlException`를 throw합니다.|  
|[AtlThrowLastWin32](debugging-and-error-reporting-global-functions.md#atlthrowlastwin32)|Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.|  
  
##  <a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 호출 스레드의 마지막 오류 코드 값을 HRESULT 형식으로 반환합니다.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>주의  
 `AtlHresultFromLastError`호출 `GetLastError` 마지막 오류 얻으려고 사용 하는 HRESULT를 변환한 후 오류를 반환 하 고는 **HRESULT_FROM_WIN32** 매크로입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlcomcli.h  

##  <a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
 Win32 오류 코드 HRESULT로 변환합니다.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>매개 변수  
 *오류*  
 변환할 오류 값입니다.  
  
### <a name="remarks"></a>주의  
 Win32 오류 코드는 매크로 사용 하 여 HRESULT로 변환 **HRESULT_FROM_WIN32**합니다.  
  
> [!NOTE]
>  사용 하는 대신 **HRESULT_FROM_WIN32(GetLastError())**, 함수를 사용 하 여 [AtlHresultFromLastError](debugging-and-error-reporting-global-functions.md#atlhresultfromlasterror)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlcomcli.h  

##  <a name="atlreporterror"></a>AtlReportError  
 설정 된 `IErrorInfo` 인터페이스 개체의 클라이언트에 오류 정보를 제공 합니다.  
  
```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] 이 오류를 보고 하는 개체의 CLSID입니다.  
  
 `lpszDesc`  
 [in] 오류를 설명 하는 문자열입니다. 유니코드 버전을 지정 하는 `lpszDesc` 유형의 **LPCOLESTR**; ANSI 버전 형식을 지정 합니다. `LPCSTR`합니다.  
  
 `iid`  
 [in] 이 오류를 정의 하는 인터페이스의 IID 또는 `GUID_NULL` 오류는 운영 체제에 의해 정의 된 경우.  
  
 `hRes`  
 [in] `HRESULT` 원하는, 호출자에 게 반환 합니다.  
  
 `nID`  
 [in] 오류 설명 문자열 저장 된 리소스 식별자입니다. 이 값 0x0200에서 0xFFFF 사이 포괄적 포함 해야 합니다. 디버그 빌드에서 **ASSERT** 경우 발생 `nID` 는 유효한 문자열을 인덱싱하지 않습니다. 릴리스 빌드에서 오류 설명 문자열 "알 수 없는 오류입니다."로 설정 됩니다.  
  
 `dwHelpID`  
 [in] 오류에 대 한 도움말 컨텍스트 식별자입니다.  
  
 `lpszHelpFile`  
 [in] 경로 오류를 설명 하는 도움말 파일의 이름입니다.  
  
 `hInst`  
 [in] 리소스에 대 한 핸들입니다. 이 매개 변수는 기본적으로 **__AtlBaseModuleModule::GetResourceInstance**여기서 **__AtlBaseModuleModule** 의 인스턴스인 전역 [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) 여기에서 파생 된 클래스 또는 합니다.  
  
### <a name="return-value"></a>반환 값  
 경우는 `hRes` 매개 변수는 0이 아니고의 값을 반환 `hRes`합니다. 경우 `hRes` 가 0 인 처음 4 개 버전의 `AtlReportError` 반환 `DISP_E_EXCEPTION`합니다. 매크로의 결과 반환 하는 마지막 두 버전 **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**합니다.  
  
### <a name="remarks"></a>설명  
 문자열 *lpszDesc* 의 오류 텍스트 설명으로 사용 됩니다. 받으면 클라이언트는 `hRes` 에서 반환할 `AtlReportError`, 클라이언트에 액세스할 수는 **IErrorInfo** 오류에 대 한 세부 정보에 대 한 구조입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM #52](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  사용 하지 마십시오 `AtlReportError` c + +에서 catch 처리기입니다. 이러한 함수의 일부 재정의 ATL 문자열 변환 매크로 내부적으로 사용, 어느 옵션을 다시 사용 된 `_alloca` 내부적으로 작동 합니다. 사용 하 여 `AtlReportError` c + + catch 처리기 c + + catch 처리기에서 예외를 일으킬 수 있습니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
    
##  <a name="atlthrow"></a>Atlthrow 변형이  
 `HRESULT` 상태 코드에 따라 오류를 표시하려면 이 함수를 호출합니다.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>매개 변수  
 `hr`  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 오류 조건이 발생 한 경우 ATL 및 MFC 코드에서 사용 됩니다. 사용자 고유의 코드에서 호출할 수도 있습니다. 이 함수의 기본 구현은 기호 정의에 따라 달라 집니다 **_ATL_NO_EXCEPTIONS** 와 MFC 또는 ATL. 프로젝트의 종류  
  
 모든 경우에이 함수는 HRESULT의 디버거를 추적합니다.  
  
 Visual Studio 2015 업데이트 3 이상 버전에서는이 함수는 잘못 된 SAL 경고가 표시 되지 않도록 하는 __declspec (noreturn 특성 사용된).  
  
 경우 **_ATL_NO_EXCEPTIONS** 정의 되어 있지 않습니다는 MFC 프로젝트에서이 함수를 throw 하는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md) HRESULT의 값에 따라 합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 함수 throw ATL 프로젝트에 정의 되지 않은 한 [CAtlException](../../atl/reference/catlexception-class.md)합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 은 정의 된 함수는 예외를 throw 하는 대신 어설션 실패를 발생 합니다.  
  
 ATL 프로젝트에 ATL 오류가 발생할 경우 사용할이 함수의 사용자 지정 구현을 제공 하는 것이 같습니다. 이 작업을 수행 하려면으로 동일한 서명 사용 하 여 사용자 고유의 함수를 정의 `AtlThrow` 및 #define `AtlThrow` 함수의 이름 이어야 합니다. 이 atlexcept.h (즉, 수행 atlbase.h atlexcept.h 포함 되므로 ATL 헤더를 포함 하기 전에 해야 함을)를 포함 하기 전에 수행 되어야 합니다. 함수 특성 `__declspec(noreturn)` 에 잘못 된 SAL 경고가 표시 되지 않도록 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing # 95](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldef.h  

##  <a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>설명  
 이 함수는 결과 추적 `GetLastError` 디버거에 합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 정의 되어 있지 않습니다는 MFC 프로젝트에서이 함수를 throw 하는 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md) 에서 반환 된 값에 따라 `GetLastError`합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 함수 throw ATL 프로젝트에 정의 되지 않은 한 [CAtlException](../../atl/reference/catlexception-class.md)합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 은 정의 된 함수는 예외를 throw 하는 대신 어설션 실패를 발생 합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldef.h  
   
     
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)   
 [디버깅 및 오류 보고 매크로](../../atl/reference/debugging-and-error-reporting-macros.md)










