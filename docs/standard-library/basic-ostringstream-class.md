---
title: "basic_ostringstream 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "basic_ostringstream"
  - "std.basic_ostringstream"
  - "sstream/std::basic_ostringstream"
  - "std::basic_ostringstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_ostringstream 클래스"
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# basic_ostringstream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<**Elem**, **Tr**, `Alloc`\> 클래스의 스트림 버퍼에 요소 및 인코드된 개체 삽입을 제어하는 개체를 설명합니다.  
  
## 구문  
  
```  
  
        template <  
   class Elem,   
   class Tr = char_traits<Elem>,   
   class Alloc = allocator<Elem>   
>  
   class basic_ostringstream : public basic_ostream<Elem, Tr>  
```  
  
#### 매개 변수  
 `Alloc`  
 할당자 클래스입니다.  
  
 `Elem`  
 문자열 기본 요소의 형식입니다.  
  
 *Tr*  
 문자열의 기본 요소에서 특수화된 문자 특성입니다.  
  
## 설명  
 이 클래스는 문자 특성이 **Tr** 클래스에 의해 결정되고 해당 요소가 `Alloc` 클래스의 할당자에 의해 할당되는 **Elem** 형식의 요소를 사용하여 스트림 버퍼에 요소 및 인코드된 개체의 삽입을 제어하는 개체를 설명합니다.  이 개체는 basic\_stringbuf\<**Elem**, **Tr**, `Alloc`\> 클래스의 개체를 저장합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_ostringstream](../Topic/basic_ostringstream::basic_ostringstream.md)|`basic_ostringstream` 형식의 개체를 생성합니다.|  
  
### Typedefs  
  
|||  
|-|-|  
|[allocator\_type](../Topic/basic_ostringstream::allocator_type.md)|이 형식은 템플릿 매개 변수 `Alloc`의 동의어입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[rdbuf](../Topic/basic_ostringstream::rdbuf.md)|`pointer` 형식의 저장된 스트림 버퍼 주소를 [basic\_stringbuf](../standard-library/basic-stringbuf-class.md)\<`Elem`, `Tr`, `Alloc`\>에 반환합니다.|  
|[str](../Topic/basic_ostringstream::str.md)|쓰기 위치를 변경하지 않고 문자열 버퍼에서 텍스트를 설정하거나 가져옵니다.|  
  
## 요구 사항  
 **헤더:** \<sstream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)