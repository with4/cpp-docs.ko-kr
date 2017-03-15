---
title: "CAtlModule 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAtlModule
- CAtlModule
- ATL.CAtlModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlModule class
ms.assetid: 63fe02f1-4c4b-4e7c-ae97-7ad7b4252415
caps.latest.revision: 19
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
ms.sourcegitcommit: 5a06fc417902378c88e2e65a9b51ee5e4356a39d
ms.openlocfilehash: 75cb5b42cd6c9de14d9abf09b20a1e23716f1149
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodule-class"></a>CAtlModule 클래스
이 클래스는 여러 ATL 모듈 클래스에서 사용 되는 메서드를 제공 합니다.  
  
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
|[CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)|ATL 레지스트리 구성 요소 (등록자) 대체 구조에 매개 변수를 추가 하려면이 메서드를 재정의 합니다.|  
|[CAtlModule::AddTermFunc](#addtermfunc)|종료 될 때 호출 되는 새 함수를 추가 합니다.|  
|[CAtlModule::GetGITPtr](#getgitptr)|글로벌 인터페이스 포인터를 반환합니다.|  
|[CAtlModule::GetLockCount](#getlockcount)|잠금 수를 반환합니다.|  
|[CAtlModule::Lock](#lock)|잠금 수를 증가 시킵니다.|  
|[CAtlModule::Term](#term)|모든 데이터 멤버를 해제합니다.|  
|[CAtlModule::Unlock](#unlock)|잠금 횟수를 줄입니다.|  
|[CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)|지정된 된 리소스를 등록 하거나 개체를 등록 취소에 포함 된 스크립트를 실행 합니다.|  
|[CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper)|이 메서드는 `UpdateRegistryFromResourceD` 레지스트리 업데이트를 수행 합니다.|  
|[CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)|지정된 된 리소스를 등록 하거나 개체를 등록 취소에 포함 된 스크립트를 실행 합니다. 이 메서드는 정적으로 ATL 레지스트리 구성 요소에 연결 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlModule::m_libid](#m_libid)|현재 모듈의 GUID를 포함 합니다.|  
|[CAtlModule::m_pGIT](#m_pgit)|전역 인터페이스 테이블에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 사용 하 여 [CAtlDllModuleT 클래스](../../atl/reference/catldllmodulet-class.md), [CAtlExeModuleT 클래스](../../atl/reference/catlexemodulet-class.md), 및 [CAtlServiceModuleT 클래스](../../atl/reference/catlservicemodulet-class.md) 지원을 제공 하기 위해 DLL, EXE 응용 프로그램 및 Windows 서비스를 각각.  
  
 Atl에서 모듈에 대 한 자세한 내용은 참조 하십시오. [ATL 모듈 클래스](../../atl/atl-module-classes.md)합니다.  
  
 이 클래스는 사용 되지 않는 대신 [CComModule 클래스](../../atl/reference/ccommodule-class.md) ATL.의 이전 버전에서 사용  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  
  
 `CAtlModule`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="a-nameaddcommonrgsreplacementsa--catlmoduleaddcommonrgsreplacements"></a><a name="addcommonrgsreplacements"></a>CAtlModule::AddCommonRGSReplacements  
 ATL 레지스트리 구성 요소 (등록자) 대체 구조에 매개 변수를 추가 하려면이 메서드를 재정의 합니다.  
  
```
virtual HRESULT AddCommonRGSReplacements(IRegistrarBase* /* pRegistrar*/) throw() = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 *pRegistrar*  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 대체 가능 매개 변수 사용 등록자의 클라이언트 런타임 데이터를 지정할 수 있습니다. 이 위해 등록 기관에 연결 된 스크립트에 대 한 대체 가능 매개 변수 값을 입력 하는 대체 맵을 유지 관리 합니다. 등록자는 런타임 시 이러한 항목을 만듭니다.  
  
 항목을 참조 하십시오 [를 사용 하 여 대체 가능 매개 변수 (The 등록자 전처리기)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) 대 한 자세한 내용은 합니다.  
  
##  <a name="a-nameaddtermfunca--catlmoduleaddtermfunc"></a><a name="addtermfunc"></a>CAtlModule::AddTermFunc  
 종료 될 때 호출 되는 새 함수를 추가 합니다.  
  
```
HRESULT AddTermFunc(_ATL_TERMFUNC* pFunc, DWORD_PTR dw) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 *pFunc*  
 추가할 함수에 대 한 포인터입니다.  
  
 `dw`  
 데이터 사용자 정의 함수에 전달 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="a-namecatlmodulea--catlmodulecatlmodule"></a><a name="catlmodule"></a>CAtlModule::CAtlModule  
 생성자입니다.  
  
```
CAtlModule() throw();
```  
  
### <a name="remarks"></a>주의  
 데이터 멤버를 초기화 하 고 모듈의 스레드 주위 중요 섹션을 시작 합니다.  
  
##  <a name="a-namedtora--catlmodulecatlmodule"></a><a name="dtor"></a>CAtlModule:: ~ CAtlModule  
 소멸자입니다.  
  
```
~CAtlModule() throw();
```  
  
### <a name="remarks"></a>주의  
 모든 데이터 멤버를 해제합니다.  
  
##  <a name="a-namegetgitptra--catlmodulegetgitptr"></a><a name="getgitptr"></a>CAtlModule::GetGITPtr  
 전역 인터페이스 테이블에 대 한 포인터를 검색합니다.  
  
```
virtual HRESULT GetGITPtr(IGlobalInterfaceTable** ppGIT) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `ppGIT`  
 전역 인터페이스 테이블에 대 한 포인터를 수신할 변수에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 코드를 반환합니다. E_POINTER 반환 됩니다 `ppGIT` NULL과 같습니다.  
  
### <a name="remarks"></a>주의  
 전역 인터페이스 테이블 개체가 존재 하지 않는, 만들어진 멤버 변수에 해당 주소가 저장 되어 있으면 [CAtlModule::m_pGIT](#m_pgit)합니다.  
  
 디버그 빌드에서 어설션 오류가 발생 하는 경우 발생 합니다 `ppGIT` NULL이 고 같으면 아니면 전역 인터페이스 테이블 포인터를 가져올 수 없습니다.  
  
 참조 [IGlobalInterfaceTable](http://msdn.microsoft.com/library/windows/desktop/ms678517) 전역 인터페이스 테이블에 대 한 내용은 합니다.  
  
##  <a name="a-namegetlockcounta--catlmodulegetlockcount"></a><a name="getlockcount"></a>CAtlModule::GetLockCount  
 잠금 수를 반환합니다.  
  
```
virtual LONG GetLockCount() throw();
```  
  
### <a name="return-value"></a>반환 값  
 잠금 수를 반환합니다. 이 값은 진단에 대 한 유용한 디버깅 수 있습니다.  
  
##  <a name="a-namelocka--catlmodulelock"></a><a name="lock"></a>CAtlModule::Lock  
 잠금 수를 증가 시킵니다.  
  
```
virtual LONG Lock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 잠금 수를 증가 하 고 업데이트 된 값을 반환 합니다. 이 값은 진단에 대 한 유용한 디버깅 수 있습니다.  
  
##  <a name="a-namemlibida--catlmodulemlibid"></a><a name="m_libid"></a>CAtlModule::m_libid  
 현재 모듈의 GUID를 포함 합니다.  
  
```
static GUID m_libid;
```  
  
##  <a name="a-namempgita--catlmodulempgit"></a><a name="m_pgit"></a>CAtlModule::m_pGIT  
 전역 인터페이스 테이블에 대 한 포인터입니다.  
  
```
IGlobalInterfaceTable* m_pGIT;
```  
  
##  <a name="a-nameterma--catlmoduleterm"></a><a name="term"></a>CAtlModule::Term  
 모든 데이터 멤버를 해제합니다.  
  
```
void Term() throw();
```  
  
### <a name="remarks"></a>주의  
 모든 데이터 멤버를 해제합니다. 이 메서드는 소멸자에 의해 호출 됩니다.  
  
##  <a name="a-nameunlocka--catlmoduleunlock"></a><a name="unlock"></a>CAtlModule::Unlock  
 잠금 횟수를 줄입니다.  
  
```
virtual LONG Unlock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 잠금 횟수를 감소 하 고 업데이트 된 값을 반환 합니다. 이 값은 진단에 대 한 유용한 디버깅 수 있습니다.  
  
##  <a name="a-nameupdateregistryfromresourceda--catlmoduleupdateregistryfromresourced"></a><a name="updateregistryfromresourced"></a>CAtlModule::UpdateRegistryFromResourceD  
 지정된 된 리소스를 등록 하거나 개체를 등록 취소에 포함 된 스크립트를 실행 합니다.  
  
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
 **True 이면** 경우 개체를 등록 해야 합니다. **FALSE** 그렇지 않은 경우.  
  
 `pMapEntries`  
 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 모듈 % %를 자동으로 사용합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 지정 하는 리소스에 포함 된 스크립트를 실행 *lpszRes 또는 nResID*합니다. 경우 `bRegister` 는 **TRUE**,이 메서드는 개체의 시스템 레지스트리에 있는 등록, 그렇지 않으면 레지스트리에서 개체를 제거 합니다.  
  
 ATL 레지스트리 구성 요소 (등록자)에 정적으로 링크를 참조 [CAtlModule::UpdateRegistryFromResourceS](#updateregistryfromresources)합니다.  
  
 이 메서드는 호출 [CAtlModule::UpdateRegistryFromResourceDHelper](#updateregistryfromresourcedhelper) 및 [IRegistrar::ResourceUnregister](iregistrar-class.md#resourceunregister)합니다.  
  
##  <a name="a-nameupdateregistryfromresourcedhelpera--catlmoduleupdateregistryfromresourcedhelper"></a><a name="updateregistryfromresourcedhelper"></a>CAtlModule::UpdateRegistryFromResourceDHelper  
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
 개체를 등록 해야 하는지 여부를 나타냅니다.  
  
 `pMapEntries`  
 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 모듈 % %를 자동으로 사용합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는의 구현을 제공 [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced)합니다.  
  
##  <a name="a-nameupdateregistryfromresourcesa--catlmoduleupdateregistryfromresources"></a><a name="updateregistryfromresources"></a>CAtlModule::UpdateRegistryFromResourceS  
 지정된 된 리소스를 등록 하거나 개체를 등록 취소에 포함 된 스크립트를 실행 합니다. 이 메서드는 정적으로 ATL 레지스트리 구성 요소에 연결 합니다.  
  
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
 리소스 스크립트를 등록 해야 하는지 여부를 나타냅니다.  
  
 `pMapEntries`  
 스크립트의 대체 가능 매개 변수와 연결 된 값을 저장 하는 대체 지도에 대 한 포인터입니다. ATL 모듈 % %를 자동으로 사용합니다. 참조 추가 대체 가능 매개 변수를 사용 하려면 [CAtlModule::AddCommonRGSReplacements](#addcommonrgsreplacements)합니다. 그렇지 않은 경우 사용 된 **NULL** 기본값입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 유사한 [CAtlModule::UpdateRegistryFromResourceD](#updateregistryfromresourced) 제외 하 고 `CAtlModule::UpdateRegistryFromResourceS` ATL 레지스트리 구성 요소 (등록자)에 대 한 정적 링크를 만듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)   
 [레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)  

