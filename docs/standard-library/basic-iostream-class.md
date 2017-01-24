---
title: "basic_iostream 클래스 | Microsoft Docs"
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
  - "istream/std::basic_iostream"
  - "std.basic_iostream"
  - "basic_iostream"
  - "std::basic_iostream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "basic_iostream 클래스"
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
caps.latest.revision: 22
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# basic_iostream 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

입력과 출력을 둘 다 수행할 수 있는 스트림 클래스입니다.  
  
## 구문  
  
```  
template <class Elem, class Tr = char_traits<Elem> >  
    class basic_iostream : public basic_istream<Elem, Tr>,  
        public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr> *_Strbuf);  
    virtual ~basic_iostream();  
};  
```  
  
## 설명  
 이 템플릿 클래스는 기본 클래스 [basic\_ostream](../standard-library/basic-ostream-class.md)\<`Elem`, `Tr`\>을 통해 삽입을 제어하고 기본 클래스 [basic\_istream](../standard-library/basic-istream-class.md)\<`Elem`, `Tr`\>을 통해 추출을 제어하는 개체를 설명합니다.  두 개체는 공통 가상 기본 클래스 [basic\_ios](../standard-library/basic-ios-class.md)\<`Elem`, `Tr`\>을 공유합니다.  또한 문자 특성이 `Tr` 클래스에 의해 결정되는 `Elem` 형식의 요소가 포함된 공통 스트림 버퍼를 관리합니다.  이 생성자는 `basic_istream`\(**strbuf**\) 및 `basic_ostream`\(**strbuf**\)을 통해 해당 기본 클래스를 초기화합니다.  
  
### 생성자  
  
|||  
|-|-|  
|[basic\_iostream](../Topic/basic_iostream::basic_iostream.md)|`basic_iostream` 개체를 만듭니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[스왑](../Topic/basic_iostream::swap.md)|제공된 `basic_iostream` 개체의 내용을 이 개체의 내용으로 교환합니다.|  
  
### 운영자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/basic_iostream::operator=.md)|지정된 `basic_iostream` 개체의 값을 이 개체에 할당합니다.  복사본을 남기지 않는 `rvalue`와 관련된 이동 할당입니다.|  
  
## 요구 사항  
 **헤더:** \<istream\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream 프로그래밍](../standard-library/iostream-programming.md)   
 [iostreams 규칙](../standard-library/iostreams-conventions.md)