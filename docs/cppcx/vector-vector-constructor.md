---
title: "Vector::Vector 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::Vector 생성자"
ms.assetid: 5454433d-e206-45ea-bc8b-bb5a7bf38c17
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::Vector 생성자
Vector 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
Vector();  
  
explicit Vector(  
    unsigned int size  
    );  
  
Vector(  
    unsigned int size,  
    T value  
    );  
  
template <typename U> explicit Vector(  
    const ::std::vector<U>& v  
    );  
  
template <typename U> explicit Vector(  
    std::vector<U>&& v  
    );  
  
Vector(  
    const T * ptr,  
    unsigned int size  
    );  
  
template <size_t N> explicit Vector(  
    const T(&arr)[N]  
    );  
  
template <size_t N> explicit Vector(  
    const std::array<T, N>& a  
    );  
  
explicit Vector(  
    const Array<T>^ arr  
    );  
  
template <typename InIt> Vector(  
    InIt first,  
    InIt last  
    );  
  
Vector(  
    std::initializer_list<T> il  
    );  
```  
  
#### 매개 변수  
 a  
 Vector를 초기화하는 데 사용될 [std::array](../standard-library/array-class-stl.md)입니다.  
  
 a  
 Vector를 초기화하는 데 사용될 [Platform::Array](../cppcx/platform-array-class.md)입니다.  
  
 `InIt`  
 현재 Vector를 초기화하는 데 사용되는 개체 컬렉션의 형식입니다.  
  
 il  
 Vector를 초기화하는 데 사용될 `T` 형식 개체의 [std::initializer\_list](../standard-library/initializer-list-class.md)입니다.  
  
 `N`  
 현재 Vector를 초기화하는 데 사용되는 개체 컬렉션의 요소 수입니다.  
  
 `size`  
 Vector의 요소 수입니다.  
  
 `value`  
 현재 Vector의 각 요소를 초기화하는 데 사용되는 값입니다.  
  
 `v`  
 현재 Vector를 초기화하는 데 사용되는 [std::vector](../Topic/vector%20Class%201.md)에 대한 [Lvalue 및 Rvalue](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)입니다.  
  
 `ptr`  
 현재 Vector를 초기화하는 데 사용되는 `std::vector`에 대한 포인터입니다.  
  
 `arr`  
 현재 Vector를 초기화하는 데 사용되는 [Platform::Array](../cppcx/platform-array-class.md) 개체입니다.  
  
 `a`  
 현재 Vector를 초기화하는 데 사용되는 [std::array](../Topic/vector%20Class%201.md) 개체입니다.  
  
 `first`  
 현재 Vector를 초기화하는 데 사용되는 개체 시퀀스의 첫 번째 요소입니다.`first` 형식은 *완벽한 전달*을 통해 전달됩니다. 자세한 내용은 [Rvalue 참조 선언자: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md)을 참조하세요.  
  
 `last`  
 현재 Vector를 초기화하는 데 사용되는 개체 시퀀스의 마지막 요소입니다.`last` 형식은 *완벽한 전달*을 통해 전달됩니다. 자세한 내용은 [Rvalue 참조 선언자: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md)을 참조하세요.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)   
 [컬렉션\(C\+\+\/CX\)](../cppcx/collections-c-cx.md)