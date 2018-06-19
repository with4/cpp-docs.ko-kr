---
title: raw_storage_iterator 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::raw_storage_iterator
- memory/std::raw_storage_iterator::element_type
- memory/std::raw_storage_iterator::iter_type
dev_langs:
- C++
helpviewer_keywords:
- std::raw_storage_iterator [C++]
- std::raw_storage_iterator [C++], element_type
- std::raw_storage_iterator [C++], iter_type
ms.assetid: 6f033f15-f48e-452a-a326-647ea2cf346f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d6c93bfc6525840343c64b8cd804ddb65f68dd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860270"
---
# <a name="rawstorageiterator-class"></a>raw_storage_iterator 클래스

초기화되지 않은 메모리에 결과를 저장하는 알고리즘을 사용할 수 있도록 제공되는 어댑터 클래스입니다.

## <a name="syntax"></a>구문

```cpp
template <class OutputIterator, class Type>
class raw_storage_iterator
```

### <a name="parameters"></a>매개 변수

`OutputIterator` 저장 되는 개체에 대 한 출력 반복기를 지정 합니다.

*형식* 저장소를 할당 하는 개체의 형식입니다.

## <a name="remarks"></a>설명

이 클래스는 생성하는 시퀀스에서 **Type** 형식의 개체를 생성하는 출력 반복기를 설명합니다. `raw_storage_iterator`\< **ForwardIterator**, **Type**> 클래스의 개체는 개체를 생성할 때 지정하는 **ForwardIterator** 클래스의 정방향 반복기 개체를 통해 저장소에 액세스합니다. **ForwardIterator** 클래스의 first 개체에 대해 **&\*first** 식은 생성된 시퀀스에서 다음 개체(**Type** 형식)에 대해 생성되지 않은 저장소를 지정해야 합니다.

