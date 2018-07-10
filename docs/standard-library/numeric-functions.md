---
title: '&lt;numeric&gt; 함수 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- numeric/std::accumulate
- numeric/std::adjacent_difference
- numeric/std::inner_product
- numeric/std::iota
- numeric/std::partial_sum
ms.assetid: a4b0449a-c80c-4a1d-8d9f-d7fcd0058f8b
helpviewer_keywords:
- std::accumulate [C++]
- std::adjacent_difference [C++]
- std::inner_product [C++]
- std::iota [C++]
- std::partial_sum [C++]
ms.openlocfilehash: d5504ed83ce41f38dc69f3fb612438800285d905
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33862584"
---
# <a name="ltnumericgt-functions"></a>&lt;numeric&gt; 함수

||||
|-|-|-|
|[accumulate](#accumulate)|[adjacent_difference](#adjacent_difference)|[inner_product](#inner_product)|
|[iota](#iota)|[partial_sum](#partial_sum)|

## <a name="accumulate"></a>  accumulate

연속적 부분 합계를 계산하여 일부 초기값을 비롯한 지정된 범위 내 모든 요소의 합계를 계산하거나, 합계 대신 지정된 이진 연산을 사용하여 유사하게 구한 연속적 부분 결과의 결과를 계산합니다.

```cpp
template <class InputIterator, class Type>
Type accumulate(InputIterator first, InputIterator last, Type val);

template <class InputIterator, class Type, class BinaryOperation>
Type accumulate(
    InputIterator first,
    InputIterator last,
    Type val,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

`first` 입력된 반복기 범위에서 첫 번째 요소를 주소 지정 합계 또는 지정된 된 이항 연산을 따라 결합 합니다.

`last` 입력된 반복기 범위에서 마지막 요소를 주소 지정 합계 또는 반복된 된 누적에 실제로 포함 된 마지막 요소 하나 다음 위치의 지정된 된 이항 연산을 따라 결합 합니다.

`val` 초기 값을 각 요소를 다시 추가 하거나 지정된 된 이항 연산을 따라와 결합 합니다.

`binary_op` 이항 연산 지정된 된 범위와 이전 응용 프로그램 결과의 각 요소에 적용 하는 것입니다.

### <a name="return-value"></a>반환 값

첫 번째 템플릿 함수의 경우 지정된 범위의 모든 요소와 `val`의 합입니다. 두 번째 템플릿 함수의 경우 ( *PartialResult, \*Iter*)에 합계 연산 대신 지정된 이진 연산을 적용한 결과입니다. 여기서 *PartialResult*는 이전에 연산을 적용한 결과이고 `Iter`은 범위의 요소를 가리키는 반복기입니다.

### <a name="remarks"></a>설명

초기값을 사용하면 범위가 비어 있을 때도 결과가 적절하게 정의되며 `val`이 반환됩니다. 이진 연산은 결합 법칙이나 교환 법칙이 성립하지 않아도 됩니다. 결과는 초기값 `val`로 초기화되며, 그리고 나면 범위 전체에서 *result* = `binary_op` ( *result*, **\***`Iter`)가 반복 계산됩니다. 여기서 `Iter`은 범위의 연속 요소를 가리키는 반복기입니다. 범위는 유효해야 하며 복잡성은 범위의 크기에 비례해야 합니다. 반복 중에 닫기가 가능하도록 하려면 이진 연산자의 반환 형식을 **Type**으로 변환할 수 있어야 합니다.

### <a name="example"></a>예제

```cpp
// numeric_accum.cpp
// compile with: /EHsc
#include <vector>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector <int> v1, v2(20);
   vector <int>::iterator iter1, iter2;

   int i;
   for (i = 1; i < 21; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   // The first member function for the accumulated sum
   int total;
   total = accumulate(v1.begin(), v1.end(), 0);

   cout << "The sum of the integers from 1 to 20 is: "
        << total << "." << endl;

   // Constructing a vector of partial sums
   int j = 0, partotal;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      partotal = accumulate(v1.begin(), iter1 + 1, 0);
      v2[j] = partotal;
      j++;
   }

   cout << "The vector of partial sums is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function for the accumulated product
   vector <int> v3, v4(10);
   vector <int>::iterator iter3, iter4;

   int s;
   for (s = 1; s < 11; s++)
   {
      v3.push_back(s);
   }

   cout << "The original vector v3 is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl;

   int ptotal;
   ptotal = accumulate(v3.begin(), v3.end(), 1, multiplies<int>());

   cout << "The product of the integers from 1 to 10 is: "
        << ptotal << "." << endl;

   // Constructing a vector of partial products
   int k = 0, ppartotal;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++) {
      ppartotal = accumulate(v3.begin(), iter3 + 1, 1, multiplies<int>());
      v4[k] = ppartotal;
      k++;
   }

   cout << "The vector of partial products is:\n ( " ;
   for (iter4 = v4.begin(); iter4 != v4.end(); iter4++)
      cout << *iter4 << " ";
   cout << ")." << endl;
}
```

```Output
The original vector v1 is:
 ( 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 ).
