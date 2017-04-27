---
title: "remove_const 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- remove_const
- type_traits/std::remove_const
dev_langs:
- C++
helpviewer_keywords:
- remove_const class
- remove_const
ms.assetid: feb76fb3-9228-41d6-80f6-2fbb04daec43
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
ms.openlocfilehash: 39a88c886636c7c79c50771b5d4a91b26be954b4
ms.lasthandoff: 02/24/2017

---
# <a name="removeconst-class"></a>remove_const 클래스
형식에서 비const 형식을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class T>  
struct remove_const;
```  
  
```  
template <class T>  
using remove_const_t = typename remove_const<T>::type;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `T`  
 수정할 형식입니다.  
  
## <a name="remarks"></a>설명  
 `remove_const<T>`의 인스턴스는 `T1`가 `T` 형식인 경우 수정된 형식인 `const T1`을 보관하고, 그렇지 않은 경우 `T`를 보관합니다.  
  
## <a name="example"></a>예제  
  
```cpp  
#include <type_traits>   
#include <iostream>   
  
int main()   
    {   
    int *p = (std::remove_const_t<const int>*)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "remove_const_t<const int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
    }  
```  
  
```Output  
remove_const_t<const int> == int  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_const 클래스](../standard-library/add-const-class.md)   
 [remove_cv 클래스](../standard-library/remove-cv-class.md)

