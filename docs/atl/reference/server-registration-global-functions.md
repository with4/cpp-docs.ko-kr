---
title: "서버 등록에 대 한 전역 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: c2f0a35d-857c-4538-a44d-c4ea0db63b06
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 4ace3bb50d824827071260e3f43cec3cda32742f
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="server-registration-global-functions"></a>서버 등록에 대 한 전역 함수
이러한 함수를 등록 하 고 개체 맵의 서버 개체를 등록 취소에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수에서 실행 되는 응용 프로그램에서 사용할 수 없습니다는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]합니다.  
  
|||  
|-|-|  
|[AtlComModuleRegisterServer](#atlcommoduleregisterserver)|이 함수는 개체 맵의 모든 개체를 등록하기 위해 호출됩니다.|  
|[AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)|이 함수는 개체 맵의 모든 개체를 등록 취소하기 위해 호출됩니다.|  
|[AtlComModuleRegisterClassObjects](#atlcommoduleregisterclassobjects)|이 함수는 클래스 개체를 등록하기 위해 호출됩니다.|  
|[AtlComModuleRevokeClassObjects](#atlcommodulerevokeclassobjects)|이 함수는 COM 모듈에서 클래스 개체를 해지 하 라고 합니다.|  
|[AtlComModuleGetClassObject](#atlcommodulegetclassobject)|이 함수는 클래스 개체를 가져오는 데 호출 됩니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  
   
##  <a name="atlcommoduleregisterserver"></a>AtlComModuleRegisterServer  
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
 형식 라이브러리를 등록 하면 TRUE입니다.  
  
 `pCLSID`  
 등록할 개체의 CLSID 가리킵니다. NULL 인 경우에 개체 맵의 모든 개체 등록 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 `AtlComModuleRegisterServer`ATL 자동 생성 된 개체 맵의 안내 하 고 지도에 각 개체를 등록 합니다. 경우 `pCLSID` 가 NULL이 아니면에서 참조 하는 개체에만 `pCLSID` 등록 됩니다; 그렇지 않은 경우 등록 된 모든 개체입니다.  
  
 이 함수를 호출 하 [CAtlComModule::RegisterServer](catlcommodule-class.md#registerserver)합니다.  
  
##  <a name="atlcommoduleunregisterserver"></a>AtlComModuleUnregisterServer  
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
 형식 라이브러리를 등록 하면 TRUE입니다.  
  
 `pCLSID`  
 등록 취소할 개체의 CLSID 가리킵니다. Null 인 경우 개체 맵의 모든 개체 등록 취소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 `AtlComModuleUnregisterServer`ATL 개체 맵의 안내 및 지도 있는 각 개체의 등록을 취소 합니다. 경우 `pCLSID` 가 NULL이 아니면에서 참조 하는 개체에만 `pCLSID` 등록 취소 하 고, 그렇지 않으면 모든 개체의 등록이 취소 됩니다.  
  
 이 함수를 호출 하 [CAtlComModule::UnregisterServer](catlcommodule-class.md#unregisterserver)합니다.  
  
##  <a name="atlcommoduleregisterclassobjects"></a>AtlComModuleRegisterClassObjects  
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
 클래스 개체를 실행할 수의 컨텍스트를 지정 합니다. 가능한 값은 위해 CLSCTX_INPROC_SERVER, CLSCTX_INPROC_HANDLER, 또는 CLSCTX_LOCAL_SERVER입니다. 참조 [CLSCTX](http://msdn.microsoft.com/library/windows/desktop/ms693716) 대 한 자세한 내용은 합니다.  
  
 `dwFlags`  
 클래스 개체에 연결 형식을 결정합니다. 가능한 값은 REGCLS_SINGLEUSE, REGCLS_MULTIPLEUSE, 또는 REGCLS_MULTI_SEPARATE입니다. 참조 [REGCLS](http://msdn.microsoft.com/library/windows/desktop/ms679697) 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 도우미 함수를 사용 하 여 [CComModule::RegisterClassObjects](ccommodule-class.md#registerclassobjects) (ATL 7.0에 사용 되지 않음) 및 [CAtlExeModuleT::RegisterClassObjects](catlexemodulet-class.md#registerclassobjects)합니다.  
  
##  <a name="atlcommodulerevokeclassobjects"></a>AtlComModuleRevokeClassObjects  
 이 함수는 실행 개체 테이블에서 클래스 팩터리를 제거하기 위해 호출됩니다.  
  
```
ATLINLINE ATLAPI AtlComModuleRevokeClassObjects(_ATL_COM_MODULE* pComModule);
```  
  
### <a name="parameters"></a>매개 변수  
 `pComModule`  
 COM 모듈에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 도우미 함수를 사용 하 여 [CComModule::RevokeClassObjects](ccommodule-class.md#revokeclassobjects) (ATL 7.0에 사용 되지 않음) 및 [CAtlExeModuleT::RevokeClassObjects](catlexemodulet-class.md#revokeclassobjects)합니다.  
  
##  <a name="atlcommodulegetclassobject"></a>AtlComModuleGetClassObject  
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
 로 식별 되는 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `ppv` NULL로 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 도우미 함수를 사용 하 여 [CComModule::GetClassObject](ccommodule-class.md#getclassobject) (ATL 7.0에 사용 되지 않음) 및 [CAtlDllModuleT::GetClassObject](catldllmodulet-class.md#getclassobject)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)

