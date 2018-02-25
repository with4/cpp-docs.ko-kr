---
title: "improper_scheduler_detach 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
dev_langs:
- C++
helpviewer_keywords:
- improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7b0a11ed3d65403444c62147091f443d3f102676
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="improperschedulerdetach-class"></a>improper_scheduler_detach 클래스
이 클래스는 `Scheduler` 개체의 `Attach` 메서드를 사용하여 스케줄러에 연결되지 않은 컨텍스트에 대해 `CurrentScheduler::Detach` 메서드를 호출하는 경우 발생하는 예외를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
class improper_scheduler_detach : public std::exception;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[improper_scheduler_detach](#ctor)|오버로드됨. `improper_scheduler_detach` 개체를 생성합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `improper_scheduler_detach`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a> improper_scheduler_detach 

 `improper_scheduler_detach` 개체를 생성합니다.  
  
```
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [Scheduler 클래스](scheduler-class.md)
