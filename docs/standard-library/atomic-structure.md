---
title: "atomic 구조체 | Microsoft Docs"
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
  - "atomic/std::atomic"
dev_langs: 
  - "C++"
ms.assetid: 261628ed-7049-41ac-99b9-cfe49f696b44
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atomic 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 `Ty` 형식의 저장 된 값의 최소 작업을 수행 하는 개체에 설명합니다.  
  
## 구문  
  
```  
template <class Ty>  
struct atomic;  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[atomic::atomic 생성자](../Topic/atomic::atomic%20Constructor.md)|원자 개체를 생성 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[atomic::operator Ty 연산자](../Topic/atomic::operator%20Ty%20Operator.md)|읽고 저장된 값을 반환 합니다. \([atomic::load 메서드](../Topic/atomic::load%20Method.md)\)|  
|[atomic::operator\= 연산자](../Topic/atomic::operator=%20Operator.md)|지정된 값 저장된 값을 사용 합니다. \([atomic::store 메서드](../Topic/atomic::store%20Method.md)\)|  
|||  
|[atomic::operator\+\+ 연산자](../Topic/atomic::operator++%20Operator.md)|저장된 값을 증가 시킵니다.  포인터와 정수 계열 특수화만 사용합니다.|  
|[atomic::operator\+\= 연산자](../Topic/atomic::operator+=%20Operator.md)|저장된 값에 지정된 값을 추가합니다.  포인터와 정수 계열 특수화만 사용합니다.|  
|[atomic::operator\-\- 연산자](../Topic/atomic::operator--%20Operator.md)|저장된 값을 감소 시킵니다.  포인터와 정수 계열 특수화만 사용합니다.|  
|[atomic::operator\-\= 연산자](../Topic/atomic::operator-=%20Operator.md)|저장하는 값으로 부터 지정된 값을 뺍니다.  포인터와 정수 계열 특수화만 사용합니다.|  
|[atomic::operator&\= 연산자](../Topic/atomic::operator&=%20Operator.md)|연산을 수행 `and` 에 지정 된 값과 저장된 된 값입니다.  완전한 특수화로만 사용됩니다.|  
|[atomic::operator&#124;\= 연산자](../Topic/atomic::operator%7C=%20Operator.md)|연산을 수행 `or` 에 지정 된 값과 저장된 된 값입니다.  완전한 특수화로만 사용됩니다.|  
|[atomic::operator^\= 연산자](../Topic/atomic::operator%5E=%20Operator.md)|연산을 수행 `exclusive or` 에 지정 된 값과 저장된 된 값입니다.  완전한 특수화로만 사용됩니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[atomic::compare\_exchange\_strong 메서드](../Topic/atomic::compare_exchange_strong%20Method.md)|수행는 `atomic_compare_and_exchange` 에서 작업 `this` 이고 결과 반환 합니다.|  
|[atomic::compare\_exchange\_weak 메서드](../Topic/atomic::compare_exchange_weak%20Method.md)|수행는 `weak_atomic_compare_and_exchange` 에서 작업 `this` 이고 결과를 반환 합니다.|  
|[atomic::fetch\_add 메서드](../Topic/atomic::fetch_add%20Method.md)|저장된 값에 지정된 값을 추가합니다.|  
|[atomic::fetch\_and 메서드](../Topic/atomic::fetch_and%20Method.md)|연산을 수행 `and` 에 지정 된 값과 저장된 된 값입니다.|  
|[atomic::fetch\_or 메서드](../Topic/atomic::fetch_or%20Method.md)|연산을 수행 `or` 에 지정 된 값과 저장된 된 값입니다.|  
|[atomic::fetch\_sub 메서드](../Topic/atomic::fetch_sub%20Method.md)|저장하는 값으로 부터 지정된 값을 뺍니다.|  
|[atomic::fetch\_xor 메서드](../Topic/atomic::fetch_xor%20Method.md)|연산을 수행 `exclusive or` 에 지정 된 값과 저장된 된 값입니다.|  
|[atomic::is\_lock\_free 메서드](../Topic/atomic::is_lock_free%20Method.md)|이 `this` 은 *잠금 가능*의 원자 연산인지 지정합니다.  원자 형식이 *잠금 가능* 원자 단위 작업이 해당 형식에는 잠금을 사용하는 경우입니다.|  
|[atomic::load 메서드](../Topic/atomic::load%20Method.md)|읽고 저장된 값을 반환 합니다.|  
|[atomic::store 메서드](../Topic/atomic::store%20Method.md)|지정된 값 저장된 값을 사용 합니다.|  
  
## 설명  
 유형 `Ty` 은 *사소 하 게 복사할 수* 있어야만 합니다.  즉, [memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md) 의 바이트를 복사 생성해야 올바른 `Ty` 개체가 원래 개체와 동일한 지 비교하여 사용합니다.  이 `compare_exchange_weak` 와 `compare_exchange_strong` 맴버 함수는 `Ty` 값이 같은 지 확인하려는 [memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md) 를 사용합니다.  이러한 함수는 `operator==` 로 정의된 `Ty` 사용합니다.  이 `atomic` 의 맴버 함수는 `Ty` 형식의 값을 복사하는 `memcpy` 을 사용합니다.  
  
 부분 특수화에서, `atomic<Ty *>`, 모든 포인터 형식에 대해 존재 합니다.  전문화된 관리되는 포인터 값을 오프셋 더하기 또는 빼기를 오프셋 수 있습니다.  형식 인수를 사용하는 산술 연산을 `ptrdiff_t` 의 크기에 따라 해당 인수를 조정하고 `Ty` 일반 주소 산술 연산을 사용하여 일관성을 유지합니다.  
  
 이 `bool` 특수화를 제외한 모든 정수 계열 형식에 있습니다.  각 특수화 풍부한 원자 산술 및 논리 연산에 사용할 수 있는 메서드를 제공합니다.  
  
||||  
|-|-|-|  
|`atomic<char>`|`atomic<signed char>`|`atomic<unsigned char>`|  
|`atomic<char16_t>`|`atomic<char32_t>`|`atomic<wchar_t>`|  
|`atomic<short>`|`atomic<unsigned short>`|`atomic<int>`|  
|`atomic<unsigned int>`|`atomic<long>`|`atomic<unsigned long>`|  
|`atomic<long long>`|`atomic<unsigned long long>`|  
  
 정수 특수화는 해당하는 `atomic_``integral` 형식으로 부터 파생됩니다.  예를 들어, `atomic<unsigned int>` 는 `atomic_uint`에서 파생됩니다.  
  
## 요구 사항  
 **헤더:** atomic  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [\<atomic\>](../standard-library/atomic.md)   
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)