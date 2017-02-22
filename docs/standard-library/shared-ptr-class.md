---
title: "shared_ptr 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "shared_ptr"
  - "tr1::shared_ptr"
  - "memory/std::tr1::shared_ptr"
  - "std::tr1::shared_ptr"
  - "std.tr1.shared_ptr"
  - "tr1.shared_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "shared_ptr 클래스"
  - "shared_ptr 클래스[TR1]"
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# shared_ptr 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동적으로 할당된 개체 주위에 참조 횟수가 계산되는 스마트 포인터를 래핑합니다.  
  
## 구문  
  
```  
template<class Ty>  
   class shared_ptr {  
public:  
    typedef Ty element_type;  
  
    shared_ptr();  
    shared_ptr(nullptr_t);   
    shared_ptr(const shared_ptr& sp);  
    shared_ptr(shared_ptr&& sp);  
    template<class Other>  
        explicit shared_ptr(Other * ptr);  
    template<class Other, class D>  
        shared_ptr(Other * ptr, D dtor);  
    template<class D>  
        shared_ptr(nullptr_t, D dtor);  
    template<class Other, class D, class A>  
        shared_ptr(Other *ptr, D dtor, A alloc);  
    template<class D, class A>  
        shared_ptr(nullptr_t, D dtor, A alloc);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>&& sp);  
    template<class Other>  
        explicit shared_ptr(const weak_ptr<Other>& wp);  
    template<class Other>  
        shared_ptr(auto_ptr<Other>& ap);  
    template<class Other, class D>  
        shared_ptr(unique_ptr<Other, D>&& up);  
    template<class Other>  
        shared_ptr(const shared_ptr<Other>& sp, Ty *ptr);  
    ~shared_ptr();  
    shared_ptr& operator=(const shared_ptr& sp);  
    template<class Other>   
        shared_ptr& operator=(const shared_ptr<Other>& sp);  
    shared_ptr& operator=(shared_ptr&& sp);  
    template<class Other>   
        shared_ptr& operator=(shared_ptr<Other>&& sp);  
    template<class Other>   
        shared_ptr& operator=(auto_ptr< Other >&& ap);  
    template <class Other, class D>   
        shared_ptr& operator=(const unique_ptr< Other, D>& up) = delete;  
    template <class Other, class D>  
        shared_ptr& operator=(unique_ptr<Other, D>&& up);  
    void swap(shared_ptr& sp);  
    void reset();  
    template<class Other>  
        void reset(Other *ptr);  
    template<class Other, class D>  
        void reset(Other *ptr, D dtor);  
    template<class Other, class D, class A>  
        void reset(Other *ptr, D dtor, A alloc);  
    Ty *get() const;  
    Ty& operator*() const;  
    Ty *operator->() const;  
    long use_count() const;  
    bool unique() const;  
    operator bool() const;  
  
    template<class Other>  
        bool owner_before(shared_ptr<Other> const& ptr) const;  
    template<class Other>  
        bool owner_before(weak_ptr<Other> const& ptr) const;  
    template<class D, class Ty>   
        D* get_deleter(shared_ptr<Ty> const& ptr);  
};  
  
```  
  
#### 매개 변수  
 `Ty`  
 공유 포인터에 의해 제어되는 형식입니다.  
  
 `Other`  
 인수 포인터에 의해 제어되는 형식입니다.  
  
 `ptr`  
 복사할 포인터입니다.  
  
 `D`  
 삭제자의 형식입니다.  
  
 `A`  
 할당자의 형식입니다.  
  
 `dtor`  
 삭제자입니다.  
  
 `alloc`  
 할당자입니다.  
  
 `sp`  
 복사 또는 이동할 스마트 포인터입니다.  
  
 `wp`  
 복사 또는 이동할 약한 포인터입니다.  
  
 `ap`  
 복사 또는 이동할 자동 포인터입니다.  
  
 `up`  
 이동할 고유 포인터입니다.  
  
