---
title: "서비스 맵 매크로 | Microsoft 문서"
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
ms.assetid: ca02a125-454a-4cf6-aac2-1c5585025ed4
caps.latest.revision: 16
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
ms.openlocfilehash: eea45a3315237c77eff0231d485111cefb8557cc
ms.lasthandoff: 02/24/2017

---
# <a name="service-map-macros"></a>서비스 맵 매크로
이러한 매크로 서비스 맵 및 항목을 정의합니다.  
  
|||  
|-|-|  
|[BEGIN_SERVICE_MAP](#begin_service_map)|ATL 서비스 맵의 시작을 표시 합니다.|  
|[END_SERVICE_MAP](#end_service_map)|ATL 서비스 맵의 끝을 표시 합니다.|  
|[SERVICE_ENTRY](#service_entry)|개체는 특정 서비스 ID를 지원함을 나타냅니다.|  
|[SERVICE_ENTRY_CHAIN](#service_entry_chain)|지시 [IServiceProviderImpl::QueryService](#queryservice) 지정된 된 개체에 체인으로 연결 합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
   
##  <a name="a-namebeginservicemapa--beginservicemap"></a><a name="begin_service_map"></a>BEGIN_SERVICE_MAP  
 서비스 맵의 시작을 표시 합니다.  
  
```
BEGIN_SERVICE_MAP(theClass)
```  
  
### <a name="parameters"></a>매개 변수  
 `theClass`  
 [in] 서비스 맵을 포함 하는 클래스를 지정 합니다.  
  
### <a name="remarks"></a>주의  
 서비스 맵을 사용 하 여 COM 개체에서 서비스 공급자 기능을 구현 하려면. 클래스를 파생 해야 하는 첫째, [IServiceProviderImpl](../../atl/reference/iserviceproviderimpl-class.md)합니다. 두 가지 유형의 항목이 있습니다.  
  
- [SERVICE_ENTRY](#service_entry) ID (SID)를 지정 된 서비스에 대 한 지원을 나타냅니다.  
  
- [SERVICE_ENTRY_CHAIN](#service_entry_chain) 하도록 [IServiceProviderImpl::QueryService](#queryservice) 다른, 지정 된 개체에 체인으로 연결 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#57;](../../atl/codesnippet/cpp/service-map-macros_1.h)]  
  
##  <a name="a-nameendservicemapa--endservicemap"></a><a name="end_service_map"></a>END_SERVICE_MAP  
 서비스 맵의 끝을 표시 합니다.  
  
```
END_SERVICE_MAP()
```  
  
### <a name="example"></a>예제  
 예를 참조 [BEGIN_SERVICE_MAP](#begin_service_map)합니다.  
  
##  <a name="a-nameserviceentrya--serviceentry"></a><a name="service_entry"></a>SERVICE_ENTRY  
 개체에 지정 된 서비스 id를 지원함을 나타냅니다 *SID*합니다.  
  
```
SERVICE_ENTRY( SID )
```  
  
### <a name="parameters"></a>매개 변수  
 *SID*  
 서비스 id입니다.  
  
### <a name="example"></a>예제  
 예를 참조 [BEGIN_SERVICE_MAP](#begin_service_map)합니다.  
  
##  <a name="a-nameserviceentrychaina--serviceentrychain"></a><a name="service_entry_chain"></a>SERVICE_ENTRY_CHAIN  
 지시 [IServiceProviderImpl::QueryService](#queryservice) 가 지정한 개체에 대 한 체인을 `punk`합니다.  
  
```
SERVICE_ENTRY_CHAIN( punk )
```  
  
### <a name="parameters"></a>매개 변수  
 `punk`  
 에 대 한 포인터는 **IUnknown** 인터페이스를 체인으로 연결 합니다.  
  
### <a name="example"></a>예제  
 예를 참조 [BEGIN_SERVICE_MAP](#begin_service_map)합니다.  
  
##  <a name="a-namequeryservicea--iserviceproviderimplqueryservice"></a><a name="queryservice"></a>IServiceProviderImpl::QueryService  
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
 [매크로](../../atl/reference/atl-macros.md)

