---
title: "&lt;array&gt; 함수 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::array::get
- array/std::array::get
ms.assetid: e0700a33-a833-4655-8735-16e71175efc8
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 38c1f1a593c43ff0fb8434bfcade4dab9740945d
ms.lasthandoff: 02/24/2017

---
# <a name="ltarraygt-functions"></a>&lt;array&gt; 함수
\<array> 헤더에는 `array` 개체에서 작동하는 두 개의 비 멤버 함수인 `get` 및 `swap`이 포함되어 있습니다.  
  
|||  
|-|-|  
|[get](#get_function)|[swap](#swap_function)|  
  
##  <a name="a-namegetfunctiona--get"></a><a name="get_function"></a>  get  
배열의 지정된 요소에 대한 참조를 반환합니다.  
  
```  
template <int Index, class T, size_t N>  
constexpr T& get(array<T, N>& arr) noexcept;  
 
template <int Index, class T, size_t N>  
constexpr const T& get(const array<T, N>& arr) noexcept;  
 
template <int Index, class T, size_t N>  
constexpr T&& get(array<T, N>&& arr) noexcept;  
```  
  
### <a name="parameters"></a>매개 변수  
 `Index`  
 요소 오프셋입니다.  
  
 `T`  
 요소의 형식입니다.  
  
 `N`  
 배열의 요소 수입니다.  
  
 `arr`  
 선택할 배열입니다.  
  
### <a name="example"></a>예제  
  
```cpp  
#include <array>   
#include <iostream>   
  
using namespace std;  
  
typedef array<int, 4> MyArray;  
  
int main()  
{  
    MyArray c0 { 0, 1, 2, 3 };  
  
    // display contents " 0 1 2 3"   
    for (const auto& e : c0)  
    {  
        cout << " " << e;  
    }  
    cout << endl;  
  
    // display odd elements " 1 3"   
    cout << " " << get<1>(c0);  
    cout << " " << get<3>(c0) << endl;  
}  
```  
  
```Output  
0 1 2 3  
1 3  
```  
  
##  <a name="a-nameswapfunctiona--swap"></a><a name="swap_function"></a>  swap  
두 개의 `array` 개체를 교환하는 `std::swap`의 비 멤버 템플릿 특수화입니다.  
  
```  
template <class Ty, std::size_t N>  
void swap(array<Ty, N>& left, array<Ty, N>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
 `left`  
 교환할 첫 번째 배열입니다.  
  
 `right`  
 교환할 두 번째 배열입니다.  
  
### <a name="remarks"></a>설명  
 이 템플릿 함수는 `left.swap(right)`를 실행합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std__array__swap.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;
int main()
{
    Myarray c0 = { 0, 1, 2, 3 };

    // display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    Myarray c1 = { 4, 5, 6, 7 };
    c0.swap(c1);

    // display swapped contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    swap(c0, c1);

    // display swapped contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();
        it != c0.end(); ++it)
        std::cout << " " << *it;
    std::cout << std::endl;

    return (0);
}
```  
  
```Output  
0 1 2 3  
4 5 6 7  
0 1 2 3  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<array>](../standard-library/array.md)


