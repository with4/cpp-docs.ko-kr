---
title: "CComObjectNoLock 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4cf4cad1a3b1a4ac0a21ef76a0eaca35732abf3a
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectnolock-class"></a>CComObjectNoLock 클래스
이 클래스는 구현 **IUnknown** 는 집계 되지 않은 원시 개체 이지만 생성자에서 모듈 잠금 횟수를 증가 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class Base>  
class CComObjectNoLock : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)개체에서 지원 하려는 다른 인터페이스와도 같이 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|생성자입니다.|  
|[CComObjectNoLock:: ~ CComObjectNoLock](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](#addref)|개체에서 참조 횟수를 증가 시킵니다.|  
|[CComObjectNoLock::QueryInterface](#queryinterface)|요청된 된 인터페이스에 대 한 포인터를 반환합니다.|  
|[CComObjectNoLock::Release](#release)|개체에 대 한 참조 횟수를 감소 시킵니다.|  
  
## <a name="remarks"></a>주의  
 `CComObjectNoLock`그러나 유사한 [CComObject](../../atl/reference/ccomobject-class.md) 구현 한다는 측면에서 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 집계 되지 않은 원시 개체;에 대 한 `CComObjectNoLock` 생성자에서 계산 모듈 잠금 증가 하지 않습니다.  
  
 다음을 사용 하 여 ATL `CComObjectNoLock` 클래스 팩터리를 내부적으로 합니다. 일반적으로이 클래스를 직접 넣지 않습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `CComObjectNoLock`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="addref"></a>CComObjectNoLock::AddRef  
 개체에서 참조 횟수를 증가 시킵니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 유용 하거나 테스트 될 수 있는 값입니다.  
  
##  <a name="ccomobjectnolock"></a>CComObjectNoLock::CComObjectNoLock  
 생성자입니다. 와 달리 [CComObject](../../atl/reference/ccomobject-class.md), 모듈 잠금 횟수를 증가 하지 않습니다.  
  
```
CComObjectNoLock(void* = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 **void\***  
 [in] 이 명명 되지 않은 매개 변수가 사용 되지 않습니다. 다른 대칭 있는 **CCom***XXX*`Object`*XXX* 생성자입니다.  
  
##  <a name="dtor"></a>CComObjectNoLock:: ~ CComObjectNoLock  
 소멸자입니다.  
  
```
~CComObjectNoLock();
```  
  
### <a name="remarks"></a>주의  
 할당 된 모든 리소스를 해제 하는 호출 [FinalRelease](ccomobjectrootex-class.md#finalrelease)합니다.  

  
##  <a name="queryinterface"></a>CComObjectNoLock::QueryInterface  
 요청된 인터페이스에 대한 포인터를 검색합니다.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 요청 된 인터페이스의 식별자입니다.  
  
 `ppvObject`  
 [out] 로 식별 되는 인터페이스 포인터에 대 한 포인터 `iid`합니다. 개체는이 인터페이스를 지원 하지 않는 경우 `ppvObject` 로 설정 된 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
##  <a name="release"></a>CComObjectNoLock::Release  
 개체에 대 한 참조 횟수를 감소 시킵니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 디버그 빌드에서 **릴리스** 진단에 유용 하거나 테스트 될 수 있는 값을 반환 합니다. 비-디버그 빌드에서만에서 **릴리스** 항상 0을 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)

