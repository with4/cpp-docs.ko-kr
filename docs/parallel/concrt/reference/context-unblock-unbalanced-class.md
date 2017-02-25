---
title: "context_unblock_unbalanced 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::context_unblock_unbalanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "context_unblock_unbalanced 클래스"
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# context_unblock_unbalanced 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 동일한 컨텍스트에서 `Context` 개체의 `Block` 및 `Unblock` 메서드 호출 쌍이 잘못된 경우 발생하는 예외를 설명합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[context_unblock_unbalanced:: context_unblock_unbalanced 생성자](#context_unblock_unbalanced__context_unblock_unbalanced_constructor)|오버로드됨. `context_unblock_unbalanced` 개체를 생성합니다.|  
  
## <a name="remarks"></a>설명  
 에 대 한 호출이 `Block` 및 `Unblock` 의 메서드는 `Context` 개체 항상 올바르게 콜백과 해야 합니다. 동시성 런타임에 작업이 어떤 순서로 든 발생할 수 있습니다. 예를 들어 `Block` 호출 다음에 `Unblock` 호출이 오거나 그 반대가 될 수 있습니다. 예를 들어,를 두 번 호출 하는 경우이 예외가 throw 됩니다는 `Unblock` 메서드에서 한 행에 적용 되었습니다. 한 `Context` 개체를 이전에 차단 되지 않습니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namecontextunblockunbalancedcontextunblockunbalancedconstructora-contextunblockunbalancedcontextunblockunbalanced-constructor"></a><a name="context_unblock_unbalanced__context_unblock_unbalanced_constructor"></a>  context_unblock_unbalanced:: context_unblock_unbalanced 생성자  
 `context_unblock_unbalanced` 개체를 생성합니다.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 네임 스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)
