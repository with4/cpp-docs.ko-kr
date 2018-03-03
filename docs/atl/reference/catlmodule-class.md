---
title: "CAtlModule 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModule
- ATLBASE/ATL::CAtlModule
- ATLBASE/ATL::CAtlModule::CAtlModule
- ATLBASE/ATL::CAtlModule::AddCommonRGSReplacements
- ATLBASE/ATL::CAtlModule::AddTermFunc
- ATLBASE/ATL::CAtlModule::GetGITPtr
- ATLBASE/ATL::CAtlModule::GetLockCount
- ATLBASE/ATL::CAtlModule::Lock
- ATLBASE/ATL::CAtlModule::Term
- ATLBASE/ATL::CAtlModule::Unlock
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceD
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceDHelper
- ATLBASE/ATL::CAtlModule::UpdateRegistryFromResourceS
- ATLBASE/ATL::CAtlModule::m_libid
- ATLBASE/ATL::CAtlModule::m_pGIT
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c969341656d0861224cf0835d08e31907328b5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="catlmodule-class"></a>CAtlModule 클래스
이 클래스는 몇 가지 ATL 모듈 클래스에서 사용 되는 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class ATL_NO_VTABLE CAtlModule : public _ATL_MODULE
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlModule::CAtlModule](#catlmodule)|생성자입니다.|  
|[CAtlModule:: ~ CAtlModule](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL 레지스트리 구성 요소 (등록자) 교체 구조에 매개 변수를 추가 하려면이 메서드를 재정의 합니다.|  
|[CAtlModule::AddTermFunc](#addtermfunc)|종료 될 때 호출 되는 새 함수를 추가 합니다.|  
|[CAtlModule::GetGITPtr](#getgitptr)|글로벌 인터페이스 포인터를 반환합니다.|  
|[CAtlModule::GetLockCount](#getlockcount)|잠금 수를 반환합니다.|  
|[CAtlModule::Lock](#lock)|잠금 수를 증가 시킵니다.|  
|[CAtlModule::Term](#term)|모든 데이터 멤버를 해제합니다.|  
|[CAtlModule::Unlock](#unlock)|잠금 횟수를 줄입니다.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|등록 하거나 등록 취소할 개체를 지정된 된 리소스에 포함 된 스크립트를 실행 합니다.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|이 메서드는 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 합니다.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|등록 하거나 등록 취소할 개체를 지정된 된 리소스에 포함 된 스크립트를 실행 합니다. 이 메서드는 정적으로 ATL 레지스트리 구성 요소에 연결합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|현재 모듈의 GUID를 포함 합니다.|  
|[CAtlModule::m_pGIT](#m_pgit)|전역 인터페이스 테이블에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스는 사용 하 여 [CAtlDllModuleT 클래스](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md), 및 [CAtlServiceModuleT 클래스](../../atl/reference/catlservicemodulet-class.md) 응용 프로그램 EXE, DLL 응용 프로그램에 대 한 지원을 제공 하 고 Windows 서비스, 각각.  
  
 ATL에서 모듈에 대 한 자세한 내용은 참조 하십시오. [ATL 모듈 클래스](../../atl/atl-module-classes.md)합니다.  
  
 이 클래스는 사용 되지 않는 대신 [CComModule 클래스](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 ATL 레지스트리 구성 요소 (등록자) 교체 구조에 매개 변수를 추가 하려면이 메서드를 재정의 합니다.  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 *pRegistrar*  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 대체 가능 매개 변수 사용 등록자의 클라이언트 실행 시간 데이터를 지정할 수 있습니다. 이렇게 하려면 등록자에 관련 된 스크립트에 대 한 대체 가능 매개 변수 값을 입력 하는 대체 맵을 유지 관리 합니다. 등록자는 런타임 시 이러한 항목을 만듭니다.  
  
 항목을 참조 [를 사용 하 여 대체 가능 매개 변수 (The 등록자 전처리기)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 내용을 확인 합니다.  
  
##  <a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 종료 될 때 호출 되는 새 함수를 추가 합니다.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pFunc*  
 추가 하는 함수에 대 한 포인터입니다.  
  
 `dw`  
 사용자 정의 데이터 함수에 전달 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="catlmodule"></a>CAtlModule::CAtlModule  
 생성자입니다.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>설명  
 데이터 멤버를 초기화 하 고 모듈의 스레드 주위 임계 영역을 시작 합니다.  
  
##  <a name="dtor"></a>CAtlModule:: ~ CAtlModule  
 소멸자입니다.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>설명  
 모든 데이터 멤버를 해제합니다.  
  
##  <a name="getgitptr"></a>CAtlModule::GetGITPtr  
 전역 인터페이스 테이블에 대 한 포인터를 검색합니다.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ppGIT`  
 전역 인터페이스 테이블에 대 한 포인터를 수신할 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 코드를 반환합니다. E_POINTER 반환 됩니다 `ppGIT` NULL과 같습니다.  
  
### <a name="remarks"></a>설명  
 전역 인터페이스 테이블 개체가 존재 하지 않는, 카탈로그 항목이 생성 된 해당 주소 멤버 변수에 저장 되어 있으면 [CAtlModule::m_pGIT](#m_pgit)합니다.  
  
 경우 디버그 빌드에 어설션 오류가 발생 합니다 `ppGIT` NULL과 같으면 아니면 전역 인터페이스 테이블 포인터를 가져올 수 없습니다.  
  
 참조 [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) 전역 인터페이스 테이블에 대 한 내용은 합니다.  
  
##  <a name="getlockcount"></a>CAtlModule::GetLockCount  
 잠금 수를 반환합니다.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>반환 값  
 잠금 수를 반환합니다. 이 값은 디버깅 및 진단에 대 한 유용한 수 있습니다.  
  
##  <a name="lock"></a>CAtlModule::Lock  
 잠금 수를 증가 시킵니다.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 잠금 수를 증가 하 고 업데이트 된 값을 반환 합니다. 이 값은 디버깅 및 진단에 대 한 유용한 수 있습니다.  
  
##  <a name="m_libid"></a>CAtlModule::m_libid  
 현재 모듈의 GUID를 포함 합니다.  
  
```
static GUID m_libid;
```  
  
##  <a name="m_pgit"></a>CAtlModule::m_pGIT  
 전역 인터페이스 테이블에 대 한 포인터입니다.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="term"></a>CAtlModule::Term  
 모든 데이터 멤버를 해제합니다.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>설명  
 모든 데이터 멤버를 해제합니다. 이 메서드는 소멸자에서 호출 됩니다.  
  
##  <a name="unlock"></a>CAtlModule::Unlock  
 잠금 횟수를 줄입니다.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 잠금 횟수를 감소 하 고 업데이트 된 값을 반환 합니다. 이 값은 디버깅 및 진단에 대 한 유용한 수 있습니다.  
  
##  <a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD  
 등록 하거나 등록 취소할 개체를 지정된 된 리소스에 포함 된 스크립트를 실행 합니다.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceD(
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceD(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszRes`  
 리소스 이름입니다.  
  
 `nResID`  
 리소스 id입니다.  
  
 `bRegister`  
 **True 이면** 개체; 등록 해야 하는 경우 **FALSE** 그렇지 않은 경우.  
  
 `pMapEntries`  
 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 모듈 % %를 자동으로 사용 합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 로 지정 된 리소스에 포함 된 스크립트를 실행 *lpszRes 또는 nResID*합니다. 경우 `bRegister` 은 **TRUE**,이 메서드는 개체가 시스템 레지스트리에 등록; 레지스트리에서 개체 그렇지 않은 경우 제거 합니다.  
  
 ATL 레지스트리 구성 요소 (등록자)에 정적으로 링크를 참조 [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)합니다.  
  
 이 메서드를 호출 [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) 및 [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister)합니다.  
  
##  <a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
 이 메서드는 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 합니다.  
  
```
inline HRESULT WINAPI UpdateRegistryFromResourceDHelper(  
    LPCOLESTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszRes`  
 리소스 이름입니다.  
  
 `bRegister`  
 개체를 등록할지 여부를 나타냅니다.  
  
 `pMapEntries`  
 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 모듈 % %를 자동으로 사용 합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는의 구현을 제공 [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)합니다.  
  
##  <a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS  
 등록 하거나 등록 취소할 개체를 지정된 된 리소스에 포함 된 스크립트를 실행 합니다. 이 메서드는 정적으로 ATL 레지스트리 구성 요소에 연결합니다.  
  
```
HRESULT WINAPI UpdateRegistryFromResourceS(  
    UINT nResID,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();

HRESULT WINAPI UpdateRegistryFromResourceS(  
    LPCTSTR lpszRes,
    BOOL bRegister,
    struct _ATL_REGMAP_ENTRY* pMapEntries = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `nResID`  
 리소스 id입니다.  
  
 `lpszRes`  
 리소스 이름입니다.  
  
 `bRegister`  
 리소스 스크립트를 등록할지 여부를 나타냅니다.  
  
 `pMapEntries`  
 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 모듈 % %를 자동으로 사용 합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 비슷한 [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) 제외 하 고 `CAtlModule::UpdateRegistryFromResourceS` ATL 레지스트리 구성 요소 (등록자)에 대 한 정적 링크를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)   
 [레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)  
