---
title: "out_of_memory 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- out_of_memory
- AMPRT/out_of_memory
- AMPRT/Concurrency::out_of_memory::out_of_memory
dev_langs:
- C++
helpviewer_keywords:
- out_of_memory class
ms.assetid: 3aa7e682-8f13-4ae6-9188-31fb423956e4
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b593f8f85d4e36496f2ec2fc7bbadf8f2bfd742e
ms.lasthandoff: 02/24/2017

---
# <a name="outofmemory-class"></a>out_of_memory 클래스
시스템 또는 장치 메모리 부족으로 인해 메서드가 실패할 때 throw 되는 예외입니다.  
  
## <a name="syntax"></a>구문  
  
```  
class out_of_memory : public runtime_exception;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[out_of_memory 생성자](#ctor)|`out_of_memory` 클래스의 새 인스턴스를 초기화합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** amprt.h  
  
 **네임스페이스:** 동시성  
## <a name="ctor"></a>out_of_memory 

 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```  
explicit out_of_memory(  
    const char * _Message ) throw();  
  
out_of_memory () throw();  
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류에 대한 설명입니다.  
  
### <a name="return-value"></a>반환 값  
 `out_of_memory` 클래스의 새 인스턴스입니다.  
  
  
## <a name="see-also"></a>참고 항목  
 [동시성 Namespace (c + + AMP)](concurrency-namespace-cpp-amp.md)

