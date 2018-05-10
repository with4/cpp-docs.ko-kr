---
title: IUMSUnblockNotification 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bda4f6e2b0565d39fd604767f3a89bcdd9a6df2c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="iumsunblocknotification-structure"></a>IUMSUnblockNotification 구조체
차단되었으며 스케줄러의 지정된 일정 컨텍스트로의 반환을 트리거한 스레드 프록시가 차단 해제되고 예약할 준비가 되었다는 리소스 관리자의 알림을 나타냅니다. `GetContext` 메서드에서 반환된 스레드 프록시의 연결된 실행 컨텍스트가 다시 예약된 후에는 이 인터페이스가 유효하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IUMSUnblockNotification;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IUMSUnblockNotification::GetContext](#getcontext)|반환 된 `IExecutionContext` 차단 된 스레드 프록시와 연결 된 실행 컨텍스트에 대 한 인터페이스입니다. 이 메서드가 반환 하 고 호출을 통해 기본 실행 컨텍스트가 다시 예약 되는 `IThreadProxy::SwitchTo` 메서드에서이 인터페이스는 더 이상 유효 합니다.|  
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|다음 반환 `IUMSUnblockNotification` 인터페이스 메서드에서 반환 되는 체인에서 `IUMSCompletionList::GetUnblockNotifications`합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="getcontext"></a>  Iumsunblocknotification:: Getcontext 메서드  
 반환 된 `IExecutionContext` 차단 된 스레드 프록시와 연결 된 실행 컨텍스트에 대 한 인터페이스입니다. 이 메서드가 반환 하 고 호출을 통해 기본 실행 컨텍스트가 다시 예약 되는 `IThreadProxy::SwitchTo` 메서드에서이 인터페이스는 더 이상 유효 합니다.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IExecutionContext` 차단 된 스레드 프록시를 실행 컨텍스트에 대 한 인터페이스입니다.  
  
##  <a name="getnextunblocknotification"></a>  Iumsunblocknotification:: Getnextunblocknotification 메서드  
 다음 반환 `IUMSUnblockNotification` 인터페이스 메서드에서 반환 되는 체인에서 `IUMSCompletionList::GetUnblockNotifications`합니다.  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 다음 `IUMSUnblockNotification` 인터페이스 메서드에서 반환 되는 체인에서 `IUMSCompletionList::GetUnblockNotifications`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IUMSScheduler 구조체](iumsscheduler-structure.md)   
 [IUMSCompletionList 구조체](iumscompletionlist-structure.md)
