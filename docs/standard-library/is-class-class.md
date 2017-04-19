---
title: "is_class 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_class
- type_traits/std::is_class
dev_langs:
- C++
helpviewer_keywords:
- is_class class
- is_class
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: af9a1513e7fac1dbcf36273f02ca26c0f9a7df6a
ms.lasthandoff: 02/24/2017

---
# <a name="isclass-class"></a>is_class 클래스
형식이 클래스인지 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
struct is_class;  
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 `class`, `struct` 또는 두 형식 중 하나의 `cv-qualified` 형태로 정의된 형식인 경우 true이고 그렇지 않은 경우 false입니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// std__type_traits__is_class.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_class<trivial> == " << std::boolalpha   
        << std::is_class<trivial>::value << std::endl;   
    std::cout << "is_class<int> == " << std::boolalpha   
        << std::is_class<int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_class<trivial> == true  
is_class<int> == false  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_compound 클래스](../standard-library/is-compound-class.md)   
 [is_union 클래스](../standard-library/is-union-class.md)

