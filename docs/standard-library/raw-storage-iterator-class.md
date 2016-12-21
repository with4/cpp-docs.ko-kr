---
title: "raw_storage_iterator 클래스 | Microsoft Docs"
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
  - "std::raw_storage_iterator"
  - "raw_storage_iterator"
  - "std.raw_storage_iterator"
  - "memory/std::raw_storage_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_storage_iterator 클래스"
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
caps.latest.revision: 17
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# raw_storage_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

초기화되지 않은 메모리에 결과를 저장하는 알고리즘을 사용할 수 있도록 제공되는 어댑터 클래스입니다.  
  
## 구문  
  
```  
  
        template <class   
        OutputIterator,  
         class   
        Type>  
class raw_storage_iterator  
```  
  
#### 매개 변수  
 `OutputIterator`  
 저장되는 개체에 대한 출력 반복기를 지정합니다.  
  
 *Type*  
 저장소를 할당할 개체 형식입니다.  
  
## 설명  
 이 클래스는 생성하는 시퀀스에서 **Type** 형식의 개체를 생성하는 출력 반복기를 설명합니다.  `raw_storage_iterator`\<**ForwardIterator**, **Type**\> 클래스의 개체는 개체를 생성할 때 지정하는 **ForwardIterator** 클래스의 정방향 반복기 개체를 통해 저장소에 액세스합니다.  **ForwardIterator** 클래스의 first 개체에 대해 **&\*first** 식은 생성된 시퀀스에서 다음 개체\(**Type** 형식\)에 대해 생성되지 않은 저장소를 지정해야 합니다.  
  
 이 어댑터 클래스는 메모리 할당 및 개체 생성을 구분하는 데 필요한 경우에 사용됩니다.  `raw_storage_iterator`를 사용하여 `malloc` 함수를 통해 할당된 메모리와 같은 초기화되지 않은 저장소에 개체를 복사할 수 있습니다.  
  
## 멤버  
  
### 생성자  
  
|||  
|-|-|  
|[raw\_storage\_iterator](../Topic/raw_storage_iterator::raw_storage_iterator.md)|지정된 기본 출력 반복기를 사용하여 원시 저장소 반복기를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[element\_type](../Topic/raw_storage_iterator::element_type.md)|원시 저장소 반복기를 저장할 요소를 설명하는 형식을 제공합니다.|  
|[iter\_type](../Topic/raw_storage_iterator::iter_type.md)|원시 저장소 반복기의 기반이 되는 반복기를 설명하는 형식을 제공합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\*](../Topic/raw_storage_iterator::operator*.md)|출력 반복기 식 \*`ii` \= `x`를 구현하는 데 사용되는 역참조 연산자입니다.|  
|[연산자 \=](../Topic/raw_storage_iterator::operator=.md)|메모리에 저장하기 위해 원시 저장소 반복기 식 \*`i` \= `x`를 구현하는 데 사용되는 대입 연산자입니다.|  
|[operator\+\+](../Topic/raw_storage_iterator::operator++.md)|원시 저장소 반복기에 대한 사전 증가 및 사후 증가 연산자입니다.|  
  
## 요구 사항  
 **헤더:** \<memory\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)