---
title: "duration 클래스 | Microsoft Docs"
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
  - "chrono/std::chrono::duration"
dev_langs: 
  - "C++"
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# duration 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 *시간 간격* 보유하고 있는 형식에 설명하는데, 두 시점 간의 경과된 시간입니다.  
  
## 구문  
  
```  
template<  
   class Rep,  
   class Period = ratio<1>  
>  
class duration;  
template<  
   class Rep,  
   class Period  
>  
class duration;  
template<  
   class Rep,  
   class Period1,  
   class Period2  
>  
class duration  
   <duration<Rep, Period1>, Period2>;  
```  
  
## 설명  
 템플릿 인수 `Rep` 는 간격에 클록 틱 수를 보유하는 데 사용 되는 형식을 설명 합니다.  템플릿 인수 `Period` 는 [비율](../standard-library/ratio.md) 나타내는 각 눈금 간격의 크기를 설명하는 인스턴스 입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[duration::period Typedef](http://msdn.microsoft.com/ko-kr/ebf2a1b9-769f-475f-8c66-cf9ed12015f2)|동의어에 대한 템플릿 `Period`매개 변수를 나타냅니다.|  
|[duration::rep Typedef](http://msdn.microsoft.com/ko-kr/f47b8abb-ae2c-4dc8-858a-f44695156950)|동의어에 대한 템플릿 `Rep`매개 변수를 나타냅니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[duration::duration 생성자](../Topic/duration::duration%20Constructor.md)|`duration` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[duration::count 메서드](../Topic/duration::count%20Method.md)|개체에 대한 클록 시간의 틱 수를 반환합니다.|  
|[duration::max 메서드](../Topic/duration::max%20Method.md)|Static.  템플릿 매개 `Ref` 변수에 허용되는 최대 값을 반환 합니다.|  
|[duration::min 메서드](../Topic/duration::min%20Method.md)|Static.  템플릿 매개 `Ref` 변수에 허용되는 최소 값을 반환 합니다.|  
|[duration::zero 메서드](../Topic/duration::zero%20Method.md)|Static.  사실, `Rep`\(0\)를 반환합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[duration::operator\- 연산자](../Topic/duration::operator-%20Operator.md)|부정된 틱 수의 `duration` 개체 복사본을 반환합니다.|  
|[duration::operator\-\- 연산자](../Topic/duration::operator--%20Operator.md)|저장된 tick 횟수를 줄입니다.|  
|[duration::operator\= 연산자](../Topic/duration::operator=%20Operator.md)|지정된 값을 나눈 나머지 값으로 저장된 틱 수를 줄일 수 있습니다.|  
|[duration::operator\*\= 연산자](../Topic/duration::operator*=%20Operator.md)|지정된 값을 저장된 틱 수를 곱합니다.|  
|[duration::operator\/\= 연산자](../Topic/duration::operator-=%20Operator1.md)|이 `duration` 개체 지정된 틱 수로 저장된 틱 수를 나눕니다.|  
|[duration::operator\+ 연산자](../Topic/duration::operator+%20Operator.md)|`*this`를 반환합니다.|  
|[duration::operator\+\+ 연산자](../Topic/duration::operator++%20Operator.md)|저장된 tick 횟수를 증가합니다.|  
|[duration::operator\+\= 연산자](../Topic/duration::operator+=%20Operator.md)|저장된 틱 카운터의 `duration` 개체 지정된 틱 수로 저장된 틱 수를 추가합니다.|  
|[duration::operator\-\= 연산자](../Topic/duration::operator-=%20Operator2.md)|저장된 틱 카운터의 `duration` 개체 지정된 틱 수로 저장된 틱 수를 뺍니다.|  
  
## 요구 사항  
 **Header:** chrono  
  
 **네임 스페이스:** std::chrono  
  
## 참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [duration\_values 구조체](../standard-library/duration-values-structure.md)