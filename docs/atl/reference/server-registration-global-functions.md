---
title: 서버 등록 전역 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlComModuleRegisterServer
- atlbase/ATL::AtlComModuleUnregisterServer
- atlbase/ATL::AtlComModuleRegisterClassObjects
- atlbase/ATL::AtlComModuleRevokeClassObjects
- atlbase/ATL::AtlComModuleGetClassObject
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08a4141ab5ff27e44f663a4d5f267c2b7d754283
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364707"
---
# <a name="server-registration-global-functions"></a>서버 등록 전역 함수
이러한 함수를 등록 하 고 개체 맵의 서버 개체를 등록 취소에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|이 함수는 개체 맵의 모든 개체를 등록하기 위해 호출됩니다.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|이 함수는 개체 맵의 모든 개체를 등록 취소하기 위해 호출됩니다.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|이 함수는 클래스 개체를 등록하기 위해 호출됩니다.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|COM 모듈에서 클래스 개체를 해지 하려면이 함수 호출 됩니다.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|이 함수는 클래스 개체를 가져오기 위해 호출 됩니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>  AtlComModuleRegisterServer  
 이 함수는 개체 맵의 모든 개체를 등록하기 위해 호출됩니다.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>매개 변수  
 `pComModule`  
 COM 모듈에 대 한 포인터입니다.  
  
 `bRegTypeLib`  
 TRUE 이면 형식 라이브러리를 등록 해야입니다.  
  
 `pCLSID`  
 등록할 개체의 CLSID 가리킵니다. NULL 인 경우에 개체 맵의 모든 개체 등록 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 `AtlComModuleRegisterServer` ATL 자동 생성 된 개체 지도에서는 지도에서 각 개체를 등록 합니다. 경우 `pCLSID` 가 NULL이 아니면 참조 하는 개체에만 `pCLSID` 등록 됩니다; 그렇지 않은 경우 등록 된 모든 개체.  
  
 이 함수를 호출 하 [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)합니다.  
  
##  <a name="atlcommoduleunregisterserver"></a>  AtlComModuleUnregisterServer  
 이 함수는 개체 맵의 모든 개체를 등록 취소하기 위해 호출됩니다.  
  
```
ATLINLINE ATLAPI AtlComModuleUnregisterServer(
    _ATL_COM_MODULE* pComModule,
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID);
```  
  
### <a name="parameters"></a>매개 변수  
 `pComModule`  
 COM 모듈에 대 한 포인터입니다.  
  
 `bUnRegTypeLib`  
 TRUE 이면 형식 라이브러리를 등록 해야입니다.  
  
 `pCLSID`  
 등록을 취소할 개체의 CLSID 가리킵니다. Null 인 경우 개체 맵의 모든 개체 등록 됩니다 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 `AtlComModuleUnregisterServer` ATL 개체 맵의 안내 하 고 지도 있는 각 개체의 등록을 취소 합니다. 경우 `pCLSID` 가 NULL이 아니면 참조 하는 개체에만 `pCLSID` 등록 되지 않은 상태가 아니면 등록 되지 않은 모든 개체.  
  
 이 함수를 호출 하 [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver)합니다.  
  
##  <a name="atlcommoduleregisterclassobjects"></a>  AtlComModuleRegisterClassObjects  
 이 함수는 클래스 개체를 등록하기 위해 호출됩니다.  
  
```
ATLINLINE ATLAPI AtlComModuleRegisterClassObjects(
    _ATL_COM_MODULE* pComModule,
    DWORD dwClsContext,
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 `pComModule`  
 COM 모듈에 대 한 포인터입니다.  
  
 `dwClsContext`  
 클래스 개체를 실행할의 컨텍스트를 지정 합니다. 가능한 값은 위해 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER, 또는 CLSCTX_LOCAL_SERVER입니다. 참조 [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) 내용을 확인 합니다.  
  
 `dwFlags`  
 클래스 개체에 연결 형식을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE, 또는 REGCLS_MULTI_SEPARATE입니다. 참조 [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) 내용을 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 도우미 함수를 사용 하 여 [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7.0에서 사용 되지 않음) 및 [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)합니다.  
  
##  <a name="atlcommodulerevokeclassobjects"></a>  AtlComModuleRevokeClassObjects  
 이 함수는 실행 개체 테이블에서 클래스 팩터리를 제거하기 위해 호출됩니다.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>매개 변수  
 `pComModule`  
 COM 모듈에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 도우미 함수를 사용 하 여 [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7.0에서 사용 되지 않음) 및 [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects)합니다.  
  
##  <a name="atlcommodulegetclassobject"></a>  AtlComModuleGetClassObject  
 이 함수는 클래스 팩터리를 반환하기 위해 호출됩니다.  
  
```
ATLINLINE ATLAPI AtlComModuleGetClassObject(
    _ATL_COM_MODULE* pComModule,
    REFCLSID rclsid,
    REFIID riid,
    LPVOID* ppv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pComModule`  
 COM 모듈에 대 한 포인터입니다.  
  
 `rclsid`  
 만들 개체의 CLSID입니다.  
  
 `riid`  
 요청된 된 인터페이스의 IID입니다.  
  
 `ppv`  
 로 식별 되는 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체가이 인터페이스를 지원 하지 않는 경우 `ppv` NULL로 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 도우미 함수를 사용 하 여 [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0에서 사용 되지 않음) 및 [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)
