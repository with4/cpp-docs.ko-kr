---
title: auto_partitioner 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
dev_langs:
- C++
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05232aa954a9ded7d2ab3a26ae4e1524610c3d04
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33705447"
---
# <a name="autopartitioner-class"></a>auto_partitioner 클래스
`auto_partitioner` 클래스는 `parallel_for`, `parallel_for_each` 및 `parallel_transform`이 반복하는 범위를 분할하는 데 사용하는 기본 방법을 나타냅니다. 이 분할 방법은 부하 분산을 위한 범위 가로채기 및 반복별 취소를 사용합니다.  
  
## <a name="syntax"></a>구문  
  
```
class auto_partitioner;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[auto_partitioner](#ctor)|`auto_partitioner` 개체를 생성합니다.|  
|[~ auto_partitioner 소멸자](#dtor)|`auto_partitioner` 개체를 제거합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `auto_partitioner`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** ppl.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="dtor"></a> ~auto_partitioner 

 `auto_partitioner` 개체를 제거합니다.  
  
```
~auto_partitioner();
```  
  
##  <a name="ctor"></a> auto_partitioner 

 `auto_partitioner` 개체를 생성합니다.  
  
```
auto_partitioner();
```  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
