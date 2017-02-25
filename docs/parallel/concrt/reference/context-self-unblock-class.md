---
title: "context_self_unblock 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::context_self_unblock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "context_self_unblock 클래스"
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# context_self_unblock 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 동일한 컨텍스트에서 `Context` 개체의 `Unblock` 메서드를 호출하는 경우 발생하는 예외를 설명합니다. 자신을 차단 해제하려는 지정된 컨텍스트의 시도를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class context_self_unblock : public std::exception;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[context_self_unblock:: context_self_unblock 생성자](#context_self_unblock__context_self_unblock_constructor)|오버로드됨. `context_self_unblock` 개체를 생성합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `exception`  
  
 `context_self_unblock`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** concrt.h  
  
 **네임스페이스:** 동시성  
  
##  <a name="a-namecontextselfunblockcontextselfunblockconstructora-contextselfunblockcontextselfunblock-constructor"></a><a name="context_self_unblock__context_self_unblock_constructor"></a>  context_self_unblock:: context_self_unblock 생성자  
 `context_self_unblock` 개체를 생성합니다.  
  
```  
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

 
context_self_unblock() throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `_Message`  
 오류 설명 메시지입니다.  
  
## <a name="see-also"></a>참고 항목  
 [동시성 네임 스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)
