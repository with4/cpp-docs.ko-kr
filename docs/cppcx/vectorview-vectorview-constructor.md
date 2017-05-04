---
title: "VectorView::VectorView 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::VectorView 생성자"
ms.assetid: 5ec14dbc-5f6f-44b6-8fc4-f5a31053eb5f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::VectorView 생성자
VectorView 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
#### 매개 변수  
 `InIt`  
 현재 VectorView를 초기화하는 데 사용되는 개체 컬렉션의 형식입니다.  
  
 il  
 VectorView를 초기화하는 데 사용될 요소가 있는 [std::initializer\_list](../standard-library/initializer-list-class.md)입니다.  
  
 `N`  
 현재 VectorView를 초기화하는 데 사용되는 개체 컬렉션의 요소 수입니다.  
  
 `size`  
 VectorView의 요소 수입니다.  
  
 `value`  
 현재 VectorView의 각 요소를 초기화하는 데 사용되는 값입니다.  
  
 `v`  
 현재 VectorView를 초기화하는 데 사용되는 [::std::vector](../Topic/vector%20Class%201.md)에 대한 [Lvalue 및 Rvalue](~/cpp/lvalues-and-rvalues-visual-cpp.md)입니다.  
  
 `ptr`  
 현재 VectorView를 초기화하는 데 사용되는 `std::vector`에 대한 포인터입니다.  
  
 `arr`  
 현재 VectorView를 초기화하는 데 사용되는 [Platform::Array](../cppcx/platform-array-class.md) 개체입니다.  
  
 `a`  
 현재 VectorView를 초기화하는 데 사용되는 [std::array](../Topic/vector%20Class%201.md) 개체입니다.  
  
 `first`  
 현재 VectorView를 초기화하는 데 사용되는 개체 시퀀스의 첫 번째 요소입니다.`first` 형식은 *완벽한 전달*을 통해 전달됩니다. 자세한 내용은 [Rvalue 참조 선언자: &&](~/cpp/rvalue-reference-declarator-amp-amp.md)을 참조하세요.  
  
 `last`  
 현재 VectorView를 초기화하는 데 사용되는 개체 시퀀스의 마지막 요소입니다.`last` 형식은 *완벽한 전달*을 통해 전달됩니다. 자세한 내용은 [Rvalue 참조 선언자: &&](~/cpp/rvalue-reference-declarator-amp-amp.md)을 참조하세요.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::Vector 클래스](../cppcx/platform-collections-vector-class.md)