## 설명  
 템플릿 클래스는 참조 개수 계산을 사용하여 리소스를 관리하는 개체를 설명합니다.  `shared_ptr` 개체는 null 포인터를 소유하거나 보유한 리소스에 대한 포인터를 보유합니다.  둘 이상의 `shared_ptr` 개체가 리소스를 소유할 수 있습니다. 특정 리소스를 소유하는 마지막 `shared_ptr` 개체가 삭제되면 리소스가 해제됩니다.  
  
 다시 할당되거나 다시 설정되면 `shared_ptr`에서 리소스 소유가 중지됩니다.  
  
 특정 멤버 함수에 대해 언급된 경우를 제외하고 템플릿 인수 `Ty`는 불완전한 형식일 수 있습니다.  
  
 `G*` 형식의 리소스 포인터 또는 `shared_ptr<G>`에서 `shared_ptr<Ty>` 개체가 생성된 경우 포인터 형식 `G*`를 `Ty*`로 변환할 수 있어야 합니다.  그렇지 않으면 코드가 컴파일되지 않습니다.  예:  
  
```cpp  
class F {};  
class G : public F {};  
```  
  
```cpp  
  
#include <memory>  
  
using namespace std;  
  
shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*  
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>  
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*  
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>  
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>  
shared_ptr<int> sp5(new G); // error, G* not convertible to int*  
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>  
```  
  
 `shared_ptr` 개체가 리소스를 소유합니다.  
  
-   해당 리소스에 대한 포인터를 사용하여 생성된 경우  
  
-   해당 리소스를 소유하는 `shared_ptr` 개체에서 생성된 경우  
  
-   해당 리소스를 가리키는 [weak\_ptr 클래스](../standard-library/weak-ptr-class.md) 개체에서 생성된 경우 또는  
  
-   해당 리소스의 소유권이 [shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md)를 사용하여 또는 멤버 함수 [shared\_ptr::reset](../Topic/shared_ptr::reset.md)을 호출하여 할당된 경우  
  
 리소스를 소유하는 `shared_ptr` 개체는 제어 블록을 공유합니다.  제어 블록은 다음을 보유합니다.  
  
-   리소스를 소유하는 `shared_ptr` 개체 수  
  
-   리소스를 가리키는 `weak_ptr` 개체 수  
  
-   해당 리소스에 대한 삭제자\(있는 경우\)  
  
