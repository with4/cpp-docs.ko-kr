---
title: "concurrent_priority_queue 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concurrent_priority_queue/concurrency::concurrent_priority_queue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "concurrent_priority_queue 클래스"
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# concurrent_priority_queue 클래스
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

`concurrent_priority_queue` 클래스는 여러 스레드가 동시에 항목을 push 및 pop 할 수 있는 컨테이너입니다.  항목들은은 템플릿 인수로 제공되는 함수에 의해 결정되는 우선 순위에 따라 팝 됩니다.  
  
## 구문  
  
```  
template <  
   typename _Ty,  
   typename _Compare=std::less<_Ty>,  
   typename _Ax = std::allocator<_Ty>  
>  
, typename _Ax = std::allocator<_Ty> > class concurrent_priority_queue;  
```  
  
#### 매개 변수  
 `_Ty`  
 우선순위 큐에 저장될 요소의 데이터 형식입니다.  
  
 `_Compare`  
 함수 개체의 형식은 우선순위 큐 내에서의 상대적인 순서를 결정하는 정렬 키로 두 요소 값을 비교할 수 있습니다.  이 인수는 선택적이며 이진 술어 `less<``_Ty``>`가 기본값입니다.  
  
 `_Ax`  
 동시 우선순위 큐를 위한 할당 및 할당 취소에 대한 세부 정보를 캡슐화하는 저장된 할당기 개체를 나타내는 형식입니다.  이 인수는 선택적 요소이며 기본값은 `allocator<``_Ty``>`입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|`allocator_type`|우선순위 큐의 할당자 클래스를 나타내는 형식입니다.|  
|`const_reference`|우선 순위 큐에 저장 된 형식의 요소를 나타내는 상수 참조 하는 형식입니다.|  
|`reference`|우선 순위 큐에 저장 된 형식의 요소의 참조를 나타내는 형식입니다.|  
|`size_type`|현재 우선순위 큐에 있는 요소의 수를 세는 형식입니다.|  
|`value_type`|현재 우선순위 큐에 저장된 데이터 형식을 나타내는 형식입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_priority\_queue::concurrent\_priority\_queue 생성자](../Topic/concurrent_priority_queue::concurrent_priority_queue%20Constructor.md)|오버로드됨.  우선순위 큐를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_priority\_queue::clear 메서드](../Topic/concurrent_priority_queue::clear%20Method.md)|현재 우선순위의 모든 요소를 지웁니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_priority\_queue::empty 메서드](../Topic/concurrent_priority_queue::empty%20Method.md)|이 메서드가 호출될 때 현재 우선순위 큐가 비어 있는지 테스트합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_priority\_queue::get\_allocator 메서드](../Topic/concurrent_priority_queue::get_allocator%20Method.md)|현재 우선순위 큐를 생성하는 데 사용되는 할당자 복사본을 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_priority\_queue::push 메서드](../Topic/concurrent_priority_queue::push%20Method.md)|오버로드됨.  현재 우선 순위 큐에 요소를 추가 합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_priority\_queue::size 메서드](../Topic/concurrent_priority_queue::size%20Method.md)|동시 우선순위 큐에 있는 요소의 개수를 반환합니다.  이 메서드는 동시성이 보장됩니다.|  
|[concurrent\_priority\_queue::swap 메서드](../Topic/concurrent_priority_queue::swap%20Method.md)|두 개의 현재 우선 순위 큐의 내용을 바꿉니다.  이 메서드는 동시성이 보장되지 않습니다.|  
|[concurrent\_priority\_queue::try\_pop 메서드](../Topic/concurrent_priority_queue::try_pop%20Method.md)|큐가 비어 있지 않은 경우 큐에서 우선 순위가 가장 높은 요소를 반환하고 제거합니다.  이 메서드는 동시성이 보장됩니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[concurrent\_priority\_queue::operator\= 연산자](../Topic/concurrent_priority_queue::operator=%20Operator.md)|오버로드됨.  다른 `concurrent_priority_queue` 개체의 내용을 여기에 할당합니다.  이 메서드는 동시성이 보장되지 않습니다.|  
  
## 설명  
 `concurrent_priority_queue`에 대한 자세한 내용은 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)를 참조하십시오.  
  
## 상속 계층  
 `concurrent_priority_queue`  
  
## 요구 사항  
 **헤더:** concurrent\_priority\_queue.h  
  
 **네임스페이스:** 동시성  
  
## 참고 항목  
 [동시성 네임스페이스](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [병렬 컨테이너 및 개체](../../../parallel/concrt/parallel-containers-and-objects.md)