The sum of the integers from 1 to 20 is: 210.
The vector of partial sums is:
 ( 1 3 6 10 15 21 28 36 45 55 66 78 91 105 120 136 153 171 190 210 ).

The original vector v3 is:
 ( 1 2 3 4 5 6 7 8 9 10 ).
The product of the integers from 1 to 10 is: 3628800.
The vector of partial products is:
 ( 1 2 6 24 120 720 5040 40320 362880 3628800 ).
```

## <a name="adjacent_difference"></a>  adjacent_difference

각 요소와 입력 범위의 해당 선행 작업간 연속 차이를 계산하고 결과를 대상 범위로 출력하거나 차이 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.

```cpp
template <class InputIterator, class OutIterator>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIterator, class BinaryOperation>
OutputIterator adjacent_difference(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

`first` 이항 연산을 지정 하는 선행 작업과 차별화 요소가 또는 다른 작업을 수행할 쌍의 값이 여기서는 입력된 범위에서 첫 번째 요소를 주소 지정 하는 입력된 반복기입니다.

`last` 이항 연산을 지정 하는 선행 작업과 차별화 요소가 또는 다른 작업을 수행할 쌍의 값이 여기서는 입력된 범위에서 마지막 요소를 주소 지정 하는 입력된 반복기입니다.

`result` 일련의 차이 또는 지정된 된 작업의 결과를 저장할 수 있는 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

`binary_op` 차이 절차에서 차감 연산을 대체 하는 일반화 된 연산에 적용할 이항 연산입니다.

### <a name="return-value"></a>반환 값

대상 범위 끝을 주소 지정하는 출력 반복기:`result` + ( `last` - `first`)

### <a name="remarks"></a>설명

출력 반복기 _ *결과* 입력된 반복기와 동일한 반복기 일 수 있는 경우 * 먼저 * 있도록 `adjacent_difference`s 계산할 수 있습니다.

값의 시퀀스에 대 한 *는*1, *는*2, *는*입력된 범위의 첫 번째 템플릿 함수에서 3 저장 연속 **partial_difference**s *는*1, *는*2- *는*1, a3- *는*대상 범위에서 2입니다.

입력 범위의 값 시퀀스 *a*1, *a*2, *a*3에 대해 두 번째 템플릿 함수는 연속하는 **partial_difference** *a*1, *a*2 `binary_op` *a*1, *a*3 `binary_op` *a*2를 대상 범위에 저장합니다.

이항 연산 `binary_op`는 적용 연산 순서가 완전히 적용되므로 결합성이 있거나 가환적일 필요가 없습니다.

### <a name="example"></a>예제

```cpp
// numeric_adj_diff.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;

   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend, LIterend2;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t * t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the adjacent_differences of
   // elements in a list output to a vector
   VIterend = adjacent_difference ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "Output vector containing adjacent_differences is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the adjacent products of the elements in a list
   VIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the adjacent products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of adjacent_differences in place
   LIterend2 = adjacent_difference ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "In place output adjacent_differences in list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend2 ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="inner_product"></a>  inner_product

두 범위의 요소 전체의 곱의 합을 계산하여 지정된 초기값에 추가하거나 합 및 곱 이진 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차의 결과를 계산합니다.

```cpp
template <class InputIterator1, class InputIterator2, class Type>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val);

