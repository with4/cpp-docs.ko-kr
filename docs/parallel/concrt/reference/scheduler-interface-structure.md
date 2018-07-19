---
title: scheduler_interface 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
dev_langs:
- C++
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b06b270c4971239b91fa81b9ad35d8fef52b7e76
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696307"
---
# <a name="schedulerinterface-structure"></a>scheduler_interface 구조체
Scheduler 인터페이스  
  
## <a name="syntax"></a>구문  
  
```
struct __declspec(novtable) scheduler_interface;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[scheduler_interface::schedule](#schedule)||  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `scheduler_interface`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** pplinterface.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="schedule"></a>  scheduler_interface:: schedule 메서드  
  
```
virtual void schedule(
    TaskProc_t,
 void*) = 0;
```  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
