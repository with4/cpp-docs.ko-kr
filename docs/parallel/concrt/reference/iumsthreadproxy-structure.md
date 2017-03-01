---
title: "IUMSThreadProxy 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IUMSThreadProxy
dev_langs:
- C++
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 55ed05f137775e819c81ce231cf8c8ad3a9974f3
ms.lasthandoff: 02/24/2017

---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy 구조체
실행 스레드에 대한 추상화입니다. 해당 스케줄러에 UMS(사용자 모드 예약 가능) 스레드를 부여하려는 경우 스케줄러 정책 요소 `SchedulerKind`의 값을 `UmsThreadDefault`로 설정하고 `IUMSScheduler` 인터페이스를 구현합니다. UMS 스레드는 Windows 7 이상 버전의 64비트 운영 체제에서만 지원됩니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Iumsthreadproxy:: Entercriticalregion 메서드](#entercriticalregion)|중요 영역을 입력 하기 위해 호출 됩니다. 중요 영역 내에 있을 때 스케줄러는 지역 중에 발생 하는 비동기 차단 작업을 관찰 하지 않습니다. 즉, 스케줄러를 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출 (Apc) 등에, UMS 스레드에 대 한에 대 한 재진입 되지 않습니다.|  
|[Iumsthreadproxy:: Enterhypercriticalregion 메서드](#enterhypercriticalregion)|매우 중요 한 지역을 입력 하기 위해 호출 됩니다. 매우 중요 한 영역 내에 있는 경우 스케줄러는 지역 중 발생 하는 모든 차단 작업을 관찰 하지 않습니다. 이는 스케줄러가 UMS 스레드에 대한 함수 호출 차단, 차단되는 잠금 가져오기 시도, 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출(APC) 등에 재진입되지 않음을 의미합니다.|  
|[Iumsthreadproxy:: Exitcriticalregion 메서드](#exitcriticalregion)|중요 영역을 종료 하기 위해 호출 됩니다.|  
|[Iumsthreadproxy:: Exithypercriticalregion 메서드](#exithypercriticalregion)|매우 중요 한 영역을 종료 하기 위해 호출 됩니다.|  
|[Iumsthreadproxy:: Getcriticalregiontype 메서드](#getcriticalregiontype)|중요 영역 내에서 스레드 프록시는의 종류를 반환 합니다. 때문에 매우 중요 한 영역 중요 영역의 상위 집합 코드는 중요 한 영역 및 매우 중요 한 영역 않았으면 `InsideHyperCriticalRegion` 반환 됩니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-nameentercriticalregiona--iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>Iumsthreadproxy:: Entercriticalregion 메서드  
 중요 영역을 입력 하기 위해 호출 됩니다. 중요 영역 내에 있을 때 스케줄러는 지역 중에 발생 하는 비동기 차단 작업을 관찰 하지 않습니다. 즉, 스케줄러를 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출 (Apc) 등에, UMS 스레드에 대 한에 대 한 재진입 되지 않습니다.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 중요 영역입니다. 중요 한 영역은 재진입입니다.  
  
##  <a name="a-nameenterhypercriticalregiona--iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>Iumsthreadproxy:: Enterhypercriticalregion 메서드  
 매우 중요 한 지역을 입력 하기 위해 호출 됩니다. 매우 중요 한 영역 내에 있는 경우 스케줄러는 지역 중 발생 하는 모든 차단 작업을 관찰 하지 않습니다. 이는 스케줄러가 UMS 스레드에 대한 함수 호출 차단, 차단되는 잠금 가져오기 시도, 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출(APC) 등에 재진입되지 않음을 의미합니다.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 매우 중요 한 영역입니다. 매우 중요 한 영역은 재진입입니다.  
  
### <a name="remarks"></a>주의  
 스케줄러 수행할지 뿐만 아니라 이러한 지역에서 메서드를 호출 하며 어떤 잠근 획득 하는 기능에 대해 주의 해야 합니다. 이러한 영역에서 코드 스케줄러는 예약에 의해 유지 되는 잠금을 차단 교착 상태 할 수 있습니다.  
  
##  <a name="a-nameexitcriticalregiona--iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>Iumsthreadproxy:: Exitcriticalregion 메서드  
 중요 영역을 종료 하기 위해 호출 됩니다.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 중요 영역입니다. 중요 한 영역은 재진입입니다.  
  
##  <a name="a-nameexithypercriticalregiona--iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>Iumsthreadproxy:: Exithypercriticalregion 메서드  
 매우 중요 한 영역을 종료 하기 위해 호출 됩니다.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 매우 중요 한 영역입니다. 매우 중요 한 영역은 재진입입니다.  
  
##  <a name="a-namegetcriticalregiontypea--iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>Iumsthreadproxy:: Getcriticalregiontype 메서드  
 중요 영역 내에서 스레드 프록시는의 종류를 반환 합니다. 때문에 매우 중요 한 영역 중요 영역의 상위 집합 코드는 중요 한 영역 및 매우 중요 한 영역 않았으면 `InsideHyperCriticalRegion` 반환 됩니다.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 형식 내에서 스레드 프록시는 중요 한 영역입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IUMSScheduler 구조체](iumsscheduler-structure.md)

