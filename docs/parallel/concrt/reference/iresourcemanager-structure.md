---
title: "IResourceManager 구조체 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IResourceManager
dev_langs:
- C++
helpviewer_keywords:
- IResourceManager structure
ms.assetid: 3dd5ec2c-fe53-4121-ae77-1bc1d1167ff4
caps.latest.revision: 20
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
ms.openlocfilehash: fb523127f60c4e8cd45b2525749b536ad55849b0
ms.lasthandoff: 02/24/2017

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
|[Iresourcemanager:: Osversion 열거형](#osversion)|운영 체제 버전을 나타내는 열거 형식입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Iresourcemanager:: Createnodetopology 메서드](#createnodetopology)|런타임의 현재 디버그에만 빌드,이 메서드는 구성과 일치 하는 실제 하드웨어를 요구 하지 않고 다양 한 하드웨어 토폴로지에서, 리소스 관리자의 테스트를 촉진 하도록 설계 된 테스트 후크입니다. 이 메서드는 런타임의 소매 빌드와 특별 한 조치를 수행 하지 않고 반환 합니다.|  
|[Iresourcemanager:: Getavailablenodecount 메서드](#getavailablenodecount)|리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.|  
|[Iresourcemanager:: Getfirstnode 메서드](#getfirstnode)|리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.|  
|[Iresourcemanager:: Reference 메서드](#reference)|리소스 관리자 인스턴스에서 참조 횟수를 증가 시킵니다.|  
|[Iresourcemanager:: Registerscheduler 메서드](#registerscheduler)|스케줄러를 리소스 관리자를 등록합니다. 사용 하 여 리소스 관리자와 통신 해야 스케줄러 등록 되 면는 `ISchedulerProxy` 반환 되는 인터페이스입니다.|  
|[Iresourcemanager:: Release 메서드](#release)|리소스 관리자 인스턴스에 대 한 참조 횟수를 줄입니다. 참조 횟수가 되 면 리소스 관리자는 소멸 `0`합니다.|  
  
## <a name="remarks"></a>주의  
 사용 하 여는 [CreateResourceManager](concurrency-namespace-functions.md) 함수는 단일 리소스 관리자 인스턴스에 인터페이스를 가져올 수 있습니다. 메서드는 리소스 관리자에 대 한 참조 횟수를 증가 시키고 호출 해야는 [iresourcemanager:: Release](#release) 메서드를 리소스 관리자와 함께 완료 되 면 참조를 해제 합니다. 일반적으로 만들면 각 스케줄러를 만드는 동안이 메서드를 호출 하 고 종료 한 후 리소스 관리자에 대 한 참조를 해제 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IResourceManager`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namecreatenodetopologya--iresourcemanagercreatenodetopology-method"></a><a name="createnodetopology"></a>Iresourcemanager:: Createnodetopology 메서드  
 런타임의 현재 디버그에만 빌드,이 메서드는 구성과 일치 하는 실제 하드웨어를 요구 하지 않고 다양 한 하드웨어 토폴로지에서, 리소스 관리자의 테스트를 촉진 하도록 설계 된 테스트 후크입니다. 이 메서드는 런타임의 소매 빌드와 특별 한 조치를 수행 하지 않고 반환 합니다.  
  
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
 각 노드에서 코어의 수를 지정 하는 배열입니다.  
  
 `pNodeDistance`  
 노드를 두 노드 사이의 거리를 지정 하는 행렬입니다. 이 매개 변수 값을 가질 수 `NULL`합니다.  
  
 `pProcessorGroups`  
 프로세서 그룹을 지정 하는 배열에 각 노드에 속합니다.  
  
### <a name="remarks"></a>주의  
 [invalid_argument](../../../standard-library/invalid-argument-class.md) 없으면 예외가 매개 변수 `nodeCount` 값이 `0` 에서는 전달 된 경우 또는 매개 변수 `pCoreCount` 값 `NULL`합니다.  
  
 [invalid_operation](invalid-operation-class.md) 다른 스케줄러는 프로세스에 존재 하는 동안이 메서드를 호출 하면 throw 됩니다.  
  
##  <a name="a-namegetavailablenodecounta--iresourcemanagergetavailablenodecount-method"></a><a name="getavailablenodecount"></a>Iresourcemanager:: Getavailablenodecount 메서드  
 리소스 관리자에서 사용할 수 있는 노드의 수를 반환합니다.  
  
```
virtual unsigned int GetAvailableNodeCount() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 리소스 관리자를 사용 하 여 사용할 수 있는 노드의 수입니다.  
  
##  <a name="a-namegetfirstnodea--iresourcemanagergetfirstnode-method"></a><a name="getfirstnode"></a>Iresourcemanager:: Getfirstnode 메서드  
 리소스 관리자를 통해 정의된 열거 순서에서 첫 번째 노드를 반환합니다.  
  
```
virtual ITopologyNode* GetFirstNode() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 리소스 관리자에서 정의 된 열거 순서에서 첫 번째 노드.  
  
##  <a name="a-nameiresourcemanagerosversiona--iresourcemanagerosversion-enumeration"></a><a name="iresourcemanager__osversion"></a>Iresourcemanager:: Osversion 열거형  
 운영 체제 버전을 나타내는 열거 형식입니다.  
  
```
enum OSVersion;
```  
  
##  <a name="a-namereferencea--iresourcemanagerreference-method"></a><a name="reference"></a>Iresourcemanager:: Reference 메서드  
 리소스 관리자 인스턴스에서 참조 횟수를 증가 시킵니다.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 결과 참조 횟수입니다.  
  
##  <a name="a-nameregisterschedulera--iresourcemanagerregisterscheduler-method"></a><a name="registerscheduler"></a>Iresourcemanager:: Registerscheduler 메서드  
 스케줄러를 리소스 관리자를 등록합니다. 사용 하 여 리소스 관리자와 통신 해야 스케줄러 등록 되 면는 `ISchedulerProxy` 반환 되는 인터페이스입니다.  
  
```
virtual ISchedulerProxy *RegisterScheduler(
    _Inout_ IScheduler* pScheduler,
    unsigned int version) = 0;
```  
  
### <a name="parameters"></a>매개 변수  
 `pScheduler`  
 `IScheduler` 등록 해야 하는 스케줄러에 대 한 인터페이스입니다.  
  
 `version`  
 통신 인터페이스의 버전 스케줄러는 리소스 관리자와 통신을 사용 합니다. 버전을 사용 하 여 리소스 관리자를 스케줄러에 오래 된 기능 액세스 권한을 확보 하면서 통신 인터페이스를 발전 시킬 수 있도록 허용 버전을 사용 해야 하는 Visual Studio 2010에 있는 리소스 관리자 기능을 사용 하려는 구독자는 `CONCRT_RM_VERSION_1`합니다.  
  
### <a name="return-value"></a>반환 값  
 `ISchedulerProxy` 리소스 관리자가 스케줄러와 연결 된 인터페이스입니다. 스케줄러에서 통신 하는 리소스 관리자와 함께이 지점에서이 인터페이스를 사용 해야 합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 리소스 관리자와 통신을 시작 합니다. 메서드는 연결 된 `IScheduler` 있는 스케줄러에 대 한 인터페이스는 `ISchedulerProxy` 인터페이스와 사용자에 게 전달 합니다. 사용자의 스케줄러에서 사용할 실행 리소스를 요청 하거나 리소스 관리자와 스레드를 구독 하려면 반환 된 인터페이스를 사용할 수 있습니다. 리소스 관리자에서 반환 되는 스케줄러 정책의 정책 요소를에서 사용 합니다는 [ischeduler:: Getpolicy](ischeduler-structure.md#getpolicy) 스케줄러 스레드 형식을 결정 하는 메서드는 작업을 실행 해야 합니다. 경우에 `SchedulerKind` 정책 키에 값 `UmsThreadDefault` 값을 값으로 정책을 읽고 `UmsThreadDefault`, `IScheduler` 메서드에 전달 하는 인터페이스 여야는 `IUMSScheduler` 인터페이스.  
  
 메서드에서 throw 한 `invalid_argument` 예외 경우 매개 변수 `pScheduler` 값 `NULL` 경우 또는 매개 변수 `version` 통신 인터페이스에 대 한 올바른 버전이 아닙니다.  
  
##  <a name="a-namereleasea--iresourcemanagerrelease-method"></a><a name="release"></a>Iresourcemanager:: Release 메서드  
 리소스 관리자 인스턴스에 대 한 참조 횟수를 줄입니다. 참조 횟수가 되 면 리소스 관리자는 소멸 `0`합니다.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>반환 값  
 결과 참조 횟수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [ISchedulerProxy 구조체](ischedulerproxy-structure.md)   
 [IScheduler 구조체](ischeduler-structure.md)

