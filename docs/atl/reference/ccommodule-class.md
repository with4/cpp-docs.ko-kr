---
title: "CComModule 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComModule
- ATLBASE/ATL::CComModule
- ATLBASE/ATL::CComModule::GetClassObject
- ATLBASE/ATL::CComModule::GetModuleInstance
- ATLBASE/ATL::CComModule::GetResourceInstance
- ATLBASE/ATL::CComModule::GetTypeLibInstance
- ATLBASE/ATL::CComModule::Init
- ATLBASE/ATL::CComModule::RegisterClassHelper
- ATLBASE/ATL::CComModule::RegisterClassObjects
- ATLBASE/ATL::CComModule::RegisterServer
- ATLBASE/ATL::CComModule::RegisterTypeLib
- ATLBASE/ATL::CComModule::RevokeClassObjects
- ATLBASE/ATL::CComModule::Term
- ATLBASE/ATL::CComModule::UnregisterClassHelper
- ATLBASE/ATL::CComModule::UnregisterServer
- ATLBASE/ATL::CComModule::UpdateRegistryClass
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CComModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CComModule::m_csObjMap
- ATLBASE/ATL::CComModule::m_csTypeInfoHolder
- ATLBASE/ATL::CComModule::m_csWindowCreate
- ATLBASE/ATL::CComModule::m_hInst
- ATLBASE/ATL::CComModule::m_hInstResource
- ATLBASE/ATL::CComModule::m_hInstTypeLib
- ATLBASE/ATL::CComModule::m_pObjMap
dev_langs: C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5b86e1f082b7be844afe3b1a84d182d1c722f500
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommodule-class"></a>CComModule 클래스
ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComModule : public _ATL_MODULE
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComModule::GetClassObject](#getclassobject)|지정 된 CLSID의 개체를 만듭니다. Dll에 해당 합니다.|  
|[CComModule::GetModuleInstance](#getmoduleinstance)|`m_hInst`를 반환합니다.|  
|[CComModule::GetResourceInstance](#getresourceinstance)|`m_hInstResource`를 반환합니다.|  
|[CComModule::GetTypeLibInstance](#gettypelibinstance)|`m_hInstTypeLib`를 반환합니다.|  
|[CComModule::Init](#init)|데이터 멤버를 초기화합니다.|  
|[CComModule::RegisterClassHelper](#registerclasshelper)|개체의 표준 클래스 등록 시스템 레지스트리에 입력합니다.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|클래스 개체를 등록합니다. 에 대 한 Exe만 해당 합니다.|  
|[CComModule::RegisterServer](#registerserver)|개체 맵의 각 개체에 대 한 시스템 레지스트리를 업데이트합니다.|  
|[CComModule::RegisterTypeLib](#registertypelib)|형식 라이브러리를 등록합니다.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|클래스 개체를 취소합니다. 에 대 한 Exe만 해당 합니다.|  
|[CComModule::Term](#term)|데이터 멤버를 해제합니다.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|시스템 레지스트리에서 개체의 표준 클래스 등록을 제거 합니다.|  
|[CComModule::UnregisterServer](#unregisterserver)|개체 맵의 각 개체의 등록을 취소 합니다.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|등록 하거나 등록 하 고 개체의 표준 클래스 등록을 취소 합니다.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|등록 하거나 등록 취소할 개체를 지정된 된 리소스에 포함 된 스크립트를 실행 합니다.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL 레지스트리 구성 요소에 정적으로 연결 됩니다. 등록 하거나 등록 취소할 개체를 지정된 된 리소스에 포함 된 스크립트를 실행 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|개체 맵 정보에 대 한 동기화 된 액세스를 보장합니다.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|형식 라이브러리 정보에 대 한 동기화 된 액세스를 보장합니다.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|창 클래스 정보 및 창 만드는 동안 사용 되는 정적 데이터에 대 한 동기화 된 액세스를 보장 합니다.|  
|[CComModule::m_hInst](#m_hinst)|모듈 인스턴스에 대 한 핸들을 포함합니다.|  
|[CComModule::m_hInstResource](#m_hinstresource)|기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.|  
|[CComModule::m_pObjMap](#m_pobjmap)|개체 맵의 모듈 인스턴스에 의해 유지 관리를 가리킵니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 클래스는 더 이상 ATL 코드 생성 마법사 사용 하 여 이제는 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 및 [CAtlModule](../../atl/reference/catlmodule-class.md) 파생 클래스입니다. 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 자세한 정보에 대 한 합니다. ATL.의 이전 릴리스를 사용 하 여 만든 응용 프로그램과 함께 사용 하기 위해 다음에 나오는 정보는 `CComModule`여전히에 대 한 ATL의 일부 이전 버전과 기능입니다.  
  
 `CComModule`COM 서버 모듈의 경우, 클라이언트가 모듈의 구성 요소에 액세스할 수 있도록 구현 합니다. `CComModule`(in process) DLL과 EXE (local) 모듈을 모두 지원합니다.  
  
 A `CComModule` 인스턴스 클래스 개체 정의 집합을 유지 하기 위해 개체 맵을 사용 합니다. 이 개체 맵의의 배열으로 구현 됩니다 `_ATL_OBJMAP_ENTRY` 구조, 및에 대 한 정보를 포함 합니다.  
  
-   입력 및 시스템 레지스트리에 설명 개체를 제거 합니다.  
  
-   클래스 팩터리를 통해 개체를 인스턴스화합니다.  
  
-   구성 요소에는 클라이언트와 루트 개체 간의 통신을 설정 합니다.  
  
-   클래스 개체의 수명 관리를 수행 합니다.  
  
 마법사를 자동으로 생성 ATL COM 응용 프로그램 마법사를 실행 하면 `_Module`의 전역 인스턴스 `CComModule` 여기에서 파생 된 클래스 또는 합니다. ATL 프로젝트 마법사에 대 한 자세한 내용은 문서 참조 [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.  
  
 외에 `CComModule`, ATL 제공 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), Exe 및 Windows 서비스에 대 한 아파트 모델 모듈을 구현 하는 합니다. 모듈에서 파생 `CComAutoThreadModule` 여러 아파트에 개체를 만들 하려는 경우.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="getclassobject"></a>CComModule::GetClassObject  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HRESULT GetClassObject(  
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rclsid`  
 [in] 만들 개체의 CLSID입니다.  
  
 `riid`  
 [in] 요청된 된 인터페이스의 IID입니다.  
  
 `ppv`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체가이 인터페이스를 지원 하지 않는 경우 `ppv` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.  
  
 `GetClassObject`Dll에 사용할 수만 있습니다.  
  
##  <a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE` 이 모듈을 식별 합니다.  
  
### <a name="remarks"></a>설명  
 반환 된 [m_hInst](#m_hinst) 데이터 멤버입니다.  
  
##  <a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE`입니다.  
  
### <a name="remarks"></a>설명  
 반환 된 [m_hInstResource](#m_hinstresource) 데이터 멤버입니다.  
  
##  <a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE`입니다.  
  
### <a name="remarks"></a>설명  
 반환 된 [m_hInstTypeLib](#m_hinsttypelib) 데이터 멤버입니다.  
  
##  <a name="init"></a>CComModule::Init  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 개체 맵 항목의 배열에 대 한 포인터입니다.  
  
 `h`  
 [in] `HINSTANCE` 에 전달 된 **DLLMain** 또는 `WinMain`합니다.  
  
 `plibid`  
 [in] 프로젝트에 연결 된 형식 라이브러리의 LIBID에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 모든 데이터 멤버를 초기화합니다.  
  
##  <a name="m_csobjmap"></a>CComModule::m_csObjMap  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>설명  
 개체 맵의에 대 한 동기화 된 액세스를 보장합니다.  
  
##  <a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>설명  
 형식 라이브러리에 대 한 동기화 된 액세스를 보장합니다.  
  
##  <a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>설명  
 창 클래스 정보를 창 만드는 동안 사용 되는 정적 데이터를 동기화 된 액세스를 보장 합니다.  
  
##  <a name="m_hinst"></a>CComModule::m_hInst  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>설명  
 모듈 인스턴스에 대 한 핸들을 포함합니다.  
  
 [Init](#init) 메서드 집합 `m_hInst` 에 전달 된 핸들에 **DLLMain** 또는 `WinMain`합니다.  
  
##  <a name="m_hinstresource"></a>CComModule::m_hInstResource  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>설명  
 기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.  
  
 [Init](#init) 메서드 집합 `m_hInstResource` 에 전달 된 핸들에 **DLLMain** 또는 `WinMain`합니다. 명시적으로 설정할 수 `m_hInstResource` 리소스에 대 한 핸들을 합니다.  
  
 [GetResourceInstance](#getresourceinstance) 에 저장 된 핸들을 반환 하는 메서드 `m_hInstResource`합니다.  
  
##  <a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>설명  
 기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.  
  
 [Init](#init) 메서드 집합 `m_hInstTypeLib` 에 전달 된 핸들에 **DLLMain** 또는 `WinMain`합니다. 명시적으로 설정할 수 `m_hInstTypeLib` 형식 라이브러리에 대 한 핸들을 합니다.  
  
 [GetTypeLibInstance](#gettypelibinstance) 에 저장 된 핸들을 반환 하는 메서드 `m_hInstTypeLib`합니다.  
  
##  <a name="m_pobjmap"></a>CComModule::m_pObjMap  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>설명  
 개체 맵의 모듈 인스턴스에 의해 유지 관리를 가리킵니다.  
  
##  <a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
ATL_DEPRECATED HRESULT RegisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] 등록할 개체의 CLSID입니다.  
  
 `lpszProgID`  
 [in] 개체에 연결 된 ProgID입니다.  
  
 `lpszVerIndProgID`  
 [in] 개체에 연결 된 버전 독립 ProgID입니다.  
  
 `nDescID`  
 [in] 개체의 설명에 대 한 문자열 리소스의 식별자입니다.  
  
 `dwFlags`  
 [in] 레지스트리에 입력 하 고 스레딩 모델을 지정 합니다. 가능한 값은 **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, 또는 **AUTPRXFLAG**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 개체의 표준 클래스 등록 시스템 레지스트리에 입력합니다.  
  
 [UpdateRegistryClass](#updateregistryclass) 메서드 호출 `RegisterClassHelper`합니다.  
  
##  <a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwClsContext`  
 [in] 클래스 개체를 실행할의 컨텍스트를 지정 합니다. 가능한 값은 **위해 CLSCTX_INPROC_SERVER**, **CLSCTX_INPROC_HANDLER**, 또는 **CLSCTX_LOCAL_SERVER**합니다. 이러한 값에 대 한 참조 [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) Windows sdk에서입니다.  
  
 `dwFlags`  
 [in] 클래스 개체에 연결 형식을 결정합니다. 가능한 값은 **REGCLS_SINGLEUSE**, **REGCLS_MULTIPLEUSE**, 또는 **REGCLS_MULTI_SEPARATE**합니다. 이러한 값에 대 한 참조 [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) Windows sdk에서입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 다른 응용 프로그램 데이터베이스에 연결할 수 있도록 ole EXE 클래스 개체를 등록 합니다. 이 메서드는 Exe를 사용할 수만 있습니다.  
  
##  <a name="registerserver"></a>CComModule::RegisterServer  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegTypeLib`  
 [in] 형식 라이브러리를 등록 합니다 여부를 나타냅니다. 기본값은 **FALSE**합니다.  
  
 `pCLSID`  
 [in] 등록할 개체의 CLSID 가리킵니다. 경우 **NULL** (기본값), 개체 맵의 모든 개체를 등록 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 에 따라는 `pCLSID` 매개 변수를 단일 클래스 개체 또는 개체 맵의 모든 개체에 대 한 시스템 레지스트리를 업데이트 합니다.  
  
 경우 `bRegTypeLib` 은 **TRUE**, 형식 라이브러리 정보도 업데이트 됩니다.  
  
 참조 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 개체 맵에 항목을 추가 하는 방법에 대 한 합니다.  
  
 `RegisterServer`자동으로 호출 됩니다 **DLLRegisterServer** dll 또는 `WinMain` EXE 사용 하 여 실행에 대 한는 **/RegServer** 명령줄 옵션입니다.  
  
##  <a name="registertypelib"></a>CComModule::RegisterTypeLib  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszIndex`  
 [in] 숫자 형식의 문자열 `"\\N"`여기서 `N` 정수 인덱스 형식 라이브러리 리소스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 시스템 레지스트리를 형식 라이브러리에 대 한 정보를 추가합니다.  
  
 모듈 인스턴스에 여러 개의 형식 라이브러리가 있으면 상위 형식 라이브러리를 사용할지 지정 하려면이 메서드의 두 번째 버전을 사용 합니다.  
  
##  <a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 클래스 개체를 제거합니다. 이 메서드는 Exe를 사용할 수만 있습니다.  
  
##  <a name="term"></a>CComModule::Term  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>설명  
 모든 데이터 멤버를 해제합니다.  
  
##  <a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] 등록을 취소할 개체의 CLSID입니다.  
  
 `lpszProgID`  
 [in] 개체에 연결 된 ProgID입니다.  
  
 `lpszVerIndProgID`  
 [in] 개체에 연결 된 버전 독립 ProgID입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 시스템 레지스트리에서 개체의 표준 클래스 등록을 제거 합니다.  
  
 [UpdateRegistryClass](#updateregistryclass) 메서드 호출 `UnregisterClassHelper`합니다.  
  
##  <a name="unregisterserver"></a>CComModule::UnregisterServer  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `bUnRegTypeLib`  
 경우 **TRUE**, 형식 라이브러리가 등록 되지 않았습니다.  
  
 `pCLSID`  
 등록을 취소할 개체의 CLSID 가리킵니다. 경우 **NULL** (기본값), 개체 맵의 모든 개체 등록 취소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 에 따라는 `pCLSID` 단일 클래스 개체 또는 개체 맵의 모든 개체 매개 변수를 등록 취소 합니다.  
  
 `UnregisterServer`자동으로 호출 됩니다 **DLLUnregisterServer** dll 또는 `WinMain` EXE 사용 하 여 실행에 대 한는 **프로그램이 /UnregServer** 명령줄 옵션입니다.  
  
 참조 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) 개체 맵에 항목을 추가 하는 방법에 대 한 합니다.  
  
##  <a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    UINT nDescID,
    DWORD dwFlags,
    BOOL bRegister);

ATL_DEPRECATED HRESULT UpdateRegistryClass(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID,
    LPCTSTR szDesc,
    DWORD dwFlags,
    BOOL bRegister);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 등록 하거나 등록 취소 개체의 CLSID입니다.  
  
 `lpszProgID`  
 개체에 연결 된 ProgID입니다.  
  
 `lpszVerIndProgID`  
 개체에 연결 된 버전 독립 ProgID입니다.  
  
 `nDescID`  
 개체의 설명에 대 한 문자열 리소스의 식별자입니다.  
  
 `szDesc`  
 개체의 설명을 포함 하는 문자열입니다.  
  
 `dwFlags`  
 레지스트리에 입력 하 고 스레딩 모델을 지정 합니다. 가능한 값은 **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, 또는 **AUTPRXFLAG**합니다.  
  
 `bRegister`  
 개체를 등록할지 여부를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 경우 `bRegister` 은 **TRUE**,이 메서드는 개체의 표준 클래스 등록 시스템 레지스트리에 입력 합니다.  
  
 경우 `bRegister` 은 **FALSE**, 개체의 등록을 제거 합니다.  
  
 값에 따라 `bRegister`, `UpdateRegistryClass` 호출 [RegisterClassHelper](#registerclasshelper) 또는 [UnregisterClassHelper](#unregisterclasshelper)합니다.  
  
 지정 하 여는 [DECLARE_REGISTRY](registry-macros.md#declare_registry) 매크로 `UpdateRegistryClass` 개체 맵의 처리 될 때 자동으로 호출 됩니다.  
  
##  <a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
virtual HRESULT UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceD(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszRes`  
 [in] 리소스 이름입니다.  
  
 `nResID`  
 [in] 리소스 id입니다.  
  
 `bRegister`  
 [in] 개체를 등록할지 여부를 나타냅니다.  
  
 `pMapEntries`  
 [in] 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 사용 하 여 자동으로 `%MODULE%`합니다. 대체 가능한 추가 매개 변수를 사용 하려면 대 한 자세한 내용은 설명을 참조 하세요. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 로 지정 된 리소스에 포함 된 스크립트를 실행 `lpszRes` 또는 `nResID`합니다.  
  
 경우 `bRegister` 은 **TRUE**,이 메서드는 개체가 시스템 레지스트리에 등록, 그렇지 않으면 개체를 등록 취소 합니다.  
  
 지정 하 여는 [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) 또는 [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) 매크로 `UpdateRegistryFromResourceD` 개체 맵의 처리 될 때 자동으로 호출 됩니다.  
  
> [!NOTE]
>  런타임 시 대체 값을 대체할 지정 하지 않으면는 `DECLARE_REGISTRY_RESOURCE` 또는 `DECLARE_REGISTRY_RESOURCEID` 매크로입니다. 대신, 배열을 만든 **_ATL_REGMAP_ENTRIES** 런타임에 자리 표시자를 바꿀 값 쌍을 이루는 구조, 각 항목에 변수 자리 표시자를 포함 합니다. 그런 다음 호출 `UpdateRegistryFromResourceD`에 대 한 배열을 전달는 `pMapEntries` 매개 변수입니다. 이렇게 하면 모든 대체 값에 추가 **_ATL_REGMAP_ENTRIES** 등록자의 대체 지도에 구조입니다.  
  
> [!NOTE]
>  ATL 레지스트리 구성 요소 (등록자)에 정적으로 링크를 참조 [UpdateRegistryFromResourceS](#updateregistryfromresources)합니다.  
  
 대체 가능 매개 변수 및 스크립트에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.  
  
##  <a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 내용을 확인 합니다.  
  
```
virtual HRESULT UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

virtual HRESULT UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszRes`  
 [in] 리소스 이름입니다.  
  
 `nResID`  
 [in] 리소스 id입니다.  
  
 `bRegister`  
 [in] 리소스 스크립트를 등록할지 여부를 나타냅니다.  
  
 `pMapEntries`  
 [in] 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 사용 하 여 자동으로 `%MODULE%`합니다. 대체 가능한 추가 매개 변수를 사용 하려면 대 한 자세한 내용은 설명을 참조 하세요. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>설명  
 비슷한 [UpdateRegistryFromResourceD](#updateregistryfromresourced) 제외 하 고 `UpdateRegistryFromResourceS` ATL 레지스트리 구성 요소 (등록자)에 대 한 정적 링크를 만듭니다.  
  
 `UpdateRegistryFromResourceS`호출 될 자동으로 개체 맵의 처리 될 때 추가한 제공 `#define _ATL_STATIC_REGISTRY` 프로그램 stdafx.h로 합니다.  
  
> [!NOTE]
>  런타임 시 대체 값을 대체할 지정 하지 않으면는 [DECLARE_REGISTRY_RESOURCE](registry-macros.md#declare_registry_resource) 또는 [DECLARE_REGISTRY_RESOURCEID](registry-macros.md#declare_registry_resourceid) 매크로입니다. 대신, 배열을 만든 **_ATL_REGMAP_ENTRIES** 런타임에 자리 표시자를 바꿀 값 쌍을 이루는 구조, 각 항목에 변수 자리 표시자를 포함 합니다. 그런 다음 호출 `UpdateRegistryFromResourceS`에 대 한 배열을 전달는 `pMapEntries` 매개 변수입니다. 이렇게 하면 모든 대체 값에 추가 **_ATL_REGMAP_ENTRIES** 등록자의 대체 지도에 구조입니다.  
  
 대체 가능 매개 변수 및 스크립트에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)
