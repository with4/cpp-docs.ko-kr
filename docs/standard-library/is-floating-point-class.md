---
title: "is_floating_point 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_floating_point
- type_traits/std::is_floating_point
dev_langs:
- C++
helpviewer_keywords:
- is_floating_point class
- is_floating_point
ms.assetid: 070679c1-115b-4ee4-8ab7-f52e5d9e157f
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: fad953c57d32b7851cff3083fc133dce5fd2ef10
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="isfloatingpoint-class"></a>is_floating_point 클래스
형식이 부동 소수점인지를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
struct is_floating_point;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 부동 소수점 형식 또는 `cv-qualified` 형태의 부동 소수점 형식인 경우 true이고, 그렇지 않은 경우 false입니다.  
  
 부동 소수점 형식은 `float`, `double` 또는 `long double` 중 하나입니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// std__type_traits__is_floating_point.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_floating_point<trivial> == " << std::boolalpha   
        << std::is_floating_point<trivial>::value << std::endl;   
    std::cout << "is_floating_point<int> == " << std::boolalpha   
        << std::is_floating_point<int>::value << std::endl;   
    std::cout << "is_floating_point<float> == " << std::boolalpha   
        << std::is_floating_point<float>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_floating_point<trivial> == false  
is_floating_point<int> == false  
is_floating_point<float> == true  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_integral 클래스](../standard-library/is-integral-class.md)