template <class InputIterator1, class InputIterator2, class Type, class BinaryOperation1, class BinaryOperation2>
Type inner_product(
    InputIterator1   first1,
    InputIterator1   last1,
    InputIterator2   first2,
    Type             val,
    BinaryOperation1  binary_op1,
    BinaryOperation2  binary_op2);
```

### <a name="parameters"></a>매개 변수

`first1` 해당 내부 제품 또는 두 번째 범위와 일반화 내부의 제품 계산 하는 첫 번째 범위에서 첫 번째 요소를 주소 지정 하는 입력된 반복기입니다.

`last1` 해당 내부 제품 또는 두 번째 범위와 일반화 내부의 제품 계산 하는 첫 번째 범위에서 마지막 요소를 주소 지정 하는 입력된 반복기입니다.

`first2` 해당 내부 제품 또는 첫 번째 범위와 일반화 내부의 제품 계산 하는 두 번째 범위에서 첫 번째 요소를 주소 지정 하는 입력된 반복기입니다.

`val` 내부 제품 또는 범위 간에 일반화 내부의 제품을 추가 하는 초기 값입니다.

*binary_op1* 내부의 제품을 일반화의 요소나 제품에 적용 된 합계의 내부의 제품 연산을 대체 하는 이항 연산입니다.

*binary_op2* 내부의 제품을 일반화에서 여러 번의 내부의 제품 요소나 작동을 대체 하는 이항 연산입니다.

### <a name="return-value"></a>반환 값

첫 번째 구성원 함수는 요소별 곱의 합을 반환하고 해당 합을 지정된 초기값에 더합니다. 따라서 값 *a*i 및 *b*i의 범위에 대해 이 함수는 다음 결과를 반환합니다.

`val` + ( *는*1 \* *b*1) + ( *는*2 \* *b*2) + … + ( *는*n \* *b*n)

반복적으로 대체 하 여 `val` 와 `val` + ( *는*i \* *b*i).

두 번째 구성원 함수는 다음 결과를 반환합니다.

`val` *binary_op1* ( *는*1 *binary_op2* *b*1) *binary_op1* ( *는*2 *binary_op2* *b*2) *binary_op1* ... *binary_op1* ( *는*n *binary_op2* *b*n)

반복적으로 대체 하 여 `val` 와 `val` *binary_op1* ( *는*i *binary_op2* *b*i).

### <a name="remarks"></a>설명

초기값을 사용하면 범위가 비어 있을 때도 결과가 적절하게 정의되며 `val`이 반환됩니다. 이진 연산은 결합 법칙이나 교환 법칙이 성립하지 않아도 됩니다. 범위는 유효해야 하며 복잡성은 범위의 크기에 비례해야 합니다. 반복 중에 닫기가 가능하도록 하려면 이진 연산자의 반환 형식을 **Type**으로 변환할 수 있어야 합니다.

### <a name="example"></a>예제

```cpp
// numeric_inner_prod.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main()
{
   using namespace std;

   vector <int> v1, v2(7), v3(7);
   vector <int>::iterator iter1, iter2, iter3;

   int i;
   for (i = 1; i <= 7; i++)
   {
      v1.push_back(i);
   }

   cout << "The original vector v1 is:\n ( " ;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
      cout << *iter1 << " ";
   cout << ")." << endl;

   list <int> l1, l2(7);
   list <int>::iterator lIter1, lIter2;

   int t;
   for (t = 1; t <= 7; t++)
   {
      l1.push_back(t);
   }

   cout << "The original list l1 is:\n ( " ;
   for (lIter1 = l1.begin(); lIter1 != l1.end(); lIter1++)
      cout << *lIter1 << " ";
   cout << ")." << endl;

   // The first member function for the inner product
   int inprod;
   inprod = inner_product(v1.begin(), v1.end(), l1.begin(), 0);

   cout << "The inner_product of the vector v1 and the list l1 is: "
        << inprod << "." << endl;

   // Constructing a vector of partial inner_products between v1 & l1
   int j = 0, parinprod;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++) {
      parinprod = inner_product(v1.begin(), iter1 + 1, l1.begin(), 0);
      v2[j] = parinprod;
      j++;
   }

   cout << "Vector of partial inner_products between v1 & l1 is:\n ( " ;
   for (iter2 = v2.begin(); iter2 != v2.end(); iter2++)
      cout << *iter2 << " ";
   cout << ")." << endl << endl;

   // The second member function used to compute
   // the product of the element-wise sums
   int inprod2;
   inprod2 = inner_product (v1.begin(), v1.end(),
      l1.begin(), 1, multiplies<int>(), plus<int>());

   cout << "The sum of the element-wise products of v1 and l1 is: "
        << inprod2 << "." << endl;

   // Constructing a vector of partial sums of element-wise products
   int k = 0, parinprod2;
   for (iter1 = v1.begin(); iter1 != v1.end(); iter1++)
   {
      parinprod2 =
         inner_product(v1.begin(), iter1 + 1, l1.begin(), 1,
         multiplies<int>(), plus<int>());
      v3[k] = parinprod2;
      k++;
   }

   cout << "Vector of partial sums of element-wise products is:\n ( " ;
   for (iter3 = v3.begin(); iter3 != v3.end(); iter3++)
      cout << *iter3 << " ";
   cout << ")." << endl << endl;
}
```

## <a name="iota"></a>  iota

시작 값을 저장하고, 첫 번째 요소부터 시작하여 간격 `[ first,  last)`의 각 요소에서 해당 값의 연속적 증분(` value++`)으로 채웁니다.

```cpp
template <class ForwardIterator, class Type>
void iota(ForwardIterator first, ForwardIterator last, Type value);
```

### <a name="parameters"></a>매개 변수

`first` 채울 범위에 있는 첫 번째 요소를 해결 하는 입력된 반복기입니다.

`last` 채울 범위에서 마지막 요소를 해결 하는 입력된 반복기입니다.

`value` 첫 번째 요소에 및 후속 요소에 대 한 연속적으로 증가를 저장 하기 위해 시작 하는 값입니다.

### <a name="remarks"></a>설명

### <a name="example"></a>예제

다음 예제에서는 [random_shuffle](../standard-library/algorithm-functions.md#random_shuffle) 함수를 사용할 수 있도록 정수 [list](../standard-library/list.md)를 채운 다음 `list`로 [vector](../standard-library/vector.md)를 채우는 `iota` 함수의 몇 가지 사용 방법을 보여 줍니다.

```cpp
// compile by using: cl /EHsc /nologo /W4 /MTd
#include <algorithm>
#include <numeric>
#include <list>
#include <vector>
#include <iostream>

