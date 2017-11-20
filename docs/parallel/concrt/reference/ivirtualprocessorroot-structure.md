---
title: "IVirtualProcessorRoot 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
dev_langs: C++
helpviewer_keywords: IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8f7a7dbff547a0a2f3fba04c10ad9107af2a26ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot 구조체
스레드 프록시가 실행될 수 있는 하드웨어 스레드의 추상화입니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IVirtualProcessorRoot : public IExecutionResource;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Ivirtualprocessorroot:: Activate](#activate)|스레드 프록시가 실행 컨텍스트 인터페이스와 연결 된 `pContext` 이 가상 프로세서 루트에서 실행을 시작 합니다.|  
|[Ivirtualprocessorroot:: Deactivate](#deactivate)|스레드 프록시가 실행 컨텍스트를 발송을 중지 하려면이 가상 프로세서 루트에서 현재 실행 합니다. 스레드 프록시에 대 한 호출 실행을 다시 시작 됩니다는 `Activate` 메서드.|  
|[Ivirtualprocessorroot:: Ensurealltasksvisible](#ensurealltasksvisible)|시스템에서 모든 프로세서에 표시 될 수 개별 프로세서의 메모리 계층 구조에 저장 된 데이터를 하면 됩니다. 메서드가 반환 되기 전에 전체 메모리 펜스 모든 프로세서에서 실행 된 있는지 확인 합니다.|  
|[Ivirtualprocessorroot:: Getid](#getid)|가상 프로세서 루트에 대 한 고유 식별자를 반환합니다.|  
  
## <a name="remarks"></a>설명  
 모든 가상 프로세서 루트에 연결 된 실행 리소스입니다. `IVirtualProcessorRoot` 인터페이스에서 상속 된 [IExecutionResource](iexecutionresource-structure.md) 인터페이스입니다. 여러 가상 프로세서 루트는 동일한 기본 하드웨어 스레드에 해당할 수 있습니다.  
  
 리소스 관리자 리소스에 대 한 요청에 응답 하는 스케줄러에 가상 프로세서 루트를 부여합니다. 스케줄러 가상 프로세서 루트를 사용 실행 컨텍스트를 활성화 하 여 작업을 수행할 수 있습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [IExecutionResource](iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="activate"></a>Ivirtualprocessorroot:: Activate 메서드  
 스레드 프록시가 실행 컨텍스트 인터페이스와 연결 된 `pContext` 이 가상 프로세서 루트에서 실행을 시작 합니다.  
  
```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 이 가상 프로세서 루트에서 발송 되는 실행 컨텍스트를 사용 하는 인터페이스입니다.  
  
### <a name="remarks"></a>설명  
 리소스 관리자는 실행 컨텍스트 인터페이스와 연결 되지 않은 경우 스레드 프록시를 제공 합니다.`pContext`  
  
 `Activate` 리소스 관리자에서 반환 되는 새로운 가상 프로세서 루트에서 작업 실행을 시작 하거나는 비활성화 하거나 비활성화 하는 가상 프로세서 루트와 스레드 프록시를 다시 시작 하려면 메서드를 사용할 수 있습니다. 참조 [ivirtualprocessorroot:: Deactivate](#deactivate) 비활성화에 대 한 자세한 내용은 합니다. 비활성화 된 가상 프로세서 루트를 매개 변수를 다시 시작 된 경우 `pContext` 가상 프로세서 루트를 비활성화 하는 데 사용 하는 매개 변수와 동일 해야 합니다.  
  
 처음으로 후속 쌍에 대 한 호출에 대 한 가상 프로세서 루트가 활성화 되 면 `Deactivate` 및 `Activate` 서로 경쟁할 수 있습니다. 즉,에 대 한 호출을 수신 하도록 리소스 관리자에 대 한 허용 `Activate` 받기 전에 `Deactivate` 을 호출 합니다.  
  
 가상 프로세서 루트를 활성화 하면 나타낸다고 리소스 관리자에이 가상 프로세서 루트는 현재 작업 수행 중입니다. 호출 해야 스케줄러를이 루트에서 실행할 수 없는 경우는 `Deactivate` 가상 프로세서 루트 유휴 상태임을 리소스 관리자에 게 알리는 메서드. 리소스 관리자의 부하 분산 시스템을이 데이터를 사용 합니다.  
  
 `invalid_argument`경우에 throw 되는 인수 `pContext` 값이 `NULL`합니다.  
  
 `invalid_operation`경우에 throw 되는 인수 `pContext` 이 가상 프로세서 루트에 의해 가장 최근에 반환 된 실행 컨텍스트를 나타내지 않습니다.  
  
 가상 프로세서 루트를 활성화 하는 작업의 기본 하드웨어 스레드 구독 수준 하나 증가 합니다. 구독 수준에 대 한 자세한 내용은 참조 하십시오. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.  
  
##  <a name="deactivate"></a>Ivirtualprocessorroot:: Deactivate 메서드  
 스레드 프록시가 실행 컨텍스트를 발송을 중지 하려면이 가상 프로세서 루트에서 현재 실행 합니다. 스레드 프록시에 대 한 호출 실행을 다시 시작 됩니다는 `Activate` 메서드.  
  
```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 현재이 루트에 의해 디스패치되 컨텍스트.  
  
### <a name="return-value"></a>반환 값  
 부울 값입니다. 값이 `true` 반환 스레드 프록시는 `Deactivate` 에 대 한 호출에 대 한 응답에서 메서드는 `Activate` 메서드. 값이 `false` 스레드 프록시 리소스 관리자의 알림 이벤트에 대 한 응답의 메서드에서 반환 됨을 나타냅니다. 사용자 모드 예약 가능 (UMS) 스레드 스케줄러에서 스케줄러의 완성 목록에 항목이 이전에 표시 하 고 처리 하기 위한 스케줄러 필요 의미 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 일시적으로 사용자의 스케줄러에서 작업을 찾을 수 없는 경우 가상 프로세서 루트와 실행을 중지 합니다. 에 대 한 호출에서 `Deactivate` 메서드 내에서 발생 해야 합니다는 `Dispatch` 가상 프로세서 루트와 마지막으로 활성화 된 실행 컨텍스트의 메서드입니다. 즉, 호출 스레드 프록시는 `Deactivate` 메서드가 가상 프로세서 루트에서 현재 실행 중인 것 이어야 합니다. 메서드를 호출 하면에서 실행 중인 아닌 가상 프로세서 루트에서 정의 되지 않은 동작이 발생할 수 있습니다.  
  
 비활성화 된 가상 프로세서 루트를 호출 하 여 해제 될 수 있습니다는 `Activate` 에 전달 된 동일한 인수 메서드는 `Deactivate` 메서드. 스케줄러는 이룰는 `Activate` 및 `Deactivate` 메서드가 쌍을 있지만 특정 순서 대로 수신 하는 데 필요 하지 않습니다. 리소스 관리자에 대 한 호출을 받는 처리할 수는 `Activate` 메서드 호출을 받기 전에 `Deactivate` 메서드를 위해 제공 되었습니다.  
  
 가상 프로세서 루트 활성화 되는 경우의 반환 값과는 `Deactivate` 메서드는 값 `false`, 스케줄러를 통해 UMS 완성 목록을 쿼리하여는 `IUMSCompletionList::GetUnblockNotifications` 메서드를 해당 정보를 작업을 수행 하 고는 이후에호출`Deactivate`메서드를 다시 합니다. 보장할 때까지 반복 해야는 `Deactivate` 메서드 값을 반환 `true`합니다.  
  
 `invalid_argument`경우에 throw 되는 인수 `pContext` 값이 `NULL`합니다.  
  
 `invalid_operation`가상 프로세서 루트 활성화 되지 않은 경우 throw 되는 인수 또는 `pContext` 이 가상 프로세서 루트에 의해 가장 최근에 반환 된 실행 컨텍스트를 나타내지 않습니다.  
  
 가상 프로세서 루트를 비활성화 하는 작업의 기본 하드웨어 스레드 구독 수준 하나 감소 합니다. 구독 수준에 대 한 자세한 내용은 참조 하십시오. [iexecutionresource:: Currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)합니다.  
  
##  <a name="ensurealltasksvisible"></a>Ivirtualprocessorroot:: Ensurealltasksvisible 메서드  
 시스템에서 모든 프로세서에 표시 될 수 개별 프로세서의 메모리 계층 구조에 저장 된 데이터를 하면 됩니다. 메서드가 반환 되기 전에 전체 메모리 펜스 모든 프로세서에서 실행 된 있는지 확인 합니다.  
  
```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pContext`  
 현재이 가상 프로세서 루트에서 디스패치되는 컨텍스트.  
  
### <a name="remarks"></a>설명  
 가상 프로세서 루트를 비활성화 스케줄러에 새 작업 추가 하 여 동기화 하려는 경우이 메서드를 유용한 알 수 있습니다. 성능상의 이유로 단일 프로세서에서 실행 되는 스레드에 의해 추가 된 작업 항목의 다른 모든 프로세서에 즉시 표시 되지 않습니다. 즉는 메모리 장벽 실행 하지 않고 사용자의 스케줄러에 작업 항목을 추가 하려는 경우도 있습니다. 와 함께에서이 메서드를 사용 하 여는 `Deactivate` 스케줄러의 컬렉션에 작업 항목이 존재 하는 동안 스케줄러 모든 가상 프로세서를 비활성화 하지 않도록 있도록 메서드 루트입니다.  
  
 에 대 한 호출에서 `EnsureAllTasksVisibleThe` 메서드 내에서 발생 해야 합니다는 `Dispatch` 가상 프로세서 루트와 마지막으로 활성화 된 실행 컨텍스트의 메서드입니다. 즉, 호출 스레드 프록시는 `EnsureAllTasksVisible` 메서드가 가상 프로세서 루트에서 현재 실행 중인 것 이어야 합니다. 메서드를 호출 하면에서 실행 중인 아닌 가상 프로세서 루트에서 정의 되지 않은 동작이 발생할 수 있습니다.  
  
 `invalid_argument`경우에 throw 되는 인수 `pContext` 값이 `NULL`합니다.  
  
 `invalid_operation`가상 프로세서 루트 활성화 되지 않은 경우 throw 되는 인수 또는 `pContext` 이 가상 프로세서 루트에 의해 가장 최근에 반환 된 실행 컨텍스트를 나타내지 않습니다.  
  
##  <a name="getid"></a>Ivirtualprocessorroot:: Getid 메서드  
 가상 프로세서 루트에 대 한 고유 식별자를 반환합니다.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 정수 식별자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
