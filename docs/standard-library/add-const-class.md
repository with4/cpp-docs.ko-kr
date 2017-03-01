---
title: "add_const 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- add_const
- std::add_const
- type_traits/std::add_const
dev_langs:
- C++
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
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
ms.openlocfilehash: cb3ac9b9a7d25d129e1faa1b98cac176153c3966
ms.lasthandoff: 02/24/2017

---
# <a name="addconst-class"></a>add_const 클래스
형식에서 const 형식을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
struct add_const;
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
 `Ty`가 참조, 함수 또는 const 한정 형식인 경우 형식 한정자 인스턴스는 수정된 형식인 `Ty`이고, 그렇지 않은 경우 `const Ty`입니다.  
  
## <a name="example"></a>예제  
  
```cpp  
// std__type_traits__add_const.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_const<int>::type *p = (const int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_const<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_const<int> == int  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_const 클래스](../standard-library/remove-const-class.md)

