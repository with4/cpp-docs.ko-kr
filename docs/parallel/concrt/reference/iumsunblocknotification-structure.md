---
title: "IUMSUnblockNotification 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IUMSUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
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
ms.openlocfilehash: 6fba6c36987107e2e8100c8b296c279592220682
ms.lasthandoff: 02/24/2017

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
|[Iumsunblocknotification:: Getcontext 메서드](#getcontext)|반환 된 `IExecutionContext` 차단 된 스레드 프록시와 연결 된 실행 컨텍스트에 대 한 인터페이스입니다. 이 메서드가 반환 하 고 기본 실행 컨텍스트를 호출 하 여 다시 예약 되는 `IThreadProxy::SwitchTo` 메서드를이 인터페이스는 더 이상 유효 합니다.|  
|[Iumsunblocknotification:: Getnextunblocknotification 메서드](#getnextunblocknotification)|다음 반환 `IUMSUnblockNotification` 인터페이스 메서드에서 반환 되는 체인에 `IUMSCompletionList::GetUnblockNotifications`합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namegetcontexta--iumsunblocknotificationgetcontext-method"></a><a name="getcontext"></a>Iumsunblocknotification:: Getcontext 메서드  
 반환 된 `IExecutionContext` 차단 된 스레드 프록시와 연결 된 실행 컨텍스트에 대 한 인터페이스입니다. 이 메서드가 반환 하 고 기본 실행 컨텍스트를 호출 하 여 다시 예약 되는 `IThreadProxy::SwitchTo` 메서드를이 인터페이스는 더 이상 유효 합니다.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 `IExecutionContext` 실행 컨텍스트를 차단 된 스레드 프록시에 대 한 인터페이스입니다.  
  
##  <a name="a-namegetnextunblocknotificationa--iumsunblocknotificationgetnextunblocknotification-method"></a><a name="getnextunblocknotification"></a>Iumsunblocknotification:: Getnextunblocknotification 메서드  
 다음 반환 `IUMSUnblockNotification` 인터페이스 메서드에서 반환 되는 체인에 `IUMSCompletionList::GetUnblockNotifications`합니다.  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 다음 `IUMSUnblockNotification` 인터페이스 메서드에서 반환 되는 체인에 `IUMSCompletionList::GetUnblockNotifications`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IUMSScheduler 구조체](iumsscheduler-structure.md)   
 [IUMSCompletionList 구조체](iumscompletionlist-structure.md)

