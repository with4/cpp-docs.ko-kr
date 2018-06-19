---
title: task_canceled 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f535a4cce75d388437025967b9c0c9b1ae0fd7a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690249"
---
# <a name="taskcanceled-class"></a>task_canceled 클래스
이 클래스는 현재 작업을 강제 취소하도록 PPL 작업 레이어에서 throw된 예외를 설명합니다. throw 됩니다는 `get()` 메서드를 [작업](/visualstudio/extensibility/debugger/task-class-internal-members), 취소 된 작업에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class task_canceled : public std::exception;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[task_canceled](#ctor)|오버로드됨. `task_canceled` 개체를 생성합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `task_canceled`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a> task_canceled 

 `task_canceled` 개체를 생성합니다.  
  
```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [concurrency 네임스페이스](concurrency-namespace.md)
