---
title: "istreambuf_iterator 클래스 | Microsoft Docs"
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
  - "istreambuf_iterator"
  - "std.istreambuf_iterator"
  - "std::istreambuf_iterator"
  - "streambuf/std::istreambuf_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istreambuf_iterator 클래스"
ms.assetid: 39002da2-61a6-48a5-9d0c-5df8271f6038
caps.latest.revision: 19
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# istreambuf_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스 istreambuf\_iterator는 저장하는 개체를 통해 액세스하는 입력 스트림 버퍼에서 문자 요소를 추출하고 `basic_streambuf`\<**CharType**, **Traits**\>에 대한 형식 포인터인 입력 반복기 개체에 대해 설명합니다.  
  
## 구문  
  
```  
  
      template <   
   class CharType  
   class Traits = char_traits<CharType>  
>  
class istreambuf_iterator  
: public iterator<input_iterator_tag, CharType, typename Traits::off_type, CharType *, CharType&>  
```  
  
#### 매개 변수  
 `CharType`  
 istreambuf\_iterator의 문자 형식을 나타내는 형식입니다.  
  
 `Traits`  
 istreambuf\_iterator의 문자 형식을 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 `char_traits`\<*CharType\>입니다.*  
  
## 설명  
 istreambuf\_iterator 클래스는 입력 반복기에 대한 요구 사항을 충족해야 합니다.  
  
 null이 아닌 저장된 포인터를 사용하여 istreambuf\_iterator 클래스를 구성 또는 증가한 이후 개체는 연결된 입력 스트림에서 **CharType** 형식의 개체에 대해 효과적인 추출 및 저장을 시도합니다.  하지만 개체를 실제로 역참조 또는 복사할 때까지 추출이 지연될 수 있습니다.  추출이 실패할 경우 개체는 저장된 포인터를 null 포인터로 대체하여 시퀀스 끝 표시기를 만듭니다.  
  
### 생성자  
  
|||  
|-|-|  
|[istreambuf\_iterator](../Topic/istreambuf_iterator::istreambuf_iterator.md)|입력 스트림에서 문자를 읽을 수 있도록 초기화된 `istreambuf_iterator`를 만듭니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/istreambuf_iterator::char_type.md)|`ostreambuf_iterator`의 문자 형식을 허용하는 형식입니다.|  
|[int\_type](../Topic/istreambuf_iterator::int_type.md)|`istreambuf_iterator`의 정수 형식을 허용하는 형식입니다.|  
|[istream\_type](../Topic/istreambuf_iterator::istream_type.md)|`istream_iterator`의 스트림 형식을 허용하는 형식입니다.|  
|[streambuf\_type](../Topic/istreambuf_iterator::streambuf_type.md)|`istreambuf_iterator`의 스트림 형식을 허용하는 형식입니다.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|`istream_iterator`의 특성 형식을 허용하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[equal](../Topic/istreambuf_iterator::equal.md)|두 입력 스트림 버퍼 반복기가 같은지 테스트합니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\*](../Topic/istreambuf_iterator::operator*.md)|역참조 연산자가 스트림의 다음 문자를 반환합니다.|  
|[operator\+\+](../Topic/istreambuf_iterator::operator++.md)|입력 스트림의 다음 문자를 반환하거나 개체를 증가하기 전에 복사하여 복사본을 반환합니다.|  
|[연산자\-\>](../Topic/istreambuf_iterator::operator-%3E.md)|멤버의 값을 반환합니다\(있는 경우\).|  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [iterator 구조체](../standard-library/iterator-struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)