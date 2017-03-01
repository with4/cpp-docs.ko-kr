---
title: "CComAutoThreadModule 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CComAutoThreadModule class
- apartment model modules
ms.assetid: 13063ea5-a57e-4aac-97d3-227137262811
caps.latest.revision: 21
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
ms.openlocfilehash: 07aaf6dc7029452fa6822c5f5f1ae09b724ddc8b
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautothreadmodule-class"></a>CComAutoThreadModule 클래스
ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class ThreadAllocator = CComSimpleThreadAllocator>  
class CComAutoThreadModule : public CComModule
```  
  
#### <a name="parameters"></a>매개 변수  
 `ThreadAllocator`  
 [in] 스레드 선택 영역을 관리 하는 클래스입니다. 기본값은 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[CreateInstance](#createinstance)|스레드를 선택 하 고 연결된 아파트에 있는 개체를 만듭니다.|  
|[GetDefaultThreads](#getdefaultthreads)|(정적) 프로세서의 수에 따라 모듈에 대 한 스레드 수를 동적으로 계산 합니다.|  
|[Init](#init)|모듈의 스레드를 만듭니다.|  
|[잠금](#lock)|모듈에는 현재 스레드에서 잠금 수를 증가 시킵니다.|  
|[잠금 해제](#unlock)|모듈 및 현재 스레드의 잠금 횟수를 줄입니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[dwThreadID](#dwthreadid)|현재 스레드의 식별자를 포함 합니다.|  
|[m_Allocator](#m_allocator)|스레드 선택 영역을 관리합니다.|  
|[m_nThreads](#m_nthreads)|모듈에서 스레드 수를 포함합니다.|  
|[m_pApartments](#m_papartments)|모듈의 아파트를 관리합니다.|  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
>  이 클래스는 사용 되지 않는으로 바뀌는 것은 [CAtlAutoThreadModule](../../atl/reference/catlautothreadmodule-class.md) 및 [CAtlModule](../../atl/reference/catlmodule-class.md) 클래스를 파생 합니다. 다음에 나오는 정보는 이전 릴리스의 ATL. 사용  
  
 `CComAutoThreadModule`파생 되며 [CComModule](../../atl/reference/ccommodule-class.md) 를 Exe 및 Windows 서비스에 대 한 스레드 풀링, 아파트 모델 COM 서버를 구현 합니다. `CComAutoThreadModule`사용 하 여 [CComApartment](../../atl/reference/ccomapartment-class.md) 모듈에서 각 스레드에 대 한 아파트를 관리할 수 있습니다.  
  
 모듈에서 파생 `CComAutoThreadModule` 여러 아파트에 개체를 만들 려 하는 경우. 포함 해야는 [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) 지정 하 여 개체의 클래스 정의에 매크로 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) 클래스 팩터리로 합니다.  
  
 기본적으로는 ATL COM 응용 프로그램 마법사 (Visual Studio.NET에서 ATL 프로젝트 마법사)에서 모듈 파생할 `CComModule`합니다. 사용 하 여 `CComAutoThreadModule`, 클래스 정의 수정 합니다. 예:  
  
 [!code-cpp[NVC_ATL_AxHost #&2;](../../atl/codesnippet/cpp/ccomautothreadmodule-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `IAtlAutoThreadModule`  
  
 [CAtlModuleT](../../atl/reference/catlmodulet-class.md)  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 [CComModule](../../atl/reference/ccommodule-class.md)  
  
 `CComAutoThreadModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="a-namecreateinstancea--ccomautothreadmodulecreateinstance"></a><a name="createinstance"></a>CComAutoThreadModule::CreateInstance  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT CreateInstance(
    void* pfnCreateInstance,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>매개 변수  
 *pfnCreateInstance*  
 [in] 생성기 함수에 대 한 포인터입니다.  
  
 `riid`  
 [in] 요청된 된 인터페이스의 IID입니다.  
  
 `ppvObj`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `ppvObj` NULL로 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 HRESULT 값입니다.  
  
### <a name="remarks"></a>주의  
 스레드를 선택 하 고 연결된 아파트에 있는 개체를 만듭니다.  
  
##  <a name="a-namedwthreadida--ccomautothreadmoduledwthreadid"></a><a name="dwthreadid"></a>CComAutoThreadModule::dwThreadID  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
DWORD dwThreadID;
```  
  
### <a name="remarks"></a>주의  
 현재 스레드의 식별자를 포함 합니다.  
  
##  <a name="a-namegetdefaultthreadsa--ccomautothreadmodulegetdefaultthreads"></a><a name="getdefaultthreads"></a>CComAutoThreadModule::GetDefaultThreads  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
static int GetDefaultThreads();
```  
  
### <a name="return-value"></a>반환 값  
 EXE 모듈에서 만들 스레드의 수입니다.  
  
### <a name="remarks"></a>주의  
 이 정적 함수는 동적으로 프로세서의 수에 따라 EXE 모듈에 대 한 스레드의 최대 수를 계산 합니다. 기본적으로이 반환 값에 전달 되는 [Init](#init) 메서드는 스레드를 만들 수 있습니다.  
  
##  <a name="a-nameinita--ccomautothreadmoduleinit"></a><a name="init"></a>CComAutoThreadModule::Init  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
HRESULT Init(
    _ATL_OBJMAP_ENTRY* p,
    HINSTANCE h,
    const GUID* plibid = NULL,
    int nThreads = GetDefaultThreads());
```  
  
### <a name="parameters"></a>매개 변수  
 `p`  
 [in] 맵 항목 개체의 배열에 대 한 포인터입니다.  
  
 `h`  
 [in] `HINSTANCE` 에 전달 된 **DLLMain** 또는 `WinMain`합니다.  
  
 `plibid`  
 [in] 포인터는 프로젝트와 관련 된 형식 라이브러리의 LIBID입니다.  
  
 `nThreads`  
 [in] 만들 스레드의 수입니다. 기본적으로 `nThreads` 에서 반환한 값은 [GetDefaultThreads](#getdefaultthreads)합니다.  
  
### <a name="remarks"></a>주의  
 데이터 멤버를 초기화 하 고 지정 된 스레드 수를 만듭니다 `nThreads`합니다.  
  
##  <a name="a-namelocka--ccomautothreadmodulelock"></a><a name="lock"></a>CComAutoThreadModule::Lock  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하거나 테스트 될 수 있는 값입니다.  
  
### <a name="remarks"></a>주의  
 모듈에 대 한 현재 스레드에 대 한 잠금 수에 원자성 증가 수행합니다. `CComAutoThreadModule`모든 클라이언트는 모듈에 액세스 하는 여부를 확인 하려면 모듈 잠금 횟수를 사용 합니다. 현재 스레드에서 잠금 수 통계 용도로 사용 됩니다.  
  
##  <a name="a-namemallocatora--ccomautothreadmodulemallocator"></a><a name="m_allocator"></a>CComAutoThreadModule::m_Allocator  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
ThreadAllocator  m_Allocator;
```     
  
### <a name="remarks"></a>주의  
 스레드 선택 영역을 관리 하는 개체입니다. 기본적으로는 `ThreadAllocator` 클래스 템플릿 매개 변수는 [CComSimpleThreadAllocator](../../atl/reference/ccomsimplethreadallocator-class.md)합니다.  
  
##  <a name="a-namemnthreadsa--ccomautothreadmodulemnthreads"></a><a name="m_nthreads"></a>CComAutoThreadModule::m_nThreads  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
int m_nThreads;
```  
  
### <a name="remarks"></a>주의  
 EXE 모듈에서 스레드 수를 포함합니다. 때 [Init](#init) 이라고 `m_nThreads` 로 설정 되어는 `nThreads` 매개 변수 값입니다. 연결 된 각 스레드의 아파트에서 관리 되는 [CComApartment](../../atl/reference/ccomapartment-class.md) 개체입니다.  
  
##  <a name="a-namempapartmentsa--ccomautothreadmodulempapartments"></a><a name="m_papartments"></a>CComAutoThreadModule::m_pApartments  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
CComApartment* m_pApartments;
```  
  
### <a name="remarks"></a>주의  
 배열을 가리키는 [CComApartment](../../atl/reference/ccomapartment-class.md) 모듈에서 아파트를 관리 하는 개체입니다. 배열의 요소 수에 따라는 [m_nThreads](#m_nthreads) 멤버입니다.  
  
##  <a name="a-nameunlocka--ccomautothreadmoduleunlock"></a><a name="unlock"></a>CComAutoThreadModule::Unlock  
 ATL 7.0부터 `CComAutoThreadModule` 는 사용 되지 않습니다: 참조 [ATL 모듈 클래스](../../atl/atl-module-classes.md) 대 한 자세한 내용은 합니다.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하거나 테스트 될 수 있는 값입니다.  
  
### <a name="remarks"></a>주의  
 모듈에 대 한 현재 스레드에 대 한 잠금 수에는 원자성 감소를 수행합니다. `CComAutoThreadModule`모든 클라이언트는 모듈에 액세스 하는 여부를 확인 하려면 모듈 잠금 횟수를 사용 합니다. 현재 스레드에서 잠금 수 통계 용도로 사용 됩니다.  
  
 모듈 잠금 수가&0;에 도달 하면 모듈 로드할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)

