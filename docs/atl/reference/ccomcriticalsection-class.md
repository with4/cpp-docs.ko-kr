---
title: "클래스 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCriticalSection
- ATLCORE/ATL::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::CComCriticalSection
- ATLCORE/ATL::CComCriticalSection::Init
- ATLCORE/ATL::CComCriticalSection::Lock
- ATLCORE/ATL::CComCriticalSection::Term
- ATLCORE/ATL::CComCriticalSection::Unlock
- ATLCORE/ATL::CComCriticalSection::m_sec
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 827ba99a141799af42fab65c36df1f22d212260a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcriticalsection-class"></a>클래스 클래스
이 클래스는 가져오는 임계 영역 개체의 소유권을 해제 하기 위한 메서드를 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|만들고 임계 영역 개체를 초기화 합니다.|  
|[CComCriticalSection::Lock](#lock)|임계 영역 개체의 소유권을 가져옵니다.|  
|[CComCriticalSection::Term](#term)|임계 영역 개체에서 사용 하는 시스템 리소스를 해제 합니다.|  
|[CComCriticalSection::Unlock](#unlock)|임계 영역 개체의 소유권을 해제 합니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|A **CRITICAL_SECTION** 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `CComCriticalSection`클래스와 유사한 [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)제외 하 고 명시적으로 초기화 하 고 중요 한 섹션을 해제 해야 합니다.  
  
 일반적으로 사용 `CComCriticalSection` 통해는 `typedef` 이름 [CriticalSection](ccommultithreadmodel-class.md#criticalsection)합니다. 이 이름은 참조 `CComCriticalSection` 때 [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) 사용 중입니다.  

  
 참조 [CComCritSecLock 클래스](../../atl/reference/ccomcritseclock-class.md) 호출 보다이 클래스를 사용 하는 보다 안전한 방법을 `Lock` 및 `Unlock` 직접 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcore.h  
  
##  <a name="ccomcriticalsection"></a>CComCriticalSection::CComCriticalSection  
 생성자입니다.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>설명  
 설정의 [m_sec](#m_sec) NULL로 데이터 멤버 **합니다.**  
  
##  <a name="init"></a>CComCriticalSection::Init  
 Win32 함수를 호출 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472)에 포함 된 임계 영역 개체를 초기화 하는 [m_sec](#m_sec) 데이터 멤버입니다.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 **E_OUTOFMEMORY** 또는 **E_FAIL** 실패 합니다.  
  
##  <a name="lock"></a>CComCriticalSection::Lock  
 Win32 함수를 호출 [유용](http://msdn.microsoft.com/library/windows/desktop/ms682608), 스레드 수에 포함 된 임계 영역 개체의 소유권을 가져올 때까지 대기 하는 [m_sec](#m_sec) 데이터 멤버입니다.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 `S_OK` 성공 **E_OUTOFMEMORY** 또는 **E_FAIL** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 임계 영역 개체를 호출 하 여 먼저 초기화 해야 합니다는 [Init](#init) 메서드. 보호 되는 코드의 실행이 완료 스레드에서 호출 해야 [잠금 해제](#unlock) 임계 영역 소유권을 해제 하려면.  
  
##  <a name="m_sec"></a>CComCriticalSection::m_sec  
 전체에서 사용 되는 임계 영역 개체를 포함 `CComCriticalSection` 메서드.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="term"></a>CComCriticalSection::Term  
 Win32 함수를 호출 [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552)에 포함 된 임계 영역 개체에서 사용 하는 모든 리소스를 해제 하는 [m_sec](#m_sec) 데이터 멤버입니다.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 한 번 `Term` 가 호출 된 중요 한 섹션 동기화에 더 이상 사용 될 수 없습니다.  
  
##  <a name="unlock"></a>CComCriticalSection::Unlock  
 Win32 함수를 호출 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169)에 포함 된 임계 영역 개체의 소유권을 해제 하는 [m_sec](#m_sec) 데이터 멤버입니다.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>반환 값  
 `S_OK`를 반환합니다.  
  
### <a name="remarks"></a>설명  
 스레드가 소유권을 가져오려면 먼저 호출 해야 합니다는 [잠금](#lock) 메서드. 호출할 때마다 `Lock` 해당 호출을 `Unlock` 임계 영역 소유권을 해제 하려면.  
  
## <a name="see-also"></a>참고 항목  
 [CComFakeCriticalSection 클래스](../../atl/reference/ccomfakecriticalsection-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CComCritSecLock 클래스](../../atl/reference/ccomcritseclock-class.md)
