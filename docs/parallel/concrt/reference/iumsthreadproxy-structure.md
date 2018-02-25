---
title: "IUMSThreadProxy 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
dev_langs:
- C++
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 484c5a8fe7f730bf772fb65dee087ccbe1ff6425
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
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
|[IUMSThreadProxy::EnterCriticalRegion](#entercriticalregion)|중요 한 영역을 입력 하기 위해 호출 됩니다. 중요 한 영역 내에 있을 때 스케줄러는 지역 동안 발생 하는 비동기 차단 작업을 관찰 하지 않습니다. 이 스케줄러에 대해 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출 (Apc) 등에, UMS 스레드에 대 한 재진입 되지 않음을 의미 합니다.|  
|[IUMSThreadProxy::EnterHyperCriticalRegion](#enterhypercriticalregion)|매우 중요 한 지역을 입력 위해 호출 됩니다. 매우 중요 한 영역 내에 있는 경우 스케줄러는 지역 동안 발생 하는 모든 차단 작업을 관찰 하지 않습니다. 이는 스케줄러가 UMS 스레드에 대한 함수 호출 차단, 차단되는 잠금 가져오기 시도, 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출(APC) 등에 재진입되지 않음을 의미합니다.|  
|[IUMSThreadProxy::ExitCriticalRegion](#exitcriticalregion)|중요 한 영역을 종료 하기 위해 호출 됩니다.|  
|[IUMSThreadProxy::ExitHyperCriticalRegion](#exithypercriticalregion)|매우 중요 한 영역을 종료 하기 위해 호출 됩니다.|  
|[IUMSThreadProxy::GetCriticalRegionType](#getcriticalregiontype)|어떤 유형의 스레드 프록시가 중요 영역을 반환 합니다. 매우 중요 한 영역 중요 한 영역 및 매우 중요 한 지역 코드에서 시작 하는 경우 중요 한 영역이의 상위 집합을 사용 하기 때문에 `InsideHyperCriticalRegion` 반환 됩니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="entercriticalregion"></a>  IUMSThreadProxy::EnterCriticalRegion Method  
 중요 한 영역을 입력 하기 위해 호출 됩니다. 중요 한 영역 내에 있을 때 스케줄러는 지역 동안 발생 하는 비동기 차단 작업을 관찰 하지 않습니다. 이 스케줄러에 대해 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출 (Apc) 등에, UMS 스레드에 대 한 재진입 되지 않음을 의미 합니다.  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 중요 영역입니다. 중요 한 영역은 재진입 합니다.  
  
##  <a name="enterhypercriticalregion"></a>  IUMSThreadProxy::EnterHyperCriticalRegion Method  
 매우 중요 한 지역을 입력 위해 호출 됩니다. 매우 중요 한 영역 내에 있는 경우 스케줄러는 지역 동안 발생 하는 모든 차단 작업을 관찰 하지 않습니다. 이는 스케줄러가 UMS 스레드에 대한 함수 호출 차단, 차단되는 잠금 가져오기 시도, 페이지 폴트, 스레드 보류, 커널 비동기 프로시저 호출(APC) 등에 재진입되지 않음을 의미합니다.  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 매우 중요 한 영역입니다. 매우 중요 한 영역은 재진입입니다.  
  
### <a name="remarks"></a>설명  
 스케줄러 수행할지 뿐만 아니라 이러한 지역에서 메서드를 호출 하며 잠급니다 어떤 획득 하는 기능에 대해 주의 해야 합니다. 이 영역에는 코드 스케줄러는 예약에 대 한 방식으로 유지 되는 잠금을 차단 교착 상태가 발생 하지 못한다면 문제가 발생할 수 있습니다.  
  
##  <a name="exitcriticalregion"></a>  IUMSThreadProxy::ExitCriticalRegion Method  
 중요 한 영역을 종료 하기 위해 호출 됩니다.  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 중요 영역입니다. 중요 한 영역은 재진입 합니다.  
  
##  <a name="exithypercriticalregion"></a>  IUMSThreadProxy::ExitHyperCriticalRegion Method  
 매우 중요 한 영역을 종료 하기 위해 호출 됩니다.  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 새 깊이 매우 중요 한 영역입니다. 매우 중요 한 영역은 재진입입니다.  
  
##  <a name="getcriticalregiontype"></a>  IUMSThreadProxy::GetCriticalRegionType Method  
 어떤 유형의 스레드 프록시가 중요 영역을 반환 합니다. 매우 중요 한 영역 중요 한 영역 및 매우 중요 한 지역 코드에서 시작 하는 경우 중요 한 영역이의 상위 집합을 사용 하기 때문에 `InsideHyperCriticalRegion` 반환 됩니다.  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 형식 스레드 프록시가 중요 영역입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IUMSScheduler 구조체](iumsscheduler-structure.md)
