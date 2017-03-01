---
title: "remove_extent 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- remove_extent
- std::remove_extent
- type_traits/std::remove_extent
dev_langs:
- C++
helpviewer_keywords:
- remove_extent class
- remove_extent
ms.assetid: b9320862-3891-49fc-80bc-571eb2c035cf
caps.latest.revision: 20
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
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 670e0b97c79fb7d022b2ca5ed08326b31c96e336
ms.lasthandoff: 02/24/2017

---
# <a name="removeextent-class"></a>remove_extent 클래스
배열 형식에서 요소 형식을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class T>  
struct remove_extent;  
 
template <class T>  
using remove_extent_t = typename remove_extent<T>::type;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
 `remove_extent<T>`의 인스턴스는 `T1`가 `T` 형식인 경우 수정된 형식인 `T1[N]`을 보관하고, 그렇지 않은 경우 `T`를 보관합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    std::cout << "remove_extent_t<int> == "  
        << typeid(std::remove_extent_t<int>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5]> == "  
        << typeid(std::remove_extent_t<int[5]>).name()  
        << std::endl;T  
    std::cout << "remove_extent_t<int[5][10]> == "  
        << typeid(std::remove_extent_t<int[5][10]>).name()  
        << std::endl;   
    return (0);   
    }  
```  
  
```Output  
remove_extent_t<int> == int  
remove_extent_t<int[5]> == int  
remove_extent_t<int[5][10]> == int [10]  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_all_extents 클래스](../standard-library/remove-all-extents-class.md)

