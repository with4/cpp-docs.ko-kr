---
title: "CComAggObject 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComAggObject<contained>
- ATL.CComAggObject
- ATL.CComAggObject<contained>
- CComAggObject
- ATL::CComAggObject
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
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
ms.openlocfilehash: 386ab09418c879c0de0d82d729a3de1b2e270016
ms.lasthandoff: 02/24/2017

---
# <a name="ccomaggobject-class"></a>CComAggObject 클래스
이 클래스를 구현 하는 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 집계 개체에 대 한 인터페이스입니다. 정의 따르면 집합체 외부 개체에 포함 됩니다. `CComAggObject` 클래스는 비슷합니다는 [CComObject 클래스](../../atl/reference/ccomobject-class.md)점을 제외 하 고 외부 클라이언트에 직접 액세스할 수 있는 인터페이스를 노출 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>매개 변수  
 `contained`  
 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)개체에서 지원 하려는 다른 인터페이스와도 같이 합니다.  
  
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
|[CComAggObject::CreateInstance](#createinstance)|이 정적 함수를 사용 하면 새 **CComAggObject** `contained` ** > ** 개체는 오버 헤드 없이 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)합니다.|  
|[CComAggObject::FinalConstruct](#finalconstruct)|최종 초기화를 수행 `m_contained`합니다.|  
|[CComAggObject::FinalRelease](#finalrelease)|최종 소멸 수행 `m_contained`합니다.|  
|[CComAggObject::QueryInterface](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|  
|[CComAggObject::Release](#release)|집계 된 개체의 참조 횟수를 감소 시킵니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|대리자 `IUnknown` 알 수 없는 외부에 대 한 호출 합니다.|  
  
## <a name="remarks"></a>주의  
 `CComAggObject`구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 집계 된 개체입니다. `CComAggObject`에 자체 **IUnknown** 인터페이스를 별도의 외부 개체의 **IUnknown** 인터페이스를 하 고 참조 횟수를 유지 관리 합니다.  
  
 집계에 대 한 자세한 내용은 문서를 참조 하십시오. [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomaggobjectaddref"></a><a name="addref"></a>CComAggObject::AddRef  
 집계 개체에서 참조 횟수를 증가 시킵니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하거나 테스트 될 수 있는 값입니다.  
  
##  <a name="a-nameccomaggobjecta--ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 생성자입니다.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 [in] 외부 알 수 없습니다.  
  
### <a name="remarks"></a>주의  
 초기화는 `CComContainedObject` 멤버 [m_contained](#m_contained), 모듈 잠금 횟수를 증가 시킵니다.  
  
 모듈 잠금 횟수를 소멸자 줄입니다.  
  
##  <a name="a-namedtora--ccomaggobjectccomaggobject"></a><a name="dtor"></a>CComAggObject:: ~ CComAggObject  
 소멸자입니다.  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>주의  
 호출 하는 할당 된 모든 리소스를 해제 [FinalRelease](#finalrelease), 및 모듈 잠금 횟수를 줄입니다.  
  
##  <a name="a-namecreateinstancea--ccomaggobjectcreateinstance"></a><a name="createinstance"></a>CComAggObject::CreateInstance  
 이 정적 함수를 사용 하면 새 **CComAggObject** `contained` ** > ** 개체는 오버 헤드 없이 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)합니다.  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>매개 변수  
 `pp`  
 [out] 에 대 한 포인터는 **CComAggObject\<***포함 된* ** > ** 포인터입니다. 경우 `CreateInstance` 실패 `pp` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 반환 된 개체 참조 개수가&0;, 라고 `AddRef` 사용 하 여 즉시 **릴리스** 를 마치면 개체 포인터에 대 한 참조를 해제 합니다.  
  
 개체에 대 한 액세스도 직접 필요한 수행 하지만 여전히 오버 헤드 없이 새 개체를 만들려고 할 경우 `CoCreateInstance`를 사용 하 여 [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) 대신 합니다.  
  
##  <a name="a-namefinalconstructa--ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 개체 생성의 최종 단계 중에 호출을이 메서드는 최종 초기화에 대해 수행 된 [m_contained](#m_contained) 멤버입니다.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="a-namefinalreleasea--ccomaggobjectfinalrelease"></a><a name="finalrelease"></a>CComAggObject::FinalRelease  
 이 메서드 해제 개체 소멸 하는 동안 호출는 [m_contained](#m_contained) 멤버입니다.  
  
```
void FinalRelease();
```  
  
##  <a name="a-namemcontaineda--ccomaggobjectmcontained"></a><a name="m_contained"></a>CComAggObject::m_contained  
 A [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 클래스에서 파생 된 개체입니다.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>매개 변수  
 `contained`  
 [in] 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)개체에서 지원 하려는 다른 인터페이스와도 같이 합니다.  
  
### <a name="remarks"></a>주의  
 모든 **IUnknown** 을 통해 호출 `m_contained` 알 수 없는 외부에 위임 됩니다.  
  
##  <a name="a-namequeryinterfacea--ccomaggobjectqueryinterface"></a><a name="queryinterface"></a>CComAggObject::QueryInterface  
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
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `iid`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `ppvObject` 로 설정 된 **NULL**합니다.  
  
 `pp`  
 [out] 형식으로 식별 되는 인터페이스 포인터에 대 한 포인터 `Q`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `pp` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 요청한 인터페이스가 있으면 **IUnknown**, `QueryInterface` 집계 된 개체의 자체에 대 한 포인터를 반환 **IUnknown** 참조 횟수를 증가 시킵니다. 이 메서드를 통해 인터페이스에 대 한 쿼리 하는 그렇지 않은 경우는 `CComContainedObject` 멤버 [m_contained](#m_contained)합니다.  
  
##  <a name="a-namereleasea--ccomaggobjectrelease"></a><a name="release"></a>CComAggObject::Release  
 집계 된 개체의 참조 횟수를 감소 시킵니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 디버그 빌드에서 **릴리스** 진단에 유용 하거나 테스트 될 수 있는 값을 반환 합니다. 비-디버그 빌드에서만에서 **릴리스** 항상 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComObject 클래스](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_ONLY_AGGREGATABLE](http://msdn.microsoft.com/library/a54220df-4330-4e4d-b7fb-8b63dd62d337)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [클래스 개요](../../atl/atl-class-overview.md)

