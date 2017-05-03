---
title: "UnorderedMap::UnorderedMap 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::UnorderedMap"
ms.assetid: bd62e663-7f3a-43ef-ad6d-8266128c778b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::UnorderedMap 생성자
UnorderedMap 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```scr  
UnorderedMap();  
  
  explicit UnorderedMap(  
      size_t n  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  explicit UnorderedMap(  
      const std::unordered_map<K, V, H, P>& m  
      );  
  
  explicit UnorderedMap(  
      std::unordered_map<K, V, H, P>&& m  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  UnorderedMap(std::initializer_list<  
      std::pair<const K, V>> il  
      );  
  
  UnorderedMap(::std::initializer_list<  
      std::pair<const K, V>> il,  
      size_t n  
      );  
  
  UnorderedMap(  
      ::std::initializer_list< ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(::std::initializer_list<  
      ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
```  
  
#### 매개 변수  
 `InIt`  
 현재 UnorderedMap의 형식 이름입니다.  
  
 `P`  
 같은지 여부를 확인하기 위해 두 키를 비교할 수 있는 함수 개체입니다. 이 매개 변수의 기본값은 [std::equal\_to\<K\>](../standard-library/equal-to-struct.md)입니다.  
  
 `H`  
 키에 대한 해시 값을 생성하는 함수 개체입니다. 해당 클래스에 의해 지원되는 키 형식의 경우 이 매개 변수의 기본값은 [hash 클래스](../Topic/hash%20Class%201.md)입니다.  
  
 `m`  
 현재 UnorderedMap을 초기화하는 데 사용되는 [std::unordered\_map](../standard-library/unordered-map-class.md)에 대한 참조 또는 [Lvalue 및 Rvalue](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)입니다.  
  
 il  
 맵을 초기화하는 데 사용될 [std::pair](../standard-library/initializer-list-class.md) 개체의 [std::initializer\_list](../standard-library/pair-structure.md)입니다.  
  
 `first`  
 현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.  
  
 `last`  
 현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections 네임스페이스](../cppcx/platform-collections-namespace.md)   
 [컬렉션](../cppcx/collections-c-cx.md)