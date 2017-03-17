---
title: "CComObject 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObject
- ATLCOM/ATL::CComObject
- ATLCOM/ATL::CComObject::CComObject
- ATLCOM/ATL::CComObject::AddRef
- ATLCOM/ATL::CComObject::CreateInstance
- ATLCOM/ATL::CComObject::QueryInterface
- ATLCOM/ATL::CComObject::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5f752b96d4a722fbddfcc9e5be3a82b8b12a86a1
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobject-class"></a>CComObject 클래스
이 클래스는 구현 **IUnknown** 집계 개체에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)개체에서 지원 하려는 다른 인터페이스와도 같이 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|생성자입니다.|  
|[CComObject:: ~ CComObject](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|개체에서 참조 횟수를 증가 시킵니다.|  
|[CComObject::CreateInstance](#createinstance)|(정적) 새로 만듭니다 `CComObject` 개체입니다.|  
|[CComObject::QueryInterface](#queryinterface)|요청된 인터페이스에 대한 포인터를 검색합니다.|  
|[CComObject::Release](#release)|개체에 대 한 참조 횟수를 감소 시킵니다.|  
  
## <a name="remarks"></a>주의  
 `CComObject`구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 집계 개체에 대 한 합니다. 그러나에 대 한 호출이 `QueryInterface`, `AddRef`, 및 **릴리스** 에 위임 되며 `CComObjectRootEx`합니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CComObject`, 문서를 참조 하십시오 [ATL COM 개체의 기본 사항](../../atl/fundamentals-of-atl-com-objects.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="addref"></a>CComObject::AddRef  
 개체에서 참조 횟수를 증가 시킵니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 이 함수는 개체에 새 증가 참조 횟수를 반환합니다. 이 값은 진단 또는 테스트 유용할 수 있습니다.  
  
##  <a name="ccomobject"></a>CComObject::CComObject  
 생성자는 모듈 잠금 횟수를 증가 시킵니다.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 **void\***  
 [in] 이 명명 되지 않은 매개 변수가 사용 되지 않습니다. 다른 대칭 있는 **CCom***XXX*`Object`*XXX* 생성자입니다.  
  
### <a name="remarks"></a>주의  
 소멸자 감소 것입니다.  
  
 하는 경우는 `CComObject`-파생 된 개체를 사용 하 여 성공적으로 생성 되는 **새** 연산자, 초기 참조 횟수는 0입니다. 적절 한 값 (1)을 참조 횟수를 설정 하려면를 호출 하 여 [AddRef](#addref) 함수입니다.  
  
##  <a name="dtor"></a>CComObject:: ~ CComObject  
 소멸자입니다.  
  
```
CComObject();
```  
  
### <a name="remarks"></a>주의  
 호출 하는 할당 된 모든 리소스를 해제 [FinalRelease](ccomobjectrootex-class.md#finalrelease), 및 모듈 잠금 횟수를 줄입니다.  

  
##  <a name="createinstance"></a>CComObject::CreateInstance  
 이 정적 함수를 사용 하면 새 **CComObject** `Base` ** > ** 오버 헤드 없이 개체 [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615)합니다.  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>매개 변수  
 `pp`  
 [out] 에 대 한 포인터는 **CComObject** `Base` ** > ** 포인터입니다. 경우 `CreateInstance` 실패 `pp` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 반환 된 개체 참조 개수가&0;, 라고 `AddRef` 사용 하 여 즉시 **릴리스** 를 마치면 개체 포인터에 대 한 참조를 해제 합니다.  
  
 개체에 대 한 액세스도 직접 필요한 수행 하지만 여전히 오버 헤드 없이 새 개체를 만들려고 할 경우 `CoCreateInstance`를 사용 하 여 [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) 대신 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_ATL_COM&#38;](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM&#39;](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="release"></a>CComObject::Release  
 개체에 대 한 참조 횟수를 감소 시킵니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 이 함수는 개체에 새 감소 참조 횟수를 반환합니다. 디버그 빌드에서 반환 값에는 진단에 유용 하거나 테스트 수 있습니다. 비-디버그 빌드에서만에서 **릴리스** 항상 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject 클래스](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [클래스 개요](../../atl/atl-class-overview.md)

