---
title: "aligned_union 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- aligned_union
- std.aligned_union
- std::aligned_union
- type_traits/std::aligned_union
dev_langs:
- C++
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 10
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
ms.openlocfilehash: d6ecefd7d6877bc65bbf6f5542ae6b7f318a9d27
ms.lasthandoff: 02/24/2017

---
# <a name="alignedunion-class"></a>aligned_union 클래스
공용 구조체 형식 및 필요한 크기를 저장할 수 있도록 적절하게 맞춰지고 충분히 큰 POD 형식을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <std::size_t Len, class... Types>  
struct aligned_union;  
 
template <std::size_t Len, class... Types>  
using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `Len`  
 공용 구조체에서 가장 큰 형식의 맞춤 값입니다.  
  
 `Types`  
 기본 공용 구조체의 고유 형식입니다.  
  
## <a name="remarks"></a>설명  
 초기화되지 않은 저장소에 공용 구조체를 저장하기 위해 필요한 맞춤과 크기를 가져오기 위해 템플릿 클래스를 사용합니다. 멤버 typedef `type`은 `Types`에 나열된 형식의 저장소에 적합한 POD 유형의 이름을 지정합니다. 최소 크기는 `Len`입니다. 형식 `std::size_t`의 정적 멤버 `alignment_value`는 `Types`에 나열된 모든 형식에 필요한 가장 엄격한 맞춤을 포함합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `aligned_union`을 사용하여 공용 구조체 배치를 위한 맞춤화된 스택 버퍼를 할당하는 방법을 보여줍니다.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
value of u->i is 1065353216  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<type_traits>  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [<type_traits>](../standard-library/type-traits.md)   
 [alignment_of 클래스](../standard-library/alignment-of-class.md)

