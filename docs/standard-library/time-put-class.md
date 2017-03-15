---
title: "time_put 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::time_put"
  - "time_put"
  - "xloctime/std::time_put"
  - "std.time_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put 클래스"
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# time_put 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

시간 값에서 `CharType` 형식의 시퀀스로 변환을 제어하는 로캘 패싯으로 사용 가능한 개체에 대해 설명하는 템플릿 클래스입니다.  
  
## 구문  
  
```  
template <  
   class CharType,  
   class OutputIterator = ostreambuf_iterator<CharType>  
> class time_put : public locale::facet;  
```  
  
#### 매개 변수  
 `CharType`  
 문자를 인코딩하기 위해 프로그램 내 사용하는 형식  
  
 `OutputIterator`  
 시간 put 함수가 출력을 쓰는 반복기의 형식입니다.  
  
## 설명  
 모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다.  처음에 저장된 값에 액세스를 시도하면 **id**에 고유한 양수 값이 저장됩니다.  
  
### 생성자  
  
|||  
|-|-|  
|[time\_put](../Topic/time_put::time_put.md)|`time_put` 형식의 개체에 대한 생성자입니다.|  
  
### 형식 정의  
  
|||  
|-|-|  
|[char\_type](../Topic/time_put::char_type.md)|로캘에서 사용하는 문자를 설명하기 위해 사용하는 형식입니다.|  
|[iter\_type](../Topic/time_put::iter_type.md)|출력 반복기에 대해 설명하는 형식입니다.|  
  
### 멤버 함수  
  
|||  
|-|-|  
|[do\_put](../Topic/time_put::do_put.md)|시간과 날짜 정보를 `CharType`의 시퀀스로 출력하는 가상 함수입니다.|  
|[put](../Topic/time_put::put.md)|시간과 날짜 정보를 `CharType`의 시퀀스로 출력합니다.|  
  
## 요구 사항  
 **헤더:** \<locale\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base 클래스](../standard-library/time-base-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)