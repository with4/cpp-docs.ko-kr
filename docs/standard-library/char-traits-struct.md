---
title: "char_traits 구조체 | Microsoft Docs"
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
  - "std::char_traits"
  - "std.char_traits"
  - "iosfwd/std::char_traits"
  - "char_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits 클래스"
  - "char_traits 구조체"
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
caps.latest.revision: 20
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# char_traits 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

char\_traits 구조체는 문자와 연결된 특성을 설명합니다.  
  
## 구문  
  
```  
template <  
   class CharType  
> struct char_traits;  
```  
  
#### 매개 변수  
 `CharType`  
 요소 데이터 형식입니다.  
  
## 설명  
 템플릿 구조체는 **CharType** 형식에 대한 다양한 문자 특성을 설명합니다.  템플릿 클래스 [basic\_string](../standard-library/basic-string-class.md) 및 [basic\_ios](../standard-library/basic-ios-class.md)를 포함하는 여러 iostream 템플릿 클래스는 이 정보를 사용하여 **CharType** 형식의 요소를 조작합니다.  이러한 요소 형식은 명시적 생성 또는 소멸을 요구하지 않아야 합니다.  기본 생성자, 복사 생성자 및 대입 연산자에 예상 의미 체계를 제공해야 합니다.  비트 복사는 할당과 동일한 효과가 있어야 합니다.  char\_traits 구조체의 멤버 함수는 예외를 발생시킬 수 없습니다.  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/char_traits::char_type.md)|문자 형식입니다.|  
|[int\_type](../Topic/char_traits::int_type.md)|`char_type` 형식의 문자 또는 EOF\(파일 끝\) 문자를 나타낼 수 있는 정수 형식입니다.|  
|[off\_type](../Topic/char_traits::off_type.md)|스트림 내의 위치 간 오프셋을 나타낼 수 있는 정수 형식입니다.|  
|[pos\_type](../Topic/char_traits::pos_type.md)|스트림 내의 위치를 나타낼 수 있는 정수 형식입니다.|  
|[state\_type](../Topic/char_traits::state_type.md)|스트림 내의 멀티바이트 문자에 대한 변환 상태를 나타내는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[assign](../Topic/char_traits::assign.md)|한 문자 값을 다른 문자 값에 할당합니다.|  
|[compare](../Topic/char_traits::compare.md)|두 문자열의 문자를 지정한 개수까지 비교합니다.|  
|[copy](../Topic/char_traits::copy.md)|한 문자열에서 다른 문자열로 지정한 개수의 문자를 복사합니다.  더 이상 사용되지 않습니다.  대신 [char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md)를 사용합니다.|  
|[\_Copy\_s](../Topic/char_traits::_Copy_s.md)|한 문자열에서 다른 문자열로 지정한 개수의 문자를 복사합니다.|  
|[eof](../Topic/char_traits::eof.md)|EOF\(파일 끝\) 문자를 반환합니다.|  
|[eq](../Topic/char_traits::eq.md)|두 `char_type` 문자가 같은지 테스트합니다.|  
|[eq\_int\_type](../Topic/char_traits::eq_int_type.md)|`int_type`로 표시된 두 문자가 같은지 테스트합니다.|  
|[find](../Topic/char_traits::find.md)|문자 범위에서 지정한 문자의 첫 번째 발생을 검색합니다.|  
|[length](../Topic/char_traits::length.md)|문자열의 길이를 반환합니다.|  
|[lt](../Topic/char_traits::lt.md)|한 문자가 다른 문자보다 작은지 테스트합니다.|  
|[move](../Topic/char_traits::move.md)|한 시퀀스에서 겹칠 수 있는 다른 시퀀스로 지정한 개수의 문자를 복사합니다.  더 이상 사용되지 않습니다.  대신 [char\_traits::\_Move\_s](../Topic/char_traits::_Move_s.md)를 사용합니다.|  
|[\_Move\_s](../Topic/char_traits::_Move_s.md)|한 시퀀스에서 겹칠 수 있는 다른 시퀀스로 지정한 개수의 문자를 복사합니다.|  
|[not\_eof](../Topic/char_traits::not_eof.md)|문자가 EOF\(파일 끝\) 문자인지 테스트합니다.|  
|[to\_char\_type](../Topic/char_traits::to_char_type.md)|`int_type` 문자를 해당하는 `char_type` 문자로 변환하고 결과를 반환합니다.|  
|[to\_int\_type](../Topic/char_traits::to_int_type.md)|`char_type` 문자를 해당하는 `int_type` 문자로 변환하고 결과를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<string\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)