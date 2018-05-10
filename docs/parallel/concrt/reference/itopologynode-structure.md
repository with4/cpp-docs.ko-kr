---
title: ITopologyNode 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
dev_langs:
- C++
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c4168fbfbd2bf17ad8b8b752d2843c8f57b0f3f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="itopologynode-structure"></a>ITopologyNode 구조체
리소스 관리자에 의해 정의된 토폴로지 노드에 대한 인터페이스입니다. 노드는 하나 이상의 실행 리소스를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```
struct ITopologyNode;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[ITopologyNode::GetExecutionResourceCount](#getexecutionresourcecount)|이 노드 아래에 함께 그룹화된 실행 리소스의 수를 반환합니다.|  
|[ITopologyNode::GetFirstExecutionResource](#getfirstexecutionresource)|열거 순서에서 이 노드 아래에 그룹화된 첫 번째 실행 리소스를 반환합니다.|  
|[ITopologyNode::GetId](#getid)|이 노드에 대 한 리소스 관리자의 고유 식별자를 반환합니다.|  
|[ITopologyNode::GetNext](#getnext)|열거 순서에 따라 다음 토폴로지 노드로 인터페이스를 반환합니다.|  
|[ITopologyNode::GetNumaNode](#getnumanode)|이 리소스 관리자가 노드가 속한 NUMA 노드 번호를 할당 하는 창을 반환 합니다.|  
  
## <a name="remarks"></a>설명  
 이 인터페이스는 리소스 관리자가 확인 되는 시스템의 토폴로지가 안내 하는 일반적으로 사용 됩니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `ITopologyNode`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrtrm.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="getexecutionresourcecount"></a>  ITopologyNode::GetExecutionResourceCount Method  
 이 노드 아래에 함께 그룹화된 실행 리소스의 수를 반환합니다.  
  
```
virtual unsigned int GetExecutionResourceCount() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 이 노드 아래에 함께 그룹화된 실행 리소스의 수입니다.  
  
##  <a name="getfirstexecutionresource"></a>  Itopologynode:: Getfirstexecutionresource 메서드  
 열거 순서에서 이 노드 아래에 그룹화된 첫 번째 실행 리소스를 반환합니다.  
  
```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 열거 순서에서 이 노드 아래에 그룹화된 첫 번째 실행 리소스입니다.  
  
##  <a name="getid"></a>  Itopologynode:: Getid 메서드  
 이 노드에 대 한 리소스 관리자의 고유 식별자를 반환합니다.  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 리소스 관리자의이 노드에 대 한 고유 식별자입니다.  
  
### <a name="remarks"></a>설명  
 동시성 런타임 프로세서 노드 그룹에는 시스템에서 하드웨어 스레드를 나타냅니다. 노드는 일반적으로 시스템의 하드웨어 토폴로지에에서 파생 됩니다. 예를 들어 동일한 프로세서 노드에서 모든 프로세서 특정 NUMA 노드 또는 특정 소켓에 속할 수 있습니다. 부터는이 노드를 고유 식별자를 할당 하는 리소스 관리자 `0` 까지 포함 하 여 `nodeCount - 1`여기서 `nodeCount` 시스템에서 프로세서 노드의 총 수를 나타냅니다.  
  
 함수에서 노드 수를 얻을 수 있습니다 [GetProcessorNodeCount](concurrency-namespace-functions.md)합니다.  
  
##  <a name="getnext"></a>  Itopologynode:: Getnext 메서드  
 열거 순서에 따라 다음 토폴로지 노드로 인터페이스를 반환합니다.  
  
```
virtual ITopologyNode *GetNext() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 열거 순서에서 다음 노드에 대한 인터페이스입니다. 시스템 토폴로지의 열거 순서에 노드가 더 이상 없을 경우 이 메서드는 `NULL` 값을 반환합니다.  
  
##  <a name="getnumanode"></a>  Itopologynode:: Getnumanode 메서드  
 이 리소스 관리자가 노드가 속한 NUMA 노드 번호를 할당 하는 창을 반환 합니다.  
  
```
virtual unsigned long GetNumaNode() const = 0;
```  
  
### <a name="return-value"></a>반환 값  
 Windows는이 리소스 관리자 노드 속해 있는 NUMA 노드 번호를 할당 합니다.  
  
### <a name="remarks"></a>설명  
 이 노드에 속하는 가상 프로세서 루트에서 실행 되는 스레드 프록시에 대 한 선호도를 하나 이상 갖습니다이 메서드에서 반환 된 NUMA 노드에 대 한 NUMA 노드 수준입니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
