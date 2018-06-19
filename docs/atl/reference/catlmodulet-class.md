---
title: CAtlModuleT 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29088c56d7020b38febb96be7512771a258e25fe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361690"
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
|[CAtlModuleT::UnregisterServer](#unregisterserver)|레지스트리에 서비스를 제거합니다.|  
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|레지스트리의 EXE 정보를 업데이트합니다.|  
  
## <a name="remarks"></a>설명  
 `CAtlModuleT`에서 파생 된 [CAtlModule](../../atl/reference/catlmodule-class.md), 실행 파일 (EXE) 이나 서비스 (EXE) ATL 모듈을 구현 합니다. 반면 서비스 모듈은 Windows가 시작 될 때 백그라운드에서 실행 되는 Windows 응용 프로그램을 실행 모듈은 로컬 작업 중이 아닌 서버, 합니다.  
  
 `CAtlModuleT` 초기화 하 고 등록 하 고 모듈의 등록을 취소를 지원을 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [_ATL_MODULE](atl-typedefs.md#_atl_module)  

  
 [CAtlModule](../../atl/reference/catlmodule-class.md)  
  
 `CAtlModuleT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
  
##  <a name="catlmodulet"></a>  CAtlModuleT::CAtlModuleT  
 생성자입니다.  
  
```
CAtlModuleT() throw();
```  
  
### <a name="remarks"></a>설명  
 호출 [CAtlModuleT::InitLibId](#initlibid)합니다.  
  
##  <a name="initlibid"></a>  CAtlModuleT::InitLibId  
 현재 모듈의 GUID가 포함 된 데이터 멤버를 초기화 합니다.  
  
```
static void InitLibId() throw();
```  
  
### <a name="remarks"></a>설명  
 생성자에서 호출 [CAtlModuleT::CAtlModuleT](#catlmodulet)합니다.  
  
##  <a name="registerappid"></a>  CAtlModuleT::RegisterAppId  
 EXE를 레지스트리에 추가 합니다.  
  
```
HRESULT RegisterAppId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="registerserver"></a>  CAtlModuleT::RegisterServer  
 레지스트리에 서비스를 추가합니다.  
  
```
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bRegTypeLib`  
 TRUE 이면 형식 라이브러리를 등록 해야입니다. 기본값은 FALSE입니다.  
  
 `pCLSID`  
 등록할 개체의 CLSID 가리킵니다. 개체 맵의 모든 개체 NULL (기본값) 하는 경우 등록 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="unregisterappid"></a>  CAtlModuleT::UnregisterAppId  
 레지스트리에서 exe 파일을 제거합니다.  
  
```
HRESULT UnregisterAppId() throw();
```  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="unregisterserver"></a>  CAtlModuleT::UnregisterServer  
 레지스트리에 서비스를 제거합니다.  
  
```
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `bUnRegTypeLib`  
 TRUE 이면 형식 라이브러리 등록을 취소할 수도입니다.  
  
 `pCLSID`  
 등록을 취소할 개체의 CLSID 가리킵니다. 경우 NULL (기본값), 개체 맵의 모든 개체를 등록 취소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
##  <a name="updateregistryappid"></a>  CAtlModuleT::UpdateRegistryAppId  
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
