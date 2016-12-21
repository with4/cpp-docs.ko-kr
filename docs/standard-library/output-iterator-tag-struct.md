---
title: "output_iterator_tag 구조체 | Microsoft Docs"
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
  - "std::output_iterator_tag"
  - "output_iterator_tag"
  - "xutility/std::output_iterator_tag"
  - "std.output_iterator_tag"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "output_iterator_tag 클래스"
  - "output_iterator_tag 구조체"
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# output_iterator_tag 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

출력 반복기를 나타내는 **iterator category** 함수에 반환 형식을 제공하는 클래스입니다.  
  
## 구문  
  
```  
  
struct output_iterator_tag {};  
  
```  
  
## 설명  
 범주 태그 클래스 알고리즘 선택에 대 한 태그를 컴파일할 때 사용 됩니다. 템플릿 함수는 가장 효율적인 알고리즘 컴파일 타임에 사용할 수 있도록 반복기 인수의 가장 구체적인 분류를 찾을 해야 합니다. 형식의 모든 반복기에 대 한 `Iterator`, `iterator_traits`\<`Iterator`\>**:: iterator\_category** 반복기의 동작을 설명 하는 가장 구체적인 범주 태그를 정의 해야 합니다.  
  
 형식이 같은 **반복기**\<**Iter**\>**:: iterator\_category** 때 **Iter** 출력 반복기로 사용할 수 있는 개체에 설명 합니다.  
  
 이 태그에 매개 변수화 되지는 `value_type` 또는 `difference_type` 반복기에 대 한 다른 반복기 태그와 마찬가지로 필요가 없기 때문에 출력 반복기 중 하나는 `value_type` 또는 `difference_type`합니다.  
  
## 예제  
 참조 [iterator\_traits](../standard-library/iterator-traits-struct.md) 또는 [random\_access\_iterator\_tag](../standard-library/random-access-iterator-tag-struct.md) 사용 하는 방법의 예 **iterator\_tag**s.  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)