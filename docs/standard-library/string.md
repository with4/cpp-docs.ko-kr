---
title: "&lt;string&gt; | Microsoft Docs"
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
  - "std::<string>"
  - "string/std::<string>"
  - "std.<string>"
  - "<string>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "string 헤더"
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;string&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컨테이너 클래스 템플릿 `basic_string` 및 다양한 지원 템플릿을 정의합니다.  
  
 `basic_string`에 대한 자세한 내용은 [basic\_string 클래스](../standard-library/basic-string-class.md)를 참조하세요.  
  
## 구문  
  
```  
#include <string>  
```  
  
## 설명  
 C\+\+ 언어와 표준 C\+\+ 라이브러리는 두 가지 문자열 형식을 지원합니다.  
  
-   Null로 종료되는 문자 배열은 보통 C 문자열이라고 합니다.  
  
-   모든 `char` 형식 템플릿 인수를 처리하는 `basic_string` 형식의 템플릿 클래스 개체입니다.  
  
### 형식 정의  
  
|||  
|-|-|  
|[string](../Topic/string%20\(C++%20STL%20%3Cstring%3E\).md)|`char` 형식 요소가 포함된 템플릿 클래스 `basic_string`의 특수화를 `string`으로 설명하는 형식입니다.|  
|[wstring](../Topic/wstring.md)|`wchar_t` 형식 요소가 포함된 템플릿 클래스 `basic_string`의 특수화를 `wstring`으로 설명하는 형식입니다.|  
|[u16string](../Topic/u16string.md)|`char16_t` 형식 요소를 기준으로 템플릿 클래스 `basic_string`의 특수화를 설명하는 형식입니다.|  
|[u32string](../Topic/u32string.md)|`char32_t` 형식 요소를 기준으로 템플릿 클래스 `basic_string`의 특수화를 설명하는 형식입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[operator \+](../Topic/operator+%20\(%3Cstring%3E\).md)|두 문자열 개체를 연결합니다.|  
|[연산자\!\=](../Topic/operator!=%20\(%3Cstring%3E\).md)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체와 같지 않은지 테스트합니다.|  
|[연산자\=\=](../Topic/operator==%20\(%3Cstring%3E\).md)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체와 같은지 테스트합니다.|  
|[operator \<](../Topic/operator%3C%20\(%3Cstring%3E\).md)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 작은지 테스트합니다.|  
|[operator \<\=](../Topic/operator%3C=%20\(in%20%3Cstring%3E\).md)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 작거나 같은지 테스트합니다.|  
|[연산자 \<\<](../Topic/operator%3C%3C%20\(%3Cstring%3E\).md)|문자열을 출력 스트림에 삽입하는 템플릿 함수입니다.|  
|[operator \>](../Topic/operator%3E%20\(%3Cstring%3E\).md)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 큰지 테스트합니다.|  
|[operator \>\=](../Topic/operator%3E=%20\(%3Cstring%3E\).md)|연산자의 좌변에 있는 문자열 개체가 우변에 있는 문자열 개체보다 크거나 같은지 테스트합니다.|  
|[연산자 \>\>](../Topic/operator%3E%3E%20\(%3Cstring%3E\).md)|입력 스트림에서 문자열을 추출하는 템플릿 함수입니다.|  
  
### 특별 템플릿 함수  
  
|||  
|-|-|  
|[스왑](../Topic/swap%20\(C++%20STL%20%3Cstring%3E\).md)|두 문자열의 문자 배열을 교환합니다.|  
|[stod](../Topic/stod.md)|문자 시퀀스를 `double.`로 변환합니다.|  
|[stof](../Topic/stof.md)|문자 시퀀스를 `float`로 변환합니다.|  
|[stoi](../Topic/stoi.md)|문자 시퀀스를 정수로 변환합니다.|  
|[stold](../Topic/stold.md)|문자 시퀀스를 `long double`로 변환합니다.|  
|[stoll](../Topic/stoll.md)|문자 시퀀스를 `long long`으로 변환합니다.|  
|[stoul](../Topic/stoul.md)|문자 시퀀스를 `unsigned long`으로 변환합니다.|  
|[stoull](../Topic/stoull.md)|문자 시퀀스를 `unsigned long long`으로 변환합니다.|  
|[to\_string](../Topic/to_string.md)|값을 `string`로 변환합니다.|  
|[to\_wstring](../Topic/to_wstring.md)|값을 와이드 `string`으로 변환합니다.|  
  
### 함수  
  
|||  
|-|-|  
|[getline](../Topic/getline%20Template%20Function.md)|입력 스트림에서 문자열을 한 줄씩 추출합니다.|  
  
### 클래스  
  
|||  
|-|-|  
|[basic\_string 클래스](../standard-library/basic-string-class.md)|임의의 문자 형식 개체 시퀀스를 저장할 수 있는 개체를 설명하는 템플릿 클래스입니다.|  
|[char\_traits 구조체](../standard-library/char-traits-struct.md)|CharType 형식 문자와 관련된 특성을 설명하는 템플릿 클래스입니다.|  
  
### 특수화  
  
|||  
|-|-|  
|[char\_traits\<char\> 구조체](../standard-library/char-traits-char-struct.md)|`char` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType\>의 특수화인 구조체입니다.|  
|[char\_traits\<wchar\_t\> 구조체](../standard-library/char-traits-wchar-t-struct.md)|`wchar_t` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType\>의 특수화인 구조체입니다.|  
|[char\_traits\<char16\_t\> 구조체](../standard-library/char-traits-char16-t-struct.md)|`char16_t` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType\>의 특수화인 구조체입니다.|  
|[char\_traits\<char32\_t\> 구조체](../standard-library/char-traits-char32-t-struct.md)|`char32_t` 형식 요소에 대한 템플릿 구조체 `char_traits`\<CharType\>의 특수화인 구조체입니다.|  
  
## 요구 사항  
  
-   **헤더:** \<string\>  
  
-   **네임스페이스:** std  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)