---
title: invalid_link_target 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
dev_langs:
- C++
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e718bd1a15df98487d0e9437c217c1750bfa5f5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695787"
---
# <a name="invalidlinktarget-class"></a>invalid_link_target 클래스
이 클래스는 메시징 블록의 `link_target` 메서드를 호출하고 메시징 블록이 대상에 연결할 수 없는 경우 발생하는 예외를 설명합니다. 메시징 블록에 허용되는 링크 수를 초과했거나 동일한 소스에 특정 대상을 두 번 연결하려고 시도한 결과일 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
class invalid_link_target : public std::exception;
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[invalid_link_target](#ctor)|오버로드됨. `invalid_link_target` 개체를 생성합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `invalid_link_target`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="ctor"></a> invalid_link_target 

 `invalid_link_target` 개체를 생성합니다.  
  
```
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Namespace 동시성](concurrency-namespace.md)   
 [비동기 메시지 블록](../../../parallel/concrt/asynchronous-message-blocks.md)



