---
title: CComClassFactory 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactory
- ATLCOM/ATL::CComClassFactory
- ATLCOM/ATL::CComClassFactory::CreateInstance
- ATLCOM/ATL::CComClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class
ms.assetid: e56dacf7-d5c4-4c42-aef4-a86d91981a1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a144f4ff9902a633933ae556df872a9d55a5409
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359247"
---
# <a name="ccomclassfactory-class"></a>CComClassFactory 클래스
이 클래스가 구현 하는 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComClassFactory 
   : public IClassFactory,  
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComClassFactory::CreateInstance](#createinstance)|지정된 된 CLSID의 개체를 만듭니다.|  
|[CComClassFactory::LockServer](#lockserver)|메모리에서 클래스 팩터리를 잠급니다.|  
  
## <a name="remarks"></a>설명  
 `CComClassFactory` 구현 하는 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 인터페이스 특정 CLSID의 개체를 만드는 수 있을 뿐만 아니라 새 개체를 보다 신속 하 게 만들 수 있도록 메모리에서 클래스 팩터리 잠금에 대 한 메서드가 포함 되어 있습니다. **IClassFactory** 시스템 레지스트리에 및 CLSID 할당를 등록 하는 모든 클래스에 대해 구현 해야 합니다.  
  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)를 선언 하는 `CComClassFactory` 기본 클래스 팩터리로 합니다. 이 기본값을 재정의 하려면 지정 중 하나는 `DECLARE_CLASSFACTORY` *XXX* 클래스 정의에 매크로입니다. 예를 들어는 [DECLARE_CLASSFACTORY_EX](aggregation-and-class-factory-macros.md#declare_classfactory_ex) 매크로 클래스 팩터리에 대 한 지정된 된 클래스를 사용 하 여:  
  
 [!code-cpp[NVC_ATL_COM#8](../../atl/codesnippet/cpp/ccomclassfactory-class_1.h)]  
  
 위의 클래스 정의 지정 하는 **CMyClassFactory** 개체의 기본 클래스 팩터리로 사용 됩니다. **CMyClassFactory** 에서 파생 되어야 `CComClassFactory` 재정의 `CreateInstance`합니다.  
  
 ATL은 클래스 팩터리를 선언 하는 다른 세 개의 매크로 제공 합니다.  
  
- [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) 사용 하 여 [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md), 라이선스를 통해 생성을 제어입니다.  
  
- [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 사용 하 여 [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)는 여러 아파트에서 개체를 만듭니다.  
  
- [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) 사용 하 여 [CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)를 생성 하는 단일 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactory::CreateInstance  
 지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.  
  
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
  
##  <a name="lockserver"></a>  CComClassFactory::LockServer  
 증가 하 고 호출 하 여 모듈 잠금 횟수를 감소 **_Module::Lock** 및 **_Module::Unlock**각각.  
  
```
STDMETHOD(LockServer)(BOOL fLock);
```  
  
### <a name="parameters"></a>매개 변수  
 `fLock`  
 [in] 경우 **TRUE**, 잠금 수가 증가 되지 않았으면, 잠금 수가 감소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 **_Module** 의 전역 인스턴스를 가리키며 [CComModule](../../atl/reference/ccommodule-class.md) 여기에서 파생 된 클래스 또는 합니다.  
  
 호출 `LockServer` 여러 개체를 신속 하 게 만들 수 있도록 클래스 팩터리를 보유할지 클라이언트 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [클래스 개요](../../atl/atl-class-overview.md)
