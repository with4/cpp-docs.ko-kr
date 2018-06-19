---
title: '&lt;functional&gt; 함수 | Microsoft 문서'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bind
- xfunctional/std::bind1st
- xfunctional/std::bind2nd
- xfunctional/std::bit_and
- xfunctional/std::bit_not
- xfunctional/std::bit_or
- xfunctional/std::bit_xor
- functional/std::cref
- type_traits/std::cref
- xfunctional/std::mem_fn
- xfunctional/std::mem_fun_ref
- xfunctional/std::not1
- xfunctional/std::not2
- xfunctional/std::ptr_fun
- functional/std::ref
- functional/std::swap
dev_langs:
- C++
helpviewer_keywords:
- std::bind [C++]
- std::bind1st
- std::bind2nd
- std::bit_and [C++]
- std::bit_not [C++]
- std::bit_or [C++]
- std::bit_xor [C++]
- std::cref [C++]
ms.assetid: c34d0b45-50a7-447a-9368-2210d06339a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b14e656d77247984ba3306d6efff78e6cca713cb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33848377"
---
# <a name="ltfunctionalgt-functions"></a>&lt;functional&gt; 함수

||||
|-|-|-|
|[bind](#bind)|[bind1st](#bind1st)|[bind2nd](#bind2nd)|
|[bit_and](#bit_and)|[bit_not](#bit_not)|[bit_or](#bit_or)|
|[bit_xor](#bit_xor)|[cref](#cref)|[mem_fn](#mem_fn)|
|[mem_fun](#mem_fun)|[mem_fun_ref](#mem_fun_ref)|[not1](#not1)|
|[not2](#not2)|[ptr_fun](#ptr_fun)|[ref](#ref)|
|[swap](#swap)|

## <a name="bind"></a>  bind

호출 가능 개체에 인수를 바인딩합니다.

```cpp
template <class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);

template <class Ret, class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);
```

### <a name="parameters"></a>매개 변수

`Fty` 호출할 개체의 형식입니다.

`TN` N 번째 형식 인수를 호출 합니다.

`fn` 호출 하는 개체입니다.

`tN` N 번째 호출 인수입니다.

### <a name="remarks"></a>설명

`Fty, T1, T2, ..., TN` 형식은 복사를 통해 생성할 수 있어야 하고 `INVOKE(fn, t1, ..., tN)`은 일부 값 `w1, w2, ..., wN`에 대한 유효한 식이어야 합니다.

첫 번째 템플릿 함수는 약한 결과 형식이 포함된 전달 호출 래퍼 `g`를 반환합니다. 효과 `g(u1, u2, ..., uM)` 은 `INVOKE(f, v1, v2, ..., vN, ` [result_of](../standard-library/result-of-class.md)`<Fty cv (V1, V2, ..., VN)>::type)`여기서 `cv` 의 cv 한정자는 `g` 바인딩된 인수 형식 및 값 `v1, v2, ..., vN` 으로 결정 아래에 지정 된 합니다. 이를 사용하여 인수를 호출 가능 개체에 바인딩하면 맞춤형 인수 목록이 포함된 호출 가능 개체가 생성됩니다.

두 번째 템플릿 함수는 `Ret`의 동의어인 중첩된 형식 `result_type`이 포함된 전달 호출 래퍼 `g`를 반환합니다. `g(u1, u2, ..., uM)`의 결과는 `INVOKE(f, v1, v2, ..., vN, Ret)`입니다. 여기서 `cv`는 `g`의 cv 한정자이고 바인딩된 인수 `v1, v2, ..., vN`의 값과 형식은 아래 지정된 대로 결정됩니다. 이를 사용하여 인수를 호출 가능 개체에 바인딩하면 맞춤형 인수 목록 및 지정된 반환 형식이 포함된 호출 가능 개체가 생성됩니다.

바인딩된 인수 `v1, v2, ..., vN` 및 해당 형식 `V1, V2, ..., VN`의 값은 다음과 같이 `bind` 호출 시 `Ti` 형식에 대한 해당 인수 `ti`의 형식 및 호출 래퍼 `g`의 cv 한정자 `cv`에 따라 결정됩니다.

`ti`가 `reference_wrapper<T>` 형식인 경우 `vi` 인수의 값은 `ti.get()`이고 해당 형식 `Vi`의 값은 `T&`입니다.

`std::is_bind_expression<Ti>::value` 값이 `true`인 경우 `vi` 인수의 값은 `ti(u1, u2, ..., uM)`이고 해당 형식 `Vi`의 값은 `result_of<Ti` `cv` `(U1&, U2&, ..., UN&>::type`입니다.

`std::is_placeholder<Ti>::value`의 `j` 값이 0이 아닌 경우 `vi` 인수의 값은 `uj`이고 해당 형식 `Vi`의 값은 `Uj&`입니다.

이외의 경우에는 `vi` 인수의 값은 `ti`이고 해당 형식 `Vi`의 값은 `Ti` `cv` `&`입니다.

예를 들어 `f(int, int)` 함수의 경우 `bind(f, _1, 0)` 식은 전달 호출 래퍼 `cw`를 반환하므로 `cw(x)`가 `f(x, 0)`을 호출합니다. `bind(f, 0, _1)` 식은 전달 호출 래퍼 `cw`를 반환하므로 `cw(x)`가 `f(0, x)`를 반환합니다.

`fn` 인수 이외에 `bind` 호출의 인수 개수는 호출 가능 개체 `fn`에 전달할 수 있는 인수 개수와 같아야 합니다. 따라서 `bind(cos, 1.0)`은 올바른 값이고 `bind(cos)` 및 `bind(cos, _1, 0.0)`은 둘 다 잘못된 값입니다.

`bind`에서 반환된 호출 래퍼에 대한 함수 호출의 인수 개수는 `bind` 호출의 모든 자리 표시자 인수에 대한 `is_placeholder<PH>::value`의 번호가 가장 높은 값보다 크거나 같아야 합니다. 따라서 `bind(cos, _2)(0.0, 1.0)`은 올바른 값이고 `cos(1.0)`을 반환하며, `bind(cos, _2)(0.0)`은 잘못된 값입니다.

### <a name="example"></a>예제

```cpp
// std__functional__bind.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

void product(double x, double y)
{
    std::cout << x << "*" << y << " == " << x * y << std::endl;
}

int main()
{
    double arg[] = { 1, 2, 3 };

    std::for_each(&arg[0], arg + 3, square);
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(square, _1));

    return (0);
}

```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="bind1st"></a>  bind1st

이항 함수의 첫 번째 인수를 지정된 값에 바인딩하여 이항 함수 개체를 단항 함수 개체로 변환하는 어댑터를 만드는 도우미 템플릿 함수입니다.

```cpp
template <class Operation, class Type>
binder1st <Operation> bind1st (const Operation& func, const Type& left);
```

### <a name="parameters"></a>매개 변수

`func` 이항 함수 개체를 단항 함수 개체로 변환할 수입니다.

`left` 이진 함수 개체의 첫 번째 인수를 바인딩할 수 값입니다.

### <a name="return-value"></a>반환 값

이진 함수 개체의 첫 번째 인수는 값에 바인딩할 결과인 단항 함수 개체로 `left`합니다.

### <a name="remarks"></a>설명

함수 바인더는 일종의 함수 어댑터이고, 함수 개체를 반환할 경우 특정 형식의 함수 컴퍼지션에서 더 복잡하고 강력한 식을 생성하는 데 사용될 수 있습니다.

`func`가 `Operation` 형식 개체이고 `c`가 상수이면 `bind1st`(`func`, `c`)는 [binder1st](../standard-library/binder1st-class.md) 클래스 생성자 `binder1st`< `Operation`>(`func`, `c`)과 동일하고 더 편리합니다.

### <a name="example"></a>예제

```cpp
// functional_bind1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan5: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 5);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind1st(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare: counting the number of integers > 5 in the vector
    // with a user defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan5());
    cout << "The number of elements in v1 greater than 5 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind2nd(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 5 is: 4.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bind2nd"></a>  bind2nd

이항 함수의 두 번째 인수를 지정된 값에 바인딩하여 이항 함수 개체를 단항 함수 개체로 변환하는 어댑터를 만드는 도우미 템플릿 함수입니다.

```cpp
template <class Operation, class Type>
binder2nd <Operation> bind2nd(const Operation& func, const Type& right);
```

### <a name="parameters"></a>매개 변수

`func` 이항 함수 개체를 단항 함수 개체로 변환할 수입니다.

`right` 이항 함수 개체의 두 번째 인수를 바인딩할 수 값입니다.

### <a name="return-value"></a>반환 값

이항 함수 개체의 두 번째 인수는 값에 바인딩할 결과인 단항 함수 개체로 `right`합니다.

### <a name="remarks"></a>설명

함수 바인더는 일종의 함수 어댑터이고, 함수 개체를 반환할 경우 특정 형식의 함수 컴퍼지션에서 더 복잡하고 강력한 식을 생성하는 데 사용될 수 있습니다.

`func`가 **Operation** 형식 개체이고 `c`가 상수이면 `bind2nd`(`func`, `c`)는 [binder2nd](../standard-library/binder2nd-class.md) 클래스 생성자 **binder2nd\<Operation>**(`func`, `c`)과 동일하고 더 편리합니다.

### <a name="example"></a>예제

```cpp
// functional_bind2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan15: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 15);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare counting the number of integers > 15 in the vector
    // with a user-defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan15());
    cout << "The number of elements in v1 greater than 15 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind1st(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 15 is: 2.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bit_and"></a>  bit_and

인수에 대해 비트 AND 연산(이항 `operator&`)을 수행하는 사전 정의된 함수 개체입니다.

```cpp
template <class Type = void>
struct bit_and : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator&
template <>
struct bit_and<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const  ->
        decltype(std::forward<T>(Left) & std::forward<U>(Right));
};
```

### <a name="parameters"></a>매개 변수

`Type``T`, `U` 지 원하는 모든 형식은 `operator&` 지정 되었거나 유추 된 형식의 피연산자를 사용 하는 합니다.

`Left` 비트 AND 연산의 왼쪽된 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `T`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

`Right` 비트 AND 연산의 오른쪽 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `U`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

### <a name="return-value"></a>반환 값

`Left & Right`의 결과입니다. 특수화된 템플릿은 `operator&`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

### <a name="remarks"></a>설명

`bit_and` 함수는 기본 데이터 형식에 대한 필수 형식이나 이항 `operator&`를 구현하는 사용자 정의 형식으로 제한됩니다.

## <a name="bit_not"></a>  bit_not

인수에 대해 비트 보수(NOT) 연산(이항 `operator~`)을 수행하는 사전 정의된 함수 개체입니다.

```cpp
template <class Type = void>
struct bit_not : public unary_function<Type, Type>
 {
    Type operator()(const Type& Right) const;
 };

// specialized transparent functor for operator~
template <>
struct bit_not<void>
 {
    template <class Type>
    auto operator()(Type&& Right) const  ->  decltype(~std::forward<Type>(Right));
 };
```

### <a name="parameters"></a>매개 변수

`Type` 지 원하는 단항 형식 `operator~`합니다.

`Right` 비트 보수 연산 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `Type`의 lvalue 또는 rvalue 참조 인수를 완벽하게 전달합니다.

### <a name="return-value"></a>반환 값

`~ Right`의 결과입니다. 특수화된 템플릿은 `operator~`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

### <a name="remarks"></a>설명

`bit_not` 함수는 기본 데이터 형식에 대한 필수 형식이나 이항 `operator~`를 구현하는 사용자 정의 형식으로 제한됩니다.

## <a name="bit_or"></a>  bit_or

인수에 대해 비트 OR 연산(`operator|`)을 수행하는 사전 정의된 함수 개체입니다.

```cpp
template <class Type = void>
struct bit_or : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator|
template <>
struct bit_or<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        ->  decltype(std::forward<T>(Left) | std::forward<U>(Right));
};
```

### <a name="parameters"></a>매개 변수

`Type``T`, `U` 지 원하는 모든 형식은 `operator|` 지정 되었거나 유추 된 형식의 피연산자를 사용 하는 합니다.

`Left` 비트 OR 연산의 왼쪽된 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `T`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

`Right` 비트 OR 연산의 오른쪽 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `U`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

### <a name="return-value"></a>반환 값

`Left | Right`의 결과입니다. 특수화된 템플릿은 `operator|`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

### <a name="remarks"></a>설명

`bit_or` 함수는 기본 데이터 형식에 대한 필수 형식이나 `operator|`를 구현하는 사용자 정의 형식으로 제한됩니다.

## <a name="bit_xor"></a>  bit_xor

인수에 대해 비트 XOR 연산(이항 `operator^`)을 수행하는 사전 정의된 함수 개체입니다.

```cpp
template <class Type = void>
struct bit_xor : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator^
template <>
struct bit_xor<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) ^ std::forward<U>(Right));
};
```

### <a name="parameters"></a>매개 변수

`Type``T`, `U` 지 원하는 모든 형식은 `operator^` 지정 되었거나 유추 된 형식의 피연산자를 사용 하는 합니다.

`Left` 비트 배타적 or 연산의 왼쪽된 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `T`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

`Right` 비트 배타적 or 연산의 오른쪽 피연산자입니다. 특수화되지 않은 템플릿은 `Type` 형식의 lvalue 참조 인수를 사용합니다. 특수화된 템플릿은 유추 형식 `U`의 lvalue 및 rvalue 참조 인수를 완벽하게 전달합니다.

### <a name="return-value"></a>반환 값

`Left ^ Right`의 결과입니다. 특수화된 템플릿은 `operator^`에 의해 반환되는 형식을 가지고 있는 결과를 완벽하게 전달합니다.

### <a name="remarks"></a>설명

`bit_xor` 함수는 기본 데이터 형식에 대한 필수 형식이나 이항 `operator^`를 구현하는 사용자 정의 형식으로 제한됩니다.

## <a name="cref"></a>  cref

인수에서 const `reference_wrapper`를 생성합니다.

```cpp
template <class Ty>
reference_wrapper<const Ty> cref(const Ty& arg);

template <class Ty>
reference_wrapper<const Ty> cref(const reference_wrapper<Ty>& arg);
```

### <a name="parameters"></a>매개 변수

`Ty` 래핑할 인수 형식입니다.

`arg` 래핑할 인수입니다.

### <a name="remarks"></a>설명

첫 번째 함수는 `reference_wrapper<const Ty>(arg.get())`를 반환합니다. 이를 사용하여 상수 참조를 래핑합니다. 두 번째 함수는 `reference_wrapper<const Ty>(arg)`를 반환합니다. 이 함수를 사용하여 래핑된 참조를 상수 참조로 다시 래핑합니다.

### <a name="example"></a>예제

```cpp
// std__functional__cref.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    int i = 1;

    std::cout << "i = " << i << std::endl;
    std::cout << "cref(i) = " << std::cref(i) << std::endl;
    std::cout << "cref(neg)(i) = "
        << std::cref(&neg)(i) << std::endl;

    return (0);
    }

```

```Output
i = 1
cref(i) = 1
cref(neg)(i) = -1
```

## <a name="mem_fn"></a>  mem_fn

단순 호출 래퍼를 생성합니다.

```cpp
template <class Ret, class Ty>
unspecified mem_fn(Ret Ty::*pm);
```

### <a name="parameters"></a>매개 변수

`Ret` 래핑된 함수의 반환 형식입니다.

`Ty` 멤버 함수 포인터의 형식입니다.

### <a name="remarks"></a>설명

템플릿 함수는 약한 결과 형식이 포함된 단순 호출 래퍼 `cw`를 반환하므로 `cw(t, a2, ..., aN)` 식은 `INVOKE(pm, t, a2, ..., aN)`과 같습니다. 이 함수는 예외를 throw하지 않습니다.

`Ty` 형식이 인수를 사용하지 않는 cv 한정자 `cv`가 포함된 멤버 함수 포인터인 경우에만 반환된 호출 래퍼가 `std::unary_function<cv Ty*, Ret>`에서 파생됩니다. 나중에 이 호출 래퍼는 중첩된 형식 `result_type`을 `Ret`의 동의어로, 중첩된 형식 `argument_type`을 `cv Ty*`의 동의어로 정의합니다.

`Ty` 형식이 `T2` 형식의 인수 하나를 사용하는 cv 한정자 `cv`가 포함된 멤버 함수 포인터인 경우에만 반환된 호출 래퍼가 `std::binary_function<cv Ty*, T2, Ret>`에서 파생됩니다. 나중에 이 호출 래퍼는 중첩된 형식 `result_type`을 `Ret`의 동의어로, 중첩된 형식 `first argument_type`을 `cv Ty*`의 동의어로, 중첩된 형식 `second argument_type`을 `T2`의 동의어로 정의합니다.

### <a name="example"></a>예제

```cpp
// std__functional__mem_fn.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

class Funs
    {
public:
    void square(double x)
        {
        std::cout << x << "^2 == " << x * x << std::endl;
        }

    void product(double x, double y)
        {
        std::cout << x << "*" << y << " == " << x * y << std::endl;
        }
    };

int main()
    {
    Funs funs;

    std::mem_fn(&Funs::square)(funs, 3.0);
    std::mem_fn(&Funs::product)(funs, 3.0, 2.0);

    return (0);
    }

```

```Output
3^2 == 9
3*2 == 6
```

## <a name="mem_fun"></a>  mem_fun

포인터 인수를 사용하여 초기화할 때 멤버 함수에 대한 함수 개체 어댑터를 생성하는 데 사용되는 도우미 템플릿 함수입니다.

```cpp
template <class Result, class Type>
mem_fun_t<Result, Type> mem_fun (Result(Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_t<Result, Type> mem_fun(Result (Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg) const);
```

### <a name="parameters"></a>매개 변수

`pmem` 클래스의 멤버 함수에 대 한 포인터 **형식** 함수 개체를 변환할 수 있습니다.

### <a name="return-value"></a>반환 값

`mem_fun_t` 또는 `mem_fun1_t` 형식의 **const** 또는 **non_const** 함수 개체입니다.

### <a name="example"></a>예제

```cpp
// functional_mem_fun.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class StoreVals
{
    int val;
public:
    StoreVals() { val = 0; }
    StoreVals(int j) { val = j; }

    bool display() { cout << val << " "; return true; }
    int squareval() { val *= val; return val; }
    int lessconst(int k) {val -= k; return val; }
};

int main( )
{
    vector<StoreVals *> v1;

    StoreVals sv1(5);
    v1.push_back(&sv1);
    StoreVals sv2(10);
    v1.push_back(&sv2);
    StoreVals sv3(15);
    v1.push_back(&sv3);
    StoreVals sv4(20);
    v1.push_back(&sv4);
    StoreVals sv5(25);
    v1.push_back(&sv5);

    cout << "The original values stored are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun calling member function through a pointer
    // square each value in the vector using squareval ()
    for_each(v1.begin(), v1.end(), mem_fun<int, StoreVals>(&StoreVals::squareval));
    cout << "The squared values are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun1 calling member function through a pointer
    // subtract 5 from each value in the vector using lessconst ()
    for_each(v1.begin(), v1.end(),
        bind2nd (mem_fun1<int, StoreVals,int>(&StoreVals::lessconst), 5));
    cout << "The squared values less 5 are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;
}
```

## <a name="mem_fun_ref"></a>  mem_fun_ref

참조 인수를 사용하여 초기화할 때 멤버 함수에 대한 함수 개체 어댑터를 생성하는 데 사용되는 도우미 템플릿 함수입니다.

```cpp
template <class Result, class Type>
mem_fun_ref_t<Result, Type> mem_fun_ref(Result (Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_ref_t<Result, Type> mem_fun_ref(Result Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (T::* pmem)(Arg) const);
```

### <a name="parameters"></a>매개 변수

`pmem` 클래스의 멤버 함수에 대 한 포인터 `Type` 함수 개체를 변환할 수 있습니다.

### <a name="return-value"></a>반환 값

`mem_fun_ref_t` 또는 `mem_fun1_ref_t` 형식의 `const` 또는 `non_const` 함수 개체입니다.

### <a name="example"></a>예제

```cpp
// functional_mem_fun_ref.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class NumVals
   {
   int val;
   public:
   NumVals ( ) { val = 0; }
   NumVals ( int j ) { val = j; }

   bool display ( ) { cout << val << " "; return true; }
   bool isEven ( ) { return ( bool )  !( val %2 ); }
   bool isPrime( )
   {
      if (val < 2) { return true; }
      for (int i = 2; i <= val / i; ++i)
      {
         if (val % i == 0) { return false; }
      }
      return true;
   }
};

int main( )
{
   vector <NumVals> v1 ( 13 ), v2 ( 13 );
   vector <NumVals>::iterator v1_Iter, v2_Iter;
   int i, k;

   for ( i = 0; i < 13; i++ ) v1 [ i ] = NumVals ( i+1 );
   for ( k = 0; k < 13; k++ ) v2 [ k ] = NumVals ( k+1 );

   cout << "The original values stored in v1 are: " ;
   for_each( v1.begin( ), v1.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the primes in the vector using isPrime ( )
   v1_Iter = remove_if ( v1.begin( ),  v1.end( ),
      mem_fun_ref ( &NumVals::isPrime ) );
   cout << "With the primes removed, the remaining values in v1 are: " ;
   for_each( v1.begin( ), v1_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   cout << "The original values stored in v2 are: " ;
   for_each( v2.begin( ), v2.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the even numbers in the vector v2 using isEven ( )
   v2_Iter = remove_if ( v2.begin( ),  v2.end( ),
      mem_fun_ref ( &NumVals::isEven ) );
   cout << "With the even numbers removed, the remaining values are: " ;
   for_each( v2.begin( ),  v2_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;
}
```

```Output
The original values stored in v1 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the primes removed, the remaining values in v1 are: 4 6 8 9 10 12
The original values stored in v2 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the even numbers removed, the remaining values are: 1 3 5 7 9 11 13
```

## <a name="not1"></a>  not1

단항 조건자의 보수를 반환합니다.

```cpp
template <class UnaryPredicate>
unary_negate<UnaryPredicate> not1(const UnaryPredicate& pred);
```

### <a name="parameters"></a>매개 변수

`pred` 무효화 하는 단항 조건자입니다.

### <a name="return-value"></a>반환 값

수정된 단항 조건자의 부정을 나타내는 단항 조건자입니다.

### <a name="remarks"></a>설명

`unary_negate`가 단항 조건자 **Pred**(*x*)에서 생성된 경우 이 함수는 **!Pred**(*x*)를 반환합니다.

### <a name="example"></a>예제

```cpp
// functional_not1.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```

## <a name="not2"></a>  not2

이항 조건자의 보수를 반환합니다.

```cpp
template <class BinaryPredicate>
binary_negate<BinaryPredicate> not2(const BinaryPredicate& func);
```

### <a name="parameters"></a>매개 변수

`func` 무효화 하는 이진 조건자입니다.

### <a name="return-value"></a>반환 값

수정된 이항 조건자의 부정을 나타내는 이항 조건자입니다.

### <a name="remarks"></a>설명

`binary_negate`가 이항 조건자 **BinPred**(*x*, *y*)에서 생성된 경우 이 함수는 ! **BinPred**(*x*, *y*)를 반환합니다.

### <a name="example"></a>예제

```cpp
// functional_not2.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate helper function not2
   sort( v1.begin( ), v1.end( ), not2(less<int>( ) ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )
```

## <a name="ptr_fun"></a>  ptr_fun

단항 및 이항 함수 포인터를 각각 조정 가능한 단항 및 이항 함수로 변환하는 데 사용되는 도우미 템플릿 함수입니다.

```cpp
template <class Arg, class Result>
pointer_to_unary_function<Arg, Result, Result (*)(Arg)> ptr_fun(Result (*pfunc)(Arg));

template <class Arg1, class Arg2, class Result>
pointer_to_binary_function<Arg1, Arg2, Result, Result (*)(Arg1, Arg2)> ptr_fun(Result (*pfunc)(Arg1, Arg2));
```

### <a name="parameters"></a>매개 변수

`pfunc` 단항 또는 이항 함수 포인터를 조정 가능한 함수를 변환할 수 있습니다.

### <a name="return-value"></a>반환 값

첫 번째 템플릿 함수는 단항 함수 [pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md) < `Arg`, **Result**>(* `pfunc`)를 반환합니다.

두 번째 템플릿 함수는 이항 함수 [pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md) \< **Arg1**, **Arg2**, **Result**>(* `pfunc`)를 반환합니다.

### <a name="remarks"></a>설명

함수 포인터는 함수 개체이고 함수를 매개 변수로 사용할 C++ 표준 라이브러리 알고리즘에 전달될 수 있지만 조정할 수는 없습니다. 함수 포인터를 어댑터와 함께 사용하려면(예: 값을 함수 포인터에 바인딩 또는 함수 포인터를 부정자와 함께 사용) 적응을 가능하게 하는 중첩된 형식을 함수 포인터에 제공해야 합니다. `ptr_fun` 도우미 함수를 통해 단항 및 이행 함수 포인터를 변환하면 함수 어댑터를 단항 및 이행 함수 포인터와 함께 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[functional_ptr_fun#1](../standard-library/codesnippet/CPP/functional-functions_1.cpp)]

## <a name="ref"></a>  ref

인수에서 `reference_wrapper` 를 생성합니다.

```cpp
template <class Ty>
reference_wrapper<Ty> ref(Ty& arg);

template <class Ty>
reference_wrapper<Ty> ref(reference_wrapper<Ty>& arg);
```

### <a name="return-value"></a>반환 값

`arg`, 특히 `reference_wrapper<Ty>(arg)`에 대한 참조입니다.

### <a name="example"></a>예제

다음 예제에서는 문자열 변수에 바인딩된 함수 및 `ref`호출에서 계산된 문자열 변수의 참조에 바인딩된 함수의 두 함수를 정의합니다. 변수의 값이 변경될 경우 첫 번째 함수는 이전 값을 계속 사용하고 두 번째 함수는 새 값을 사용합니다.

```cpp
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <ostream>
#include <string>
#include <vector>
using namespace std;
using namespace std;
using namespace std::placeholders;

bool shorter_than(const string& l, const string& r) {
    return l.size() < r.size();
}

int main() {
    vector<string> v_original;
    v_original.push_back("tiger");
    v_original.push_back("cat");
    v_original.push_back("lion");
    v_original.push_back("cougar");

    copy(v_original.begin(), v_original.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    string s("meow");

    function<bool (const string&)> f = bind(shorter_than, _1, s);
    function<bool (const string&)> f_ref = bind(shorter_than, _1, ref(s));

    vector<string> v;

    // Remove elements that are shorter than s ("meow")

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Now change the value of s.
    // f_ref, which is bound to ref(s), will use the
    // new value, while f is still bound to the old value.

    s = "kitty";

    // Remove elements that are shorter than "meow" (f is bound to old value of s)

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Remove elements that are shorter than "kitty" (f_ref is bound to ref(s))

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f_ref), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;
}
```

```Output
tiger cat lion cougar
tiger lion cougar
tiger lion cougar
tiger cougar
```

## <a name="swap"></a>  swap

두 `function` 개체를 교환합니다.

```cpp
template <class Fty>
void swap(function<Fty>& f1, function<Fty>& f2);
```

### <a name="parameters"></a>매개 변수

`Fty` 함수 개체에 의해 제어 되는 형식입니다.

`f1` 첫 번째 함수 개체입니다.

`f2` 두 번째 함수 개체입니다.

### <a name="remarks"></a>설명

함수에서 `f1.swap(f2)`을 반환합니다.

### <a name="example"></a>예제

```cpp
// std__functional__swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    swap(fn0, fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }

```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```

## <a name="see-also"></a>참고자료

[\<functional>](../standard-library/functional.md)<br/>
