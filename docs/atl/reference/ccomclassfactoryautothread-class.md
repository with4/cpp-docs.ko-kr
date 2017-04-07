---
title: "CComClassFactoryAutoThread 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
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
ms.openlocfilehash: 88728e6fccc4aea6e8a1f0bbb2811ed299dd4ad9
ms.lasthandoff: 03/31/2017

---
# <a name="ccomclassfactoryautothread-class"></a>CComClassFactoryAutoThread 클래스
이 클래스가 구현 하는 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) 인터페이스, 및 개체를 여러 아파트에서 만들 수 있습니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComClassFactoryAutoThread 
   : public IClassFactory, 
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|지정된 된 CLSID의 개체를 만듭니다.|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|메모리에서 클래스 팩터리를 잠급니다.|  
  
## <a name="remarks"></a>주의  
 `CComClassFactoryAutoThread`유사한 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), 개체를 여러 아파트에서 만들 수 있습니다. 이 지원을 활용 하려면 사용자 EXE 모듈에서 파생 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다.  
  
 ATL 개체에서 파생 하 여 일반적으로 클래스 팩터리를 획득 [CComCoClass](../../atl/reference/ccomcoclass-class.md)합니다. 이 클래스는 매크로 포함 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)를 선언 하는 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) 기본 클래스 팩터리로 합니다. 사용 하도록 `CComClassFactoryAutoThread`, 지정는 [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) 개체의 클래스 정의에 매크로입니다. 예:  
  
 [!code-cpp[#9 NVC_ATL_COM](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactoryAutoThread::CreateInstance  
 지정된 된 CLSID의 개체를 만들고이 개체에 대 한 인터페이스 포인터를 검색 합니다.  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
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
  
### <a name="remarks"></a>설명  
 모듈에서 파생 된 경우 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` 먼저 개체를 만드는 연결된 아파트에 스레드를 선택 합니다.  
  
##  <a name="lockserver"></a>CComClassFactoryAutoThread::LockServer  
 증가 하 고 호출 하 여 모듈 잠금 횟수를 감소 **_Module::Lock** 및 **_Module::Unlock**각각.  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>매개 변수  
 `fLock`  
 [in] 경우 **TRUE**, 잠금 수가 증가 되지 않았으면, 잠금 수가 감소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>주의  
 사용 하는 경우 `CComClassFactoryAutoThread`, **_Module** 의 전역 인스턴스를 일반적으로 참조 [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md)합니다.  
  
 호출 `LockServer` 여러 개체를 신속 하 게 만들 수 있도록 클래스 팩터리를 보유할지 클라이언트 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 클래스](../../atl/reference/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton 클래스](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [클래스 개요](../../atl/atl-class-overview.md)

