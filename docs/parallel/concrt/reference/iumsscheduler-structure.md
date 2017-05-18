---
title: "IUMSScheduler 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler
- CONCRTRM/concurrency::IUMSScheduler::IUMSScheduler::SetCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSScheduler structure
ms.assetid: 3a500225-4e02-4849-bb56-d744865f5870
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 58ca59224b5d9cdeb282562349642736a1b22c74
ms.contentlocale: ko-kr
ms.lasthandoff: 03/17/2017

---
# <a name="iumsscheduler-structure"></a>IUMSScheduler 구조체
동시성 런타임의 리소스 관리자를 통해 UMS(사용자 모드 예약 가능) 스레드를 전달하려는 작업 스케줄러의 추상화에 대한 인터페이스입니다. 리소스 관리자는 이 인터페이스를 사용하여 UMS 스레드 스케줄러와 통신합니다. `IUMSScheduler` 인터페이스는 `IScheduler` 인터페이스에서 상속됩니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IUMSScheduler : public IScheduler;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Iumsscheduler:: Setcompletionlist](#setcompletionlist)|할당 된 `IUMSCompletionList` UMS 스레드 스케줄러에 대 한 인터페이스입니다.|  
  
## <a name="remarks"></a>설명  
 구현을 제공 해야 리소스 관리자와 통신 하는 사용자 지정 스케줄러를 구현 하는 경우 일반 Win32 스레드 대신 스케줄러로 전달 될 UMS 스레드는 `IUMSScheduler` 인터페이스입니다. 스케줄러 정책 키에 대 한 정책 값을 설정 해야 하는 또한 `SchedulerKind` 되도록 `UmsThreadDefault`합니다. 정책 UMS 스레드를 지정 하는 경우는 `IScheduler` 에 대 한 매개 변수로 전달 되는 인터페이스는 [iresourcemanager:: Registerscheduler](iresourcemanager-structure.md#registerscheduler) 메서드 해야는 `IUMSScheduler` 인터페이스.  
  
 리소스 관리자에 게 UMS 기능이 운영 체제에만 UMS 스레드를 제공할 수는 있습니다. Windows 7 이상 버전의 64 비트 운영 체제 UMS 스레드를 지원합니다. 스케줄러 정책을 만드는 경우는 `SchedulerKind` 키 값으로 설정 된 `UmsThreadDefault` 기본 플랫폼 UMS의 값을 지원 하지 않습니다는 `SchedulerKind` 해당 정책에는 키 값으로 변경 됩니다 `ThreadScheduler`합니다. 항상 다시이 정책 값 전에 읽어야 UMS 스레드를 수신 하도록 합니다.  
  
 `IUMSScheduler` 인터페이스는 양방향 채널을 스케줄러와 리소스 관리자 간의 통신의 한쪽 끝입니다. 다른 쪽 끝으로 표현 됩니다는 `IResourceManager` 및 `ISchedulerProxy` 인터페이스는 리소스 관리자를 통해 구현 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [IScheduler](ischeduler-structure.md)  
  
 `IUMSScheduler`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="setcompletionlist"></a>Iumsscheduler:: Setcompletionlist 메서드  
 할당 된 `IUMSCompletionList` UMS 스레드 스케줄러에 대 한 인터페이스입니다.  
  
```
virtual void SetCompletionList(_Inout_ IUMSCompletionList* pCompletionList) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pCompletionList`  
 스케줄러에 대 한 완성 목록 인터페이스입니다. 스케줄러 당 하나의 목록이 있습니다.  
  
### <a name="remarks"></a>설명  
 리소스 관리자는 스케줄러 요청한 리소스의 초기 할당 후 브로드캐스트하며 UMS 스레드를 지정 하는 스케줄러에서이 메서드를 호출 합니다. 스케줄러에서 사용할 수는 `IUMSCompletionList` UMS 스레드 프록시 차단이 해제 시기를 결정 하는 인터페이스입니다. UMS 스케줄러에 할당 된 가상 프로세서 루트에서 실행 되는 스레드 프록시에서이 인터페이스에 액세스 하는 것만 유효 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [IScheduler 구조체](ischeduler-structure.md)   
 [IUMSCompletionList 구조체](iumscompletionlist-structure.md)   
 [IResourceManager 구조체](iresourcemanager-structure.md)

