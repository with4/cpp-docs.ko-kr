---
title: "auto_ptr 클래스 | Microsoft Docs"
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
  - "std::auto_ptr"
  - "std.auto_ptr"
  - "auto_ptr"
  - "memory/std::auto_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_ptr 클래스"
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# auto_ptr 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어가 블록을 나갈 때 리소스가 자동으로 삭제되도록 리소스를 스마트 포인터로 래핑합니다.  
  
 더욱 강력한 `unique_ptr` 클래스가 `auto_ptr`을 대체합니다.  자세한 내용은 [unique\_ptr 클래스](../standard-library/unique-ptr-class.md)를 참조하세요.  
  
 `throw()` 및 예외 처리에 대한 자세한 내용은 [예외 사양\(throw\)](../cpp/exception-specifications-throw-cpp.md)을 참조하세요.  
  
## 구문  
  
```  
template<class Type>  
    class auto_ptr {  
public:  
    typedef Type element_type;  
    explicit auto_ptr(Type *_Ptr = 0) throw();  
    auto_ptr(auto_ptr<Type>& _Right) throw();  
    template<class Other>  
        operator auto_ptr<Other>() throw();  
    template<class Other>  
        auto_ptr<Type>& operator=(auto_ptr<Other>& _Right) throw();  
    template<class Other>  
        auto_ptr(auto_ptr<Other>& _Right);  
    auto_ptr<Type>& operator=(auto_ptr<Type>& _Right);  
    ~auto_ptr();  
    Type& operator*() const throw();  
    Type *operator->()const throw();  
    Type *get() const throw();  
    Type *release()throw();  
    void reset(Type *_Ptr = 0);  
};  
```  
  
#### 매개 변수  
 `_Right`  
 기존 리소스를 가져올 `auto_ptr`입니다.  
  
 `_Ptr`  
 저장된 포인터를 바꾸도록 지정된 포인터입니다.  
  
## 설명  
 이 템플릿 클래스는 할당된 개체에 대한 `auto_ptr,`이라는 스마트 포인터를 설명합니다.  포인터는 null이거나 `new`로 할당된 개체를 지정해야 합니다.  저장된 값이 다른 개체에 할당되면 `auto_ptr`이 소유권을 전송합니다.  null 포인터를 사용한 전송 후 저장된 값을 대체합니다. `auto_ptr<Type>`에 대한 소멸자는 할당된 개체를 삭제합니다.  `auto_ptr<Type>`은 예외가 발생하는 경우에도 제어가 블록을 나갈 때 할당된 개체가 자동으로 삭제되도록 합니다.  동일한 개체를 소유하는 두 개의 `auto_ptr<Type>` 개체를 생성하면 안 됩니다.  
  
 함수 호출에 대한 인수로 `auto_ptr<Type>` 개체 값을 전달할 수 있습니다.  `auto_ptr`은 표준 라이브러리 컨테이너의 요소일 수 없습니다.  표준 템플릿 라이브러리 컨테이너를 사용하여 `auto_ptr<Type>` 개체의 시퀀스를 안정적으로 관리할 수는 없습니다.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[auto\_ptr](../Topic/auto_ptr::auto_ptr.md)|`auto_ptr` 형식의 개체에 대한 생성자입니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/auto_ptr::element_type.md)|이 형식은 템플릿 매개 변수 `Type`의 동의어입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[Get](../Topic/auto_ptr::get.md)|이 멤버 함수는 저장된 포인터 `myptr`을 반환합니다.|  
|[릴리스](../Topic/auto_ptr::release.md)|이 멤버는 저장된 포인터 `myptr`을 null 포인터로 대체하고 이전에 저장된 포인터를 반환합니다.|  
|[다시 설정](../Topic/auto_ptr::reset.md)|이 멤버 함수는 저장된 포인터 값 `myptr`이 함수 호출의 결과로 변경되는 경우에만 `delete myptr` 식을 계산합니다.  그런 다음 저장된 포인터를 `ptr`로 바꿉니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/auto_ptr::operator=.md)|한 `auto_ptr` 개체에서 다른 개체로 소유권을 전송하는 대입 연산자입니다.|  
|[operator\*](../Topic/auto_ptr::operator*.md)|`auto_ptr` 형식의 개체에 대한 역참조 연산자입니다.|  
|[연산자\-\>](../Topic/auto_ptr::operator-%3E.md)|멤버 액세스를 허용하기 위한 연산자입니다.|  
|[operator auto\_ptr\<Other\>](../Topic/auto_ptr::operator%20auto_ptr%3COther%3E.md)|한 종류의 `auto_ptr`에서 다른 종류의 `auto_ptr`로 캐스팅합니다.|  
|[operator auto\_ptr\_ref\<Other\>](../Topic/auto_ptr::operator%20auto_ptr_ref%3COther%3E.md)|`auto_ptr`에서 `auto_ptr_ref`로 캐스팅합니다.|  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique\_ptr 클래스](../standard-library/unique-ptr-class.md)