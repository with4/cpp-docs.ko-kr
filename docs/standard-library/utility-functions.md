---
title: '&lt;utility&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: a26a4a0cab0bdea8a7a642cc760da0f3fc79b471
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="ltutilitygt-functions"></a>&lt;utility&gt; 함수

||||
|-|-|-|
|[exchange](#exchange)|[forward](#forward)|[get 함수 &lt;utility&gt;](#get)|
|[make_pair](#make_pair)|[move](#move)|[swap](#swap)|

## <a name="exchange"></a>  exchange

**(C++14)** 개체에 새 값을 할당하고 이전 값을 반환합니다.

```cpp
template <class T, class Other = T>
T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>매개 변수

`val` New_val의 값을 받을 개체입니다.

`new_val` 값이 복사 되거나 val로 이동 하는 개체입니다.

### <a name="remarks"></a>설명

복합 형식에서 `exchange`는 이동 생성자를 사용할 수 있는 경우 이전 값의 복사를 방지하고, 임시 개체이거나 이동된 경우 새 값의 복사를 방지하며, 사용 가능한 변환 대입 연산자를 통해 모든 형식을 새 값으로 받아들입니다. exchange 함수는 왼쪽 인수가 오른쪽 인수로 이동되거나 복사되지 않는다는 점에서 [std::swap](../standard-library/algorithm-functions.md#swap)과 다릅니다.

### <a name="example"></a>예제

다음 예제에서는 `exchange`을 사용하는 방법을 보여 줍니다. 실제로 `exchange`는 복사하는 데 비용이 많이 드는 큰 개체에서 가장 유용합니다.

```cpp
#include <utility>
#include <iostream>

using namespace std;

struct C
{
   int i;
   //...
};

int main()
{
   // Use brace initialization
   C c1{ 1 };
   C c2{ 2 };
   C result = exchange(c1, c2);
   cout << "The old value of c1 is: " << result.i << endl;
   cout << "The new value of c1 after exchange is: " << c1.i << endl;

   return 0;
}
```

```Output
The old value of c1 is: 1
The new value of c1 after exchange is: 2
```

## <a name="forward"></a>  forward

인수가 rvalue 또는 rvalue 참조인 경우 rvalue 참조에 대한 해당 인수를 조건적으로 캐스팅합니다. 그러면 인수의 rvalue 특성이 전달 함수로 복원되어 완벽하게 전달됩니다.

```cpp
template <class Type>    // accepts lvalues
constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`Type`|`Arg`에 전달된 값 형식(`Arg` 형식과 다를 수 있음)입니다. 일반적으로 전달 함수의 템플릿 인수에 의해 결정됩니다.|
|`Arg`|캐스팅할 인수입니다.|

### <a name="return-value"></a>반환 값

`Arg`에 전달된 값이 원래 rvalue였거나 rvalue에 대한 참조였던 경우 `Arg`에 대한 rvalue를 반환합니다. 그렇지 않으면 해당 형식을 수정하지 않고 `Arg`를 반환합니다.

### <a name="remarks"></a>설명

`forward`를 호출하려면 명시적 템플릿 인수를 지정해야 합니다.

`forward`는 인수를 전달하지 않습니다. 대신 원래 rvalue 또는 rvalue 참조였던 경우 해당 인수를 rvalue 참조에 조건적으로 캐스팅하면 `forward`를 사용하여 컴파일러에서 전달된 인수의 원래 형식을 알고 오버로드 해결을 수행할 수 있습니다. 전달 함수에 대한 인수의 명백한 형식은 원래 형식과 다를 수 있습니다. 예를 들어, rvalue가 함수에 대해 사용되고 매개 변수 이름에 바인딩된 경우, 이름을 지정하면 해당 값이 실제로 rvalue로 존재하는지와 상관없이 lvalue가 됩니다. `forward`는 인수의 rvalue 특성을 복원합니다.

오버로드 해결을 수행하기 위해 인수의 원래 값의 rvalue 특성을 복원하는 것을 *완벽한 전달*이라고 합니다. 완벽한 전달을 사용하면 템플릿 함수에서 참조 형식의 인수를 허용하고 올바른 오버로드 해결을 위해 필요할 때 rvalue 특성을 복원할 수 있습니다. 완벽한 전달을 수행하면 rvalue에 대해 이동 의미 체계를 보존하고 인수의 참조 형식만 다른 함수의 오버로드를 제공하지 않아도 됩니다.

## <a name="get"></a>  get

인덱스 위치 또는 형식을 기준으로 `pair` 개체에서 요소를 가져옵니다.

```cpp
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
constexpr tuple_element_t<Index, pair<T1, T2>>&
get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
constexpr const tuple_element_t<Index, pair<T1, T2>>&
get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
constexpr tuple_element_t<Index, pair<T1, T2>>&&
get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```

### <a name="parameters"></a>매개 변수

`Index` 지정 된 요소의 0 기반 인덱스입니다.

`T1` 첫 번째 pair 요소의 형식입니다.

`T2` 두 번째 pair 요소의 형식입니다.

`pr` 선택할 쌍입니다.

### <a name="remarks"></a>설명

각각의 템플릿 함수는 `pair` 인수의 요소에 대한 참조를 반환합니다.

인덱싱된 오버로드에 대해 `Index` 의 값이 0이면 함수는 `pr.first` 를 반환하고, `Index` 의 값이 1이면 함수는 `pr.second`를 반환합니다. `RI` 형식은 반환된 요소의 형식입니다.

인덱스 매개 변수가 없는 오버로드에서는 반환할 요소가 형식 인수로 추론됩니다. `get<T>(Tuple)` 을 호출할 때 `pr` 에 T 형식의 요소가 두 개 이상 있거나 없는 경우 컴파일러 오류가 생성됩니다.

### <a name="example"></a>예제

```cpp
#include <utility>
#include <iostream>
using namespace std;
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;

    /*
    Output:
    9 3.14
    1 0.27
    */

}
```

## <a name="make_pair"></a>  make_pair

`pair` 형식의 개체를 만드는 데 사용할 수 있는 템플릿 함수. 여기서 구성 요소 형식은 매개 변수로 전달된 데이터 형식을 기준으로 자동 선택됩니다.

```cpp
template <class T, class U>
pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
pair<T, U> make_pair(T&& Val1, U&& Val2);
```

### <a name="parameters"></a>매개 변수

`Val1` 첫 번째 요소로 초기화 하는 값 `pair`합니다.

`Val2` 두 번째 요소를 초기화 하는 값 `pair`합니다.

### <a name="return-value"></a>반환 값

생성된 쌍 개체: `pair`< `T`, `U`>( `Val1`, `Val2`)

### <a name="remarks"></a>설명

`make_pair`는 [reference_wrapper Class](../standard-library/reference-wrapper-class.md) 형식의 개체를 참조 형식으로 변환하고 감소하는 배열 및 함수를 포인터로 변환합니다.

반환된 `pair` 개체에서 `T`은 다음과 같이 결정됩니다.

- 입력 형식 `T`이 `reference_wrapper<X>`인 경우 반환된 형식 `T`은 `X&`입니다.

- 그렇지 않은 경우, 반환된 형식 `T`은 `decay<T>::type`입니다. [decay Class](../standard-library/decay-class.md)가 지원되지 않는 경우 반환된 형식 `T`는 입력 형식 `T`와 동일합니다.

반환된 형식 `U`는 마찬가지로 입력 형식 `U`에서 결정됩니다.

`make_pair`의 장점 하나는 저장되는 개체 형식이 컴파일러에서 자동으로 저장되며 명시적으로 지정하지 않아도 된다는 점입니다. `make_pair<int, int>(1, 2)`를 사용할 경우 불필요하게 장황해지고 컴파일 문제의 원인이 될 수 있는 복잡한 rvalue 참조 문제만 더해지므로 `make_pair` 등의 명시적 템플릿 인수를 사용하지 마십시오. 이 예제에서 올바른 구문은 `make_pair(1, 2)`입니다.

`make_pair` 도우미 함수도 입력 매개 변수로 한 쌍이 필요한 함수에 두 값을 전달할 수 있습니다.

### <a name="example"></a>예제

도우미 함수 `make_pair`를 사용하여 쌍을 선언하고 초기화하는 방법을 알아보려면 [pair 구조체](../standard-library/pair-structure.md)를 참조하세요.

## <a name="move"></a>  move

무조건 인수를 rvalue 참조로 캐스트합니다. 따라서 형식이 이동 가능할 경우 이동 가능하다는 신호를 줍니다.

```cpp
template <class Type>
constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`Type`|참조 축소 규칙과 함께 `Arg`에 전달된 인수의 형식에서 추론된 형식입니다.|
|`Arg`|캐스팅할 인수입니다. `Arg`의 형식이 rvalue 참조로 지정되는 것처럼 보여도 lvalue 참조가 rvalue 참조에 바인딩될 수 있기 때문에 `move`도 lvalue 인수를 수용합니다.|

### <a name="return-value"></a>반환 값

형식과 상관없이, rvalue 참조로서의 `Arg`는 참조 형식입니다.

### <a name="remarks"></a>설명

템플릿 인수 `Type`은 명시적으로 지정하는 것이 아니며, `Arg`에 전달된 값의 형식에서 추론해야 합니다. `Type`의 형식은 참조 축소 규칙에 따라 추가 조정됩니다.

`move`는 인수를 이동하지 않습니다. 대신, lvalue일 수 있는 인수를 무조건 rvalue로 캐스트할 경우 `Arg` 형식에 이동이 활성화되어 있으면 컴파일러가 나중에 해당 형식에 전달된 값을 복사하지 않고 이동합니다. 해당 형식에 이동이 활성화되어 있지 않은 경우에는 대신 복사됩니다.

`Arg`에 전달된 값이 lvalue인 경우, 즉 이름이 있거나 주소를 가져올 수 있는 경우, 이동이 발생하면 무효화됩니다. 이동 이후에는 이름 또는 주소로 `Arg`에 전달된 값을 참조하지 마세요.

## <a name="swap"></a>  swap

두 [pair 구조체](../standard-library/pair-structure.md) 개체의 요소를 교환합니다.

```cpp
template <class T, class U>
void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`left`|`pair` 형식의 개체입니다.|
|`right`|`pair` 형식의 개체입니다.|

### <a name="remarks"></a>설명

`swap`의 장점 하나는 저장되는 개체 형식이 컴파일러에서 자동으로 저장되며 명시적으로 지정하지 않아도 된다는 점입니다. `swap<int, int>(1, 2)`를 사용할 경우 불필요하게 장황해지고 컴파일 문제의 원인이 될 수 있는 복잡한 rvalue 참조 문제만 더해지므로 `swap` 등의 명시적 템플릿 인수를 사용하지 마십시오.

## <a name="see-also"></a>참고자료

[\<utility>](../standard-library/utility.md)<br/>