using namespace std;

int main(void)
{
    list <int> intList(10);
    vector <list<int>::iterator> intVec(intList.size());

    // Fill the list
    iota(intList.begin(), intList.end(), 0);

    // Fill the vector with the list so we can shuffle it
    iota(intVec.begin(), intVec.end(), intList.begin());

    random_shuffle(intVec.begin(), intVec.end());

    // Output results
    cout << "Contents of the integer list: " << endl;
    for (auto i: intList) {
        cout << i << ' ';
    }
    cout << endl << endl;

    cout << "Contents of the integer list, shuffled by using a vector: " << endl;
    for (auto i: intVec) {
        cout << *i << ' ';
    }
    cout << endl;
}
```

## <a name="partial_sum"></a>  partial_sum

첫 번째 요소부터 *i*번째 요소까지 입력 범위에서 일련의 합계를 계산하고 각 합계의 결과를 대상 범위의 *i*번째 요소에 저장하거나 합 연산을 지정된 다른 이진 연산으로 대체한 일반화된 절차 결과를 계산합니다.

```cpp
template <class InputIterator, class OutIt>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result);

template <class InputIterator, class OutIt, class Fn2>
OutputIterator partial_sum(
    InputIterator first,
    InputIterator last,
    OutputIterator result,
    BinaryOperation binary_op);
