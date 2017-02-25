---
title: "concurrent_queue 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_queue/concurrency::concurrent_queue"
  - "concurrent_queue/Concurrency::concurrent_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_queue 클래스"
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# concurrent_queue 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_queue` 클래스는 요소에 선입선출 방식으로 액세스할 수 있는 시퀀스 컨테이너 클래스입니다.  이것은 `push` 및 `try_pop` 같은 동시성이 보장된 작업의 제한된 집합을 활성화합니다.  
  
## 구문  
  
```  
template<  
   typename _Ty,  
   class _Ax  
>  
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;  
```  
  
#### 매개 변수  
 `_Ty`  
 큐에 저장될 요소의 데이터 형식입니다.  
  
 `_Ax`  
 동시 큐를 위한 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당기 개체를 나타내는 형식입니다.  이 인수는 선택적 요소이며 기본값은 `allocator<``_Ty``>`입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`allocator_type`|동시 큐의 할당자 클래스를 나타내는 형식입니다.|  
|`const_iterator`|연속 큐에 있는 요소에서 스레드가 안전하지 않은 `const` 반복기를 나타내는 형식입니다.|  
|`const_reference`|`const` 작업을 읽고 수행하기 위해 동시 큐에 저장된 `const` 요소에 대한 참조를 제공하는 형식입니다.|  
|`difference_type`|동시 큐에 있는 두 요소 사이의 부호가 있는 거리를 제공하는 형식입니다.|  
|`iterator`|연속 큐에 있는 요소에서 스레드가 안전하지 않은 반복기를 나타내는 형식입니다.|  
|`reference`|동시 큐에 저장된 요소에 대한 참조를 제공하는 형식입니다.|  
|`size_type`|동시 큐에 있는 요소의 수를 세는 형식입니다.|  
|`value_type`|동시 큐에 저장된 데이터 형식을 나타내는 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_queue::concurrent\_queue 생성자](../Topic/concurrent_queue::concurrent_queue%20Constructor.md)|오버로드됨.  동시 큐를 생성합니다.|  
|[concurrent\_queue::~concurrent\_queue 소멸자](../Topic/concurrent_queue::~concurrent_queue%20Destructor.md)|동시 큐를 소멸시킵니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_queue::clear 메서드](../Topic/concurrent_queue::clear%20Method.md)|현재 큐에 추가된 요소를 소멸시켜 동시 큐를 지웁니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_queue::empty 메서드](../Topic/concurrent_queue::empty%20Method.md)|이 메서드가 호출될 때 동시 큐가 비어 있는지 테스트합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_queue::get\_allocator 메서드](../Topic/concurrent_queue::get_allocator%20Method.md)|동시 큐를 생성하는 데 사용되는 할당자 복사본을 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_queue::push 메서드](../Topic/concurrent_queue::push%20Method.md)|오버로드됨.  동시 큐의 꼬리 끝에 있는 항목을 큐에 추가합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_queue::try\_pop 메서드](../Topic/concurrent_queue::try_pop%20Method.md)|사용할 수 있는 경우 큐에서 항목을 제거합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_queue::unsafe\_begin 메서드](../Topic/concurrent_queue::unsafe_begin%20Method.md)|오버로드됨.  동시 큐의 시작 부분에 대한 형식 `iterator` 또는 `const_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_queue::unsafe\_end 메서드](../Topic/concurrent_queue::unsafe_end%20Method.md)|오버로드됨.  동시 큐의 끝 부분에 대한 형식 `iterator` 또는 `const_iterator`의 반복기를 반환합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_queue::unsafe\_size 메서드](../Topic/concurrent_queue::unsafe_size%20Method.md)|큐의 항목 수를 반환합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
  
## 설명  
 자세한 내용은 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)을 참조하십시오.  
  
## 상속 계층  
 `concurrent_queue`  
  
## 요구 사항  
 **헤더:** concurrent\_queue.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)