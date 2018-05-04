---
title: 레지스트리 매크로 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed9b172217f1ca7ada7d8752151126b53055df37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="registry-macros"></a>레지스트리 매크로
이러한 매크로 유용한 형식 라이브러리 및 레지스트리 시설을 정의 합니다.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Atl에 기반한 종속성을 방지 하기 위해 개체에 포함 되도록 개체에 대 한 등록 코드 합니다. DLL입니다.|  
|[DECLARE_LIBID](#declare_libid)|ATL 가져올 수 있는 방법을 제공는 *libid* 형식 라이브러리의 합니다.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|기본 ATL 등록을 방지할 수 있습니다.|  
|[DECLARE_REGISTRY](#declare_registry)|가 입력 또는 시스템 레지스트리에 주요 개체의 항목을 제거 합니다.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|자동으로 등록 하는 데 필요한 정보를 지정 된 *appid*합니다.|  
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|명명 된 리소스를 찾아 그 안에 레지스트리 스크립트를 실행 합니다.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|ID 번호로 식별 되는 리소스를 찾아 그 안에 레지스트리 스크립트를 실행 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY  
 Atl에 기반한 종속성을 방지 하기 위해 개체에 포함 되도록 개체에 대 한 등록 코드가 필요한 경우를 나타내는 기호 DLL입니다.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>설명  
 정의 하는 경우 **ATL_STATIC_REGISTRY**, 다음 코드를 사용 해야 합니다.  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="declare_libid"></a>  DECLARE_LIBID  
 ATL 가져올 수 있는 방법을 제공는 *libid* 형식 라이브러리의 합니다.  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>매개 변수  
 *libid*  
 형식 라이브러리의 GUID입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `DECLARE_LIBID` 에 `CAtlModuleT`-클래스를 파생 합니다.  
  
### <a name="example"></a>예제  
 ATL 프로젝트 마법사에서 생성 된 아닌 특성을 사용이 매크로 사용 하는 예제를 갖습니다.  
  
##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY  
 사용 하 여 `DECLARE_NO_REGISTRY` 이 매크로 표시 되는 클래스에 대 한 기본 ATL 등록을 방지 하려는 경우.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>  DECLARE_REGISTRY  
 시스템 레지스트리에 표준 클래스 등록을 입력 하거나 시스템 레지스트리에서 제거 합니다.  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>매개 변수  
 `class`  
 [in] 이전 버전과 호환성을 위해 포함 됩니다.  
  
 `pid`  
 [in] `LPCTSTR` 버전별 프로그램 식별자입니다.  
  
 *vpid*  
 [in] `LPCTSTR` 버전 독립 프로그램 식별자입니다.  
  
 *nid*  
 [in] A **UINT** 프로그램 설명으로 사용 하도록 레지스트리를에 리소스 문자열의 인덱스입니다.  
  
 `flags`  
 [in] A `DWORD` 프로그램을 포함 하의 스레딩 모델 레지스트리에 합니다. 다음 값 중 하나 여야 합니다: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, 또는 **AUTPRXFLAG**합니다.  
  
### <a name="remarks"></a>설명  
 표준 등록 CLSID, 프로그램 ID, 버전 독립 프로그램 ID, 설명 문자열 및 스레드 모델 구성 됩니다.  
  
 ATL 클래스 추가 마법사를 사용 하 여 제어할 또는 개체를 만들 때 마법사 자동으로 레지스트리 스크립트 기반 지원을 구현 하 고 추가 [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) 파일에는 매크로입니다. 사용 하 여이 매크로 교체 해야 하는 경우 레지스트리 스크립트 기반 지원 하지 않으려면 `DECLARE_REGISTRY`합니다. `DECLARE_REGISTRY` 만 레지스트리에 위에서 설명한 5 개의 기본 키를 삽입 합니다. 다른 키를 레지스트리에 삽입 하는 코드를 직접 작성 해야 합니다.  
  
##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID  
 자동으로 등록 하는 데 필요한 정보를 지정 된 *appid*합니다.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>매개 변수  
 *resid*  
 에 대 한 정보를 포함 하는.rgs 파일의 리소스 id는 *appid*합니다.  
  
 *appid*  
 GUID  
  
### <a name="remarks"></a>설명  
 사용 하 여 `DECLARE_REGISTRY_APPID_RESOURCEID` 에 `CAtlModuleT`-클래스를 파생 합니다.  
  
### <a name="example"></a>예제  
 클래스 추가 코드 마법사로 ATL 프로젝트에 추가 되는 클래스가이 매크로 사용 하는 예제를 갖습니다.  
  
##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE  
 레지스트리 파일을 포함 하는 명명 된 리소스를 가져오고 개체를 시스템 레지스트리에 입력 하거나 시스템 레지스트리에서 제거 스크립트를 실행 합니다.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 문자열 리소스의 식별자입니다.  
  
### <a name="remarks"></a>설명  
 ATL 프로젝트 마법사를 사용 하 여 제어할 또는 개체를 만들 때 마법사는 자동으로 레지스트리 스크립트 기반 지원을 구현 하 고 추가 [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) 비슷한 매크로 `DECLARE_REGISTRY_RESOURCE`, 프로그램 파일입니다.  
  
 ATL 레지스트리 구성 요소 (등록자) 최적화 레지스트리 액세스에 대 한 정적으로 연결할 수 있습니다. 등록 기관 코드에 정적으로 링크를 하려면 stdafx.h 파일에 다음 줄을 추가 합니다.  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 ATL을 런타임 시 대체 값으로 대체 하려는 경우를 지정 하지 않으면는 `DECLARE_REGISTRY_RESOURCE` 또는 `DECLARE_REGISTRY_RESOURCEID` 매크로입니다. 대신, 배열을 만든 **_ATL_REGMAP_ENTRIES** 런타임에 자리 표시자를 바꿀 값 쌍을 이루는 구조, 각 항목에 변수 자리 표시자를 포함 합니다. 그런 다음 호출 [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) 또는 [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), 배열을 전달 합니다. 대체 값의 모든 추가이 **_ATL_REGMAP_ENTRIES** 등록자의 대체 지도에 구조입니다.  

  
 대체 가능 매개 변수 및 스크립트에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.  
  
##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID  
 와 동일 [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) 마법사에서 생성 된 사용 하 여 **UINT** 문자열 이름 대신는 리소스를 식별 하 합니다.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>매개 변수  
 *x*  
 [in] 마법사에서 생성 한 리소스의 식별자입니다.  
  
### <a name="remarks"></a>설명  
 ATL 프로젝트 마법사를 사용 하 여 제어할 또는 개체를 만들 때 마법사는 자동으로 레지스트리 스크립트 기반 지원을 구현 하 고 추가 된 `DECLARE_REGISTRY_RESOURCEID` 파일에는 매크로입니다.  
  
 ATL 레지스트리 구성 요소 (등록자) 최적화 레지스트리 액세스에 대 한 정적으로 연결할 수 있습니다. 등록 기관 코드에 정적으로 링크를 하려면 stdafx.h 파일에 다음 줄을 추가 합니다.  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 ATL을 런타임 시 대체 값으로 대체 하려는 경우를 지정 하지 않으면는 `DECLARE_REGISTRY_RESOURCE` 또는 `DECLARE_REGISTRY_RESOURCEID` 매크로입니다. 대신, 배열을 만든 **_ATL_REGMAP_ENTRIES** 런타임에 자리 표시자를 바꿀 값 쌍을 이루는 구조, 각 항목에 변수 자리 표시자를 포함 합니다. 그런 다음 호출 [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) 또는 [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), 배열을 전달 합니다. 대체 값의 모든 추가이 **_ATL_REGMAP_ENTRIES** 등록자의 대체 지도에 구조입니다.  

  
 대체 가능 매개 변수 및 스크립트에 대 한 자세한 내용은 문서 참조 [ATL 레지스트리 구성 요소 (등록자)](../../atl/atl-registry-component-registrar.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [매크로](../../atl/reference/atl-macros.md)
