---
title: "is_fundamental 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_fundamental
dev_langs: C++
helpviewer_keywords:
- is_fundamental class
- is_fundamental
ms.assetid: b84eee84-2fb2-4611-beaf-b384074d8b6a
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b206144be401990d3646f78611acb18d71862de4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="isfundamental-class"></a>is_fundamental 클래스
형식이 void 또는 산술형인지 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <class Ty>  
struct is_fundamental;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Ty`  
 형식이 쿼리입니다.  
  
## <a name="remarks"></a>설명  
 형식 조건자의 인스턴스는 `Ty` 형식이 `void`, 정수 형식, 부동 소수점 형식 또는 이들 형식 중 하나의 `cv-qualified` 형식이면 true이고, 그렇지 않으면 false입니다.  
  
## <a name="example"></a>예  
  
```cpp  
// std__type_traits__is_fundamental.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
struct trivial   
    {   
    int val;   
    };   
  
int main()   
    {   
    std::cout << "is_fundamental<trivial> == " << std::boolalpha   
        << std::is_fundamental<trivial>::value << std::endl;   
    std::cout << "is_fundamental<int> == " << std::boolalpha   
        << std::is_fundamental<int>::value << std::endl;   
    std::cout << "is_fundamental<const float> == " << std::boolalpha   
        << std::is_fundamental<const float>::value << std::endl;   
    std::cout << "is_fundamental<void> == " << std::boolalpha   
        << std::is_fundamental<void>::value << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
is_fundamental<trivial> == false  
is_fundamental<int> == true  
is_fundamental<const float> == true  
is_fundamental<void> == true  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [is_compound 클래스](../standard-library/is-compound-class.md)
