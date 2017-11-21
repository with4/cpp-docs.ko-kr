---
title: "CComObjectStack 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
dev_langs: C++
helpviewer_keywords: CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a4e00fc1f703df824daf7c0f1fc5fbaed05beb32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomobjectstack-class"></a>CComObjectStack 클래스
이 클래스는 임시 COM 개체를 만들고의 기본 구현을 제공 **IUnknown**합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 파생 된 클래스에 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), 개체에서 지원할 하려는 다른 모든 인터페이스와도 합니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|생성자입니다.|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|0을 반환합니다. 디버그 모드에서 호출 되는 `_ASSERTE`합니다.|  
|[CComObjectStack::QueryInterface](#queryinterface)|반환 **E_NOINTERFACE**합니다. 디버그 모드에서 호출 되는 `_ASSERTE`합니다.|  
|[CComObjectStack::Release](#release)|0을 반환합니다. 디버그 모드에서 호출 되는 `_ASSERTE`합니다. ~|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|포함는 **HRESULT** 생성 중에 반환 되는 `CComObjectStack` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CComObjectStack`임시 COM 개체를 만들고 개체의 기본 구현을 제공 하는 데 사용 되 **IUnknown**합니다. 일반적으로 개체 (즉, 스택에 밀어 넣은) 하나의 함수 내에 지역 변수도 사용 됩니다. 함수가 완료 되 면 해당 개체가 삭제 됩니다, 이후 참조 횟수 해도 효율성을 높이기 위해 수행 되지 않습니다.  
  
 다음 예제에서는 함수 내에서 사용 하는 COM 개체를 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 임시 개체가 `Tempobj` 스택으로 푸시됩니다 및 함수가 완료 될 때 자동으로 사라집니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
##  <a name="addref"></a>CComObjectStack::AddRef  
 0을 반환합니다.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>반환 값  
 0을 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 모드에서 호출 되는 `_ASSERTE`합니다.  
  
##  <a name="ccomobjectstack"></a>CComObjectStack::CComObjectStack  
 생성자입니다.  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>설명  
 호출 `FinalConstruct` 다음 설정 [m_hResFinalConstruct](#m_hresfinalconstruct) 에 `HRESULT` 반환한 `FinalConstruct`합니다. 기본 클래스를 파생 하지 경우 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), 직접 제공 해야 `FinalConstruct` 메서드. 이 소멸자는 `FinalRelease`을 호출합니다.  
  
##  <a name="dtor"></a>CComObjectStack:: ~ CComObjectStack  
 소멸자입니다.  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>설명  
 할당 된 모든 리소스를 해제 하는 호출 [FinalRelease](ccomobjectrootex-class.md#finalrelease)합니다.  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct  
 포함 된 `HRESULT` 호출에서 반환 된 `FinalConstruct` 생성 중는 `CComObjectStack` 개체입니다.  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectStack::QueryInterface  
 반환 **E_NOINTERFACE**합니다.  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>반환 값  
 반환 **E_NOINTERFACE**합니다.  
  
### <a name="remarks"></a>설명  
 디버그 모드에서 호출 되는 `_ASSERTE`합니다.  
  
##  <a name="release"></a>CComObjectStack::Release  
 0을 반환합니다.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>반환 값  
 0을 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 모드에서 호출 되는 `_ASSERTE`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CComAggObject 클래스](../../atl/reference/ccomaggobject-class.md)   
 [CComObject 클래스](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal 클래스](../../atl/reference/ccomobjectglobal-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)
