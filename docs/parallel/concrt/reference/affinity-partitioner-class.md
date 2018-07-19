---
title: affinity_partitioner 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
dev_langs:
- C++
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2242346bda717117e2b43ba108d86fd2a77a3b58
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691133"
---
# <a name="affinitypartitioner-class"></a>affinity_partitioner 클래스
`affinity_partitioner` 클래스는 `static_partitioner` 클래스와 비슷하지만 하위 범위를 작업자 스레드로 매핑하는 선택을 통해 캐시 선호도를 향상시킵니다. 동일한 데이터 집합에서 루프를 다시 실행하고 데이터가 캐시에 맞는 경우 성능을 훨씬 향상시킬 수 있습니다. 데이터 집약성을 활용하려면 특정 데이터 집합에 대해 실행되는 병렬 루프의 후속 반복과 함께 동일한 `affinity_partitioner` 개체를 사용해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class affinity_partitioner;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[affinity_partitioner](#ctor)|`affinity_partitioner` 개체를 생성합니다.|  
|[~ affinity_partitioner 소멸자](#dtor)|제거 프로그램 `affinity_partitioner` 개체입니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `affinity_partitioner`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dtor"></a> ~affinity_partitioner 

 제거 프로그램 `affinity_partitioner` 개체입니다.  
  
```
~affinity_partitioner();
```  
  
##  <a name="ctor"></a> affinity_partitioner 

 `affinity_partitioner` 개체를 생성합니다.  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
