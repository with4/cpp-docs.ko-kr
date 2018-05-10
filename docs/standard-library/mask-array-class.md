---
title: mask_array 클래스 | Microsoft 문서
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- valarray/std::mask_array
dev_langs:
- C++
helpviewer_keywords:
- mask_array class
ms.assetid: c49bed6a-3000-4f39-bff6-cb9a453acb0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b19ac68f1d1db9ac73e0519b566f68443775db11
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="maskarray-class"></a>mask_array 클래스

하위 집합 배열 간의 작업을 제공하여 부울 식으로 지정된 부모 valarray의 하위 집합인 개체를 지원하는 내부 보조 템플릿 클래스입니다.

## <a name="syntax"></a>구문

## <a name="remarks"></a>설명

이 클래스는 **valarray\<Type>** 개체에서 선택할 요소의 시퀀스를 설명하는 [valarray\<bool>](../standard-library/valarray-bool-class.md) 클래스의 **ba** 개체와 함께 [valarray](../standard-library/valarray-class.md)**\<Type>** 클래스의 **va** 개체에 대한 참조를 저장하는 개체를 설명합니다.

**mask_array\<Type>** 개체를 생성하려면 [va&#91;ba&#93;](../standard-library/valarray-class.md#op_at) 형식의 식을 작성하면 됩니다. 그러면 mask_array 클래스의 멤버 함수는 선택한 요소의 시퀀스에만 영향을 준다는 점을 제외하고 **valarray\<Type>** 에 대해 정의된 해당하는 함수 시그니처처럼 동작합니다.

시퀀스는 최대 **ba.size** 개 요소로 구성됩니다. 요소 *J* 는 **ba**[ *J*]가 true인 경우에만 포함됩니다. 따라서 **ba**에 있는 true 요소 수 만큼의 요소가 시퀀스에 있습니다. `I` 가 **ba**에서 가장 낮은 true 요소의 인덱스인 경우 **va**[ `I`]는 선택한 시퀀스의 요소 0입니다.

## <a name="example"></a>예제

```cpp
// mask_array.cpp
// compile with: /EHsc
#include <valarray>
#include <iostream>

int main( )
{
   using namespace std;
   int i;

   valarray<int> va ( 10 );
   for ( i = 0 ; i < 10 ; i += 2 )
      va [ i ] =  i;
   for ( i = 1 ; i < 10 ; i += 2 )
      va [ i ] =  -1;

   cout << "The initial operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;

   // Use masked subsets to assign a value of 10
   // to all elements grrater than 3 in value
   va [va > 3 ] = 10;
   cout << "The modified operand valarray is:  ( ";
      for ( i = 0 ; i < 10 ; i++ )
         cout << va [ i ] << " ";
   cout << ")." << endl;
}
```

### <a name="output"></a>출력

```Output
The initial operand valarray is:  (0 -1 2 -1 4 -1 6 -1 8 -1).
The modified operand valarray is:  (0 -1 2 -1 10 -1 10 -1 10 -1).
```

## <a name="requirements"></a>요구 사항

**헤더:** \<valarray>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