```

### <a name="parameters"></a>매개 변수

`first` 입력된 반복기 범위에서 첫 번째 요소를 주소 지정를 부분적으로 합계 또는 지정 된 이진 연산에 따라 결합 합니다.

`last` 입력된 반복기 범위에서 마지막 요소를 주소 지정 되도록 부분적으로 합 또는 지정된 된 이항 연산을 따라 결합 하는 반복된 된 누적에 실제로 포함 된 마지막 요소 하나 다음 위치의 합니다.

`result` 일련의 부분적 합 또는 지정된 된 작업의 결과를 저장할 수 있는 대상 범위의 첫 번째 요소를 주소 지정 하는 출력 반복기입니다.

`binary_op` 이항 연산 부분적 합 절차에서 합 연산을 대체 하는 일반화 된 연산에 적용 하는 것입니다.

### <a name="return-value"></a>반환 값

대상 범위 끝을 주소 지정하는 출력 반복기:`result` + ( `last` - `first`)

### <a name="remarks"></a>설명

부분 합을 계산할 수 있도록 출력 반복기 `result`는 입력 반복기 `first`와 동일한 반복기일 수 있습니다.

입력 범위의 값 시퀀스 *a*1, *a*2, *a*3에 대해 첫 번째 템플릿 함수는 연속 부분 합을 대상 범위에 저장합니다. 여기서 *i*번째 요소는 (  ( ( *a*1 + *a*2) + *a*3) *a*i)로 지정됩니다.

값의 시퀀스에 대 한 *는*1, *는*2, *는*3, 입력 범위의 두 번째 템플릿 함수 저장 여기서 i 번째 요소는 대상 범위에서 연속적 부분 합계 받은 ((( *는*1 `binary_op` *는*2) `binary_op` *는*3) *는*i).

이항 연산 `binary_op`는 적용 연산 순서가 완전히 적용되므로 결합성이 있거나 가환적일 필요가 없습니다.

### <a name="example"></a>예제

```cpp
// numeric_partial_sum.cpp
// compile with: /EHsc
#include <vector>
#include <list>
#include <numeric>
#include <functional>
#include <iostream>

int main( )
{
   using namespace std;
   vector<int> V1( 10 ), V2( 10 );
   vector<int>::iterator VIter1, VIter2, VIterend, VIterend2;

   list <int> L1;
   list <int>::iterator LIter1, LIterend;

   int t;
   for ( t = 1 ; t <= 10 ; t++ )
   {
      L1.push_back( t );
   }

   cout << "The input list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != L1.end( ) ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;

   // The first member function for the partial sums of
   // elements in a list output to a vector
   VIterend = partial_sum ( L1.begin ( ) , L1.end ( ) ,
      V1.begin ( ) );

   cout << "The output vector containing the partial sums is:\n ( " ;
   for ( VIter1 = V1.begin( ) ; VIter1 != VIterend ; VIter1++ )
      cout << *VIter1 << " ";
   cout << ")." << endl;

   // The second member function used to compute
   // the partial product of the elements in a list
   VIterend2 = partial_sum ( L1.begin ( ) , L1.end ( ) , V2.begin ( ) ,
      multiplies<int>( ) );

   cout << "The output vector with the partial products is:\n ( " ;
   for ( VIter2 = V2.begin( ) ; VIter2 != VIterend2 ; VIter2++ )
      cout << *VIter2 << " ";
   cout << ")." << endl;

   // Computation of partial sums in place
   LIterend = partial_sum ( L1.begin ( ) , L1.end ( ) , L1.begin ( ) );
   cout << "The in place output partial_sum list L1 is:\n ( " ;
   for ( LIter1 = L1.begin( ) ; LIter1 != LIterend ; LIter1++ )
      cout << *LIter1 << " ";
   cout << ")." << endl;
}
```

## <a name="see-also"></a>참고자료

[\<numeric>](../standard-library/numeric.md)<br/>
