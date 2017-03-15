---
title: "task_canceled 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: dcf930c7efd1a7d7b015919b2009440045dd18fe
ms.lasthandoff: 02/24/2017

---
# <a name="taskcanceled-class"></a>task_canceled 클래스
이 클래스는 현재 작업을 강제 취소하도록 PPL 작업 레이어에서 throw된 예외를 설명합니다. 또한 의해 throw 되는 `get()` 메서드를 [작업](/visualstudio/extensibility/debugger/task-class-internal-members), 취소 된 작업에 대 한 합니다.  
  
## <a name="syntax"></a>구문  
  
```
class task_canceled : public std::exception;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[task_canceled 생성자](#ctor)|오버로드됨. `task_canceled` 개체를 생성합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `task_canceled`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namectora-taskcanceled"></a><a name="ctor"></a>task_canceled 

 `task_canceled` 개체를 생성합니다.  
  
```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)

