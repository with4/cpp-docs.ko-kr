---
title: "ctype 클래스 | Microsoft Docs"
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
  - "ctype"
  - "std::ctype"
  - "std.ctype"
  - "CType"
  - "xlocale/std::ctype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype 클래스"
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
caps.latest.revision: 19
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctype 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

문자를 분류하고, 대문자에서 소문자로 변환하고, 네이티브 문자 집합과 로캘에서 사용하는 문자 집합 사이에서 변환하는 데 사용하는 패싯을 제공하는 클래스입니다.  
  
## 구문  
  
```  
template <class CharType>  
   class ctype : public ctype_base;  
```  
  
#### 매개 변수  
 `CharType`  
 문자를 인코딩하기 위해 프로그램 내 사용하는 형식  
  
## 설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다.  처음에 저장된 값에 액세스를 시도하면**id**에 고유한 양수 값이 저장됩니다. 분류 기준에는 기본 클래스 ctype\_base에 중첩된 비트 마스크 형식이 있습니다.  
  
 표준 C\+\+ 라이브러리는 이 템플릿 클래스의 두 가지 명시적 특수화를 정의합니다.  
  
-   [ctype](#vclrf_locale_ctype_class)\<`char`\>, 차이를 별도로 설명하는 명시적 특수화  
  
-   **ctype**\<`wchar_t`\>, 요소를 와이드 문자로 처리합니다.  
  
 템플릿 클래스의 기타 특수화 **ctype**\<**CharType**\>:  
  
-   **CharType** 형식의 ***ch*** 값을 \(`char`\)**ch** 식 `char` 형식의 값으로 변환합니다.  
  
-   `char` 형식의 ***바이트*** 값을 **CharType**\(**바이트**\) 식의 **CharType** 형식의 값으로 변환합니다.  
  
 나머지 작업은 `char` 값에 대해 명시적 특수화인 **ctype**\<`char`\>과 동일한 방식으로 수행됩니다.  
  
### 생성자  
  
|||  
|-|-|  
|[ctype](../Topic/ctype::ctype.md)|문자의 로캘 패싯으로 사용할 수 있는 `ctype` 클래스의 개체에 대한 생성자입니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/ctype::char_type.md)|로캘에서 사용하는 문자를 설명하는 형식|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[do\_is](../Topic/ctype::do_is.md)|단일 문자에 특정 특성이 있는지 여부를 테스트하거나 범위에 있는 각 문자의 특성을 분류하고 배열에 저장하기 위해 호출하는 가상 함수입니다.|  
|[do\_narrow](../Topic/ctype::do_narrow.md)|로캘에서 사용하는 `CharType` 형식의 문자를 네이티브 문자 집합의 `char` 형식의 해당 문자로 변환하기 위해 호출하는 가상 함수입니다.|  
|[do\_scan\_is](../Topic/ctype::do_scan_is.md)|범위에서 지정된 마스크와 일치하는 첫 번째 문자를 찾기 위해 호출하는 가상 함수입니다.|  
|[do\_scan\_not](../Topic/ctype::do_scan_not.md)|범위에서 지정된 마스크와 일치하지 않는 첫 번째 문자를 찾기 위해 호출하는 가상 함수입니다.|  
|[do\_tolower](../Topic/ctype::do_tolower.md)|문자 또는 문자 범위를 소문자로 변환하기 위해 호출하는 함수입니다.|  
|[do\_toupper](../Topic/ctype::do_toupper.md)|문자 또는 문자 범위를 대문자로 변환하기 위해 호출하는 함수입니다.|  
|[do\_widen](../Topic/ctype::do_widen.md)|네이티브 문자 집합의 `char` 형식의 문자를 로캘에서 사용하는 `CharType` 형식의 문자로 변환하기 위해 호출하는 가상 함수입니다.|  
|[is](../Topic/ctype::is.md)|단일 문자에 특정 특성이 있는지 여부를 테스트하거나 범위에 있는 각 문자의 특성을 분류하고 배열에 저장합니다.|  
|[narrow](../Topic/ctype::narrow.md)|로캘에서 사용하는 `CharType` 형식의 문자를 네이티브 문자 집합의 형식 문자의 해당 문자로 변환합니다.|  
|[scan\_is](../Topic/ctype::scan_is.md)|범위에서 지정된 마스크와 일치하는 첫 번째 문자를 찾습니다.|  
|[scan\_not](../Topic/ctype::scan_not.md)|범위에서 지정된 마스크와 일치하지 않는 첫 번째 문자를 찾습니다.|  
|[tolower](../Topic/ctype::tolower.md)|문자 또는 문자 범위를 소문자로 변환합니다.|  
|[toupper](../Topic/ctype::toupper.md)|문자 또는 문자 범위를 대문자로 변환합니다.|  
|[widen](../Topic/ctype::widen.md)|네이티브 문자 집합의 `char` 형식의 문자를 로캘에서 사용하는 `CharType` 형식의 해당 문자로 변환합니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<locale\>](../standard-library/locale.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)