---
title: CComObjectGlobal 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3614962d3bebada0c63b7fe804b52efaa965c6a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32362445"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal 클래스
이 클래스는 포함 하는 모듈에서 참조 횟수를 관리 하면 `Base` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지원할 하려는 다른 모든 인터페이스와도 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|생성자입니다.|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|전역 구현 `AddRef`합니다.|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|전역 구현 `QueryInterface`합니다.|  
|[CComObjectGlobal::Release](#release)|전역 구현 **릴리스**합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|포함는 **HRESULT** 생성 중에 반환 되는 `CComObjectGlobal` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CComObjectGlobal` 포함 하는 모듈에서 참조 횟수를 관리 하 여 `Base` 개체입니다. `CComObjectGlobal` 모듈은 출시으로 개체가 삭제 되지 않습니다 보장 합니다. 개체는 전체 모듈의 참조 횟수가 0이 되는 경우에 제거 됩니다.  
  
 예를 들어,를 사용 하 여 `CComObjectGlobal`, 클래스 팩터리와 모든 클라이언트에서 공유 하는 일반적인 전역 개체를 보유할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectGlobal::AddRef  
 개체의 참조 횟수를 1 씩 증가 시킵니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 진단에 대 한 유용 하 고 테스트 될 수 있는 값입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 `AddRef` 호출 **_Module::Lock**여기서 **_Module** 의 인스턴스인 전역 [CComModule](../../atl/reference/ccommodule-class.md) 여기에서 파생 된 클래스 또는 합니다.  
  
##  <a name="ccomobjectglobal"></a>  CComObjectGlobal::CComObjectGlobal  
 생성자입니다. 호출 `FinalConstruct` 다음 설정 [m_hResFinalConstruct](#m_hresfinalconstruct) 에 `HRESULT` 반환한 `FinalConstruct`합니다.  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>설명  
 기본 클래스를 파생 하지 경우 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), 직접 제공 해야 `FinalConstruct` 메서드. 이 소멸자는 `FinalRelease`을 호출합니다.  
  
##  <a name="dtor"></a>  CComObjectGlobal:: ~ CComObjectGlobal  
 소멸자입니다.  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제 하는 호출 [FinalRelease](ccomobjectrootex-class.md#finalrelease)합니다.  
  
##  <a name="m_hresfinalconstruct"></a>  CComObjectGlobal::m_hResFinalConstruct  
 포함 된 `HRESULT` 호출에서 `FinalConstruct` 생성 중는 `CComObjectGlobal` 개체입니다.  
  
```
HRESULT m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>  CComObjectGlobal::QueryInterface  
 요청 된 인터페이스 포인터에 대 한 포인터를 검색합니다.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>매개 변수  
 `iid`  
 [in] 요청 된 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 [out] Iid로 식별 되는 인터페이스 포인터에 대 한 포인터 또는 **NULL** 인터페이스를 찾을 수 없는 경우.  
  
### <a name="return-value"></a>반환 값  
 표준 `HRESULT` 값입니다.  
  
### <a name="remarks"></a>설명  
 `QueryInterface`에서는 COM 맵 테이블의 인터페이스만 처리됩니다.  
  
##  <a name="release"></a>  CComObjectGlobal::Release  
 1 씩 개체의 참조 횟수를 감소 시킵니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 디버그 빌드에서 **릴리스** 진단에 대 한 유용 하 고 테스트 될 수 있는 값을 반환 합니다. 디버그가 아닌 빌드에서 **릴리스** 항상 0을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 기본적으로 **릴리스** 호출 **_Module::Unlock**여기서 **_Module** 의 인스턴스인 전역 [CComModule](../../atl/reference/ccommodule-class.md) 여기에서 파생 된 클래스 또는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComObjectStack 클래스](../../atl/reference/ccomobjectstack-class.md)   
 [CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)   
 [CComObject 클래스](../../atl/reference/ccomobject-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