이 어댑터 클래스는 메모리 할당 및 개체 생성을 구분하는 데 필요한 경우에 사용됩니다. `raw_storage_iterator`를 사용하여 `malloc` 함수를 통해 할당된 메모리와 같은 초기화되지 않은 저장소에 개체를 복사할 수 있습니다.

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[raw_storage_iterator](#raw_storage_iterator)|지정된 기본 출력 반복기를 사용하여 원시 저장소 반복기를 생성합니다.|

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[element_type](#element_type)|원시 저장소 반복기를 저장할 요소를 설명하는 형식을 제공합니다.|
|[iter_type](#iter_type)|원시 저장소 반복기의 기반이 되는 반복기를 설명하는 형식을 제공합니다.|

### <a name="operators"></a>연산자

|연산자|설명|
|-|-|
|[operator*](#op_star)|출력 반복기 식 * `ii` = `x`를 구현하는 데 사용되는 역참조 연산자입니다.|
|[operator=](#op_eq)|메모리에 저장하기 위해 원시 저장소 반복기 식 * `i` = `x`를 구현하는 데 사용되는 대입 연산자입니다.|
|[operator++](#op_add_add)|원시 저장소 반복기에 대한 사전 증가 및 사후 증가 연산자입니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<memory>

**네임스페이스:** std

## <a name="element_type"></a>  raw_storage_iterator::element_type

원시 저장소 반복기를 저장할 요소를 설명하는 형식을 제공합니다.

```cpp
typedef Type element_type;
```

### <a name="remarks"></a>설명

이 형식은 raw_storage_iterator 클래스 템플릿 매개 변수 **Type**과 동일한 의미입니다.

## <a name="iter_type"></a>  raw_storage_iterator::iter_type

원시 저장소 반복기의 기반이 되는 반복기를 설명하는 형식을 제공합니다.

```cpp
typedef ForwardIterator iter_type;
```

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 **ForwardIterator**와 동일한 의미입니다.

## <a name="op_star"></a>  raw_storage_iterator::operator*

원시 저장소 반복기 식 \* *ii* = *x*를 구현하는 데 사용되는 역참조 연산자입니다.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator*();
```

### <a name="return-value"></a>반환 값

원시 저장소 반복기에 대한 참조

### <a name="remarks"></a>설명

원시 저장소 반복기가 충족해야 하는 **ForwardIterator**에 대한 요구 사항은 \* *ii* = *t* 식만 유효해야 한다는 것과 해당 반복기 자체는 **operator** 또는 `operator=`에 대해 어떤 정보도 제공하지 않아야 한다는 것입니다. 이 구현의 구성원 연산자는 [operator=](#op_eq)( **constType**&)이 \* *ptr* = `val`과 같이 식에서 실제 저장을 수행할 수 있도록 **\*this**를 반환합니다.

### <a name="example"></a>예제

```cpp
// raw_storage_iterator_op_deref.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };

   Int &operator=(int i)
   {
      if (!bIsConstructed)
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl;
      x = i;
      return *this;
   };

   int x;

private:
   bool bIsConstructed;
};

int main( void)
{
   Int *pInt = ( Int* ) malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;
 *pInt = 5;
   raw_storage_iterator< Int*, Int > it( pInt );
 *it = 5;
}
\* Output:
Not constructed.
Copying 5
Constructing 5
*\
```

## <a name="op_eq"></a>  raw_storage_iterator::operator=

메모리에 저장하기 위해 원시 저장소 반복기 식 \* *i* = *x*를 구현하는 데 사용되는 대입 연산자입니다.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator=(
    const Type& val);
```

### <a name="parameters"></a>매개 변수

`val` 형식의 개체의 값 **형식** 메모리에 삽입할 수 있습니다.

### <a name="return-value"></a>반환 값

연산자는 `val`을 메모리에 삽입한 다음 원시 저장소 반복기에 대한 참조를 반환합니다.

### <a name="remarks"></a>설명

원시 저장소 반복기가 충족해야 하는 **ForwardIterator** 상태에 대한 요구 사항은 \* *ii* = *t* 식만 유효해야 한다는 것과 해당 반복기 자체는 **operator** 또는 `operator=`에 대해 어떤 정보도 제공하지 않아야 한다는 것입니다. 이러한 구성원 연산자는 **\*this**를 반환합니다.

대입 연산자는 placement new 식 **new** ( ( `void` \*)&\* **first**) **Type**( `val`)을 평가하여 저장된 반복기 값을 먼저 사용해 출력 시퀀스에서 다음 개체를 생성합니다.

### <a name="example"></a>예제

```cpp
// raw_storage_iterator_op_assign.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int( int i )
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if ( !bIsConstructed )
         cout << "Not constructed.\n";
      cout << "Copying " << i << endl; x = i;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

int main( void )
{
   Int *pInt = ( Int* )malloc( sizeof( Int ) );
   memset( pInt, 0, sizeof( Int ) ); // Set bIsConstructed to false;

*pInt = 5;

   raw_storage_iterator<Int*, Int> it( pInt );
 *it = 5;
}
\* Output:
Not constructed.
Copying 5
Constructing 5
*\
```

## <a name="op_add_add"></a>  raw_storage_iterator::operator++

원시 저장소 반복기에 대한 사전 증가 및 사후 증가 연산자입니다.

```cpp
raw_storage_iterator<ForwardIterator, Type>& operator++();

raw_storage_iterator<ForwardIterator, Type> operator++(int);
```

### <a name="return-value"></a>반환 값

원시 저장소 반복기 또는 원시 저장소 반복기에 대한 참조입니다.

### <a name="remarks"></a>설명

첫 번째 연산자는 연결된 입력 스트림에서 **CharType** 형식의 개체를 추출하고 저장하려고 합니다. 두 번째 연산자는 개체의 복사본을 만들고 개체를 증가시킨 다음 복사본을 반환합니다.

첫 번째 preincrement 연산자는 저장된 출력 반복기 개체를 증가시키고 **\*this**를 반환합니다.

두 번째 postincrement 연산자는 **\*this**의 복사본을 만들고 저장된 출력 반복기 개체를 증가시킨 다음 해당 복사본을 반환합니다.

생성자는 출력 반복기 개체로 **first**를 저장합니다.

### <a name="example"></a>예제

```cpp
// raw_storage_iterator_op_incr.cpp
// compile with: /EHsc
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

int main( void )
{
   int *pInt = new int[5];
   std::raw_storage_iterator<int*,int> it( pInt );
   for ( int i = 0; i < 5; i++, it++ ) {
 *it = 2 * i;
};

   for ( int i = 0; i < 5; i++ ) cout << "array " << i << " = " << pInt[i] << endl;;

   delete[] pInt;
}
\* Output:
array 0 = 0
array 1 = 2
array 2 = 4
array 3 = 6
array 4 = 8
*\
```

## <a name="raw_storage_iterator"></a>  raw_storage_iterator::raw_storage_iterator

지정된 기본 출력 반복기를 사용하여 원시 저장소 반복기를 생성합니다.

```cpp
explicit raw_storage_iterator(ForwardIterator first);
```

### <a name="parameters"></a>매개 변수

`first` 기반이 되는 정방향 반복기는 `raw_storage_iterator` 생성 되 고 개체입니다.

### <a name="example"></a>예제

```cpp
// raw_storage_iterator_ctor.cpp
// compile with: /EHsc /W3
#include <iostream>
#include <iterator>
#include <memory>
#include <list>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << i << endl;
      x = i;
      bIsConstructed = true;
   };
   Int &operator=( int i )
   {
      if (!bIsConstructed)
         cout << "Error! I'm not constructed!\n";
      cout << "Copying " << i << endl;  x = i; return *this;
   };
   int x;
   bool bIsConstructed;
};

int main( void )
{
   std::list<int> l;
   l.push_back( 1 );
   l.push_back( 2 );
   l.push_back( 3 );
   l.push_back( 4 );

   Int *pInt = (Int*)malloc(sizeof(Int)*l.size( ));
   memset (pInt, 0, sizeof(Int)*l.size( ));
   // Hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ), pInt );  // C4996
   for (unsigned int i = 0; i < l.size( ); i++)
      cout << "array " << i << " = " << pInt[i].x << endl;;

   memset (pInt, 0, sizeof(Int)*l.size( ));
   // hack: make sure bIsConstructed is false

   std::copy( l.begin( ), l.end( ),
      std::raw_storage_iterator<Int*,Int>(pInt));  // C4996
   for (unsigned int i = 0; i < l.size( ); i++ )
      cout << "array " << i << " = " << pInt[i].x << endl;

   free(pInt);
}
\* Output:
Error! I'm not constructed!
Copying 1
Error! I'm not constructed!
Copying 2
Error! I'm not constructed!
Copying 3
Error! I'm not constructed!
Copying 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
Constructing 1
Constructing 2
Constructing 3
Constructing 4
array 0 = 1
array 1 = 2
array 2 = 3
array 3 = 4
*\
```

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
