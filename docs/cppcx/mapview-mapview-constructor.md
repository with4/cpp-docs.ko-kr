---
title: "MapView::MapView 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::MapView 생성자"
ms.assetid: 67a3250c-b527-47ac-a103-0fd186046d71
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::MapView 생성자
MapView 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```  
explicit MapView(  
    const C& comp = C()  
    );  
  
explicit MapView(  
    const ::std::map<K, V, C>& m  
    );  
  
explicit MapView(  
    std::map<K, V, C>&& m  
    );  
  
template <typename InIt> MapView(  
    InIt first,  
    InIt last,  
    const C& comp = C()  
    );  
  
MapView(::std::initializer_list<  
    std::pair<const K, V>> il,  
    const C& comp = C()  
    );  
```  
  
#### 매개 변수  
 `InIt`  
 현재 MapView의 형식 이름입니다.  
  
 `comp`  
 두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체입니다.  
  
 `m`  
 현재 MapView를 초기화하는 데 사용되는 [Lvalue 및 Rvalue](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md)에 대한 참조 또는 [map 클래스](../standard-library/map-class.md)입니다.  
  
 `first`  
 현재 MapView를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.  
  
 `last`  
 현재 MapView를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.  
  
 il  
 MapView에 삽입될 요소가 있는 [std::initializer\_list\<std::pair\<K,V\>\>](../standard-library/initializer-list-class.md)입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::MapView 클래스](../cppcx/platform-collections-mapview-class.md)