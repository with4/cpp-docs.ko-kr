---
title: "moneypunct 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "moneypunct"
  - "std.moneypunct"
  - "xlocmon/std::moneypunct"
  - "std::moneypunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "moneypunct 클래스"
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# moneypunct 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스는 통화 입력 필드 또는 통화 출력 필드를 나타내는 데 사용 가능한 `CharType` 형식의 시퀀스를 설명하는 데 로캘 패싯으로 사용할 수 있는 개체에 대해 설명합니다.  템플릿 매개 변수 `Intl`이 `true`인 경우 국제 규약을 준수합니다.  
  
## 구문  
  
```  
template<class CharType, bool Intl>   
   class moneypunct;  
```  
  
#### 매개 변수  
 `CharType`  
 문자를 인코딩하기 위해 프로그램 내 사용하는 형식  
  
 `Intl`  
 국제 규약을 준수하는지 여부를 지정하는 플래그입니다.  
  
## 설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다.  처음에 저장된 값에 액세스를 시도하면**id**에 고유한 양수 값이 저장됩니다.  
  
 상수 정적 개체 intl에는 템플릿 매개 변수 **Intl**의 값이 저장됩니다.  
  
### 생성자  
  
|||  
|-|-|  
|[moneypunct](../Topic/moneypunct::moneypunct.md)|`moneypunct` 형식의 개체 생성자입니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/moneypunct::char_type.md)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[string\_type](../Topic/moneypunct::string_type.md)|`CharType` 형식의 문자가 포함된 문자열을 설명하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[curr\_symbol](../Topic/moneypunct::curr_symbol.md)|통화 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|  
|[decimal\_point](../Topic/moneypunct::decimal_point.md)|소수점 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|  
|[do\_curr\_symbol](../Topic/moneypunct::do_curr_symbol.md)|통화 기호로 사용할 로캘별 요소 시퀀스를 반환하는 보호된 가상 멤버 함수입니다.|  
|[do\_decimal\_point](../Topic/moneypunct::do_decimal_point.md)|소수점 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_frac\_digits](../Topic/moneypunct::do_frac_digits.md)|보호된 가상 멤버 함수가 소수점 오른쪽에 표시할 자릿수를 로캘별로 반환합니다.|  
|[do\_grouping](../Topic/moneypunct::do_grouping.md)|보호된 가상 멤버 함수가 소수점 자리 왼쪽의 숫자를 그룹화하는 방법을 결정하는 로캘별 규칙을 반환합니다.|  
|[do\_neg\_format](../Topic/moneypunct::do_neg_format.md)|음수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_negative\_sign](../Topic/moneypunct::do_negative_sign.md)|음수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_pos\_format](../Topic/moneypunct::do_pos_format.md)|양수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_negative\_sign](../Topic/moneypunct::do_positive_sign.md)|양수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[do\_thousands\_sep](../Topic/moneypunct::do_thousands_sep.md)|1000 단위 구분 기호로 사용할 로캘별 요소 시퀀스를 반환하기 위해 호출하는 보호된 가상 멤버 함수입니다.|  
|[frac\_digits](../Topic/moneypunct::frac_digits.md)|소수점 오른쪽에 표시할 자릿수를 로캘별로 반환합니다.|  
|[그룹화](../Topic/moneypunct::grouping.md)|소수점 왼쪽의 숫자를 그룹화할 방법을 결정하기 위한 로캘별 규칙을 반환합니다.|  
|[neg\_format](../Topic/moneypunct::neg_format.md)|음수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환합니다.|  
|[negative\_sign](../Topic/moneypunct::negative_sign.md)|음수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|  
|[pos\_format](../Topic/moneypunct::pos_format.md)|양수 금액의 출력의 서식을 지정하기 위한 로캘별 규칙을 반환합니다.|  
|[positive\_sign](../Topic/moneypunct::positive_sign.md)|양수 부호 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|  
|[thousands\_sep](../Topic/moneypunct::thousands_sep.md)|1000 단위 구분 기호로 사용할 로캘별 요소 시퀀스를 반환합니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<locale\>](../standard-library/locale.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)