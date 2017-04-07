---
title: "CAtlModuleT 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
dev_langs:
- C++
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 9c0c6a2302932df06db7166d83fe9a561dfe38ac
ms.lasthandoff: 02/24/2017

---
# <a name="catlmodulet-class"></a>CAtlModuleT 클래스
이 클래스는 ATL 모듈을 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스에서 파생 된 `CAtlModuleT`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CAtlModuleT::InitLibId](#initlibid)|현재 모듈의 GUID가 포함 된 데이터 멤버를 초기화 합니다.|  
|[CAtlModuleT::RegisterAppId](#registerappid)|EXE를 레지스트리에 추가 합니다.|  
|[CAtlModuleT::RegisterServer](#registerserver)|레지스트리에 서비스를 추가합니다.|  
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|레지스트리에서 exe 파일을 제거합니다.|  
|[CAtlModuleT::UnregisterServer](#unregisterserver)|레지스트리에서 서비스를 제거합니다.|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|레지스트리의 EXE 정보를 업데이트합니다.|  
  
## <a name="remarks"></a>주의  
 `CAtlModuleT`에서 파생 된 [CAtlModule](../../atl/reference/catlmodule-class.md), 실행 파일 (EXE) 또는 서비스 (EXE) ATL 모듈을 구현 합니다. 반면 서비스 모듈은 Windows가 시작 될 때 백그라운드에서 실행 되는 Windows 응용 프로그램 실행 모듈은 로컬에서 작업 중이 아닌 서버.  
  
 `CAtlModuleT`초기화 하 고, 등록 및 모듈의 등록을 취소에 대 한 지원을 제공 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="catlmodulet"></a>CAtlModuleT::CAtlModuleT  
 생성자입니다.  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>주의  
 호출 [CAtlModuleT::InitLibId](#initlibid)합니다.  
  
##  <a name="initlibid"></a>CAtlModuleT::InitLibId  
 현재 모듈의 GUID가 포함 된 데이터 멤버를 초기화 합니다.  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>주의  
 생성자에서 호출 [CAtlModuleT::CAtlModuleT](#catlmodulet)합니다.  
  
##  <a name="registerappid"></a>CAtlModuleT::RegisterAppId  
 EXE를 레지스트리에 추가 합니다.  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="registerserver"></a>CAtlModuleT::RegisterServer  
 레지스트리에 서비스를 추가합니다.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegTypeLib`  
 형식 라이브러리를 등록 하면 TRUE입니다. 기본값은 FALSE입니다.  
  
 `pCLSID`  
 등록할 개체의 CLSID 가리킵니다. NULL (기본값), 개체 맵의 모든 개체를 등록할 경우.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="unregisterappid"></a>CAtlModuleT::UnregisterAppId  
 레지스트리에서 exe 파일을 제거합니다.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="unregisterserver"></a>CAtlModuleT::UnregisterServer  
 레지스트리에서 서비스를 제거합니다.  
  
```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bUnRegTypeLib`  
 형식 라이브러리 등록을 취소할 이기도 한 경우 TRUE입니다.  
  
 `pCLSID`  
 등록 취소할 개체의 CLSID 가리킵니다. NULL (기본값), 개체 맵의 모든 개체는가 등록 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="updateregistryappid"></a>CAtlModuleT::UpdateRegistryAppId  
 레지스트리의 EXE 정보를 업데이트합니다.  
  
```
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegister`  
 예약됨.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAtlModule 클래스](../../atl/reference/catlmodule-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [모듈 클래스](../../atl/atl-module-classes.md)

