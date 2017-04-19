---
title: "is_base_of 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_base_of
- type_traits/std::is_base_of
dev_langs:
- C++
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
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
ms.openlocfilehash: 22b1f7f93d82fbe5780352c11cb9024b8305d79c
ms.lasthandoff: 02/24/2017

---
# <a name="isbaseof-class"></a>is_base_of 클래스
한 형식이 다른 형식의 기본 형식인지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Base, class Derived>  
struct is_base_of;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 테스트할 기본 클래스입니다.  
  
 `Derived`  
 테스트할 파생 형식입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `Base` 형식이 `Derived` 형식의 기본 클래스인 경우 true이고, 그렇지 않은 경우 false입니다.  
  
## <a name="example"></a>예제  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
struct base   
    {   
    int val;   
    };   
  
struct derived   
    : public base   
    {   
    };   
  
int main()   
    {   
    std::cout << "is_base_of<base, base> == " << std::boolalpha   
        << std::is_base_of<base, base>::value << std::endl;   
    std::cout << "is_base_of<base, derived> == " << std::boolalpha   
        << std::is_base_of<base, derived>::value << std::endl;   
    std::cout << "is_base_of<derived, base> == " << std::boolalpha   
        << std::is_base_of<derived, base>::value << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
is_base_of<base, base> == true  
is_base_of<base, derived> == true  
is_base_of<derived, base> == false  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_convertible 클래스](../standard-library/is-convertible-class.md)

