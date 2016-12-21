---
title: "allocator_base 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "allocators.allocator_base"
  - "stdext.allocators.allocator_base"
  - "allocator_base"
  - "allocators/stdext::allocator_base"
  - "stdext::allocator_base"
  - "stdext::allocators::allocator_base"
  - "allocators/stdext::allocators::allocator_base"
  - "allocators::allocator_base"
  - "stdext.allocator_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator_base 클래스"
ms.assetid: f920b45f-2a88-4bb0-8ead-b6126b426ed4
caps.latest.revision: 17
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator_base 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동기화 필터에서 사용자 정의 할당자를 만드는 데 필요한 기본 클래스 및 일반 함수를 정의합니다.  
  
## 구문  
  
```  
template <class Type, class Sync> class allocator_base  
```  
  
#### 매개 변수  
  
|매개 변수|설명|  
|-----------|--------|  
|`Type`|할당자에 의해 할당된 요소 형식입니다.|  
|`Sync`|할당자에 대한 동기화 정책\([sync\_none 클래스](../standard-library/sync-none-class.md), [sync\_per\_container 클래스](../standard-library/sync-per-container-class.md), [sync\_per\_thread 클래스](../standard-library/sync-per-thread-class.md) 또는 [sync\_shared 클래스](../standard-library/sync-shared-class.md)\)입니다.|  
  
### 생성자  
  
|||  
|-|-|  
|[allocator\_base](../Topic/allocator_base::allocator_base.md)|`allocator_base` 형식의 개체를 생성합니다.|  
  
### TypeDefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator_base::const_pointer.md)|할당자에 의해 관리되는 개체 형식에 대한 상수 포인터를 제공하는 형식입니다.|  
|[const\_reference](../Topic/allocator_base::const_reference.md)|할당자에 의해 관리되는 개체 형식에 대한 상수 참조를 제공하는 형식입니다.|  
|[difference\_type](../Topic/allocator_base::difference_type.md)|할당자에 의해 관리되는 개체 형식에 대한 포인터 값의 차이를 나타낼 수 있는 부호 있는 정수 형식입니다.|  
|[포인터](../Topic/allocator_base::pointer.md)|할당자에 의해 관리되는 개체 형식에 대한 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/allocator_base::reference.md)|할당자에 의해 관리되는 개체 형식에 대한 참조를 제공하는 형식입니다.|  
|[size\_type](../Topic/allocator_base::size_type.md)|템플릿 클래스 `allocator_base`의 개체가 할당할 수 있는 시퀀스의 길이를 나타내는 부호 없는 정수 형식입니다.|  
|[value\_type](../Topic/allocator_base::value_type.md)|할당자에 의해 관리되는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[\_Charalloc](../Topic/allocator_base::_Charalloc.md)|`char` 형식의 배열에 대한 저장소를 할당합니다.|  
|[\_Chardealloc](../Topic/allocator_base::_Chardealloc.md)|`char` 형식의 요소를 포함하는 배열에 대한 저장소를 해제합니다.|  
|[주소](../Topic/allocator_base::address.md)|값이 지정된 개체의 주소를 찾습니다.|  
|[할당](../Topic/allocator_base::allocate.md)|적어도 지정된 개수의 요소를 저장할 수 있을 만큼 큰 메모리 블록을 할당합니다.|  
|[construct](../Topic/allocator_base::construct.md)|지정된 값으로 초기화된 특정 형식의 개체를 지정된 주소에 생성합니다.|  
|[deallocate](../Topic/allocator_base::deallocate.md)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
|[destroy](../Topic/allocator_base::destroy.md)|개체가 저장된 메모리 할당을 취소하지 않고 개체 소멸자를 호출합니다.|  
|[max\_size](../Topic/allocator_base::max_size.md)|사용 가능한 메모리가 모두 사용되기 전에 allocator 클래스의 개체가 할당할 수 있는 `Type` 형식의 요소 수를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<allocators\>  
  
 **네임스페이스:** stdext  
  
## 참고 항목  
 [\<allocators\>](../standard-library/allocators-header.md)