---
title: "디버깅 및 오류 보고 함수를 전역 | Microsoft 문서"
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4a412910d13d10606080c14412d33d2b614fdcec
ms.lasthandoff: 02/24/2017

---
# <a name="debugging-and-error-reporting-global-functions"></a>디버깅 및 오류 보고 함수를 전역
이러한 함수는 유용한 디버깅 및 추적 기능을 제공 합니다.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66)|반환 된 `GetLastError` 형태의 HRESULT 오류 코드입니다.|  
|[AtlHresultFromWin32](http://msdn.microsoft.com/library/63add2dd-274c-4e72-a98c-040b93413a2f)|Win32 오류 코드 HRESULT로 변환합니다.|  
|[AtlReportError](http://msdn.microsoft.com/library/86b046a5-ea18-4ecf-9aab-40fc1eab847c)|설정 **IErrorInfo** 클라이언트에 오류 세부 정보를 제공 합니다.|  
|[AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)|`CAtlException`를 throw합니다.|  
|[AtlThrowLastWin32](http://msdn.microsoft.com/library/8bce8e56-c7cd-4ebb-8c62-80ebc63a3d07)|Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.|  
  
##  <a name="a-nameatlhresultfromlasterrora--atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 호출 스레드의 마지막 오류 코드 값을 HRESULT 형식으로 반환합니다.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>주의  
 `AtlHresultFromLastError`호출 `GetLastError` 를 마지막으로 오류를 가져오는 사용 하는 HRESULT를 변환한 후 오류를 반환 하 고는 **HRESULT_FROM_WIN32** 매크로입니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlcomcli.h  

##  <a name="a-nameatlhresultfromwin32a--atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
 Win32 오류 코드 HRESULT로 변환합니다.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>매개 변수  
 *오류*  
 변환할 오류 값입니다.  
  
### <a name="remarks"></a>주의  
 Win32 오류 코드 매크로 사용 하 여 HRESULT로 변환 **HRESULT_FROM_WIN32**합니다.  
  
> [!NOTE]
>  사용 하는 대신 **HRESULT_FROM_WIN32(GetLastError())**, 함수를 사용 하 여 [AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66)합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlcomcli.h  

##  <a name="a-nameatlreporterrora--atlreporterror"></a><a name="atlreporterror"></a>AtlReportError  
 설정 하는 `IErrorInfo` 인터페이스 개체의 클라이언트에 오류 정보를 제공할 수 있습니다.  
  
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
 [in] 오류를 설명 하는 문자열입니다. 유니코드 버전을 지정 하는 `lpszDesc` 형식의 **LPCOLESTR**; ANSI 버전의 형식을 지정 `LPCSTR`합니다.  
  
 `iid`  
 [in] 이 오류를 정의 하는 인터페이스의 IID 또는 `GUID_NULL` 오류는 운영 체제에 의해 정의 된 경우.  
  
 `hRes`  
 [in] `HRESULT` 원하는, 호출자에 게 반환 합니다.  
  
 `nID`  
 [in] 오류 설명 문자열 저장 된 리소스 식별자입니다. 이 값 까지의 0x0200 사이의 0xFFFF 내 해야 합니다. 디버그 빌드에서 **ASSERT** 경우 발생 합니다 `nID` 는 유효한 문자열 인덱싱되지 않습니다. 릴리스 빌드에서 오류 설명 문자열 "알 수 없는 오류가 발생 했습니다."로 설정 됩니다.  
  
 `dwHelpID`  
 [in] 오류에 대 한 도움말 컨텍스트 식별자입니다.  
  
 `lpszHelpFile`  
 [in] 경로 오류를 설명 하는 도움말 파일의 이름입니다.  
  
 `hInst`  
 [in] 리소스에 대 한 핸들입니다. 이 매개 변수는 기본적으로 **__AtlBaseModuleModule::GetResourceInstance**여기서 **__AtlBaseModuleModule** 의 인스턴스인 전역 [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) 에서 파생 된 클래스 또는 합니다.  
  
### <a name="return-value"></a>반환 값  
 하는 경우는 `hRes` 매개 변수는&0;이 아니고의 값을 반환 `hRes`합니다. 경우 `hRes` 가&0;이 아니면 처음&4; 개 버전의 `AtlReportError` 반환 `DISP_E_EXCEPTION`합니다. 매크로의 결과 반환 하는 마지막 두 버전 **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**합니다.  
  
### <a name="remarks"></a>주의  
 문자열 *lpszDesc* 오류에 대 한 텍스트 설명으로 사용 됩니다. 받으면 클라이언트는 `hRes` 에서 반환할 `AtlReportError`, 클라이언트에 액세스할 수는 **IErrorInfo** 오류에 대 한 세부 정보에 대 한 구조입니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#52;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  사용 하지 않는 `AtlReportError` c + +에서 catch 처리기입니다. 이러한 함수의 재정의 중 일부는 ATL 문자열 변환 매크로 내부적으로 사용, 다시 사용 하 여 `_alloca` 내부적으로 작동 합니다. 사용 하 여 `AtlReportError` c + + catch 처리기 c + + catch 처리기에서 예외를 일으킬 수 있습니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
    
##  <a name="a-nameatlthrowa--atlthrow"></a><a name="atlthrow"></a>AtlThrow  
 `HRESULT` 상태 코드에 따라 오류를 표시하려면 이 함수를 호출합니다.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>매개 변수  
 `hr`  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 오류 조건이 발생할 경우 ATL 및 MFC 코드에서 사용 됩니다. 사용자 고유의 코드에서 호출할 수도 있습니다. 이 함수의 기본 구현은 기호 정의에 따라 달라 집니다 **_ATL_NO_EXCEPTIONS** 와 MFC 또는 ATL. 프로젝트의 종류  
  
 모든 경우에이 함수는 디버거에 HRESULT를 추적합니다.  
  
 Visual Studio 2015 업데이트 3 이상 버전에서는이 함수는 가짜 SAL 경고를 방지 하려면 특성 사용된 __declspec (noreturn).  
  
 경우 **_ATL_NO_EXCEPTIONS** 정의 되지 않은 MFC 프로젝트에서는이 함수는 다음과 같이 throw 됩니다. 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md) HRESULT의 값을 기반으로 합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 함수 throw ATL 프로젝트에 정의 되지 않은 한 [CAtlException](../../atl/reference/catlexception-class.md)합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 은 정의 된 함수는 예외를 throw 하지 않고 어설션 실패를 발생 합니다.  
  
 ATL 프로젝트에 ATL 오류 발생 시 사용할이 함수의 사용자 지정 구현을 제공 하는 것이 같습니다. 이 위해으로 동일한 시그니처를 가진 사용자가 직접 함수 정의 `AtlThrow` 및 #define `AtlThrow` 함수의 이름 이어야 합니다. 이 atlexcept.h (즉, 수행 atlbase.h atlexcept.h에 포함 되어 있으므로 모든 ATL 헤더를 포함 하기 전에 해야 함을)를 포함 하기 전에 수행 되어야 합니다. 함수 특성 `__declspec(noreturn)` 의사 SAL 경고를 방지할 수 있습니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_Windowing #&95;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldef.h  

##  <a name="a-nameatlthrowlastwin32a--atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Windows 함수 `GetLastError`의 결과에 따라 오류를 표시하려면 이 함수를 호출합니다.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 결과 추적 `GetLastError` 디버거.  
  
 경우 **_ATL_NO_EXCEPTIONS** 정의 되지 않은 MFC 프로젝트에서는이 함수는 다음과 같이 throw 됩니다. 한 [CMemoryException](../../mfc/reference/cmemoryexception-class.md) 또는 [COleException](../../mfc/reference/coleexception-class.md) 에서 반환 된 값에 따라 `GetLastError`합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 함수 throw ATL 프로젝트에 정의 되지 않은 한 [CAtlException](../../atl/reference/catlexception-class.md)합니다.  
  
 경우 **_ATL_NO_EXCEPTIONS** 은 정의 된 함수는 예외를 throw 하지 않고 어설션 실패를 발생 합니다.  

## <a name="requirements"></a>요구 사항  
 **헤더:** atldef.h  
   
     
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)   
 [디버깅 및 오류 보고 매크로](../../atl/reference/debugging-and-error-reporting-macros.md)










