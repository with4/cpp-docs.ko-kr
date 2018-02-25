---
title: "is_pointer 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_pointer
dev_langs:
- C++
helpviewer_keywords:
- is_pointer class
- is_pointer
ms.assetid: 44e0a403-7241-4e0a-8922-32877bcb9a4c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f0c4048ebaa98a6533e210335ecedceb931c644
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="ispointer-class"></a>is_pointer 클래스
형식이 포인터인지 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
struct is_pointer;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 `void`에 대한 포인터, 개체에 대한 포인터 또는 함수에 대한 포인터이거나 이러한 포인터 중 하나의 `cv-qualified` 형식인 경우 true이고, 그렇지 않은 경우 false입니다. `Ty`가 멤버에 대한 포인터 또는 멤버 함수에 대한 포인터인 경우 `is_pointer`는 false입니다.  
  
## <a name="example"></a>예  
  
```cpp  
// std__type_traits__is_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_pointer<trivial> == " << std::boolalpha   
        << std::is_pointer<trivial>::value << std::endl;   
    std::cout << "is_pointer<int trivial::*> == " << std::boolalpha   
        << std::is_pointer<int trivial::*>::value << std::endl;   
    std::cout << "is_pointer<trivial *> == " << std::boolalpha   
        << std::is_pointer<trivial *>::value << std::endl;   
    std::cout << "is_pointer<int> == " << std::boolalpha   
        << std::is_pointer<int>::value << std::endl;   
    std::cout << "is_pointer<int *> == " << std::boolalpha   
        << std::is_pointer<int *>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_pointer<trivial> == false  
is_pointer<int trivial::*> == false  
is_pointer<trivial *> == true  
is_pointer<int> == false  
is_pointer<int *> == true  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_member_pointer 클래스](../standard-library/is-member-pointer-class.md)   
 [is_reference 클래스](../standard-library/is-reference-class.md)
