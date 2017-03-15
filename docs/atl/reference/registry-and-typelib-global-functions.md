---
title: "레지스트리 및 TypeLib 전역 함수 | Microsoft 문서"
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
- RegistryDataExchange function, global functions
ms.assetid: d58b8a4e-975c-4417-8b34-d3c847f679b3
caps.latest.revision: 22
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
ms.openlocfilehash: 9d454f2eac1b29785fe40a480fc43c7c34a861a3
ms.lasthandoff: 02/24/2017

---
# <a name="registry-and-typelib-global-functions"></a>레지스트리 및 TypeLib 전역 함수
이러한 함수에 로드 하 고 형식 라이브러리를 등록에 대 한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수에서 실행 되는 응용 프로그램에서 사용할 수 없습니다는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]합니다.  
  
|||  
|-|-|  
|[AtlRegisterTypeLib](#atlregistertypelib)|이 함수는 형식 라이브러리를 등록하기 위해 호출됩니다.|  
|[AtlUnRegisterTypeLib](#atlunregistertypelib)|이 함수는 형식 라이브러리 등록을 취소 하 라고 합니다.|  
|[AtlLoadTypeLib](#atlloadtypelib)|이 함수는 형식 라이브러리를 로드하기 위해 호출됩니다.|  
|[AtlUpdateRegistryFromResourceD](#atlupdateregistryfromresourced)|이 함수는 제공된 리소스에서 레지스트리를 업데이트하기 위해 호출됩니다.|  
|[RegistryDataExchange](#registrydataexchange)|이 함수는 시스템 레지스트리에서 읽거나 쓰기 위해 호출됩니다. 에 의해 호출 된 [레지스트리 데이터 교환 매크로](../../atl/reference/registry-data-exchange-macros.md)합니다.|  
  
 이러한 함수는 레지스트리 정보를 저장 하는 프로그램에 사용 하 여 노드를 제어 합니다.  
  
|||  
|-|-|  
|[AtlGetPerUserRegistration](#atlgetperuserregistration)|응용 프로그램에 대 한 레지스트리 액세스 리디렉션하는지 여부를 검색 된 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|  
|[AtlSetPerUserRegistration](#atlsetperuserregistration)|응용 프로그램에 대 한 레지스트리 액세스 리디렉션하는지 여부를 설정 하는 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h

## <a name="a-nameatlgetperuserregistrationa-atlgetperuserregistration"></a><a name="atlgetperuserregistration"></a>AtlGetPerUserRegistration
이 함수를 사용 하 여 응용 프로그램에 대 한 레지스트리 액세스 리디렉션하는지 여부를 확인 하는 **HKEY_CURRENT_USER** (**HKCU**) 노드.  
  
### <a name="syntax"></a>구문  
  
```  
ATLINLINE ATLAPI AtlGetPerUserRegistration(bool* pEnabled);  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `pEnabled`  
 `TRUE`나타냅니다 레지스트리 정보가 전송 되는 **HKCU** 노드; `FALSE` 나타냅니다 응용 프로그램 기본 노드를 레지스트리 정보를 씁니다. 기본 노드는 **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>반환 값  
 `S_OK`그렇지 않으면 메서드는 성공 하는 경우는 `HRESULT` 오류가 발생 하는 경우 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 레지스트리 리디렉션 기본적으로 사용 되지 않습니다. 이 옵션을 사용 하면 레지스트리 액세스 되 리디렉션됩니다 **HKEY_CURRENT_USER\Software\Classes**합니다.  
  
 리디렉션의 전역있지 않습니다. 이 레지스트리 리디렉션은 MFC 및 ATL 프레임 영향을 받습니다.  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

##  <a name="a-nameatlregistertypeliba--atlregistertypelib"></a><a name="atlregistertypelib"></a>AtlRegisterTypeLib  
 이 함수는 형식 라이브러리를 등록하기 위해 호출됩니다.  
  
  
```
ATLAPI AtlRegisterTypeLib(HINSTANCE hInstTypeLib, LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstTypeLib`  
 모듈 인스턴스에 대 한 핸들입니다.  
  
 `lpszIndex`  
 형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다. 인덱스가 없는 해야 하는 경우에 NULL 일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 도우미 함수를 사용 하 여 [AtlComModuleUnregisterServer](server-registration-global-functions.md#atlcommoduleunregisterserver) 및 [CAtlComModule::RegisterTypeLib](../../atl/reference/catlcommodule-class.md#registertypelib)합니다.  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h

## <a name="a-nameatlsetperuserregistrationa-atlsetperuserregistration"></a><a name="atlsetperuserregistration"></a>AtlSetPerUserRegistration
응용 프로그램에 대 한 레지스트리 액세스 리디렉션하는지 여부를 설정 하는 **HKEY_CURRENT_USER** (**HKCU**) 노드.  
  
### <a name="syntax"></a>구문  
  
```  
ATLINLINE ATLAPI AtlSetPerUserRegistration(bool bEnable);  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`나타냅니다 레지스트리 정보가 전송 되는 **HKCU** 노드; `FALSE` 나타냅니다 응용 프로그램 기본 노드를 레지스트리 정보를 씁니다. 기본 노드는 **HKEY_CLASSES_ROOT** (**HKCR**).  
  
### <a name="return-value"></a>반환 값  
 `S_OK`그렇지 않으면 메서드는 성공 하는 경우는 `HRESULT` 오류가 발생 하는 경우 오류 코드입니다.  
  
### <a name="remarks"></a>주의  
 레지스트리 리디렉션 기본적으로 사용 되지 않습니다. 이 옵션을 사용 하면 레지스트리 액세스 되 리디렉션됩니다 **HKEY_CURRENT_USER\Software\Classes**합니다.  
  
 리디렉션의 전역있지 않습니다. 이 레지스트리 리디렉션은 MFC 및 ATL 프레임 영향을 받습니다.  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h  

##  <a name="a-nameatlunregistertypeliba--atlunregistertypelib"></a><a name="atlunregistertypelib"></a>AtlUnRegisterTypeLib  
 이 함수는 형식 라이브러리를 등록 취소하기 위해 호출됩니다.  
  
### <a name="syntax"></a>구문  
```
ATLAPI AtlUnRegisterTypeLib(
    HINSTANCE hInstTypeLib, 
    LPCOLESTR lpszIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstTypeLib`  
 모듈 인스턴스에 대 한 핸들입니다.  
  
 `lpszIndex`  
 형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다. 인덱스가 없는 해야 하는 경우에 NULL 일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 도우미 함수를 사용 하 여 [CAtlComModule::UnRegisterTypeLib](../../atl/reference/catlcommodule-class.md#unregistertypelib) 및 [AtlComModuleUnregisterServer](#atlcommoduleunregisterserver)합니다.  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h

##  <a name="a-nameatlloadtypeliba--atlloadtypelib"></a><a name="atlloadtypelib"></a>AtlLoadTypeLib  
 이 함수는 형식 라이브러리를 로드하기 위해 호출됩니다.  
  
### <a name="syntax"></a>구문  
```
ATLINLINE ATLAPI AtlLoadTypeLib(
    HINSTANCE hInstTypeLib,
    LPCOLESTR lpszIndex,
    BSTR* pbstrPath,
    ITypeLib** ppTypeLib);
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstTypeLib`  
 형식 라이브러리와 연결 된 모듈에 대 한 핸들입니다.  
  
 `lpszIndex`  
 형식에서 문자열 "\\\N", 여기서 N은 정수 인덱스 형식 라이브러리 리소스입니다. 인덱스가 없는 해야 하는 경우에 NULL 일 수 있습니다.  
  
 *pbstrPath*  
 반환이 성공적 이면 형식 라이브러리와 연결 된 모듈의 전체 경로 포함 합니다.  
  
 `ppTypeLib`  
 반환이 성공적 이면 로드 된 형식 라이브러리에 대 한 포인터에 대 한 포인터를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 도우미 함수를 사용 하 여 [AtlRegisterTypeLib](#atlregistertypelib) 및 [AtlUnRegisterTypeLib](#atlunregistertypelib)합니다.  
  
##  <a name="a-nameatlupdateregistryfromresourceda--atlupdateregistryfromresourced"></a><a name="atlupdateregistryfromresourced"></a>AtlUpdateRegistryFromResourceD  
 이 함수는 Visual Studio 2013에서 사용이 중단되었으며, Visual Studio 2015에서 제거되었습니다.  
  
```
<removed>
```  
  
### <a name="parameters"></a>매개 변수  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameregistrydataexchangea--registrydataexchange"></a><a name="registrydataexchange"></a>RegistryDataExchange  
 이 함수는 시스템 레지스트리에서 읽거나 쓰기 위해 호출됩니다.  

### <a name="syntax"></a>구문  
```
HRESULT RegistryDataExchange(
    T* pT,
    enum RDXOperations rdxOp,
    void* pItem = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 *pT*  
 현재 개체에 대 한 포인터입니다.  
  
 *rdxOp*  
 작업을 나타내는 열거형 값의 함수를 수행 해야 합니다. 허용 되는 값에 대 한 설명 섹션의 표를 참조 하십시오.  
  
 `pItem`  
 읽기, 또는 레지스트리에 쓸 수 있는 데이터에 대 한 포인터입니다. 데이터를 레지스트리에서 삭제할 키를 나타낼 수도 있습니다. 기본값은 NULL입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 S_OK 또는 실패 시 오류 HRESULT 반환합니다.  
  
### <a name="remarks"></a>주의  
 매크로 [BEGIN_RDX_MAP](registry-data-exchange-macros.md#begin_rdx_map) 및 [END_RDX_MAP](registry-data-exchange-macros.md#end_rdx_map) 호출 하는 함수를 확장 하 고 `RegistryDataExchange`합니다.  
  
 함수가 작업을 수행 해야 함을 나타내는 가능한 열거형 값은 다음과에서 같습니다.  
  
|열거형 값|작업|  
|----------------|---------------|  
|eReadFromReg|레지스트리에서 데이터를 읽습니다.|  
|eWriteToReg|레지스트리 데이터를 씁니다.|  
|eDeleteFromReg|레지스트리에서 키를 삭제 합니다.|  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlbase.h

## <a name="see-also"></a>참고 항목  
 [함수](atl-functions.md)
 [레지스트리 데이터 교환 매크로](registry-data-exchange-macros.md)






