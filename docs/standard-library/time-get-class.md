---
title: "time_get 클래스 | Microsoft Docs"
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
  - "std.time_get"
  - "xloctime/std::time_get"
  - "time_get"
  - "std::time_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_get 클래스"
ms.assetid: 869d5f5b-dbab-4628-8333-bdea7e272023
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_get 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 `CharType` 형식의 시퀀스에서 시간 값으로 변환을 제어하는 로캘 패싯으로 사용할 수 있는 개체를 설명합니다.  
  
## 구문  
  
```  
template <  
   class CharType,  
   class InputIterator = istreambuf_iterator<CharType>  
> class time_get : public time_base;  
```  
  
#### 매개 변수  
 `CharType`  
 문자를 인코딩하기 위해 프로그램 내 사용하는 형식  
  
 `InputIterator`  
 시간 값을 읽어올 반복기입니다.  
  
## 설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다.  처음에 저장된 값에 액세스를 시도하면**id**에 고유한 양수 값이 저장됩니다.  
  
### 생성자  
  
|||  
|-|-|  
|[time\_get](../Topic/time_get::time_get.md)|`time_get` 형식의 개체에 대한 생성자입니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/time_get::char_type.md)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[iter\_type](../Topic/time_get::iter_type.md)|입력 반복기에 대해 설명하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[date\_order](../Topic/time_get::date_order.md)|패싯에서 사용하는 날짜 순서를 반환합니다.|  
|[do\_date\_order](../Topic/time_get::do_date_order.md)|패싯에서 사용하는 날짜 순서를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_get](../Topic/time_get::do_get.md)|문자 데이터를 읽고 시간 값으로 변환합니다.|  
|[do\_get\_date](../Topic/time_get::do_get_date.md)|문자열을 `x` 지정자가 `strftime`에 대해 만든 날짜로 구문 분석하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_get\_monthname](../Topic/time_get::do_get_monthname.md)|문자열을 월 이름으로 구문 분석하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_get\_time](../Topic/time_get::do_get_time.md)|`X` 지정자가 `strftime`에 대해 만든 날짜로 문자열을 구문 분석하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_get\_weekday](../Topic/time_get::do_get_weekday.md)|문자열을 요일 이름으로 구문 분석하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_get\_year](../Topic/time_get::do_get_year.md)|문자열을 연도 이름으로 구문 분석하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[get](../Topic/time_get::get.md)|문자 데이터 소스를 읽고 해당 데이터를 시간 구조체에 저장된 시간으로 변환합니다.|  
|[get\_date](../Topic/time_get::get_date.md)|문자열을 `x` 지정자가 `strftime`에 대해 만든 날짜로 구문 분석합니다.|  
|[get\_monthname](../Topic/time_get::get_monthname.md)|문자열을 월 이름으로 구문 분석합니다.|  
|[get\_time](../Topic/time_get::get_time.md)|문자열을 `X` 지정자가 `strftime`에 대해 만든 날짜로 구문 분석합니다.|  
|[get\_weekday](../Topic/time_get::get_weekday.md)|문자열을 요일 이름으로 구문 분석합니다.|  
|[get\_year](../Topic/time_get::get_year.md)|문자열을 연도 이름으로 구문 분석합니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base 클래스](../standard-library/time-base-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)