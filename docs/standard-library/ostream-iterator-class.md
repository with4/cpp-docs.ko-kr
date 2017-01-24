---
title: "ostream_iterator 클래스 | Microsoft Docs"
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
  - "ostream_iterator"
  - "std.ostream_iterator"
  - "std::ostream_iterator"
  - "iterator/std::ostream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream_iterator 클래스"
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
caps.latest.revision: 17
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ostream_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스 ostream\_iterator는 연속 요소를 추출 **연산자 \<\<**가 포함된 출력 스트림에 쓰는 출력 반복기 개체에 대해 설명합니다.  
  
## 구문  
  
```  
  
      template <  
   class Type   
   class CharType = char  
   class Traits = char_traits<CharType>  
>  
class ostream_iterator  
```  
  
#### 매개 변수  
 *형식*  
 출력 스트림에 삽입될 개체의 형식입니다.  
  
 `CharType`  
 `ostream_iterator`의 문자 형식을 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 `char`*입니다.*  
  
 `Traits`  
 `ostream_iterator`의 문자 형식을 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 `char_traits`\<*CharType\>입니다.*  
  
 ostream\_iterator 클래스는 출력 반복기에 대한 요구 사항을 충족해야 합니다.  알고리즘은 `ostream_iterator`를 사용하여 출력 스트림에 직접 쓸 수 있습니다.  
  
### 생성자  
  
|||  
|-|-|  
|[ostream\_iterator](../Topic/ostream_iterator::ostream_iterator.md)|출력 스트림으로 쓰도록 초기화 및 구분된 `ostream_iterator`를 구성합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/ostream_iterator::char_type.md)|`ostream_iterator`의 문자 형식을 허용하는 형식입니다.|  
|[ostream\_type](../Topic/ostream_iterator::ostream_type.md)|`ostream_iterator`의 스트림 형식을 허용하는 형식입니다.|  
|[traits\_type](../Topic/ostream_iterator::traits_type.md)|`ostream_iterator`의 특성 형식을 허용하는 형식입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\*](../Topic/ostream_iterator::operator*.md)|출력 반복기 식 \*`i` \= `x`을 구현하는 데 사용된 역참조 연산자.|  
|[operator\+\+](../Topic/ostream_iterator::operator++.md)|연산이 호출되기 전에 주소 지정한 동일한 개체에 `ostream_iterator`를 반환한 비함수 증분 연산자.|  
|[operator\=](../Topic/ostream_iterator::operator=.md)|출력 스트림을 작성하기 위해 출력 반복기 식 \*`i` \= `x`을 구현하는 데 사용된 할당 연산자.|  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)