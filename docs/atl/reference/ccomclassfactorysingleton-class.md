---
title: "CComClassFactorySingleton 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
caps.latest.revision: 21
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
ms.openlocfilehash: 55d8fb96dfce1b278763cc348c605f8e76b5f56f
ms.lasthandoff: 03/31/2017

---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton 클래스
이 클래스에서 파생 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 생성 합니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 클래스입니다.  
  
 `CComClassFactorySingleton`파생 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 사용 하 여 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 단일 개체를 생성 합니다. 호출할 때마다는 `CreateInstance` 메서드 단순히 인터페이스 포인터에 대 한이 개체를 쿼리 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](#createinstance)|쿼리 `m_spObj` 인터페이스 포인터에 대 한 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 하 여 생성 된 개체 `CComClassFactorySingleton`합니다.|  
  
## <a name="remarks"></a>설명  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)를 선언 하는 `CComClassFactory` 기본 클래스 팩터리로 합니다. 사용 하도록 `CComClassFactorySingleton`, 지정는 [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) 개체의 클래스 정의에 매크로입니다. 예:  
  
 [!code-cpp[#10 NVC_ATL_COM](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactorySingleton::CreateInstance  
 호출 `QueryInterface` 통해 [m_spObj](#m_spobj) 인터페이스 포인터를 검색 합니다.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>매개 변수  
 `pUnkOuter`  
 [in] 개체를 만드는 경우, 집계의 일환으로 다음 `pUnkOuter` 알 수 없는 외부 이어야 합니다. 그렇지 않으면 `pUnkOuter` 해야 **NULL**합니다.  
  
 `riid`  
 [in] 요청된 된 인터페이스의 IID입니다. 경우 `pUnkOuter` 이 아닌 **NULL**, `riid` 해야 **IID_IUnknown**합니다.  
  
 `ppvObj`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `riid`합니다. 개체가이 인터페이스를 지원 하지 않는 경우 `ppvObj` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="m_spobj"></a>CComClassFactorySingleton::m_spObj  
 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 하 여 생성 된 개체 `CComClassFactorySingleton`합니다.  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>설명  
 호출할 때마다는 [CreateInstance](#createinstance) 메서드 단순히 인터페이스 포인터에 대 한이 개체를 쿼리 합니다.  
  
 현재 형태의 `m_spObj` 방식으로 인해 주요 변경 내용 수를 표시 하는 `CComClassFactorySingleton` ATL.의 이전 버전에서 이전 버전에서의 `CComClassFactorySingleton` 클래스 팩터리로 동시에 서버를 초기화 하는 동안 개체를 만든 합니다. Visual c + +.NET 2003 개체가 첫 번째 요청에 느리게 생성 됩니다. 이 변경은 초기 초기화를 사용 하는 프로그램에서 오류가 발생할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 클래스](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactoryAutoThread 클래스](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [클래스 개요](../../atl/atl-class-overview.md)

