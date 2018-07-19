---
title: IResourceManager 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IResourceManager
- CONCRTRM/concurrency::IResourceManager
- CONCRTRM/concurrency::IResourceManager::IResourceManager::OSVersion
- CONCRTRM/concurrency::IResourceManager::IResourceManager::CreateNodeTopology
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetAvailableNodeCount
- CONCRTRM/concurrency::IResourceManager::IResourceManager::GetFirstNode
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Reference
- CONCRTRM/concurrency::IResourceManager::IResourceManager::RegisterScheduler
- CONCRTRM/concurrency::IResourceManager::IResourceManager::Release
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd87a71c8f5d41e38f6a1b18be96a7bab8f3bb8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693499"
---
# <a name="iresourcemanager-structure"></a>IResourceManager 구조체
동시성 런타임의 리소스 관리자에 대한 인터페이스입니다. 스케줄러가 리소스 관리자와 통신하는 데 사용되는 인터페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```
struct IResourceManager;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-enumerations"></a>public 열거형  
  
|이름|설명|  
|----------|-----------------|  
|[IResourceManager::OSVersion](#osversion)|운영 체제 버전을 나타내는 열거 형식입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[IResourceManager::CreateNodeTopology](#createnodetopology)|런타임에서의 빌드를 디버그에만 있음,이 메서드는 하드웨어 토폴로지는 구성과 일치 하는 실제 하드웨어를 요구 하지 않고 다양 한 리소스 관리자의 테스트를 촉진 하도록 설계 된 테스트 연결 합니다. 런타임 소매 빌드와이 메서드는 작업을 수행 하지 않고 반환 합니다.|  
|[IResourceManager::GetAvailableNodeCount](#getavailablenodecount)|리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.|  
|[IResourceManager::GetFirstNode](#getfirstnode)|리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.|  
|[IResourceManager::Reference](#reference)|리소스 관리자 인스턴스가에서 참조 횟수를 증가 시킵니다.|  
|[IResourceManager::RegisterScheduler](#registerscheduler)|리소스 관리자에는 스케줄러에 등록합니다. 사용 하 여 리소스 관리자와 협의 스케줄러 등록 되 면는 `ISchedulerProxy` 반환 되는 인터페이스입니다.|  
|[IResourceManager::Release](#release)|리소스 관리자 인스턴스에 대 한 참조 횟수를 줄입니다. 참조 개수가 되 면 리소스 관리자는 소멸 `0`합니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여는 [CreateResourceManager](concurrency-namespace-functions.md) 함수는 단일 리소스 관리자 인스턴스에 인터페이스를 가져올 수 있습니다. 메서드는 리소스 관리자에 대 한 참조 횟수를 증가 시키고 호출 해야 합니다는 [iresourcemanager:: Release](#release) 메서드를 리소스 관리자를 사용 하 여 완료 되 면 참조를 해제 합니다. 일반적으로 만들면 각 스케줄러를 만드는 동안이 메서드를 호출 하 고 종료 한 후 리소스 관리자에 대 한 참조를 해제 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IResourceManager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="createnodetopology"></a>  Iresourcemanager:: Createnodetopology 메서드  
 런타임에서의 빌드를 디버그에만 있음,이 메서드는 하드웨어 토폴로지는 구성과 일치 하는 실제 하드웨어를 요구 하지 않고 다양 한 리소스 관리자의 테스트를 촉진 하도록 설계 된 테스트 연결 합니다. 런타임 소매 빌드와이 메서드는 작업을 수행 하지 않고 반환 합니다.  
  
```
virtual void CreateNodeTopology(
    unsigned int nodeCount,
    _In_reads_(nodeCount) unsigned int* pCoreCount,
    _In_reads_opt_(nodeCount) unsigned int** pNodeDistance,
    _In_reads_(nodeCount) unsigned int* pProcessorGroups) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `nodeCount`  
 시뮬레이션 되는 프로세서 노드의 수입니다.  
  
 `pCoreCount`  
 각 노드에서 코어 수를 지정 하는 배열입니다.  
  
 `pNodeDistance`  
 노드를 두 노드 사이의 거리를 지정 하는 행렬입니다. 이 매개 변수 값을 가질 수 `NULL`합니다.  
  
 `pProcessorGroups`  
 프로세서 그룹을 지정 하는 배열에 각 노드에 속합니다.  
  
