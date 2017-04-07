---
title: "IObjectSafetyImpl 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
dev_langs:
- C++
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: cdcc008797e94988fb42fd6239603fa300a84233
ms.lasthandoff: 03/31/2017

---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl 클래스
이 클래스의 기본 구현을 제공는 `IObjectSafety` 클라이언트가 검색 한 개체의 보안 수준을 설정 하는 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]에서 실행되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T,DWORD dwSupportedSafety>  
class IObjectSafetyImpl
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IObjectSafetyImpl`합니다.  
  
 *dwSupportedSafety*  
 컨트롤에 대 한 지원 되는 보안 옵션을 지정합니다. 다음 값 중 하나입니다.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_CALLER** 로 식별 된 인터페이스는 [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) 매개 변수 `riid` 스크립트 수 있어야 합니다.  
  
- **INTERFACESAFE_FOR_UNTRUSTED_DATA** 로 식별 된 인터페이스는 `SetInterfaceSafetyOptions` 매개 변수 `riid` 해야 안전 하 게 사용할 신뢰할 수 없는 데이터에 대 한 초기화 하는 동안 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|현재 개체에 대해 설정 안전 옵션 뿐만 아니라 개체에서 지 원하는 보안 옵션을 검색 합니다.|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|개체에 초기화 또는 스크립트에 대 한 안전 하 게 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[IObjectSafetyImpl::m_dwCurrentSafety](#m_dwcurrentsafety)|개체의 현재 보안 수준을 저장합니다.|  
  
## <a name="remarks"></a>주의  
 클래스 `IObjectSafetyImpl` 의 기본 구현을 제공 `IObjectSafety`합니다. `IObjectSafety` 인터페이스 클라이언트가 검색 하 고 개체의 보안 수준을 설정할 수 있습니다. 예를 들어 웹 브라우저 호출할 수 **IObjectSafety::SetInterfaceSafetyOptions** 초기화 또는 스크립트 컨트롤을 조정 하려면.  
  
 사용는 [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) 사용 하 여 매크로 **CATID_SafeForScripting** 및 **CATID_SafeForInitializing** 구성 요소 범주 구성 요소는 안전 하 게 보호를 지정 하는 대체 방법을 설명 합니다.  
  
 **관련 문서** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md), [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlctl.h  
  
##  <a name="getinterfacesafetyoptions"></a>IObjectSafetyImpl::GetInterfaceSafetyOptions  
 현재 개체에 대해 설정 안전 옵션 뿐만 아니라 개체에서 지 원하는 보안 옵션을 검색 합니다.  
  
```
HRESULT GetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```  
  
### <a name="remarks"></a>주의  
 개체의 구현에 의해 지원 되는 모든 인터페이스에 대 한 적절 한 값을 반환 하는 구현 **iunknown:: Queryinterface**합니다.  
  
> [!IMPORTANT]
>  지 원하는 개체 `IObjectSafety` 자체 보안 요구 사항과 위임 하는 모든 개체에 대 한 책임이 있습니다. 프로그래머는 해야 사용자의 컨텍스트에서 코드를 실행할 수 있는 계정 문제를 고려, 사이트 간 스크립팅 및 적합 한 영역 확인을 수행 합니다.  
  
 참조 [IObjectSafety::GetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768223.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="m_dwcurrentsafety"></a>IObjectSafetyImpl::m_dwCurrentSafety  
 개체의 현재 보안 수준을 저장합니다.  
  
```
DWORD m_dwCurrentSafety;
```  
  
##  <a name="setinterfacesafetyoptions"></a>IObjectSafetyImpl::SetInterfaceSafetyOptions  
 개체에 초기화 또는 설정 하 여 스크립트에 대 한 안전 하 게는 [m_dwCurrentSafety](#m_dwcurrentsafety) 적절 한 값으로 멤버입니다.  
  
```
HRESULT SetInterfaceSafetyOptions(  
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```  
  
### <a name="remarks"></a>주의  
 구현은 반환 **E_NOINTERFACE** 개체의 구현에 의해 지원 되지 않습니다 인터페이스에 대해 **iunknown:: Queryinterface**합니다.  
  
> [!IMPORTANT]
>  지 원하는 개체 `IObjectSafety` 자체 보안 요구 사항과 위임 하는 모든 개체에 대 한 책임이 있습니다. 프로그래머는 해야 사용자의 컨텍스트에서 코드를 실행할 수 있는 계정 문제를 고려, 사이트 간 스크립팅 및 적합 한 영역 확인을 수행 합니다.  
  
 참조 [IObjectSafety::SetInterfaceSafetyOptions](https://msdn.microsoft.com/library/aa768225.aspx) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IObjectSafety 인터페이스](https://msdn.microsoft.com/library/aa768224.aspx)   
 [클래스 개요](../../atl/atl-class-overview.md)

