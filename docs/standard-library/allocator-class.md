---
title: "allocator 클래스 | Microsoft Docs"
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
  - "std::allocator"
  - "allocator"
  - "memory/std::allocator"
  - "std.allocator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "allocator 클래스"
ms.assetid: 3fd58076-56cc-43bb-ad58-b4b7c9c6b410
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# allocator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 저장소 할당 및 **형식** 형식의 개체에 대한 배열 해제를 관리하는 개체를 설명합니다. 클래스 **allocator**의 개체는 표준 C\+\+ 라이브러리의 여러 컨테이너 템플릿 클래스에 대한 생성자에 지정된 기본 할당자 개체입니다.  
  
## 구문  
  
```  
  
template <class   
Type  
>  
class allocator  
  
```  
  
#### 매개 변수  
 *형식*  
 저장소를 할당하거나 할당 취소할 개체의 형식입니다.  
  
## 설명  
 모든 표준 템플릿 라이브러리 컨테이너에는 **allocator**로 기본 설정되는 템플릿 매개 변수가 있습니다. 사용자 지정 할당자로 컨테이너를 생성하면 해당 컨테이너 요소의 할당 및 해제를 제어할 수 있습니다.  
  
 예를 들어 할당자 개체에서 전용 힙 또는 공유 메모리에 저장소를 할당하거나, 작거나 큰 개체 크기에 맞게 최적화할 수 있습니다. 또한 제공된 형식 정의를 사용하여 공유 메모리를 관리하는 특수 접근자 개체를 통해 요소에 액세스하거나 자동 가비지 컬렉션을 수행하도록 지정할 수 있습니다. 따라서 할당자 개체를 사용하여 저장소를 할당하는 클래스는 표준 C\+\+ 라이브러리의 컨테이너처럼 이러한 형식을 사용하여 포인터 및 참조 개체를 선언해야 합니다.  
  
 **\(C\_\+\+98\/03만 해당\)**할당자 클래스에서 파생시키는 경우 `_Other` typedef에서 새로 파생 클래스를 참조하는 [rebind](../Topic/allocator::rebind.md) 구조체를 제공해야 합니다.  
  
 따라서 할당자는 다음과 같은 형식을 정의합니다.  
  
-   [pointer](../Topic/allocator::pointer.md)는 **형식**에 대한 포인터처럼 동작합니다.  
  
-   [const\_pointer](../Topic/allocator::const_pointer.md)는 **형식**에 대한 const 포인터처럼 동작합니다.  
  
-   [reference](../Topic/allocator::reference.md)는 **형식**에 대한 참조처럼 동작합니다.  
  
-   [const\_reference](../Topic/allocator::const_reference.md)는 **형식**에 대한 const 참조처럼 동작합니다.  
  
 이러한 **형식**은 할당된 요소에 대해 포인터 및 참조를 사용해야 하는 폼을 지정합니다. \([allocator::pointer](../Topic/allocator::pointer.md)는 클래스 **allocator**에 대한 명확한 정의가 있는 경우에도 모든 할당자 개체에 대한 **형식**\*과 동일할 필요가 없습니다.\)  
  
 **C\+\+11 이상:**  할당자에서 이동 작업을 사용하려면 최소 할당자 인터페이스를 사용하고 복사 생성자, \=\= 및 \!\= 연산자, 할당 및 할당 취소를 구현하세요. 자세한 내용 및 예제는 [할당자](../standard-library/allocators.md)를 참조하세요.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[할당자](../Topic/allocator::allocator.md)|`allocator` 개체를 만드는 데 사용되는 생성자입니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[const\_pointer](../Topic/allocator::const_pointer.md)|할당자에 의해 관리되는 개체 형식에 대한 상수 포인터를 제공하는 형식입니다.|  
|[const\_reference](../Topic/allocator::const_reference.md)|할당자에 의해 관리되는 개체 형식에 대한 상수 참조를 제공하는 형식입니다.|  
|[difference\_type](../Topic/allocator::difference_type.md)|할당자에 의해 관리되는 개체 형식에 대한 포인터 값의 차이를 나타낼 수 있는 부호 있는 정수 형식입니다.|  
|[포인터](../Topic/allocator::pointer.md)|할당자에 의해 관리되는 개체 형식에 대한 포인터를 제공하는 형식입니다.|  
|[참조](../Topic/allocator::reference.md)|할당자에 의해 관리되는 개체 형식에 대한 참조를 제공하는 형식입니다.|  
|[size\_type](../Topic/allocator::size_type.md)|템플릿 클래스 `allocator`의 개체가 할당할 수 있는 시퀀스의 길이를 나타내는 부호 없는 정수 형식입니다.|  
|[value\_type](../Topic/allocator::value_type.md)|할당자에 의해 관리되는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[주소](../Topic/allocator::address.md)|값이 지정된 개체의 주소를 찾습니다.|  
|[할당](../Topic/allocator::allocate.md)|적어도 지정된 개수의 요소를 저장할 수 있을 만큼 큰 메모리 블록을 할당합니다.|  
|[construct](../Topic/allocator::construct.md)|지정된 값으로 초기화된 특정 형식의 개체를 지정된 주소에 생성합니다.|  
|[deallocate](../Topic/allocator::deallocate.md)|지정된 위치부터 시작하여 저장소에서 지정된 개수의 개체를 해제합니다.|  
|[제거](../Topic/allocator::destroy.md)|개체가 저장된 메모리 할당을 취소하지 않고 개체 소멸자를 호출합니다.|  
|[max\_size](../Topic/allocator::max_size.md)|사용 가능한 메모리를 사용하기 전에 클래스 `allocator`의 개체에서 할당할 수 있는 `Type` 형식의 요소 수를 반환합니다.|  
|[rebind](../Topic/allocator::rebind.md)|한 형식의 개체에 할당자를 사용하여 다른 형식의 개체에 저장소를 할당할 수 있는 구조체입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\=](../Topic/allocator::operator=.md)|`allocator` 개체를 다른 `allocator` 개체에 할당합니다.|  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)