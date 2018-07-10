---
title: CComAggObject 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 426a01c1957b276174b8b36884605b69dd501de8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364221"
---
# <a name="ccomaggobject-class"></a>CComAggObject 클래스
이 클래스가 구현 하는 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 집계 개체에 대 한 인터페이스입니다. 정의 따르면 집계 개체는 외부 개체 안에 포함 됩니다. `CComAggObject` 클래스는 비슷합니다는 [CComObject 클래스](../../atl/reference/ccomobject-class.md)제외 하 고 외부 클라이언트에 직접 액세스할 수 있는 인터페이스를 노출 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>매개 변수  
 `contained`  
 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지원할 하려는 다른 인터페이스와도 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|생성자입니다.|  
|[CComAggObject:: ~ CComAggObject](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|집계 개체에서 참조 횟수를 증가 시킵니다.|  
|[CComAggObject::CreateInstance](#createinstance)|이 정적 함수를 사용 하면 새 **CComAggObject <** `contained` **>** 개체는 오버 헤드 없이 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)합니다.|  
|[CComAggObject::FinalConstruct](#finalconstruct)|최종 초기화를 수행 `m_contained`합니다.|  
|[CComAggObject::FinalRelease](#finalrelease)|최종 소멸 수행 `m_contained`합니다.|  
|[CComAggObject::QueryInterface](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|  
|[CComAggObject::Release](#release)|집계 개체에 대 한 참조 횟수를 줄입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|대리자 `IUnknown` 알 수 없는 외부에 대 한 호출입니다.|  
  
## <a name="remarks"></a>설명  
 `CComAggObject` 구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 집계 개체에 대 한 합니다. `CComAggObject` 에 자체 **IUnknown** 인터페이스를 외부 개체의 별도로 **IUnknown** , 인터페이스 및 참조 횟수를 유지 관리 합니다.  
  
 집계에 대 한 자세한 내용은 문서 참조 [ATL COM 개체 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="addref"></a>  CComAggObject::AddRef  
 집계 개체에서 참조 횟수를 증가 시킵니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 대 한 유용한 또는 테스트 수 있는 값입니다.  
  
##  <a name="ccomaggobject"></a>  CComAggObject::CComAggObject  
 생성자입니다.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 [in] 외부 알 수 없습니다.  
  
### <a name="remarks"></a>설명  
 초기화는 `CComContainedObject` 멤버 [m_contained](#m_contained), 모듈의 잠금 횟수를 증가 시킵니다.  
  
 모듈 잠금 횟수를 소멸자 줄입니다.  
  
##  <a name="dtor"></a>  CComAggObject:: ~ CComAggObject  
 소멸자입니다.  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>설명  
 호출 하는 할당 된 모든 리소스를 해제 [FinalRelease](#finalrelease), 및 모듈 잠금 횟수를 줄입니다.  
  
##  <a name="createinstance"></a>  CComAggObject::CreateInstance  
 이 정적 함수를 사용 하면 새 **CComAggObject <** `contained` **>** 개체는 오버 헤드 없이 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)합니다.  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>매개 변수  
 `pp`  
 [out] 에 대 한 포인터는 **CComAggObject\<* * * 포함 된* **>** 포인터입니다. 경우 `CreateInstance` 실패 `pp` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 반환 되는 개체에는 참조 횟수가 0, 없으므로 호출 `AddRef` 즉시을 사용 하 여 **릴리스** 를 마치면 개체 포인터에 대 한 참조를 해제 합니다.  
  
 직접 필요 않는 개체에 액세스할 수 있지만 여전히 오버 헤드 없이 새 개체를 만들려고 할 경우 `CoCreateInstance`를 사용 하 여 [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) 대신 합니다.  
  
##  <a name="finalconstruct"></a>  CComAggObject::FinalConstruct  
 개체 생성의 최종 단계 중 호출이 메서드는 최종 초기화에 대해 수행 된 [m_contained](#m_contained) 멤버입니다.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="finalrelease"></a>  CComAggObject::FinalRelease  
 이 메서드 해제 개체 소멸 하는 동안 호출 된 [m_contained](#m_contained) 멤버입니다.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>  CComAggObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 클래스에서 파생 된 개체입니다.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>매개 변수  
 `contained`  
 [in] 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지원할 하려는 다른 인터페이스와도 합니다.  
  
### <a name="remarks"></a>설명  
 모든 **IUnknown** 통해 호출 `m_contained` 알 수 없는 외부으로 위임 됩니다.  
  
##  <a name="queryinterface"></a>  CComAggObject::QueryInterface  
 요청된 인터페이스에 대한 포인터를 검색합니다.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 요청 된 인터페이스의 식별자입니다.  
  
 `ppvObject`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `iid`합니다. 개체가이 인터페이스를 지원 하지 않는 경우 `ppvObject` 로 설정 된 **NULL**합니다.  
  
 `pp`  
 [out] 형식으로 식별 된 인터페이스 포인터에 대 한 포인터 `Q`합니다. 개체가이 인터페이스를 지원 하지 않는 경우 `pp` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 요청한 인터페이스가 **IUnknown**, `QueryInterface` 집계 된 개체의 자체에 대 한 포인터를 반환 **IUnknown** 참조 횟수를 증가 시킵니다. 그렇지 않으면이 메서드를 통해 인터페이스에 대 한 쿼리는 `CComContainedObject` 멤버 [m_contained](#m_contained)합니다.  
  
##  <a name="release"></a>  CComAggObject::Release  
 집계 개체에 대 한 참조 횟수를 줄입니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 디버그 빌드에서 **릴리스** 진단에 대 한 유용한 또는 테스트 수 있는 값을 반환 합니다. 디버그가 아닌 빌드에서 **릴리스** 항상 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComObject 클래스](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)   
 [DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)   
 [DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)   
 [클래스 개요](../../atl/atl-class-overview.md)
