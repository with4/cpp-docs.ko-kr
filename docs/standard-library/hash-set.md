---
title: "&lt;hash_set&gt; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_set>
- std.<hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: cd8ab51b229f1c62cd6f3dd1862920d683834975
ms.lasthandoff: 02/24/2017

---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;
> [!NOTE]
>  이 헤더는 사용되지 않습니다. [<unordered_set>](../standard-library/unordered-set.md)을 대신 사용하는 것이 좋습니다.  
  
 컨테이너 템플릿 클래스 hash_set 및 hash_multiset와 각 클래스의 지원 템플릿을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <hash_set>  
  
```  
  
## <a name="remarks"></a>설명  
  
### <a name="operators"></a>연산자  
  
|Hash_set 버전|Hash_multiset 버전|설명|  
|-----------------------|----------------------------|-----------------|  
|[operator!=(hash_set)](../standard-library/hash-set-operators.md#operator_neq)|[operator!=(hash_multiset)](../standard-library/hash-set-operators.md#operator_neq__hash_multiset_)|연산자의 좌변에 있는 hash_set 또는 hash_multiset 개체가 우변에 있는 hash_set 또는 hash_multiset 개체와 같지 않은지 테스트합니다.|  
|[operator==(hash_set)](http://msdn.microsoft.com/en-us/791b95bd-f917-4716-aea6-add50badbfac)|[operator==(hash_multiset)](http://msdn.microsoft.com/en-us/cfa9aa0c-d5f6-403a-9441-35c2a4cee0fb)|연산자의 좌변에 있는 hash_set 또는 hash_multiset 개체가 우변에 있는 hash_set 또는 hash_multiset 개체와 같은지 테스트합니다.|  
  
### <a name="specialized-template-functions"></a>특별 템플릿 함수  
  
|Hash_set 버전|Hash_multiset 버전|설명|  
|-----------------------|----------------------------|-----------------|  
|[swap(hash_set)](../standard-library/hash-set-functions.md#swap)|[swap(hash_multiset)](../standard-library/hash-set-functions.md#swap__hash_multiset_)|두 hash_set 또는 hash_multiset의 요소를 교환합니다.|  
  
### <a name="classes"></a>클래스  
  
|||  
|-|-|  
|[hash_compare 클래스](../standard-library/hash-compare-class.md)|해시 연관 컨테이너(hash_map, hash_multimap, hash_set 또는 hash_multiset) 중 하나에서 기본 **Traits** 매개 변수 개체로 사용하여 포함된 요소의 순서를 지정하고 해시할 수 있는 개체를 설명합니다.|  
|[hash_set 클래스](../standard-library/hash-set-class.md)|포함된 요소의 값이 고유하고 키 값으로 사용된 컬렉션의 데이터를 빠르게 검색하고 저장하는 데 사용됩니다.|  
|[hash_multiset 클래스](../standard-library/hash-multiset-class.md)|포함된 요소의 값이 고유하고 키 값으로 사용된 컬렉션의 데이터를 빠르게 검색하고 저장하는 데 사용됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 표준 라이브러리 참조](../standard-library/cpp-standard-library-reference.md)




