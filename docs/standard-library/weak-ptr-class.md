---
title: "weak_ptr 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.tr1.weak_ptr"
  - "tr1.weak_ptr"
  - "weak_ptr"
  - "tr1::weak_ptr"
  - "std::tr1::weak_ptr"
  - "memory/std::tr1::weak_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "weak_ptr 클래스"
  - "weak_ptr 클래스[TR1]"
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# weak_ptr 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

약하게 링크된 포인터를 래핑합니다.  
  
## 구문  
  
```  
template<class Ty> class weak_ptr {  
public:  
    typedef Ty element_type;  
  
    weak_ptr();  
    weak_ptr(const weak_ptr&);  
    template<class Other>  
        weak_ptr(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr(const shared_ptr<Other>&);  
  
    weak_ptr& operator=(const weak_ptr&);  
    template<class Other>  
        weak_ptr& operator=(const weak_ptr<Other>&);  
    template<class Other>  
        weak_ptr& operator=(shared_ptr<Other>&);  
  
    void swap(weak_ptr&);  
    void reset();  
  
    long use_count() const;  
    bool expired() const;  
    shared_ptr<Ty> lock() const;  
    };  
```  
  
#### 매개 변수  
 `Ty`  
 약한 포인터에 의해 제어되는 형식입니다.  
  
## 설명  
 이 템플릿 클래스는 하나 이상의 [shared\_ptr 클래스](../standard-library/shared-ptr-class.md) 개체에 의해 관리되는 리소스를 가리키는 개체를 설명합니다.  리소스를 가리키는 `weak_ptr` 개체는 리소스의 참조 횟수에 영향을 주지 않습니다.  따라서 해당 리소스를 관리하는 마지막 `shared_ptr` 개체가 삭제되면 해당 리소스를 가리키는 `weak_ptr` 개체가 있는 경우에도 리소스가 해제됩니다.  이는 데이터 구조에서 순환을 방지하는 데 필요합니다.  
  
 `weak_ptr` 개체는 리소스를 소유하는 `shared_ptr` 개체에서 생성된 경우, 리소스를 가리키는 `weak_ptr` 개체에서 생성된 경우 또는 [weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md)를 사용하여 리소스가 할당된 경우 해당 리소스를 가리킵니다.  `weak_ptr` 개체는 가리키는 리소스에 대한 직접 액세스를 제공하지 않습니다.  리소스를 사용해야 하는 코드는 멤버 함수 [weak\_ptr::lock](../Topic/weak_ptr::lock.md)을 호출하여 만든, 해당 리소스를 소유하는 `shared_ptr` 개체를 통해 사용합니다.  리소스를 소유하는 모든 `shared_ptr` 개체가 삭제되어 `weak_ptr` 개체가 가리키는 리소스가 해제된 경우 개체가 만료되었습니다.  만료된 `weak_ptr` 개체에 대해 `lock`을 호출하면 빈 shared\_ptr 개체가 생성됩니다.  
  
 빈 weak\_ptr 개체는 리소스를 가리키지 않으며 제어 블록이 없습니다.  멤버 함수 `lock`은 빈 shared\_ptr 개체를 반환합니다.  
  
 `shared_ptr` 개체가 제어하는 둘 이상의 리소스가 상호 참조하는 `shared_ptr` 개체를 보유한 경우 순환이 발생합니다.  예를 들어 요소 세 개가 포함된 순환 연결된 목록에 헤드 노드 `N0`가 있습니다. 해당 노드는 다음 노드 `N1`을 소유하는 `shared_ptr` 개체를 보유합니다. 해당 노드는 다음 노드 `N2`를 소유하는 `shared_ptr` 개체를 보유합니다. 해당 노드는 다시 헤드 노드 `N0`을 소유하는 `shared_ptr` 개체를 보유하여 순환을 닫습니다.  이 경우 참조 횟수는 결코 0이 되지 않으며 순환의 노드가 해제되지 않습니다.  순환을 제거하려면 마지막 노드 `N2`가 `shared_ptr` 개체 대신 `N0`을 가리키는 `weak_ptr` 개체를 보유해야 합니다.  `weak_ptr` 개체는 `N0`을 소유하지 않으므로 `N0`의 참조 횟수에 영향을 주지 않으며, 헤드 노드에 대한 프로그램의 마지막 참조가 삭제되면 목록의 노드도 삭제됩니다.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[weak\_ptr::weak\_ptr](../Topic/weak_ptr::weak_ptr.md)|`weak_ptr`를 생성합니다.|  
  
### 메서드  
  
|||  
|-|-|  
|[weak\_ptr::element\_type](../Topic/weak_ptr::element_type.md)|요소의 형식입니다.|  
|[weak\_ptr::expired](../Topic/weak_ptr::expired.md)|소유권이 만료되었는지 테스트합니다.|  
|[weak\_ptr::lock](../Topic/weak_ptr::lock.md)|리소스의 단독 소유권을 가져옵니다.|  
|[weak\_ptr::owner\_before](../Topic/weak_ptr::owner_before.md)|이 `weak_ptr`이 제공된 포인터 앞에 정렬\(또는 보다 작음\)되는 경우 `true`를 반환합니다.|  
|[weak\_ptr::reset](../Topic/weak_ptr::reset.md)|소유하는 리소스를 해제합니다.|  
|[weak\_ptr::swap](../Topic/weak_ptr::swap.md)|두 `weak_ptr` 개체를 교환합니다.|  
|[weak\_ptr::use\_count](../Topic/weak_ptr::use_count.md)|지정된 `shared_ptr` 개체 수를 계산합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[weak\_ptr::operator\=](../Topic/weak_ptr::operator=.md)|소유하는 리소스를 대체합니다.|  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [shared\_ptr 클래스](../standard-library/shared-ptr-class.md)