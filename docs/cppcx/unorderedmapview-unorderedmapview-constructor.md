---
title: "UnorderedMapView::UnorderedMapView 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::UnorderedMapView"
ms.assetid: 408aa6ca-dd8d-4946-a817-42a31d19f429
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMapView::UnorderedMapView 생성자
UnorderedMapView 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
  
UnorderedMapView();  
  
explicit UnorderedMapView(size_t n);  
  
UnorderedMapView(size_t n, const H& h);  
  
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m  
    );  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
  
UnorderedMapView(  
    std::initializer_list<std::pair<const K, V>> il  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
```  
  
#### 매개 변수  
 n  
 공간을 미리 할당할 요소의 수입니다.  
  
 `InIt`  
 UnorderedMapView의 형식 이름입니다.  
  
 `H`  
 키에 해시 값을 사용할 수 있는 함수 개체입니다.`std::hash`에 의해 지원되는 형식의 경우 기본값은 [std::hash\<K\>](http://msdn.microsoft.com/ko-kr/54f67435-af9d-4217-a29d-fa4d2491a104)입니다.  
  
 `P`  
 같은지 확인하기 위해 두 키를 비교할 수 있는 함수 개체를 제공하는 형식입니다. 기본값은 [std::equal\_to\<K\>](../standard-library/equal-to-struct.md)입니다.  
  
 `m`  
 UnorderedMapView를 초기화하는 데 사용되는 [std::unordered\_map](../standard-library/unordered-map-class.md)에 대한 참조 또는 [Lvalue 및 Rvalue](~/cpp/lvalues-and-rvalues-visual-cpp.md)입니다.  
  
 `first`  
 UnorderedMapView를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.  
  
 `last`  
 UnorderedMapView를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)