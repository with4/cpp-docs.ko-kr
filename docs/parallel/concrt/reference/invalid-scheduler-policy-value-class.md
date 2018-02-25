---
title: "invalid_scheduler_policy_value 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbcbef5fc97f10b923b9a6b692a7cfa3799151b0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="invalidschedulerpolicyvalue-class"></a>invalid_scheduler_policy_value 클래스
이 클래스는 `SchedulerPolicy` 개체의 정책 키가 해당 키에 잘못된 값으로 설정된 경우 발생하는 예외를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```
class invalid_scheduler_policy_value : public std::exception;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[invalid_scheduler_policy_value](invalid-scheduler-policy-thread-specification-class.md#ctor|오버로드됨. `invalid_scheduler_policy_value` 개체를 생성합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
    
##  <a name="ctor"></a> invalid_scheduler_policy_value 

 `invalid_scheduler_policy_value` 개체를 생성합니다.  
  
```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  

## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [SchedulerPolicy 클래스](schedulerpolicy-class.md)
