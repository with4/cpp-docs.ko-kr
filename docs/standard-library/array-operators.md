---
title: "&lt;array&gt; 연산자 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array/std::array::operator!=
- array/std::array::operator<
- array/std::array::operator<=
- array/std::array::operator>
- array/std::array::operator>=
- array/std::array::operator==
dev_langs: C++
ms.assetid: c8f46282-f179-4909-9a01-639cb8e18c27
caps.latest.revision: "12"
manager: ghogen
ms.openlocfilehash: e4854303bc80603ccbdf908aefc31f304487fb1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="ltarraygt-operators"></a>&lt;array&gt; 연산자
\<array> 헤더는 다음의 `array` 비 멤버 비교 템플릿 함수를 포함합니다.  
  
||||  
|-|-|-|  
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|  
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  operator!=  
 배열 비교, 같지 않음  
  
```  
template <Ty, std::size_t N>  
bool operator!=(
    const array<Ty, N>& left,  
    const array<Ty, N>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
 `left`  
 비교할 왼쪽 컨테이너입니다.  
  
 `right`  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수가 `!(left == right)`을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std__array__operator_ne.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
  
// display contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 != c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 != c1);   
    std::cout << std::endl;   
  
    return (0);   
    }   
```  
  
```Output  
0 1 2 3  
4 5 6 7  
false  
true  
```  
  
##  <a name="op_lt"></a>  operator&lt;  
 배열 비교, 보다 작음  
  
```  
template <Ty, std::size_t N>  
bool operator<(
    const array<Ty, N>& left,  
    const array<Ty, N>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
 `left`  
 비교할 왼쪽 컨테이너입니다.  
  
 `right`  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 [array 클래스](../standard-library/array-class-stl.md) 템플릿 클래스의 두 개체를 비교하기 위한 템플릿 함수 오버로드 `operator<`입니다. 함수에서 `lexicographical_compare(left.begin(), left.end(), right.begin())`을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std__array__operator_lt.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
  
// display contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 < c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 < c1);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
false  
true  
```  
  
##  <a name="op_lt_eq"></a>  operator&lt;=  
 배열 비교, 보다 작거나 같음  
  
```  
template <Ty, std::size_t N>  
bool operator<=(
    const array<Ty, N>& left,  
    const array<Ty, N>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
 `left`  
 비교할 왼쪽 컨테이너입니다.  
  
 `right`  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수가 `!(right < left)`을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std__array__operator_le.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
  
// display contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 <= c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c1 <= c0);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
true  
false  
```  
  
##  <a name="op_eq_eq"></a>  operator==  
 배열 비교, 같음  
  
```  
template <Ty, std::size_t N>  
bool operator==(
    const array<Ty, N>& left,  
    const array<Ty, N>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
 `left`  
 비교할 왼쪽 컨테이너입니다.  
  
 `right`  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 [array 클래스](../standard-library/array-class-stl.md) 템플릿 클래스의 두 개체를 비교하기 위한 템플릿 함수 오버로드 `operator==`입니다. 함수에서 `equal(left.begin(), left.end(), right.begin())`을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std__array__operator_eq.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
  
// display contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 == c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 == c1);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
true  
false  
```  
  
##  <a name="op_gt"></a>  operator&gt;  
 배열 비교, 보다 큼  
  
```  
template <Ty, std::size_t N>  
bool operator>(
    const array<Ty, N>& left,  
    const array<Ty, N>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
 `left`  
 비교할 왼쪽 컨테이너입니다.  
  
 `right`  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수가 `(right < left)`을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std__array__operator_gt.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
  
// display contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 > c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c1 > c0);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
false  
true  
```  
  
##  <a name="op_gt_eq"></a>  operator&gt;=  
 배열 비교, 보다 크거나 같음  
  
```  
template <Ty, std::size_t N>  
bool operator>=(
    const array<Ty, N>& left,  
    const array<Ty, N>& right);
```  
  
### <a name="parameters"></a>매개 변수  
 `Ty`  
 요소의 형식입니다.  
  
 `N`  
 배열의 크기입니다.  
  
 `left`  
 비교할 왼쪽 컨테이너입니다.  
  
 `right`  
 비교할 오른쪽 컨테이너입니다.  
  
### <a name="remarks"></a>설명  
 템플릿 함수가 `!(left < right)`을 반환합니다.  
  
### <a name="example"></a>예제  
  
```cpp  
// std__array__operator_ge.cpp   
// compile with: /EHsc   
#include <array>   
#include <iostream>   
  
typedef std::array<int, 4> Myarray;   
int main()   
    {   
    Myarray c0 = {0, 1, 2, 3};   
  
// display contents " 0 1 2 3"   
    for (Myarray::const_iterator it = c0.begin();   
        it != c0.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
    Myarray c1 = {4, 5, 6, 7};   
  
// display contents " 4 5 6 7"   
    for (Myarray::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " " << *it;   
    std::cout << std::endl;   
  
// display results of comparisons   
    std::cout << std::boolalpha << " " << (c0 >= c0);   
    std::cout << std::endl;   
    std::cout << std::boolalpha << " " << (c0 >= c1);   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
0 1 2 3  
4 5 6 7  
true  
false  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<array>](../standard-library/array.md)

