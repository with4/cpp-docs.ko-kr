---
title: "tuple_size 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- tuple_size
- std::tuple_size
- utility/std::tuple_size
dev_langs: C++
helpviewer_keywords: std::tuple_size
ms.assetid: 73852fc5-eb68-41f1-8379-465cedc2314a
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ef3d1fae353de8962684b080c223bd4a6a235acf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tuplesize-class"></a>tuple_size 클래스
`tuple` 에 포함된 요소 수를 보관합니다.  
  
## <a name="syntax"></a>구문  
  
```  
// TEMPLATE STRUCT tuple_size  
template <class Tuple>  
   struct tuple_size;  
  
// number of elements in array  
template <class Elem, size_t Size>  
   struct tuple_size<array<Elem, Size>>  
      : integral_constant<size_t, Size>; 
  
// size of pair
template <class T1, class T2>
   struct tuple_size<pair<T1, T2>> 
      : integral_constant<size_t, 2>

// size of tuple  
template <class... Types>  
   struct tuple_size<tuple<Types...>>  
      : integral_constant<size_t, sizeof...(Types)>;  
  
// size of const tuple  
template <class Tuple>  
   struct tuple_size<const Tuple>;  
  
// size of volatile tuple  
template <class Tuple>  
   struct tuple_size<volatile Tuple>;  
  
// size of const volatile tuple  
template <class Tuple>  
   struct tuple_size<const volatile Tuple>;   
```  
  
#### <a name="parameters"></a>매개 변수  
*Tuple*  
튜플의 형식입니다. 
  
*Elem*  
배열 요소의 형식입니다. 
  
*Size*  
배열의 크기입니다. 
  
*T1*  
쌍의 첫 번째 구성원 형식입니다. 
  
*T2*  
쌍의 두 번째 구성원 형식입니다. 
  
*유형*  
튜플 요소의 형식입니다. 
  
  
## <a name="remarks"></a>설명  
템플릿 클래스에는 해당 값이 `value` 형식 튜플의 범위인 내부 상수 식인 `Tuple`멤버가 있습니다.  
  
배열의 템플릿 특수화에는 해당 값이 `value`(배열의 크기)인 정수 계열 상수 식 `Size` 구성원이 있습니다.  
  
쌍의 템플릿 특수화에는 해당 값이 2인 정수 계열 상수 식 `value` 구성원이 있습니다.  
  
## <a name="example"></a>예  
  
```cpp  
#include <tuple>   
#include <iostream>  
  
using namespace std;  
  
typedef tuple<int, double, int, double> MyTuple;  
int main()  
{  
    MyTuple c0(0, 1.5, 2, 3.7);  
  
    // display contents " 0 1 2 3"   
    cout << " " << get<0>(c0);  
    cout << " " << get<1>(c0);  
    cout << " " << get<2>(c0);  
    cout << " " << get<3>(c0) << endl;  
  
    // display size " 4"   
    cout << " " << tuple_size<MyTuple>::value << endl;  
}  
```  
  
```Output  
 0 1.5 2 3.7  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<tuple>  
 **헤더:** \<array>(배열 특수화용)  
 **헤더:** \<utility>(쌍 특수화용)  
  
 **네임스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [\<tuple>](../standard-library/tuple.md)   
 [tuple](../standard-library/tuple-class.md)  
 [tuple_element 클래스](../standard-library/tuple-element-class-tuple.md)
