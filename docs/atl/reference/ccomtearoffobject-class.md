---
title: "CComTearOffObject 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComTearOffObject
- ATLCOM/ATL::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::CComTearOffObject
- ATLCOM/ATL::CComTearOffObject::AddRef
- ATLCOM/ATL::CComTearOffObject::QueryInterface
- ATLCOM/ATL::CComTearOffObject::Release
- ATLCOM/ATL::CComTearOffObjectBase
- ATLCOM/ATL::m_pOwner
dev_langs:
- C++
helpviewer_keywords:
- tear-off interfaces, ATL
- tear-off interfaces
- CComTearOffObject class
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 3e8e997f26df1adca8050bd4d967a38297685831
ms.lasthandoff: 02/24/2017

---
# <a name="ccomtearoffobject-class"></a>CComTearOffObject 클래스
이 클래스는 분리 인터페이스를 구현합니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class Base>
class CComTearOffObject : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 분리 클래스에서 파생 된 `CComTearOffObjectBase` 중이 고 인터페이스 지원 하기 위해 분리 개체입니다.  
  
 두 단계로 분리 인터페이스를 구현 하는 ATL-는 `CComTearOffObjectBase` 메서드는 참조 횟수를 처리 및 `QueryInterface`, 동안 `CComTearOffObject` 구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509)합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComTearOffObject::CComTearOffObject](#ccomtearoffobject)|생성자입니다.|  
|[CComTearOffObject:: ~ CComTearOffObject](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComTearOffObject::AddRef](#addref)|에 대 한 참조 횟수를 증가 `CComTearOffObject` 개체입니다.|  
|[CComTearOffObject::QueryInterface](#queryinterface)|분리 클래스 또는 소유자 클래스에서 요청된 된 인터페이스에 대 한 포인터를 반환합니다.|  
|[CComTearOffObject::Release](#release)|에 대 한 참조 횟수를 감소는 `CComTearOffObject` 개체를 삭제 합니다.|  
  
### <a name="ccomtearoffobjectbase-methods"></a>CComTearOffObjectBase 메서드  
  
|||  
|-|-|  
|[CComTearOffObjectBase](#ccomtearoffobjectbase)|생성자입니다.|  
  
### <a name="ccomtearoffobjectbase-data-members"></a>CComTearOffObjectBase 데이터 멤버  
  
|||  
|-|-|  
|[m_pOwner](#m_powner)|에 대 한 포인터는 `CComObject` 소유자 클래스에서 파생 됩니다.|  
  
## <a name="remarks"></a>주의  
 `CComTearOffObject`해당 인터페이스 쿼리 하는 경우에 인스턴스화될는 별도 개체로 분리 인터페이스를 구현 합니다. 참조 횟수가&0; 인 경우는 분리 삭제 됩니다. 일반적으로 거의 사용 되지 않는 기본 개체의 모든 인스턴스에 대 한 vtable 포인터를 저장 한 분리를 사용 하 여 이후 하는 인터페이스에 대 한 분리 인터페이스를 빌드할 수 있습니다.  
  
 분리에서 구현 하는 클래스를 파생 시켜야 `CComTearOffObjectBase` 지원 하기 위해 분리 개체 원하는 어떤 인터페이스에서 합니다. `CComTearOffObjectBase`소유자 클래스와 스레드 모델에 템플릿 화 됩니다. 소유자 클래스에 있는 한 분리 구현 되는 개체의 클래스가입니다. 스레드 모델을 지정 하지 않으면 기본 스레드 모델이 사용 됩니다.  
  
 분리 클래스에 대 한 COM 맵을 만들어야 합니다. ATL 인스턴스화하는 분리 하면 생기게 됩니다 **CComTearOffObject\<CYourTearOffClass >** 또는 **CComCachedTearOffObject\<CYourTearOffClass >**합니다.  
  
 예를 들어, 호출기 샘플에에서는 `CBeeper2` 클래스는 분리 클래스 및 `CBeeper` 클래스는 소유자 클래스:  
  
 [!code-cpp[NVC_ATL_COM&#43;](../../atl/codesnippet/cpp/ccomtearoffobject-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `CComTearOffObject`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="addref"></a>CComTearOffObject::AddRef  
 참조 횟수를 증가 `CComTearOffObject` 하나는 개체입니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하 고 테스트 될 수 있는 값입니다.  
  
##  <a name="ccomtearoffobject"></a>CComTearOffObject::CComTearOffObject  
 생성자입니다.  
  
```
CComTearOffObject(void* pv);
```  
  
### <a name="parameters"></a>매개 변수  
 `pv`  
 [in] 포인터에 대 한 포인터로 변환 되는 **CComObject\<소유자 >** 개체입니다.  
  
### <a name="remarks"></a>주의  
 소유자의 참조 횟수가&1; 씩 증가 시킵니다.  
  
##  <a name="dtor"></a>CComTearOffObject:: ~ CComTearOffObject  
 소멸자입니다.  
  
```
~CComTearOffObject();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제 하 고 감소 FinalRelease, 모듈을 호출, 잠글 수 있습니다.  
  
##  <a name="ccomtearoffobjectbase"></a>CComTearOffObject::CComTearOffObjectBase  
 생성자입니다.  
  
```
CComTearOffObjectBase();
```  
  
### <a name="remarks"></a>주의  
 초기화는 [m_pOwner](#m_powner) 멤버를 **NULL**합니다.  
  
##  <a name="m_powner"></a>CComTearOffObject::m_pOwner  
 에 대 한 포인터는 [CComObject](../../atl/reference/ccomobject-class.md) 에서 파생 된 개체 *소유자*합니다.  
  
```
CComObject<Owner>* m_pOwner;
```  
  
### <a name="parameters"></a>매개 변수  
 *소유자*  
 [in] 한 분리 구현 되는 클래스입니다.  
  
### <a name="remarks"></a>주의  
 에 포인터가 초기화 되 **NULL** 생성 중입니다.  
  
##  <a name="queryinterface"></a>CComTearOffObject::QueryInterface  
 요청된 인터페이스에 대한 포인터를 검색합니다.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 요청 된 인터페이스의 IID입니다.  
  
 `ppvObject`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `iid`, 또는 **NULL** 인터페이스를 찾을 수 없는 경우.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 분리 클래스에서 인터페이스에 먼저를 쿼리합니다. 인터페이스가 없는 경우, 소유자 개체의 인터페이스에 대 한 쿼리 합니다. 요청한 인터페이스가 있으면 **IUnknown**, 반환 된 **IUnknown** 소유자의 합니다.  
  
##  <a name="release"></a>CComTearOffObject::Release  
 참조 횟수를&1; 씩 감소 하 고, 참조 횟수가&0; 인 경우 삭제는 `CComTearOffObject`합니다.  
  
```
STDMETHOD_ULONG Release();
```  
  
### <a name="return-value"></a>반환 값  
 비-디버그 빌드에서만에서 항상&0;을 반환 합니다. 디버그 빌드에서 진단에 유용 하거나 테스트 될 수 있는 값을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComCachedTearOffObject 클래스](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

