---
title: "insert_iterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::insert_iterator"
  - "iterator/std::insert_iterator"
  - "std.insert_iterator"
  - "insert_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "insert_iterator 클래스"
  - "insert_iterator 클래스, 구문"
ms.assetid: d5d86405-872e-4e3b-9e68-c69a2b7e8221
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# insert_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

출력 반복기의 요구 사항을 충족하는 반복기 어댑터에 대해 설명합니다.  반복기 어댑터는 요소를 덮어쓰는 것이 아니라, 시퀀스에 요소를 삽입하므로 C\+\+ 시퀀스 및 연관 컨테이너의 반복기가 제공한 덮어쓰기 의미 체계와 다른 의미 체계를 제공합니다.  `insert_iterator` 클래스는 조정하는 컨테이너 형식에 대해 템플릿화됩니다.  
  
## 구문  
  
```  
template <class Container> class insert_iterator;  
```  
  
#### 매개 변수  
 `Container`  
 `insert_iterator`가 요소를 삽입할 컨테이너의 형식입니다.  
  
## 설명  
 형식이 **Container**인 컨테이너는 다양한 크기의 컨테이너 요구 사항을 충족해야 하며 매개 변수의 형식이 **Container::iterator**, **Container::value\_type**이거나 **Container::iterator** 형식을 반환할 경우 두 개의 인수 삽입 멤버 함수가 있어야 합니다.  표준 템플릿 라이브러리 시퀀스 및 정렬된 연관 컨테이너는 이러한 요구 사항을 준수하며 `insert_iterator`를 사용할 수 있도록 조정되었습니다.  연관 컨테이너의 경우 위치 인수는 힌트로 처리되며, 힌트가 얼마나 양호한가에 따라 성능이 향상되거나 저하될 수 있습니다.  `insert_iterator`는 항상 컨테이너를 사용하여 초기화해야 합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[insert\_iterator](../Topic/insert_iterator::insert_iterator.md)|컨테이너의 지정된 위치에 요소를 삽입하는 `insert_iterator`를 만듭니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[container\_type](../Topic/insert_iterator::container_type.md)|일반 삽입 대상인 컨테이너를 나타내는 형식입니다.|  
|[참조](../Topic/insert_iterator::reference.md)|연관 컨테이너에서 제어하는 시퀀스의 요소에 대한 참조를 제공하는 형식입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\*](../Topic/insert_iterator::operator*.md)|일반 삽입을 위해 출력 반복기 식을 구현하는 데 사용된 역참조 연산자 \*`i` \= `x`|  
|[operator\+\+](../Topic/insert_iterator::operator++.md)|값을 저장할 다음 위치에 `insert_iterator`를 증가시킵니다.|  
|[operator\=](../Topic/insert_iterator::operator=.md)|일반 삽입을 위해 출력 반복기 식을 구현하는 데 사용된 할당 연산자 \*`i` \= `x`|  
  
## 요구 사항  
 **헤더**: \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)