### <a name="remarks"></a>설명  
 [invalid_argument](../../../standard-library/invalid-argument-class.md) 경우 throw 되 매개 변수 `nodeCount` 값 `0` 에서는 전달 된 경우 매개 변수 `pCoreCount` 값 `NULL`합니다.  
  
 [invalid_operation](invalid-operation-class.md) 다른 스케줄러는 프로세스에 존재 하는 동안이 메서드를 호출 하면 throw 됩니다.  
  
##  <a name="getavailablenodecount"></a>  Iresourcemanager:: Getavailablenodecount 메서드  
 리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 리소스 관리자를 사용 하 여 사용할 수 있는 노드의 수입니다.  
  
##  <a name="getfirstnode"></a>  Iresourcemanager:: Getfirstnode 메서드  
 리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 리소스 관리자에 의해 정의 된 열거 순서에서 첫 번째 노드.  
  
##  <a name="iresourcemanager__osversion"></a>  Iresourcemanager:: Osversion 열거형  
 운영 체제 버전을 나타내는 열거 형식입니다.  
  
```
enum OSVersion;
```  
  
##  <a name="reference"></a>  Iresourcemanager:: Reference 메서드  
 리소스 관리자 인스턴스가에서 참조 횟수를 증가 시킵니다.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 결과 참조 횟수입니다.  
  
##  <a name="registerscheduler"></a>  Iresourcemanager:: Registerscheduler 메서드  
 리소스 관리자에는 스케줄러에 등록합니다. 사용 하 여 리소스 관리자와 협의 스케줄러 등록 되 면는 `ISchedulerProxy` 반환 되는 인터페이스입니다.  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pScheduler`  
 `IScheduler` 등록할 수 있도록 스케줄러에 대 한 인터페이스입니다.  
  
 `version`  
 스케줄러 사용 리소스 관리자와 통신 하도록 통신 인터페이스의 버전입니다. 버전을 사용 하면 리소스 관리자 통신 인터페이스 이전 기능 액세스 권한을 요청 스케줄러 수 발전 합니다. 버전을 사용 해야 하는 Visual Studio 2010에 있는 리소스 관리자 기능을 사용 하려는 구독자는 `CONCRT_RM_VERSION_1`합니다.  
  
### <a name="return-value"></a>반환 값  
 `ISchedulerProxy` 리소스 관리자가 사용자의 스케줄러와 연결 된 인터페이스입니다. 사용자의 스케줄러에서이 지점에서 리소스 관리자와 통신 하도록이 인터페이스를 사용 해야 합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 사용 하 여 리소스 관리자와 통신을 시작 합니다. 메서드는 연결 된 `IScheduler` 있는 스케줄러에 대 한 인터페이스는 `ISchedulerProxy` 인터페이스 및 사용자에 게 전달 합니다. 사용자의 스케줄러에서 사용 하기 위해 실행 리소스를 요청 하거나 스레드 리소스 관리자를 구독 하려면 반환 된 인터페이스를 사용할 수 있습니다. 리소스 관리자에서 반환 된 스케줄러 정책의 정책 요소를에서 사용 합니다는 [ischeduler:: Getpolicy](ischeduler-structure.md#getpolicy) 스케줄러 스레드 형식을 결정 하는 메서드는 작업을 실행 해야 합니다. 경우에 `SchedulerKind` 정책 키에 값 `UmsThreadDefault` 값을 값으로 정책을 읽고 `UmsThreadDefault`, `IScheduler` 메서드에 전달 된 인터페이스 이어야 합니다는 `IUMSScheduler` 인터페이스입니다.  
  
 메서드에서 throw는 `invalid_argument` 예외 경우 매개 변수 `pScheduler` 값 `NULL` 경우 매개 변수 `version` 은 통신 인터페이스에 대 한 올바른 버전이 아닙니다.  
  
##  <a name="release"></a>  Iresourcemanager:: Release 메서드  
 리소스 관리자 인스턴스에 대 한 참조 횟수를 줄입니다. 참조 개수가 되 면 리소스 관리자는 소멸 `0`합니다.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 결과 참조 횟수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ISchedulerProxy 구조체](ischedulerproxy-structure.md)   
 [IScheduler 구조체](ischeduler-structure.md)