-   제어 블록에 대한 사용자 지정 할당자\(있는 경우\)  
  
 null 포인터를 사용하여 초기화된 `shared_ptr` 개체에는 제어 블록이 있고 비어 있지 않습니다.  `shared_ptr` 개체가 리소스를 해제한 후에는 더 이상 해당 리소스를 소유하지 않습니다.  `weak_ptr` 개체가 리소스를 해제한 후에는 더 이상 해당 리소스를 가리키지 않습니다.  
  
 리소스를 소유하는 `shared_ptr` 개체 수가 0이 되면 리소스의 소유권이 원래 생성된 방식에 따라 개체를 삭제하거나 개체 주소를 삭제자에 전달하여 리소스가 해제됩니다.  리소스를 소유하는 `shared_ptr` 개체 수가 0이고 해당 리소스를 가리키는 `weak_ptr` 개체 수가 0이면 제어 블록에 대한 사용자 지정 할당자를 사용하여\(있는 경우\) 제어 블록이 해제됩니다.  
  
 빈 `shared_ptr` 개체는 리소스를 소유하지 않으며 제어 블록이 없습니다.  
  
 삭제자는 멤버 함수 `operator()`가 있는 함수 개체입니다.  복사를 통해 해당 형식을 생성할 수 있어야 하며, 복사 생성자와 소멸자에서 예외가 발생하지 않아야 합니다.  삭제할 개체를 나타내는 매개 변수 하나를 사용합니다.  
  
 일부 함수는 결과 `shared_ptr<Ty>` 또는 `weak_ptr<Ty>` 개체의 속성을 정의하는 인수 목록을 사용합니다.  여러 가지 방법으로 이러한 인수 목록을 지정할 수 있습니다.  
  
 인수 없이 \- 결과 개체는 빈 `shared_ptr` 개체 또는 빈 `weak_ptr` 개체입니다.  
  
 `ptr` \- 관리할 리소스에 대한 `Other*` 형식의 포인터입니다.  `Ty`는 완전한 형식이어야 합니다.  제어 블록을 할당할 수 없어 함수가 실패하면 `delete ptr` 식을 계산합니다.  
  
 `ptr, dtor` \- 관리할 리소스에 대한 `Other*` 형식의 포인터 및 해당 리소스에 대한 삭제자입니다.  제어 블록을 할당할 수 없어 함수가 실패하면 `dtor(ptr)`을 호출하므로 잘 정의해야 합니다.  
  
 `ptr, dtor, alloc` \- 관리할 리소스에 대한 `Other*` 형식의 포인터, 해당 리소스에 대한 삭제자 및 할당하고 해제해야 하는 저장소를 관리할 할당자입니다.  제어 블록을 할당할 수 없어 함수가 실패하면 `dtor(ptr)`을 호출하므로 잘 정의해야 합니다.  
  
 `sp` \- 관리할 리소스를 소유하는 `shared_ptr<Other>` 개체입니다.  
  
 `wp` \- 관리할 리소스를 가리키는 `weak_ptr<Other>` 개체입니다.  
  
 `ap` \- 관리할 리소스에 대한 포인터를 보유하는 `auto_ptr<Other>` 개체입니다.  함수가 성공하면 `ap.release()`를 호출하고, 그렇지 않으면 `ap`를 변경하지 않고 그대로 둡니다.  
  
 모든 경우에서 포인터 형식 `Other*`를 `Ty*`로 변환할 수 있어야 합니다.  
  
## 스레드로부터의 안전성  
 개체가 소유권을 공유하는 복사본이더라도 다중 스레드가 여러 `shared_ptr` 개체를 동시에 읽고 쓸 수 있습니다.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[shared\_ptr::shared\_ptr](../Topic/shared_ptr::shared_ptr.md)|`shared_ptr`를 생성합니다.|  
|[shared\_ptr::~shared\_ptr](../Topic/shared_ptr::~shared_ptr.md)|`shared_ptr`을 삭제합니다.|  
  
### 메서드  
  
|||  
|-|-|  
|[shared\_ptr::element\_type](../Topic/shared_ptr::element_type.md)|요소의 형식입니다.|  
|[shared\_ptr::get](../Topic/shared_ptr::get.md)|소유하는 리소스의 주소를 가져옵니다.|  
|[shared\_ptr::owner\_before](../Topic/shared_ptr::owner_before.md)|`shared_ptr`이 제공된 포인터 앞에 정렬되는\(또는 보다 작은\) 경우 true를 반환합니다.|  
|[shared\_ptr::reset](../Topic/shared_ptr::reset.md)|소유하는 리소스를 대체합니다.|  
|[shared\_ptr::swap](../Topic/shared_ptr::swap.md)|두 `shared_ptr` 개체를 교환합니다.|  
|[shared\_ptr::unique](../Topic/shared_ptr::unique.md)|소유하는 리소스가 고유한지 테스트합니다.|  
|[shared\_ptr::use\_count](../Topic/shared_ptr::use_count.md)|리소스 소유자 수를 계산합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[shared\_ptr::operator boolean\-type](../Topic/shared_ptr::operator%20boolean-type.md)|소유하는 리소스가 있는지 테스트합니다.|  
|[shared\_ptr::operator\*](../Topic/shared_ptr::operator*.md)|지정된 값을 가져옵니다.|  
|[shared\_ptr::operator\=](../Topic/shared_ptr::operator=.md)|소유하는 리소스를 대체합니다.|  
|[shared\_ptr::operator\-\>](../Topic/shared_ptr::operator-%3E.md)|지정된 값으로 포인터를 가져옵니다.|  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [weak\_ptr 클래스](../standard-library/weak-ptr-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)