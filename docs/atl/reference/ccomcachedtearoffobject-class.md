---
title: "CComCachedTearOffObject 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComCachedTearOffObject
- ATL.CComCachedTearOffObject
- ATL.CComCachedTearOffObject<contained>
- CComCachedTearOffObject
- ATL::CComCachedTearOffObject<contained>
dev_langs:
- C++
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
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
ms.openlocfilehash: 96f040c732c5545a9b8febb32fcb1636f0fe4a40
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject 클래스
이 클래스는 구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 인터페이스의 분리 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template
 <class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
 ::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>매개 변수  
 `contained`  
 분리 클래스에서 파생 된 `CComTearOffObjectBase` 중이 고 인터페이스 지원 하기 위해 분리 개체입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|생성자입니다.|  
|[CComCachedTearOffObject:: ~ CComCachedTearOffObject](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComCachedTearOffObject::AddRef](#addref)|에 대 한 참조 횟수를 증가 `CComCachedTearOffObject` 개체입니다.|  
|[CComCachedTearOffObject::FinalConstruct](#finalconstruct)|호출 된 `m_contained::FinalConstruct` (분리 클래스의 메서드).|  
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|호출 된 `m_contained::FinalRelease` (분리 클래스의 메서드).|  
|[CComCachedTearOffObject::QueryInterface](#queryinterface)|에 대 한 포인터를 반환 된 `IUnknown` 의 `CComCachedTearOffObject` 개체 또는 분리 클래스에서 요청된 된 인터페이스에 (클래스 `contained`).|  
|[CComCachedTearOffObject::Release](#release)|에 대 한 참조 횟수를 감소는 `CComCachedTearOffObject` 개체 및 참조 횟수가 0 이면 삭제 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComCachedTearOffObject::m_contained](#m_contained)|A `CComContainedObject` 분리 클래스에서 파생 된 개체 (클래스 `contained`).|  
  
## <a name="remarks"></a>주의  
 `CComCachedTearOffObject`구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 인터페이스의 분리 합니다. 이 클래스에서 다른 `CComTearOffObject` 한다는 점에서 `CComCachedTearOffObject` 에 자체 **IUnknown**소유자 개체와에서는 별도로 **IUnknown** (소유자의 분리는 만들 대상 개체를가 하는 데 사용). `CComCachedTearOffObject`자체 유지 관리에 참조 횟수의 **IUnknown** 하 고 참조 횟수가&0;이 되 면 자체를 삭제 합니다. 그러나 해당 분리 중 하나에 대 한 쿼리 하는 경우 인터페이스를 소유자 개체의 참조 횟수 **IUnknown** 증가 됩니다.  
  
 하는 경우는 `CComCachedTearOffObject` 개체는 분리 구현 이미 인스턴스화되고 분리 인터페이스 쿼리 하는 다시 동일한 `CComCachedTearOffObject` 개체가 다시 사용 됩니다. 반대로, 분리 인터페이스를 구현한 경우에 `CComTearOffObject` 다시 쿼리 하는 소유자 개체를 통해 다른 `CComTearOffObject` 인스턴스화할 수 있습니다.  
  
 소유자 클래스를 구현 해야 `FinalRelease` 호출 **릴리스** 에 캐시 된 **IUnknown** 에 대 한는 `CComCachedTearOffObject`는 참조 횟수를 감소 합니다. 이 인해 `CComCachedTearOffObject`의 `FinalRelease` 에 호출 되 고 삭제 된 분리 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomcachedtearoffobjectaddref"></a><a name="addref"></a>CComCachedTearOffObject::AddRef  
 참조 횟수를 증가 `CComCachedTearOffObject` 1 개체입니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하 고 테스트 될 수 있는 값입니다.  
  
##  <a name="a-nameccomcachedtearoffobjecta--ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a>CComCachedTearOffObject::CComCachedTearOffObject  
 생성자입니다.  
  
```
CComCachedTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 [in] 에 대 한 포인터는 **IUnknown** 의 `CComCachedTearOffObject`합니다.  
  
### <a name="remarks"></a>주의  
 초기화는 `CComContainedObject` 멤버 [m_contained](#m_contained)합니다.  
  
##  <a name="a-namedtora--ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a>CComCachedTearOffObject:: ~ CComCachedTearOffObject  
 소멸자입니다.  
  
```
~CComCachedTearOffObject();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제 하는 호출 [FinalRelease](#finalrelease)합니다.  
  
##  <a name="a-namefinalconstructa--ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a>CComCachedTearOffObject::FinalConstruct  
 호출 **m_contained::FinalConstruct** 만들려는 `m_contained`, `CComContainedObject` <  `contained`> 분리 클래스에서 구현 된 인터페이스에 액세스 하는 데 사용 되는 개체입니다.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="a-namefinalreleasea--ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a>CComCachedTearOffObject::FinalRelease  
 호출 **m_contained::FinalRelease** 를 무료로 `m_contained`, `CComContainedObject` <  `contained`> 개체입니다.  
  
```
void FinalRelease();
```  
  
##  <a name="a-namemcontaineda--ccomcachedtearoffobjectmcontained"></a><a name="m_contained"></a>CComCachedTearOffObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 분리 클래스에서 파생 된 개체입니다.  
  
```
CcomContainedObject <contained> m_contained;
```     
  
### <a name="parameters"></a>매개 변수  
 `contained`  
 [in] 분리 클래스에서 파생 된 `CComTearOffObjectBase` 중이 고 인터페이스 지원 하기 위해 분리 개체입니다.  
  
### <a name="remarks"></a>주의  
 메서드 `m_contained` 상속 되는 개체를 통해 캐시 된 분리의 분리 클래스에 분리 인터페이스에 액세스 하는 데 사용 됩니다 `QueryInterface`, `FinalConstruct`, 및 `FinalRelease`합니다.  
  
##  <a name="a-namequeryinterfacea--ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a>CComCachedTearOffObject::QueryInterface  
 요청된 인터페이스에 대한 포인터를 검색합니다.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 요청 된 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `iid`, 또는 **NULL** 인터페이스를 찾을 수 없는 경우.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 요청한 인터페이스가 있으면 **IUnknown**에 대 한 포인터를 반환 합니다.는 `CComCachedTearOffObject`의 자체 **IUnknown** 참조 횟수를 증가 시킵니다. 그렇지 않은 경우 사용 하 여 분리 클래스에 인터페이스에 대 한 쿼리는 [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) 에서 상속 된 `CComObjectRootEx`합니다.  

  
##  <a name="a-namereleasea--ccomcachedtearoffobjectrelease"></a><a name="release"></a>CComCachedTearOffObject::Release  
 참조 횟수를 1 씩 감소 하 고, 참조 횟수가 0 이면 삭제는 `CComCachedTearOffObject` 개체입니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 비-디버그 빌드에서만에서 항상 0을 반환 합니다. 디버그 빌드에서 진단에 유용 하거나 테스트 될 수 있는 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComTearOffObject 클래스](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

