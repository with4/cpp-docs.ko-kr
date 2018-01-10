---
title: "is_member_object_pointer 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_member_object_pointer
dev_langs: C++
helpviewer_keywords:
- is_member_object_pointer class
- is_member_object_pointer
ms.assetid: 64f9cdf3-4621-4310-a076-a7bc986926b9
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: abd7a37c32a2def953f376a28de6c561cea55fee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ismemberobjectpointer-class"></a>is_member_object_pointer 클래스
형식이 멤버 개체에 대한 포인터인지 여부를 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
struct is_member_object_pointer;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 멤버 개체이거나 멤버 개체에 대한 `cv-qualified` 포인터인 경우 true이고 그렇지 않은 경우 false입니다. `Ty`가 멤버 함수에 대한 포인터인 경우 `is_member_object_pointer`는 false입니다.  
  
## <a name="example"></a>예  
  
```cpp  
// std__type_traits__is_member_object_pointer.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
struct functional   
    {   
    int f();   
    };   
  
int main()   
    {   
    std::cout << "is_member_object_pointer<trivial *> == "   
        << std::boolalpha   
        << std::is_member_object_pointer<trivial *>::value   
        << std::endl;   
    std::cout << "is_member_object_pointer<int trivial::*> == "   
        << std::boolalpha   
        << std::is_member_object_pointer<int trivial::*>::value   
        << std::endl;   
    std::cout << "is_member_object_pointer<int (functional::*)()> == "   
        << std::boolalpha   
        << std::is_member_object_pointer<int (functional::*)()>::value   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_member_object_pointer<trivial *> == false  
is_member_object_pointer<int trivial::*> == true  
is_member_object_pointer<int (functional::*)()> == false  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_member_pointer 클래스](../standard-library/is-member-pointer-class.md)
