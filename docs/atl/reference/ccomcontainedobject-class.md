---
title: "CComContainedObject 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComContainedObject
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 60958f328d78205c3432f35ed4e3e3c4b652ebfe
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcontainedobject-class"></a>CComContainedObject 클래스
이 클래스는 구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 소유자 개체에 위임 하 여 **IUnknown**합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class Base>  
class CComContainedObject : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|생성자입니다. 소유자 개체에 대 한 멤버 포인터를 초기화 `IUnknown`합니다.|  
|[CComContainedObject:: ~ CComContainedObject](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComContainedObject::AddRef](#addref)|소유자 개체의 참조 횟수를 증가 시킵니다.|  
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|소유자 개체의 검색 `IUnknown`합니다.|  
|[CComContainedObject::QueryInterface](#queryinterface)|소유자 개체에 대해 요청 된 인터페이스에 대 한 포인터를 검색 합니다.|  
|[CComContainedObject::Release](#release)|소유자 개체의 참조 횟수를 감소 시킵니다.|  
  
## <a name="remarks"></a>주의  
 사용 하 여 ATL `CComContainedObject` 클래스에서 [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), 및 [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)합니다. `CComContainedObject`구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 소유자 개체에 위임 하 여 **IUnknown**합니다. (소유자가 생성 되는 분리 인터페이스는 개체 또는 집계의 외부 개체입니다.) `CComContainedObject` 호출 `CComObjectRootEx`의 `OuterQueryInterface`, `OuterAddRef`, 및 `OuterRelease`를 통해 상속 된 모든, `Base`합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `CComContainedObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="a-nameaddrefa--ccomcontainedobjectaddref"></a><a name="addref"></a>CComContainedObject::AddRef  
 소유자 개체의 참조 횟수를 증가 시킵니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하거나 테스트 될 수 있는 값입니다.  
  
##  <a name="a-nameccomcontainedobjecta--ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a>CComContainedObject::CComContainedObject  
 생성자입니다.  
  
```
CComContainedObject(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 [in] 소유자 개체의 **IUnknown**합니다.  
  
### <a name="remarks"></a>주의  
 설정의 `m_pOuterUnknown` 멤버 포인터 (통해 상속는 `Base` 클래스)를 `pv`합니다.  
  
##  <a name="a-namedtora--ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a>CComContainedObject:: ~ CComContainedObject  
 소멸자입니다.  
  
```
~CComContainedObject();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="a-namegetcontrollingunknowna--ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a>CComContainedObject::GetControllingUnknown  
 반환 된 `m_pOuterUnknown` 멤버 포인터 (통해 상속는 *자료* 클래스) 소유자 개체를 보유 하는 **IUnknown**합니다.  
  
```
IUnknown* GetControllingUnknown();
```  
  
### <a name="return-value"></a>반환 값  
 소유자 개체의 **IUnknown**합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 가상 일 수 있음 경우 `Base` 가 선언 된 [DECLARE_GET_CONTROLLING_UNKNOWN](http://msdn.microsoft.com/library/82b0199a-a9d5-4f95-a711-fa1ae18e1f77) 매크로입니다.  
  
##  <a name="a-namequeryinterfacea--ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a>CComContainedObject::QueryInterface  
 소유자 개체에 대해 요청 된 인터페이스에 대 한 포인터를 검색 합니다.  
  
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
  
##  <a name="a-namereleasea--ccomcontainedobjectrelease"></a><a name="release"></a>CComContainedObject::Release  
 소유자 개체의 참조 횟수를 감소 시킵니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 디버그 빌드에서 **릴리스** 진단에 유용 하거나 테스트 될 수 있는 값을 반환 합니다. 비-디버그 빌드에서만에서 **릴리스** 항상 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

