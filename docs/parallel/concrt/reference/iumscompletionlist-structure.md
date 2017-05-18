---
title: "IUMSCompletionList 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 65655e4e03a7b187e0bbadbd576bc088bb57f7c8
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="iumscompletionlist-structure"></a>IUMSCompletionList 구조체
UMS 완성 목록을 나타냅니다. UMS 스레드가 차단되는 경우 원래 스레드가 차단되는 동안 기본 가상 프로세서 루트에 예약할 항목을 결정하기 위해 스케줄러의 지정된 일정 컨텍스트가 디스패치됩니다. 원래 스레드가 차단 해제되면 운영 체제에서 이 인터페이스를 통해 액세스할 수 있는 완성 목록에 대기시킵니다. 스케줄러는 지정된 일정 컨텍스트 또는 작업을 검색하는 다른 위치에 있는 완성 목록을 쿼리할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Iumscompletionlist:: Getunblocknotifications](#getunblocknotifications)|체인을 검색 `IUMSUnblockNotification` 프록시 차단이 해제 마지막으로이 메서드는 해당 관련된 스레드 호출 된 실행 컨텍스트를 나타내는 인터페이스입니다.|  
  
## <a name="remarks"></a>주의  
 한 스케줄러 수행할지 완성 목록에서 항목을 큐에서 제거 하기 위해이 인터페이스를 이용한 후 수행 되는 작업에 대해 주의 해야 합니다. 실행 가능한 컨텍스트에 스케줄러의 목록에 배치 해야 항목과 최대한 빨리 일반적으로 액세스할 수 있습니다. 일으킬 가능성이 있으므로 큐에서 제거 된 항목 중 하나에 제공 된에 임의 잠금의 소유 합니다. 스케줄러에 항목을 큐에서 제거에 대 한 호출 및 스케줄러 내에서 일반적으로 액세스할 수 있는 목록에서 해당 항목의 위치 사이 차단할 수는 없는 임의의 함수 호출 가능 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="getunblocknotifications"></a>Iumscompletionlist:: Getunblocknotifications 메서드  
 체인을 검색 `IUMSUnblockNotification` 프록시 차단이 해제 마지막으로이 메서드는 해당 관련된 스레드 호출 된 실행 컨텍스트를 나타내는 인터페이스입니다.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 체인을 `IUMSUnblockNotification` 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 실행 컨텍스트가 재조정 된 후에 반환 된 알림을 유효 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [IUMSScheduler 구조체](iumsscheduler-structure.md)   
 [IUMSUnblockNotification 구조체](iumsunblocknotification-structure.md)

