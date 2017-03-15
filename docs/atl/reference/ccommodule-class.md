---
title: "CComModule 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComModule
dev_langs:
- C++
helpviewer_keywords:
- CComModule class
- DLL modules [C++], ATL
ms.assetid: f5face2c-8fd8-40e6-9ec3-54ab74701769
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
ms.openlocfilehash: d2bd7566a25cd135cb541c4d90f2700b5f0d47b2
ms.lasthandoff: 02/24/2017

---
# <a name="ccommodule-class"></a>CComModule 클래스
ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
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
|[CComModule::RegisterClassHelper](#registerclasshelper)|시스템 레지스트리에 있는 개체의 표준 클래스 등록을 입력합니다.|  
|[CComModule::RegisterClassObjects](#registerclassobjects)|클래스 개체를 등록합니다. 에 대 한 Exe에만 해당 합니다.|  
|[CComModule::RegisterServer](#registerserver)|개체 맵의 각 개체에 대 한 시스템 레지스트리를 업데이트합니다.|  
|[CComModule::RegisterTypeLib](#registertypelib)|형식 라이브러리를 등록합니다.|  
|[CComModule::RevokeClassObjects](#revokeclassobjects)|클래스 개체를 취소합니다. 에 대 한 Exe에만 해당 합니다.|  
|[CComModule::Term](#term)|데이터 멤버를 해제합니다.|  
|[CComModule::UnregisterClassHelper](#unregisterclasshelper)|시스템 레지스트리에서 개체의 표준 클래스 등록을 제거합니다.|  
|[CComModule::UnregisterServer](#unregisterserver)|개체 맵의 각 개체를 등록 취소합니다.|  
|[CComModule::UpdateRegistryClass](#updateregistryclass)|등록 하거나 등록 하 고 개체의 표준 클래스 등록을 취소 합니다.|  
|[CComModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|지정된 된 리소스를 등록 하거나 개체를 등록 취소에 포함 된 스크립트를 실행 합니다.|  
|[CComModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|ATL 레지스트리 구성 요소에 정적으로 연결 됩니다. 지정된 된 리소스를 등록 하거나 개체를 등록 취소에 포함 된 스크립트를 실행 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComModule::m_csObjMap](#m_csobjmap)|개체 맵 정보에 대 한 동기화 된 액세스를 확인합니다.|  
|[CComModule::m_csTypeInfoHolder](#m_cstypeinfoholder)|형식 라이브러리 정보에 대 한 동기화 된 액세스를 확인합니다.|  
|[CComModule::m_csWindowCreate](#m_cswindowcreate)|창 클래스 정보 및 창 만드는 동안 사용 되는 정적 데이터에 대 한 동기화 된 액세스를 확인 합니다.|  
|[CComModule::m_hInst](#m_hinst)|모듈 인스턴스에 대 한 핸들을 포함합니다.|  
|[CComModule::m_hInstResource](#m_hinstresource)|기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.|  
|[CComModule::m_hInstTypeLib](#m_hinsttypelib)|기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.|  
|[CComModule::m_pObjMap](#m_pobjmap)|개체 맵의 모듈 인스턴스에 의해 유지 관리를 가리킵니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
>  이 클래스는 사용 되지 않으며 ATL 코드 생성 마법사 사용 하 여 이제는 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 및 [CAtlModule](../../atl/reference/catlmodule-class.md) 파생 클래스입니다. 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 에 대 한 자세한 내용은 합니다. ATL.의 이전 릴리스를 사용 하 여 만든 응용 프로그램과 함께 사용 하기 위해 다음에 나오는 정보는 `CComModule`여전히에 대 한 ATL의 일부 이전 버전과 기능입니다.  
  
 `CComModule`모듈의 구성 요소에 액세스 하는 클라이언트는 COM 서버 모듈을 구현 합니다. `CComModule`(프로세스에서) DLL과 EXE (로컬) 모듈 둘 다 지원합니다.  
  
 A `CComModule` 인스턴스 클래스 개체 정의의 집합을 유지 하기 위해 개체 맵을 사용 합니다. 이 개체 맵의 배열로 서 구현 됩니다 `_ATL_OBJMAP_ENTRY` 구조, 및에 대 한 정보를 포함 합니다.  
  
-   입력 하 고 시스템 레지스트리에 있는 설명 개체를 제거 합니다.  
  
-   클래스 팩터리를 통해 개체를 인스턴스화.  
  
-   구성 요소에는 클라이언트와 루트 개체 간의 통신을 설정합니다.  
  
-   클래스 개체의 수명 관리를 수행 합니다.  
  
 마법사를 자동으로 생성 ATL COM 응용 프로그램 마법사를 실행 하면 `_Module`의 전역 인스턴스 `CComModule` 에서 파생 된 클래스 또는 합니다. ATL 프로젝트 마법사에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)합니다.  
  
 외에 `CComModule`, ATL은 제공 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), Exe 및 Windows 서비스에 대 한 아파트 모델 모듈을 구현 하는 합니다. 모듈에서 파생 `CComAutoThreadModule` 여러 아파트에 개체를 만들 려 하는 경우.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 `CComModule`  
  
## <a name="requirements"></a>요구 사항  
 `Header:`atlbase.h  
  
##  <a name="a-namegetclassobjecta--ccommodulegetclassobject"></a><a name="getclassobject"></a>CComModule::GetClassObject  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
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
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `ppv` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.  
  
 `GetClassObject`Dll에 사용할 수만 있습니다.  
  
##  <a name="a-namegetmoduleinstancea--ccommodulegetmoduleinstance"></a><a name="getmoduleinstance"></a>CComModule::GetModuleInstance  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE` 이 모듈을 식별 합니다.  
  
### <a name="remarks"></a>주의  
 반환 된 [m_hInst](#m_hinst) 데이터 멤버입니다.  
  
##  <a name="a-namegetresourceinstancea--ccommodulegetresourceinstance"></a><a name="getresourceinstance"></a>CComModule::GetResourceInstance  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE`입니다.  
  
### <a name="remarks"></a>주의  
 반환 된 [m_hInstResource](#m_hinstresource) 데이터 멤버입니다.  
  
##  <a name="a-namegettypelibinstancea--ccommodulegettypelibinstance"></a><a name="gettypelibinstance"></a>CComModule::GetTypeLibInstance  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HINSTANCE GetTypeLibInstance() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE`입니다.  
  
### <a name="remarks"></a>주의  
 반환 된 [m_hInstTypeLib](#m_hinsttypelib) 데이터 멤버입니다.  
  
##  <a name="a-nameinita--ccommoduleinit"></a><a name="init"></a>CComModule::Init  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 맵 항목 개체의 배열에 대 한 포인터입니다.  
  
 `h`  
 [in] `HINSTANCE` 에 전달 된 **DLLMain** 또는 `WinMain`합니다.  
  
 `plibid`  
 [in] 포인터는 프로젝트와 관련 된 형식 라이브러리의 LIBID입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 모든 데이터 멤버를 초기화합니다.  
  
##  <a name="a-namemcsobjmapa--ccommodulemcsobjmap"></a><a name="m_csobjmap"></a>CComModule::m_csObjMap  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
CRITICAL_SECTION m_csObjMap;
```  
  
### <a name="remarks"></a>주의  
 개체 맵의에 대 한 동기화 된 액세스를 확인합니다.  
  
##  <a name="a-namemcstypeinfoholdera--ccommodulemcstypeinfoholder"></a><a name="m_cstypeinfoholder"></a>CComModule::m_csTypeInfoHolder  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
CRITICAL_SECTION m_csTypeInfoHolder;
```  
  
### <a name="remarks"></a>주의  
 형식 라이브러리에 대 한 동기화 된 액세스를 확인합니다.  
  
##  <a name="a-namemcswindowcreatea--ccommodulemcswindowcreate"></a><a name="m_cswindowcreate"></a>CComModule::m_csWindowCreate  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
CRITICAL_SECTION m_csWindowCreate;
```  
  
### <a name="remarks"></a>주의  
 창 클래스 정보를 창 만드는 동안 사용 되는 정적 데이터를 동기화 된 액세스를 확인 합니다.  
  
##  <a name="a-namemhinsta--ccommodulemhinst"></a><a name="m_hinst"></a>CComModule::m_hInst  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HINSTANCE m_hInst;
```  
  
### <a name="remarks"></a>주의  
 모듈 인스턴스에 대 한 핸들을 포함합니다.  
  
 [Init](#init) 메서드 집합 `m_hInst` 에 전달 된 핸들에 **DLLMain** 또는 `WinMain`합니다.  
  
##  <a name="a-namemhinstresourcea--ccommodulemhinstresource"></a><a name="m_hinstresource"></a>CComModule::m_hInstResource  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HINSTANCE m_hInstResource;
```  
  
### <a name="remarks"></a>주의  
 기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.  
  
 [Init](#init) 메서드 집합 `m_hInstResource` 에 전달 된 핸들에 **DLLMain** 또는 `WinMain`합니다. 명시적으로 설정할 수 `m_hInstResource` 리소스에 대 한 핸들을 합니다.  
  
 [GetResourceInstance](#getresourceinstance) 에 저장 된 핸들을 반환 하는 메서드 `m_hInstResource`합니다.  
  
##  <a name="a-namemhinsttypeliba--ccommodulemhinsttypelib"></a><a name="m_hinsttypelib"></a>CComModule::m_hInstTypeLib  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HINSTANCE m_hInstTypeLib;
```  
  
### <a name="remarks"></a>주의  
 기본적으로 모듈 인스턴스에 대 한 핸들을 포함합니다.  
  
 [Init](#init) 메서드 집합 `m_hInstTypeLib` 에 전달 된 핸들에 **DLLMain** 또는 `WinMain`합니다. 명시적으로 설정할 수 `m_hInstTypeLib` 형식 라이브러리에 대 한 핸들을 합니다.  
  
 [GetTypeLibInstance](#gettypelibinstance) 에 저장 된 핸들을 반환 하는 메서드 `m_hInstTypeLib`합니다.  
  
##  <a name="a-namempobjmapa--ccommodulempobjmap"></a><a name="m_pobjmap"></a>CComModule::m_pObjMap  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
_ATL_OBJMAP_ENTRY* m_pObjMap;
```  
  
### <a name="remarks"></a>주의  
 개체 맵의 모듈 인스턴스에 의해 유지 관리를 가리킵니다.  
  
##  <a name="a-nameregisterclasshelpera--ccommoduleregisterclasshelper"></a><a name="registerclasshelper"></a>CComModule::RegisterClassHelper  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
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
 [in] 스레딩 모델 레지스트리에 입력을 지정 합니다. 가능한 값은 **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, 또는 **AUTPRXFLAG**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 시스템 레지스트리에 있는 개체의 표준 클래스 등록을 입력합니다.  
  
 [UpdateRegistryClass](#updateregistryclass) 메서드 호출 `RegisterClassHelper`합니다.  
  
##  <a name="a-nameregisterclassobjectsa--ccommoduleregisterclassobjects"></a><a name="registerclassobjects"></a>CComModule::RegisterClassObjects  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT RegisterClassObjects(DWORD dwClsContext, DWORD dwFlags) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `dwClsContext`  
 [in] 클래스 개체를 실행할 수의 컨텍스트를 지정 합니다. 가능한 값은 **위해 CLSCTX_INPROC_SERVER**, **CLSCTX_INPROC_HANDLER**, 또는 **CLSCTX_LOCAL_SERVER**합니다. 이러한 값에 대 한 참조 [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwFlags`  
 [in] 클래스 개체에 연결 형식을 결정합니다. 가능한 값은 **REGCLS_SINGLEUSE**, **REGCLS_MULTIPLEUSE**, 또는 **REGCLS_MULTI_SEPARATE**합니다. 이러한 값에 대 한 참조 [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 다른 응용 프로그램 데이터베이스에 연결할 수 있도록 ole EXE 클래스 개체를 등록 합니다. 이 메서드는 Exe를 사용할 수만 있습니다.  
  
##  <a name="a-nameregisterservera--ccommoduleregisterserver"></a><a name="registerserver"></a>CComModule::RegisterServer  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,  
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegTypeLib`  
 [in] 형식 라이브러리를 등록할 적이 있는지 여부를 나타냅니다. 기본값은 **FALSE**합니다.  
  
 `pCLSID`  
 [in] 등록할 개체의 CLSID 가리킵니다. 경우 **NULL** (기본값), 개체 맵의 모든 개체를 등록 합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 에 따라는 `pCLSID` 매개 변수를 개체 맵의 모든 개체 또는 단일 클래스 개체에 대 한 시스템 레지스트리를 업데이트 합니다.  
  
 경우 `bRegTypeLib` 는 **TRUE**, 형식 라이브러리 정보 업데이트 됩니다.  
  
 참조 [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) 개체 맵의에 항목을 추가 하는 방법에 대 한 내용은 합니다.  
  
 `RegisterServer`자동으로 호출 됩니다 **DLLRegisterServer** dll 또는 `WinMain` 으로 실행 하는 EXE에 대 한는 **/RegServer** 명령줄 옵션입니다.  
  
##  <a name="a-nameregistertypeliba--ccommoduleregistertypelib"></a><a name="registertypelib"></a>CComModule::RegisterTypeLib  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT RegisterTypeLib() throw();
HRESULT RegisterTypeLib(LPCTSTR lpszIndex) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszIndex`  
 [in] 형식에서 문자열 `"\\N"`여기서 `N` 정수 인덱스는 형식 라이브러리 리소스입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 시스템 레지스트리를 형식 라이브러리에 대 한 정보를 추가합니다.  
  
 여러 개의 형식 라이브러리를 포함 하는 모듈 인스턴스를이 메서드의 두 번째 버전 사용 하 여 지정 된 형식 라이브러리를 사용 해야 합니다.  
  
##  <a name="a-namerevokeclassobjectsa--ccommodulerevokeclassobjects"></a><a name="revokeclassobjects"></a>CComModule::RevokeClassObjects  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT RevokeClassObjects() throw();
```  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 클래스 개체를 제거합니다. 이 메서드는 Exe를 사용할 수만 있습니다.  
  
##  <a name="a-nameterma--ccommoduleterm"></a><a name="term"></a>CComModule::Term  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>주의  
 모든 데이터 멤버를 해제합니다.  
  
##  <a name="a-nameunregisterclasshelpera--ccommoduleunregisterclasshelper"></a><a name="unregisterclasshelper"></a>CComModule::UnregisterClassHelper  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
ATL_DEPRECATED HRESULT UnregisterClassHelper(  
    const CLSID& clsid,
    LPCTSTR lpszProgID,
    LPCTSTR lpszVerIndProgID);
```  
  
### <a name="parameters"></a>매개 변수  
 `clsid`  
 [in] 등록을 취소할 수 개체의 CLSID입니다.  
  
 `lpszProgID`  
 [in] 개체에 연결 된 ProgID입니다.  
  
 `lpszVerIndProgID`  
 [in] 개체에 연결 된 버전 독립 ProgID입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 시스템 레지스트리에서 개체의 표준 클래스 등록을 제거합니다.  
  
 [UpdateRegistryClass](#updateregistryclass) 메서드 호출 `UnregisterClassHelper`합니다.  
  
##  <a name="a-nameunregisterservera--ccommoduleunregisterserver"></a><a name="unregisterserver"></a>CComModule::UnregisterServer  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT UnregisterServer(const CLSID* pCLSID = NULL) throw ();
inline HRESULT UnregisterServer(BOOL bUnRegTypeLib, const CLSID* pCLSID = NULL) throw ();
```  
  
### <a name="parameters"></a>매개 변수  
 `bUnRegTypeLib`  
 경우 **TRUE**, 형식 라이브러리가 등록 되지 않았습니다.  
  
 `pCLSID`  
 등록 취소할 개체의 CLSID 가리킵니다. 경우 **NULL** (기본값), 개체 맵의 모든 개체 등록 취소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 에 따라는 `pCLSID` 매개 변수를 단일 클래스 개체 또는 개체 맵의 모든 개체를 등록 취소 합니다.  
  
 `UnregisterServer`자동으로 호출 됩니다 **DLLUnregisterServer** dll 또는 `WinMain` 으로 실행 하는 EXE에 대 한는 **/UnregServer** 명령줄 옵션입니다.  
  
 참조 [OBJECT_ENTRY_AUTO](http://msdn.microsoft.com/library/5a0f4fa5-0905-43d2-b337-e22f979c9e4c) 개체 맵의에 항목을 추가 하는 방법에 대 한 내용은 합니다.  
  
##  <a name="a-nameupdateregistryclassa--ccommoduleupdateregistryclass"></a><a name="updateregistryclass"></a>CComModule::UpdateRegistryClass  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
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
 등록 하거나 등록 취소할 개체의 CLSID입니다.  
  
 `lpszProgID`  
 개체에 연결 된 ProgID입니다.  
  
 `lpszVerIndProgID`  
 개체에 연결 된 버전 독립 ProgID입니다.  
  
 `nDescID`  
 개체의 설명에 대 한 문자열 리소스의 식별자입니다.  
  
 `szDesc`  
 개체의 설명을 포함 하는 문자열입니다.  
  
 `dwFlags`  
 스레딩 모델 레지스트리에 입력을 지정 합니다. 가능한 값은 **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, 또는 **AUTPRXFLAG**합니다.  
  
 `bRegister`  
 개체를 등록 해야 하는지 여부를 나타냅니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 경우 `bRegister` 는 **TRUE**,이 메서드는 개체의 표준 클래스 등록 시스템 레지스트리에 입력 합니다.  
  
 경우 `bRegister` 는 **FALSE**, 개체의 등록을 제거 합니다.  
  
 값에 따라 `bRegister`, `UpdateRegistryClass` 호출 [RegisterClassHelper](#registerclasshelper) 또는 [UnregisterClassHelper](#unregisterclasshelper)합니다.  
  
 지정 하 여는 [DECLARE_REGISTRY](http://msdn.microsoft.com/library/89b8949b-5c27-4a9c-8a51-ad276bba3a54) 매크로 `UpdateRegistryClass` 개체 맵의 처리 될 때 자동으로 호출 됩니다.  
  
##  <a name="a-nameupdateregistryfromresourceda--ccommoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CComModule::UpdateRegistryFromResourceD  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
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
 [in] 개체를 등록 해야 하는지 여부를 나타냅니다.  
  
 `pMapEntries`  
 [in] 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 사용 하 여 자동으로 `%MODULE%`합니다. 추가 대체 가능 매개 변수를 사용 하려면 자세한 내용은 설명 부분을 참조 하십시오. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 지정 하는 리소스에 포함 된 스크립트를 실행 `lpszRes` 또는 `nResID`합니다.  
  
 경우 `bRegister` 는 **TRUE**,이 메서드는 개체의 시스템 레지스트리에 있는 등록, 그렇지 않으면 개체를 등록 취소 합니다.  
  
 지정 하 여는 [DECLARE_REGISTRY_RESOURCE](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b) 또는 [DECLARE_REGISTRY_RESOURCEID](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b) 매크로 `UpdateRegistryFromResourceD` 개체 맵의 처리 될 때 자동으로 호출 됩니다.  
  
> [!NOTE]
>  런타임 시 대체 값으로 대체를 지정 하지 마십시오는 `DECLARE_REGISTRY_RESOURCE` 또는 `DECLARE_REGISTRY_RESOURCEID` 매크로입니다. 대신, 배열을 만든 **_ATL_REGMAP_ENTRIES** 런타임에 자리 표시자를 바꿀 값 쌍을 이루는 구조에 있는 각 항목 변수 자리 표시자를 포함 합니다. 다음 호출 `UpdateRegistryFromResourceD`, 배열에 대 한 전달는 `pMapEntries` 매개 변수입니다. 이렇게 하면 모든 대체 값에 추가 **_ATL_REGMAP_ENTRIES** 등록자의 대체 맵에 구조입니다.  
  
> [!NOTE]
>  ATL 레지스트리 구성 요소 (등록자)에 정적으로 링크를 참조 [UpdateRegistryFromResourceS](#updateregistryfromresources)합니다.  
  
 대체 가능 매개 변수 및 스크립팅 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.  
  
##  <a name="a-nameupdateregistryfromresourcesa--ccommoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CComModule::UpdateRegistryFromResourceS  
 ATL 7.0부터 `CComModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
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
 [in] 리소스 스크립트를 등록 해야 하는지 여부를 나타냅니다.  
  
 `pMapEntries`  
 [in] 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 사용 하 여 자동으로 `%MODULE%`합니다. 추가 대체 가능 매개 변수를 사용 하려면 자세한 내용은 설명 부분을 참조 하십시오. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 유사한 [UpdateRegistryFromResourceD](#updateregistryfromresourced) 제외 하 고 `UpdateRegistryFromResourceS` ATL 레지스트리 구성 요소 (등록자)에 대 한 정적 링크를 만듭니다.  
  
 `UpdateRegistryFromResourceS`호출 될 자동으로 개체 맵의 처리 될 때 추가한 제공 `#define _ATL_STATIC_REGISTRY` 프로그램 stdafx.h에 있습니다.  
  
> [!NOTE]
>  런타임 시 대체 값으로 대체를 지정 하지 마십시오는 [DECLARE_REGISTRY_RESOURCE](http://msdn.microsoft.com/library/7ac11498-8ee2-4156-8df2-7076f7ddda8b) 또는 [DECLARE_REGISTRY_RESOURCEID](http://msdn.microsoft.com/library/65bf3576-5396-416e-ba48-e14b3236c49b) 매크로입니다. 대신, 배열을 만든 **_ATL_REGMAP_ENTRIES** 런타임에 자리 표시자를 바꿀 값 쌍을 이루는 구조에 있는 각 항목 변수 자리 표시자를 포함 합니다. 다음 호출 `UpdateRegistryFromResourceS`, 배열에 대 한 전달는 `pMapEntries` 매개 변수입니다. 이렇게 하면 모든 대체 값에 추가 **_ATL_REGMAP_ENTRIES** 등록자의 대체 맵에 구조입니다.  
  
 대체 가능 매개 변수 및 스크립팅 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

