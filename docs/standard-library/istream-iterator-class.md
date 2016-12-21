---
title: "istream_iterator 클래스 | Microsoft Docs"
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
  - "iterator/std::istream_iterator"
  - "std.istream_iterator"
  - "std::istream_iterator"
  - "istream_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream_iterator 클래스"
ms.assetid: fb52a8cd-7f71-48d1-b73e-4b064e2a8d16
caps.latest.revision: 18
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# istream_iterator 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

입력 반복기 개체에 대해 설명합니다.  입력 스트림에서 `Type` 클래스의 개체를 추출하여 `pointer` 형식의 개체를 통해 액세스하고 `basic_istream`\<`CharType`, `Traits`\>에 보관합니다.  
  
## 구문  
  
```  
template<class Type,  
    class CharType = char,  
    class Traits = char_traits<CharType>,  
    class Distance = ptrdiff_t,  
> class istream_iterator  
 : public iterator<  
        input_iterator_tag,  
        Type,   
        Distance,   
        const Type *,  
        const Type&  
    >;  
```  
  
#### 매개 변수  
 `Type`  
 입력 스트림에서 추출할 개체의 형식입니다.  
  
 `CharType`  
 `istream_iterator`의 문자 형식을 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 `char`입니다.  
  
 `Traits`  
 `istream_iterator`의 문자 형식을 나타내는 형식입니다.  이 인수는 선택 사항이며 기본값은 `char_traits`\<`CharType`\>입니다.  
  
 `Distance`  
 `istream_iterator`에 대해 차이 형식을 나타내는 부호 있는 정수 계열 형식입니다.  이 인수는 선택 사항이며 기본값은 `ptrdiff_t`입니다.  
  
 null이 아닌 저장된 포인터를 사용하여 istream\_iterator 클래스를 구성 또는 증가한 이후 개체는 연결된 입력 스트림에서 `Type` 형식의 개체에 대해 효과적인 추출 및 저장을 시도합니다.  추출이 실패할 경우 개체는 저장된 포인터를 null 포인터로 대체하여 시퀀스 끝 표시기를 만듭니다.  
  
### 생성자  
  
|||  
|-|-|  
|[istream\_iterator](../Topic/istream_iterator::istream_iterator.md)|기본 `istream_iterator`로 스트림의 끝 반복기를 구성하거나 반복기의 스트림 형식에 초기화된 `istream_iterator`로 구성합니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/istream_iterator::char_type.md)|`istream_iterator`의 문자 형식을 허용하는 형식입니다.|  
|[istream\_type](../Topic/istream_iterator::istream_type.md)|`istream_iterator`의 스트림 형식을 허용하는 형식입니다.|  
|[traits\_type](../Topic/istream_iterator::traits_type.md)|`istream_iterator`의 특성 형식을 허용하는 형식입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator\*](../Topic/istream_iterator::operator*.md)|역참조 연산자는 `istream_iterator`에서 주소 지정하는 형식 `Type`의 저장된 개체를 반환합니다.|  
|[연산자\-\>](../Topic/istream_iterator::operator-%3E.md)|멤버의 값을 반환합니다\(있는 경우\).|  
|[operator\+\+](../Topic/istream_iterator::operator++.md)|입력 스트림에서 증가된 개체를 추출하거나 개체를 증가하기 전에 복사하여 복사본을 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<iterator\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [input\_iterator\_tag 구조체](../standard-library/input-iterator-tag-struct.md)   
 [iterator 구조체](../standard-library/iterator-struct.md)   
 [\<iterator\>](../standard-library/iterator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)