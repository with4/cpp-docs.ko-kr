---
title: "is_convertible 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_convertible
- std::is_convertible
- type_traits/std::is_convertible
dev_langs:
- C++
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
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
ms.openlocfilehash: 381fa9297dd9fad3efd84078a000fea65af0abfd
ms.lasthandoff: 02/24/2017

---
# <a name="isconvertible-class"></a>is_convertible 클래스
한 가지 형식을 다른 형식으로 변환할 수 있는지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class From, class To>  
struct is_convertible;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `From`  
 변환할 원본 형식입니다.  
  
 `Ty`  
 변환할 대상 형식입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 식 `To to = from;`이 올바른 형식인 경우 true입니다(여기서 `from`은 `From` 형식의 개체임).  
  
## <a name="example"></a>예제  
  
```cpp  
// std__type_traits__is_convertible.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha   
        << std::is_convertible<trivial, int>::value << std::endl;   
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha   
        << std::is_convertible<trivial, trivial>::value << std::endl;   
    std::cout << "is_convertible<char, int> == " << std::boolalpha   
        << std::is_convertible<char, int>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_convertible<trivial, int> == false  
is_convertible<trivial, trivial> == true  
is_convertible<char, int> == true  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_base_of 클래스](../standard-library/is-base-of-class.md)

