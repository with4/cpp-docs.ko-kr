---
title: '&lt;set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<set>
- std::<set>
- <set>
dev_langs:
- C++
helpviewer_keywords:
- set header
ms.assetid: 43cb1ab2-6383-48cf-8bdc-2b96d7203596
caps.latest.revision: 20
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 1295a8c71464b7cc9d204c807c3492000b73ffa1
ms.lasthandoff: 02/24/2017

---
# <a name="ltsetgt"></a>&lt;set&gt;
컨테이너 템플릿 클래스 set 및 multiset과 지원 템플릿을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <set>  
  
```  
  
## <a name="members"></a>멤버  
  
### <a name="operators"></a>연산자  
  
|set 버전|multiset 버전|설명|  
|-----------------|----------------------|-----------------|  
|[operator!= (set)](../standard-library/set-operators.md#operator_neq)|[operator!= (multiset)](../standard-library/set-operators.md#operator_neq)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체와 같지 않은지 테스트합니다.|  
|[operator< (set)](../standard-library/set-operators.md#operator_lt_)|[operator< (multiset)](../standard-library/set-operators.md#operator_lt_)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 작은지 테스트합니다.|  
|[operator<= (set)](../standard-library/set-operators.md#operator_lt__eq)|[operator\<= (multiset)](../standard-library/set-operators.md#operator_lt__eq)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 작거나 같은지 테스트합니다.|  
|[operator== (set)](../standard-library/set-operators.md#operator_eq_eq)|[operator== (multiset)](../standard-library/set-operators.md#operator_eq_eq)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체와 같은지 테스트합니다.|  
|[operator> (set)](../standard-library/set-operators.md#operator_gt_)|[operator> (multiset)](../standard-library/set-operators.md#operator_gt_)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 큰지 테스트합니다.|  
|[operator>= (set)](../standard-library/set-operators.md#operator_gt__eq)|[operator>= (multiset)](../standard-library/set-operators.md#operator_gt__eq)|연산자의 좌변에 있는 set 또는 multiset 개체가 우변에 있는 set 또는 multiset 개체보다 크거나 같은지 테스트합니다.|  
  
### <a name="specialized-template-functions"></a>특별 템플릿 함수  
  
|set 버전|multiset 버전|설명|  
|-----------------|----------------------|-----------------|  
|[swap](../standard-library/set-functions.md#swap)|[swap](../standard-library/set-functions.md#swap)|두 set 또는 multiset의 요소를 교환합니다.|  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[set 클래스](../standard-library/set-class.md)|포함된 요소의 값이 고유하고 데이터가 자동 정렬되는 기준인 키 값으로 사용된 컬렉션의 데이터를 저장 및 검색하는 데 사용됩니다.|  
|[multiset 클래스](../standard-library/multiset-class.md)|포함된 요소의 값이 고유할 필요가 없고 데이터가 자동 정렬되는 기준인 키 값으로 사용된 컬렉션의 데이터를 저장 및 검색하는 데 사용됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)




