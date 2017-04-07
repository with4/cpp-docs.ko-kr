---
title: "CComSafeDeleteCriticalSection 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
dev_langs:
- C++
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
caps.latest.revision: 18
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 511627de9d4f6411c508dd78a237cf546e2493de
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsafedeletecriticalsection-class"></a>CComSafeDeleteCriticalSection 클래스
이 클래스는 가져오기 및 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|생성자입니다.|  
|[CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComSafeDeleteCriticalSection::Init](#init)|만들고 임계 영역 개체를 초기화 합니다.|  
|[CComSafeDeleteCriticalSection::Lock](#lock)|임계 영역 개체의 소유권을 가져오면 됩니다.|  
|[CComSafeDeleteCriticalSection::Term](#term)|임계 영역 개체에서 사용 하는 시스템 리소스를 해제 합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[m_bInitialized](#m_binitialized)|플래그 여부는 내부 **CRITICAL_SECTION** 개체가 초기화 되었습니다.|  
  
## <a name="remarks"></a>주의  
 `CComSafeDeleteCriticalSection`클래스에서 파생 [클래스](../../atl/reference/ccomcriticalsection-class.md)합니다. 그러나 `CComSafeDeleteCriticalSection` 추가 안전 메커니즘을 통해 [클래스](../../atl/reference/ccomcriticalsection-class.md)합니다.  
  
 인스턴스가 `CComSafeDeleteCriticalSection` 범위를 벗어나거나 명시적으로 메모리에서 삭제, 기본 임계 영역 개체 자동으로 정리 됩니다 경우 여전히 유효 합니다. 또한는 [CComSafeDeleteCriticalSection::Term](#term) 메서드는 기본 임계 영역 개체 아직 할당 되지 않은 메모리에서 이미 해제 된 경우 정상적으로 종료 됩니다.  
  
 참조 [클래스](../../atl/reference/ccomcriticalsection-class.md) 임계 도우미 클래스에 대 한 자세한 내용은 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [클래스](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComSafeDeleteCriticalSection`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="ccomsafedeletecriticalsection"></a>CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection  
 생성자입니다.  
  
```
CComSafeDeleteCriticalSection();
```  
  
### <a name="remarks"></a>주의  
 설정의 [m_bInitialized](#m_binitialized) 데이터 멤버를 **false**합니다.  
  
##  <a name="dtor"></a>CComSafeDeleteCriticalSection:: ~ CComSafeDeleteCriticalSection  
 소멸자입니다.  
  
```
~CComSafeDeleteCriticalSection() throw();
```  
  
### <a name="remarks"></a>주의  
 내부 해제 **CRITICAL_SECTION** 경우 메모리에서 개체는 [m_bInitialized](#m_binitialized) 데이터 멤버가로 설정 된 **true**합니다.  
  
##  <a name="init"></a>CComSafeDeleteCriticalSection::Init  
 기본 클래스 구현을 호출 [Init](/visualstudio/debugger/init) 설정 [m_bInitialized](#m_binitialized) 를 **true** 성공 하는 경우.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>반환 값  
 결과 반환 [CComCriticalSection::Init](../../atl/reference/ccomcriticalsection-class.md#init)합니다.  
  
##  <a name="lock"></a>CComSafeDeleteCriticalSection::Lock  
기본 클래스 구현을 호출 [잠금](ccomcriticalsection-class.md#lock)합니다.  

  
```
HRESULT Lock();
```  
  
### <a name="return-value"></a>반환 값  
 결과 반환 [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드에서 [m_bInitialized](#m_binitialized) 데이터 멤버가로 설정 된 **true** 입력 합니다. 이 condidtion 충족 되지 않으면 어설션에서 디버그 빌드에서 생성 됩니다.  
  
 함수 동작에 자세한 내용은를 참조 [CComCriticalSection::Lock](../../atl/reference/ccomcriticalsection-class.md#lock)합니다.  
  
##  <a name="m_binitialized"></a>CComSafeDeleteCriticalSection::m_bInitialized  
 플래그 여부는 내부 **CRITICAL_SECTION** 개체가 초기화 되었습니다.  
  
```
bool m_bInitialized;
```  
  
### <a name="remarks"></a>주의  
 **m_bInitialized** 데이터 멤버는 기본의 유효성을 추적 하는 데 **CRITICAL_SECTION** 연관 된 개체는 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) 클래스입니다. 내부 **CRITICAL_SECTION** 개체는이 플래그 설정 하지 않으면 메모리에서 해제를 시도 되지 것입니다 **true**합니다.  
  
##  <a name="term"></a>CComSafeDeleteCriticalSection::Term  
 기본 클래스 구현을 호출 [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term) 경우 내부 **CRITICAL_SECTION** 개체는 유효 합니다.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>반환 값  
 결과 반환 [CComCriticalSection::Term](../../atl/reference/ccomcriticalsection-class.md#term), 또는 **s_ok이 고** 경우 [m_bInitialized](#m_binitialized) 로 설정 된 **false** 입력 합니다.  
  
### <a name="remarks"></a>주의  
 경우에도이 메서드는 내부 호출 하지 않아도 안전 합니다 **CRITICAL_SECTION** 개체가 유효 하지 않습니다. 이 클래스의 소멸자가이 메서드를 호출 하는 경우는 [m_bInitialized](#m_binitialized) 데이터 멤버가로 설정 된 **true**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 클래스](../../atl/reference/ccomcriticalsection-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)

