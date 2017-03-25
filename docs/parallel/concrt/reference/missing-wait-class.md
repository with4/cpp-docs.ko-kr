---
title: "missing_wait 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: 19
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 70b1c77660992b33de2204fd4f4221ed6e957e21
ms.lasthandoff: 03/17/2017

---
# <a name="missingwait-class"></a>missing_wait 클래스
이 클래스는 개체의 소멸자를 실행할 때 `task_group` 또는 `structured_task_group` 개체에 여전히 예약된 작업이 있는 경우 발생하는 예외를 설명합니다. 예외의 결과로 스택 해제 때문에 소멸자에 도달한 경우에는 이 예외가 발생하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[missing_wait](#ctor)|오버로드됨. `missing_wait` 개체를 생성합니다.|  
  
## <a name="remarks"></a>주의  
 예외 흐름이 없으면 담당 하는 호출의 `wait` 또는 `run_and_wait` 의 메서드는 `task_group` 또는 `structured_task_group` 개체를 소멸 하는 개체를 허용 하기 전에 합니다. 호출 하는 것을 잊어버린 한다는 표시로이 예외를 throw 하는 런타임에 `wait` 또는 `run_and_wait` 메서드.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a>missing_wait 

 `missing_wait` 개체를 생성합니다.  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [task_group 클래스](task-group-class.md)   
 [대기](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [structured_task_group 클래스](structured-task-group-class.md)

