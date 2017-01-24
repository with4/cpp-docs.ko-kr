---
title: "unique_ptr 클래스 | Microsoft Docs"
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
  - "unique_ptr"
  - "std.unique_ptr"
  - "std::unique_ptr"
  - "memory/std::unique_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unique_ptr 클래스"
ms.assetid: acdf046b-831e-4a4a-83aa-6d4ee467db9a
caps.latest.revision: 22
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unique_ptr 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

소유한 개체 또는 배열에 대한 포인터를 저장합니다.  개체\/배열은 다른 `unique_ptr`이 소유하지 않습니다.  개체\/배열은 `unique_ptr`이 소멸될 때 소멸됩니다.  
  
## 구문  
  
```  
template< class T, class Del = default_delete<T> >  
    class unique_ptr {  
public:  
    unique_ptr( );  
    unique_ptr( nullptr_t Nptr );  
    explicit unique_ptr( pointer Ptr );  
    unique_ptr( pointer Ptr,  
        typename conditional<is_reference<Del>::value,   
            Del,  
            typename add_reference<const Del>::type>::type Deleter);  
    unique_ptr (pointer Ptr,  
        typename remove_reference<Del>::type&& Deleter);  
    unique_ptr (unique_ptr&& Right);  
    template<class T2, Class Del2> unique_ptr( unique_ptr<T2, Del2>&& Right );  
    unique_ptr( const unique_ptr& Right    ) = delete;  
    unique_ptr& operator=(const unique_ptr& Right     ) = delete;  
};  
  
```  
  
```  
//Specialization for arrays:  
template <class T, class D> class unique_ptr<T[], D>   
{   public:       
     typedef pointer;  
     typedef T element_type;  
     typedef D deleter_type;  
  
     constexpr unique_ptr() noexcept;  
     template <class U> explicit unique_ptr(U p) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     template <class U> unique_ptr(U p, see below d) noexcept;  
     unique_ptr(unique_ptr&& u) noexcept;  
     constexpr unique_ptr(nullptr_t) noexcept : unique_ptr() { }  
     template <class U, class E>  
       unique_ptr(unique_ptr<U, E>&& u) noexcept;  
  
     ~unique_ptr();  
  
     unique_ptr& operator=(unique_ptr&& u) noexcept;  
     template <class U, class E>  
       unique_ptr& operator=(unique_ptr<U, E>&& u) noexcept;  
     unique_ptr& operator=(nullptr_t) noexcept;  
  
     T& operator[](size_t i) const;  
     pointer get() const noexcept;  
     deleter_type& get_deleter() noexcept;  
     const deleter_type& get_deleter() const noexcept;  
     explicit operator bool() const noexcept;  
  
     pointer release() noexcept;  
     void reset(pointer p = pointer()) noexcept;  
     void reset(nullptr_t = nullptr) noexcept;  
     template <class U> void reset(U p) noexcept = delete;  
     void swap(unique_ptr& u) noexcept;  
  
    // disable copy from lvalue  
     unique_ptr(const unique_ptr&) = delete;  
     unique_ptr& operator=(const unique_ptr&) = delete;  
   };  
 }  
  
```  
  
#### 매개 변수  
 `Right`  
 `unique_ptr`  
  
 `Nptr`  
 `rvalue` 형식의 `std::nullptr_t`입니다.  
  
 `Ptr`  
 `pointer`  
  
 `Deleter`  
 `deleter`에 바인딩되는 `unique_ptr` 함수.  
  
## 예외  
 `unique_ptr`에는 예외가 생성되지 않았습니다.  
  
## 설명  
 `unique_ptr` 클래스는 `auto_ptr`을 대체하며 STL 컨테이너의 요소로 사용할 수 있습니다.  
  
 의 새 인스턴스를 효율적으로 만들려면 [make\_unique](../Topic/make_unique.md) `unique_ptr`도우미 함수를 사용하십시오.  
  
 `unique_ptr`은 리소스를 고유하게 관리합니다.  각 `unique_ptr` 개체는 null 포인터를 소유 또는 저장하는 개체에 대해 포인터를 저장합니다.  리소스는 둘 이상의 `unique_ptr` 개체가 소유할 수 없습니다.  특정 리소스를 소유하는 `unique_ptr` 개체가 소멸될 때 리소스가 해제됩니다.  `unique_ptr` 개체를 이동할 수 있지만 복사할 수는 없습니다.  자세한 내용은 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 참조하세요.  
  
 리소스는 특정 `deleter`에 대해 리소스가 할당된 방식을 알고 있는 `Del` 형식의 저장된 `unique_ptr` 개체를 호출하여 해제됩니다.  기본 `deleter` `default_delete``<T>`는 `_Ptr`를 사용하여 `new`에서 가리키는 리소스를 할당하고 `delete _``Ptr`을 호출하여 해제할 수 있음을 가정합니다.  \(부분 특수화 `unique_ptr<T[]>`는 `new[]`로 할당된 배열 개체를 관리하며, delete\[\] `deleter`을 호출하는 데 전문화된 기본 `default_delete<T[]>``_Ptr`이 있습니다.\)  
  
 소유한 리소스에 대한 저장된 포인터, `stored_ptr`에는 `pointer`가 있습니다.  정의된 경우 `Del::pointer`이고, 정의되지 않은 경우 `T *` 입니다.  `deleter`가 상태 비저장일 경우 저장된 `stored_deleter` 개체 `deleter`는 개체에서 공간을 차지하지 않습니다.  `Del`는 참조 형식이 될 수 있습니다.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[unique\_ptr::unique\_ptr](../Topic/unique_ptr::unique_ptr.md)|`unique_ptr`의 8가지 생성자가 있습니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[deleter\_type](../Topic/deleter_type.md)|템플릿 매개 변수 `Del`의 동의어.|  
|[element\_type](../Topic/element_type.md)|템플릿 매개 변수 `T`의 동의어`.`|  
|[포인터](../Topic/pointer.md)|`Del::pointer`의 동의어\(정의된 경우\)이며 그렇지 않은 경우 `T *`.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[unique\_ptr::get](../Topic/unique_ptr::get.md)|`stored_ptr`를 반환합니다.|  
|[unique\_ptr::get\_deleter](../Topic/unique_ptr::get_deleter.md)|`stored_deleter`에 대한 참조를 반환합니다.|  
|[unique\_ptr::release](../Topic/unique_ptr::release.md)|`pointer()`에 `stored_ptr`를 반환하고 이전 내용을 반환합니다.|  
|[unique\_ptr::reset](../Topic/unique_ptr::reset.md)|현재 소유한 리소스를 해제하고 새 리소스를 허용합니다.|  
|[unique\_ptr::swap](../Topic/unique_ptr::swap.md)|리소스를 교환하고 `deleter`를 제공된 `unique_ptr`로 교환합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|`operator bool`|연산자는 `bool`로 변환 가능한 형식의 값을 반환합니다.  `bool`일 경우 `true`로 변환한 결과는 `get() != pointer()`입니다. 그렇지 않으면 `false`입니다.|  
|`operator->`|멤버 함수에서 `stored_ptr`을 반환합니다`.`|  
|`operator*`|멤버 함수에서 `stored_ptr`을 반환합니다\*`.`|  
|[unique\_ptr operator\=](../Topic/unique_ptr%20operator=.md)|`unique_ptr`  값\(또는 `pointer-type`\) 값을 현재 `unique_ptr`에 할당합니다.|  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<memory\>](../standard-library/memory.md)