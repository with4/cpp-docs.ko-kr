---
title: "IServiceProviderImpl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
dev_langs:
- C++
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 69a59fe23b3ca787dee86b1bbdc6775a44903f91
ms.lasthandoff: 02/24/2017

---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl 클래스
이 클래스의 기본 구현을 제공는 `IServiceProvider` 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class T>  
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 파생 된 클래스에 `IServiceProviderImpl`합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IServiceProviderImpl::QueryService](#queryservice)|만듭니다 또는 지정된 된 서비스에 액세스 하 고 서비스에 대 한 지정된 된 인터페이스에 대 한 인터페이스 포인터를 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 `IServiceProvider` 인터페이스 해당 GUID로 지정 된 서비스를 찾아서는 서비스에 요청된 된 인터페이스에 대 한 인터페이스 포인터를 반환 합니다. 클래스 `IServiceProviderImpl` 이 인터페이스의 기본 구현을 제공 합니다.  
  
 **IServiceProviderImpl** 하나의 메서드를 지정 합니다: [QueryService](#queryservice), 또는 액세스 하는 지정된 된 서비스를 만들고 서비스에 대 한 지정된 된 인터페이스에 대 한 인터페이스 포인터를 반환 합니다.  
  
 `IServiceProviderImpl`로 시작 하는 서비스 맵을 사용 하 여 [BEGIN_SERVICE_MAP](http://msdn.microsoft.com/library/3c6ae156-8776-4588-8227-2d234daec236) 끝나는 [END_SERVICE_MAP](http://msdn.microsoft.com/library/9a35d02a-014c-413a-bb0b-bcca11ab45a6)합니다.  
  
 두 항목을 포함 하는 서비스 맵을: [SERVICE_ENTRY](http://msdn.microsoft.com/library/e65ff9cc-15e8-41cf-b686-f99eb6686ca9), 개체에서 지원 되는 지정 된 서비스 id (SID)를 나타내는 및 [SERVICE_ENTRY_CHAIN](http://msdn.microsoft.com/library/09be4ce4-3ccd-4ff2-a95e-a9d5275354c1), 되는 호출 `QueryService` 다른 개체에 대 한 체인을 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IServiceProvider`  
  
 `IServiceProviderImpl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="queryservice"></a>IServiceProviderImpl::QueryService  
 만듭니다 또는 지정된 된 서비스에 액세스 하 고 서비스에 대 한 지정된 된 인터페이스에 대 한 인터페이스 포인터를 반환 합니다.  
  
```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 [IN]`guidService`  
 서비스 식별자 (SID)에 대 한 포인터입니다.  
  
 [IN]`riid`  
 호출자를 액세스 하는 인터페이스의 식별자입니다.  
  
 [OUT]`ppvObj`  
 요청된 된 인터페이스에 대 한 간접 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 된 `HRESULT` 값은 다음 중 하나입니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|S_OK|성공적으로 서비스를 만들거나 검색 됩니다.|  
|E_INVALIDARG|하나 이상의 인수가 잘못된 경우|  
|E_OUTOFMEMORY|서비스를 만들 충분 한 메모리가 없습니다.|  
|E_UNEXPECTED|알 수 없는 오류가 발생했습니다.|  
|E_NOINTERFACE|요청된 된 인터페이스가이 서비스의 일부가 아니거나 서비스를 알 수 없습니다.|  
  
### <a name="remarks"></a>주의  
 `QueryService`지정된 된 서비스에 요청된 된 인터페이스에 대 한 간접 포인터를 반환합니다. 호출자에 게는 더 이상 필요한 경우이 포인터를 해제 하는 일을 담당 합니다.  
  
 호출 하는 경우 `QueryService`, 서비스 식별자를 전달 하면 ( `guidService`) 및 인터페이스 식별자 ( `riid`). `guidService` 액세스, 서비스 지정 및 `riid` 서비스의 일부인 인터페이스를 식별 합니다. 반환에서 인터페이스에 대 한 간접 포인터를 나타납니다.  
  
 인터페이스를 구현 하는 개체는 다른 서비스의 일부인 인터페이스를 구현할 수도 있습니다. 다음을 살펴보세요.  
  
-   이러한 인터페이스의 일부 선택적 수 있습니다. 서비스 설명에 정의 된 모든 인터페이스는 반환 된 모든 개체 또는 서비스의 모든 구현에서 반드시 존재 합니다.  
  
-   에 대 한 호출 달리 `QueryInterface`, 다른 서비스 id를 전달 해도 반드시 서로 다른 구성 요소 개체 모델 (COM) 개체를 반환 됩니다.  
  
-   반환 된 개체에는 서비스의 정의 포함 되지 않는 인터페이스를 추가로 있을 수 있습니다.  
  
 SID_SMyService SID_SYourService, 등 두 개의 서비스 둘 다 지정할 수 동일한 인터페이스를 사용 하지만 인터페이스의 구현을 두 서비스 간에 공통 전혀 없을 수 있습니다. 이 방법이 작동 하기 때문에 호출을 `QueryService` (SID_SMyService, IID_IDispatch)는 다른 개체를 반환할 수 `QueryService` (SID_SYourService, IID_IDispatch). 개체 id는 다른 서비스 식별자를 지정 하는 경우 간주 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

