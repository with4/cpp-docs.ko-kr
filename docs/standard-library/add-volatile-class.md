---
title: "add_volatile 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- add_volatile
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
caps.latest.revision: 21
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
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: c770950bfb69eaee2fde9aca63b0010f5a2da26a
ms.lasthandoff: 02/24/2017

---
# <a name="addvolatile-class"></a>add_volatile 클래스
지정된 형식에서 휘발성 형식을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
struct add_volatile;  
 
template <class T>
using add_volatile_t = typename add_volatile<T>::type;  
```  
  
### <a name="parameters"></a>매개 변수  
*T*  
수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
`add_volatile<T>`의 인스턴스에는 *T*가 참조, 함수 또는 휘발성 한정 형식인 경우 *T*, 아닌 경우 `volatile` *T*인 멤버 typedef `type`이 있습니다. `add_volatile_t` 별칭은 멤버 typedef `type`에 액세스하기 위한 바로 가기입니다. 
  
## <a name="example"></a>예제  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_volatile_t<int> *p = (volatile int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_volatile<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
} 
```  
  
```Output  
add_volatile<int> == int  
```  
  
## <a name="requirements"></a>요구 사항  

**헤더:** \<type_traits>  
  
**네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
[<type_traits>](../standard-library/type-traits.md)   
[remove_volatile 클래스](../standard-library/remove-volatile-class.md)

