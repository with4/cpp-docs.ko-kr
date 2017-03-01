---
title: "&lt;스레드&gt; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 9b32de86d2ec84017157cccf1a05b9e9b6802e47
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt"></a>&lt;스레드&gt;
표준 헤더 포함 \<스레드 > 클래스를 정의 `thread` 및 다양 한 지원 기능입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>주의  
  
> [!NOTE]
>  사용 하 여 컴파일되는 코드에서 **/clr**,이 헤더는 차단 됩니다.  
  
 `__STDCPP_THREADS__` 매크로 스레드가이 헤더에 의해 지원 되는 표시에&0;이 아닌 값으로 정의 됩니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-classes"></a>public 클래스  
  
|이름|설명|  
|----------|-----------------|  
|[thread 클래스](../standard-library/thread-class.md)|관찰 하 고 응용 프로그램의 실행 스레드를 관리 하는 데 사용 되는 개체를 정의 합니다.|  
  
### <a name="public-structures"></a>공용 구조체  
  
|이름|설명|  
|----------|-----------------|  
|[hash 구조체(C++ 표준 라이브러리)](../standard-library/hash-structure-stl.md)|고유 하 게 의해 결정 되는 값을 반환 하는 멤버 함수 정의 `thread::id`합니다. 멤버 함수 정의 [해시](../standard-library/hash-class.md) 매핑 값 형식에 적합 한 함수 `thread::id` 인덱스 값의 분포에 있습니다.|  
  
### <a name="public-functions"></a>공용 함수  
  
|이름|설명|  
|----------|-----------------|  
|[get_id 함수](../standard-library/thread-functions.md#get_id_function)|현재 실행 스레드를 고유하게 식별합니다.|  
|[sleep_for 함수](../standard-library/thread-functions.md#sleep_for_function)|호출 스레드를 차단합니다.|  
|[sleep_until 함수](../standard-library/thread-functions.md#sleep_until_function)|최소한 지정된 시간까지 호출 스레드를 차단합니다.|  
|[swap 함수](../standard-library/thread-functions.md#swap_function)|두 개의 상태 교환 `thread` 개체입니다.|  
|[yield 함수](../standard-library/thread-functions.md#yield_function)|정상적인 경우라면 현재 스레드가 계속 실행되더라도 운영 체제에 다른 스레드를 실행할 것을 알립니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[연산자 > = 연산자](../standard-library/thread-operators.md#operator_gt__eq)|하나의 `thread::id` 개체가 다른 개체보다 크거나 같은지를 확인합니다.|  
|[연산자 > 연산자](../standard-library/thread-operators.md#operator_gt_)|하나의 `thread::id` 개체가 다른 개체보다 큰지를 확인합니다.|  
|[연산자<=></=>](../standard-library/thread-operators.md#operator_lt__eq)|하나의 `thread::id` 개체가 다른 개체보다 작거나 같은지를 확인합니다.|  
|[연산자<>](../standard-library/thread-operators.md#operator_lt_)|하나의 `thread::id` 개체가 다른 개체보다 작은지를 확인합니다.|  
|[연산자! = 연산자](../standard-library/thread-operators.md#operator_neq)|두 `thread::id` 개체가 다른지 비교합니다.|  
|[연산자 = = 연산자](../standard-library/thread-operators.md#operator_eq_eq)|두 `thread::id` 개체가 같은지 비교합니다.|  
|[연산자<>](../standard-library/thread-operators.md#operator_lt__lt_)|`thread::id` 개체의 텍스트 표현을 스트림에 삽입합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)


